# accelerating kubernetes onboarding and application transformation  


## intro
This repository provides the content of a conversation led webinar between Raif and Rom held by StorageOS on August 18th 2021 about how to onboarding Kubernetes within an organization and what application transformation means.

The content is for educational purposes, tested on Google Cloud and can be reused freely as-is. Both Red Hat Services and StorageOS Customer Success are available to provide the audience with the supporting experience in such journey. 

## context

The webinar addressses a series of questions that are commonly discussed within customers and partners workshops. The repository is presenting additional content to highlight the talking points of the webinar.

## transformation

Before deploying Kubernetes and deploying a first workload, it is important to address terminology, concepts and practices for a successful transformation.

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







