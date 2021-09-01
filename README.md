# accelerating kubernetes onboarding and application transformation  


## intro
This repository provides the content of a conversation led webinar between Raif and Rom held by StorageOS on August 18th 2021 about how to onboarding Kubernetes within an organization and what application transformation means.

The content is for educational purposes, is linked to field experience, and, for the demo, tested on Google Cloud. The content can be reused freely as-is. Both Red Hat Services and StorageOS Customer Success are available to provide the audience with the supporting experience in such journey. 

## context

The webinar addressses a series of questions that are commonly discussed within customers and partners workshops. The repository is presenting additional content to highlight the talking points of the webinar.

## modernizing legacy systems

Before deploying Kubernetes and deploying a first workload, it is important to address terminology, concepts and practices for a successful transformation journey. Often, an application transformation from legacy to microservices will go through a step called a "lift and shift", but what does it mean? 

### lift and shift
Lift and shift is one practice providing [options to modernize legacy systems](https://www.gartner.com/smarterwithgartner/7-options-to-modernize-legacy-systems/) like:
- rehosting; redeploy the application component to other infrastructure (physical, virtual or cloud) without modifying its code, features or functions.
- replatforming; migrate to a new runtime platform, making minimal changes to the code, but not the code structure, features or functions like migrating the runtime to container runtime like docker, containerd, or CRI-O, but without touching the application itself.

The lift and shift approach gives a relatively easy way to migrate toward a Kubernetes platform at a reduced cost but with reduced benefits from it in terms of elasticity. To fully appreciate the Kubernetes capabilities, an application modernization might be required. 

### application modernization
Application modernization comes into multiple forms and the most seen are the followings:
- refactoring; modifying the code to "some extent" to accomodate a newer runtime.
- rearchitecting; materially altering the code to shift it to a new application architecture and exploit new and better capabilities like using configmaps and secrets in K8s rather that files and property files.
- modernization; rewriting the application to utilize modern techniques and features.
- rebuilding; redesigning and rewriting the application component from scratch while preserving its scope and specifications. 
- replacing; finding an off-the-shelf replacement due to the high cost of all previous options.

### which approach
The journey is depending on multiple factors that are directly set by an organization or inherent from the legacy systems. Three ususal key metrics are:
- cost and time; usually projects have budget and timeline associated with the scope which will define organically the choice between any of the modernizing technics. 
- knowledge; how much is known about the application and dependencies? Is there still existing knowledge within the organization? Is there any consulting firm on the market still having knowledge about the application and its internals? 

Considering at least the above along with the organization needs, business drivers and targets will ensure the appropriate approach will be taken to reduce the risks of such transformation.
It is worth considering that a lift and shift should be considered as an intermediate or transient step in the modernization journey allowing the organization to move smoothly towards a Kubernetes platform with a reduced impact of change while the organization starts building the appetite within the IT and Application departments.

### application transformation

One of the most heard terms or concept when speaking about application transformation is "Lift and Shift". The concept of "Lift and Shift" is moving an application from one infrastructure to another. The is also popular for infrastructure components like traditional/legacy storage vendors migrating data set from one platform to another (same or different vendor as target).


## legacy infra  

This is the starting point from the webinar, an existing workload that is currently working in a customer environment. To illustrate the application migration/transformation, or moving from a bare metal/virtual machine based deployment to a microservice one with or without refactoring, a typical multi-tenant CMS like Druapl fits perfectly the exercice. 

```
     HAProxy LB -------------- VM01 -------------------------------------  VM02
                         Drupal Front-End                            MySQL Back-End
                              site01                                     sitedb01
                              site02                                     sitedb02
                              site03                                     sitedb03
                              site04                                     sitedb04
                              site05                                     sitedb05     
```
The above is a simplier version of something commonly seen within medium to large companies especially using a hypervisor providing the necessary features to support business continuity. 


## kubernetes infra

```
                                                  
                              Drupal Front-End                            MySQL Back-End
                         
                   |---------- service-01               StatefulSet-01                         
                   |                     site01                                     sitedb01
                   |---------- service-02               StatefulSet-02
                   |                     site02                                     sitedb02
      LoadBalancer |---------- service-03               StatefulSet-03
                   |                     site03                                     sitedb03
                   |---------- service-04               StatefulSet-04
                   |                     site04                                     sitedb04
                   |---------- service-05               StatefulSet-05
                                         site05                                     sitedb05     


```







