## webinar storyboard

Introduction of the hosts                                                
Overview of the agenda along with key take away                         5min 

Presenting a traditional CRM deployed on 2 VMs                          
- based on drupal + mysql 
- 5 sites within one drupal instance
- 5 DBs within one mysql instance 
including potential deployments with Ansible, XLRelease
including storage and backup solutions for BCP                          5min 

Presenting a microservice version to migrate the CRMs         
- drupal + postgresql 
-- 5 sites in one instance becomes 5 drupal workloads 
-- 5 DBs in one instance become 5 postgresql workloads                  
including deployment strategies                                         5min 
including DevOps practices like IaC and GitOps                          10min 

Presenting persistent data challenges due to k8s design
- storage type (block, file, object)
- access mode (rwo, rwx, rox) 
- data migration approaches 
- backup                                                                10min 

Reminding the audience of the key take away
Q&A                                                                     10min
