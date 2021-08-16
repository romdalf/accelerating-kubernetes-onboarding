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
    - What is the difference between a lift and shift version refactoring?
    - How can an organization make a decision regarding one or the other?
    - If a lift and shift is done, is it forever? 
    - Would you consider doing a lift and shift using kubvirt? 

Presenting a microservice version to migrate the CRMs         
- drupal + postgresql 
-- 5 sites in one instance becomes 5 drupal workloads 
-- 5 DBs in one instance become 5 postgresql workloads                  
including deployment strategies                                         5min 

    Q&A - Presenting a microservice version to migrate the CRMs         
    - Considering the current setup, why would it be better to split the sites into dedicated workload?
    - What not splitting the sites in dedicated workload have an impact? 
    - What is the concept of deployment strategies? Why should we care? 

including DevOps practices like IaC and GitOps                          10min 

    Q&A - DevOps practices
    - There is a lot of buzz around Agile and DevOps. Can a non Agile organization benefit of Kubernetes? 
    - Starting with the basics, IaC and GitOps are almost mandatory, why?
    - What are the benefits of using such practices? 

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
