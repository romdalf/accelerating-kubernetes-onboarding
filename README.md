# accelerating kubernetes onboarding and application transformation  

This repository provides the content of a webinar held by StorageOS on August 18th 2021.   

The content is for educational purposes, tested on Google Cloud and can be reused freely as-is.   

## legacy infra  

To illustrate the application transformation, or moving from a bare metal/virtual machine based deployment to a microservice one, a typical multi-tenant CMS like Druapl fits perfectly the example. 

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

