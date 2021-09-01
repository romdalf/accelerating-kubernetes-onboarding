# Accelerating kubernetes onboarding and application transformation  

Table of Content:
* [Intro](#intro)
* [Context](#context)
* [Why Kubernetes](#why-kubernetes)
* [Mordernizing legacy systems](#modernizing-legacy-systems)
     * [Lift and shift](#lift-and-shift)
     * [Application modernization](#application-modernization)
     * [Which approach](#which-approach)
* [Practices](#practices)
     * [Agile](#agile)
     * [DevOps](#devops)
* []() 

## Intro
This repository provides the content of a conversation led webinar between Raif and Rom held by StorageOS on August 18th 2021 about how to onboarding Kubernetes within an organization and what application transformation means.

The content is for educational purposes, is linked to field experience, and, for the demo, tested on Google Cloud. The content can be reused freely as-is. Both Red Hat Services and StorageOS Customer Success are available to provide the audience with the supporting experience in such journey. 

## Context

The webinar addressses a series of questions that are commonly discussed within customers and partners workshops. The repository is presenting additional content to highlight the talking points of the webinar.

## Why kubernetes

[Infrastructure Elasticity & self healing](https://kubernetes.io/docs/concepts/overview/what-is-kubernetes/) are the magic words. Kubernetes provides an easy way to scale applications, it restarts containers that fail, replaces containers, kills containers that don't respond to your user-defined health check, and doesn't advertise them to clients until they are ready to serve.
In other words, Kubernetes orchestrates a series, if not all, of day 2 operations related to the availability of applications to ensure business continuity with a reduce friction or burden on the Operational teams.

## Modernizing legacy systems

Before deploying Kubernetes and deploying a first workload, it is important to address terminology, concepts and practices for a successful transformation journey. Often, an application transformation from legacy to microservices will go through a step called a "lift and shift", but what does it mean? 

### Lift and shift
Lift and shift is one practice providing [options to modernize legacy systems](https://www.gartner.com/smarterwithgartner/7-options-to-modernize-legacy-systems/) like:
- rehosting; redeploy the application component to other infrastructure (physical, virtual or cloud) without modifying its code, features or functions.
- replatforming; migrate to a new runtime platform, making minimal changes to the code, but not the code structure, features or functions like migrating the runtime to container runtime like docker, containerd, or CRI-O, but without touching the application itself.

The lift and shift approach gives a relatively easy way to migrate toward a Kubernetes platform at a reduced cost but with reduced benefits from it in terms of elasticity. To fully appreciate the Kubernetes capabilities, an application modernization might be required. 

### Application modernization
Application modernization comes into multiple forms and the most seen are the followings:
- refactoring; modifying the code to "some extent" to accomodate a newer runtime.
- rearchitecting; materially altering the code to shift it to a new application architecture and exploit new and better capabilities like using configmaps and secrets in K8s rather that files and property files.
- modernization; rewriting the application to utilize modern techniques and features.
- rebuilding; redesigning and rewriting the application component from scratch while preserving its scope and specifications. 
- replacing; finding an off-the-shelf replacement due to the high cost of all previous options.

### Which approach
The journey is depending on multiple factors that are directly set by an organization or inherent from the legacy systems. Three ususal key metrics are:
- cost and time; usually projects have budget and timeline associated with the scope which will define organically the choice between any of the modernizing technics. 
- knowledge; how much is known about the application and dependencies? Is there still existing knowledge within the organization? Is there any consulting firm on the market still having knowledge about the application and its internals? 

Considering at least the above along with the organization needs, business drivers and targets will ensure the appropriate approach will be taken to reduce the risks of such transformation.
It is worth considering that a lift and shift should be considered as an intermediate or transient step in the modernization journey allowing the organization to move smoothly towards a Kubernetes platform with a reduced impact of change while the organization starts building the appetite within the IT and Application departments.


## Practices

The first part, discussing about modernizing legacy systems, gave an overview about options for existing applications to be migrated from legacy systems to a Kubernetes platform but it does not cover the paradigm shift from a project delivery and day-to-day standpoint.

Kubernetes as a platform offers a wide range of abstractions for all the different usual infrastructure layers like the network, compute, OS, availability, elasticity, and more. But Kubernetes as platform offers a new way of addressing and consuming these components via the usage of a configuration file defining a desired state rather than command line to be executed. The configuration file containing the desired state for the ports being used by the application or the usage of persistent volume will be process and executed by Kubernetes orchestrating all these components. 

Two buzz words have to be considered and adopted to ensure leveraging the best out of Kubernetes; [Agile](https://en.wikipedia.org/wiki/Agile_software_development) and [DevOps](https://en.wikipedia.org/wiki/DevOps). Let's have a short introduction to both.

### Agile
From the Wikipedia definition of [Agile](https://en.wikipedia.org/wiki/Agile_software_development), one highlight is in direct link with Kubernetes: 
> it encourages flexible responses to changes in requirements, resource availability, and understanding of the problems to be solved.
The concept of flexible/flexibility is one of the main benefits of Kubernetes and will drive the transformation of IT landscape. 

### DevOps
From the Wikipedia definition of [DevOps](https://en.wikipedia.org/wiki/DevOps), one highlight is in direct link with Kubernetes:
> DevOps is a set of practices that combines software development (Dev) and IT operations (Ops). It aims to shorten the systems development life cycle and provide continuous delivery with high software quality

When both Agile and DevOps are combined and adopted, an organization can then quickly react to changes by having a flexible IT landscape along with short development and delivery cycles which correspond to the Kubernetes mission statement. 

### mandatory practices
[Dozens if not hundreds of practices](https://openpracticelibrary.com/) exist and could help teams to build faster. However, it's important to start walking before running. Therefor, these two practices will be a perfect starting point for a smooth adoption of Kubernetes, and Agiles and DevOps practices.

#### IaC
IaC or [Infrastructure as Code](https://en.wikipedia.org/wiki/Infrastructure_as_code) provides a centralized reference of all the configuration files defining the desired state of any infrastructure components related to Kubernetes or not, and a collaborative way for members of one or multiple teams to review, approve, and carry changes to the infrastructure. 
The practices will depend on a Git service that will act as a central repository providing the necessary features to support to [four eyes principle](https://www.openriskmanual.org/wiki/Four_Eyes_Principle).





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







