## webinar storyboard
```
Introduction of the hosts                                                
Overview of the agenda along with key take away                         5min 

Presenting a traditional CRM deployed on 2 VMs                          
- based on drupal + mysql 
- 5 sites within one drupal instance
- 5 DBs within one mysql instance 
including potential deployments with Ansible, XLRelease
including storage and backup solutions for BCP                          10min 

    Q&A - Presenting a traditional CRM deployed on 2 VMs                          
    - What is a lift and shift?
    https://www.gartner.com/smarterwithgartner/7-options-to-modernize-legacy-systems/
    Rehost. Redeploy the application component to other infrastructure (physical, virtual or cloud) without modifying its code, features or functions.
Replatform. Migrate to a new runtime platform, making minimal changes to the code, but not the code structure, features or functions

Rearchitect. Materially alter the code to shift it to a new application architecture and exploit new and better capabilities. 
Rebuild. Redesign or rewrite the application component from scratch while preserving its scope and specifications.
Replace. Eliminate the former application component altogether and replace it, considering new requirements and needs at the same time.

    - What are the options for a lift and shift? 
    - Other options are refactoring and modernization. What are the differences?
    - How can an organization make a decision regarding one or the other?
    - If a lift and shift is done, is it forever? 

Presenting a microservice version to migrate the CRMs         
- drupal + postgresql 
-- 5 sites in one instance becomes 5 drupal workloads 
-- 5 DBs in one instance become 5 postgresql workloads                  

including DevOps practices like IaC and GitOps                          10min 
    Q&A - DevOps practices
    - There is a lot of buzz around Agile and DevOps. Can a non Agile organization benefit of Kubernetes? 
    - Starting with the basics, IaC and GitOps are almost mandatory, why? 
    - What are the benefits of using such practices? 

including deployment strategies                                         5min 
    Q&A - Presenting a microservice version to migrate the CRMs
    - Why Kubernetes? 
    - Considering the current setup, why would it be better to split the sites into dedicated workload?
    - What not splitting the sites in dedicated workload would have an impact? 
    - What is the concept of deployment strategies? 
    - Why should we care? 

Presenting persistent data challenges due to k8s design
- storage type (block, file, object)
- access mode (rwo, rwx, rox) 
- data migration approaches 
- backup                                                                10min 

    Q&A - Presenting persistent data challenges due to k8s design
    - Why is persistent data important?
    - What are the different storage type and their usage? 
    - In k8s, there is the concept of access mode? What are the differences between each others?
    - Migrating data is a pain. Is it different with k8s?
    - What the major differences between traditional environment/VM or bare metal based backups vs k8s?

Reminding the audience of the key take away
Q&A 




``` 
