## webinar storyboard

Introduction of the hosts                                                
Overview of the agenda along with key take away                         5min

Presenting a traditional CRM deployed on 2 VMs                          
 - based on drupal + mysql
 - 5 sites within one drupal instance
 - 5 DBs within one mysql instance
including potential deployments with Ansible, XLRelease
including storage and backup solutions for BCP                          10min

Presenting a traditional CRM deployed on 2 VMs                          
 
**Q&A**
 - What is a lift and shift?
	 - **Lift and Shift :** mainly is to move applications to other infrastructure (physical, virtual or cloud) without modifying its code, features or functions.
- What are the options for a lift and shift?
	- Actually i like [Gartner article "7 Options to Modernize Legacy Systems"](https://www.gartner.com/smarterwithgartner/7-options-to-modernize-legacy-systems/)
    According to Gartner, The two main options are;
      - **Rehost.** Redeploy the application component to other infrastructure (physical, virtual or cloud) without modifying its code, features or functions.
      - **Replatform.** Migrate to a new runtime platform, making minimal changes to the code, but not the code structure, features or functions. Like migrating the runtime  to container runtime like docker, containerd, or CRI-O, but without touching the application itself.

- Other options are refactoring and modernization. What are the differences?
  - Refactoring is mainly modifying the code to "some extent" to accommodate the new runtime capabilities.
   This can be
    - **Rearchitect.** Materially alter the code to shift it to a new application architecture and exploit new and better capabilities. like using configmaps and secrets in K8s rather that files and property files.
  - modernization, is to rewrite the application to utilize modern techniques and features
      - **Rebuild.** Redesign or rewrite the application component from scratch while preserving its scope and specifications. like rewriting the application using

- How can an organization make a decision regarding one or the other?
  - It really depends what is the organization needs, Rearchitecting has medium costs and risks, whereas rebuilding or replacing provides best results with higher costs and risks. So we need to align with the business drivers and organization targets.

- If a lift and shift is done, is it forever?
Normally lift and shift is an intermediate or transient step in the modernization journey and the idea is to reduce the impact of change within the organization and start building the appetite within the IT department.  

Presenting a microservice version to migrate the CRMs         
- drupal + postgresql
-- 5 sites in one instance becomes 5 drupal workloads
-- 5 DBs in one instance become 5 postgresql workloads                  

including DevOps practices like IaC and GitOps                          10min
    
**Q&A**
- There is a lot of buzz around Agile and DevOps. Can a non Agile organization benefit of Kubernetes?

- Lets define;
	- Agile: [Wiki: Agile software development](https://en.wikipedia.org/wiki/Agile_software_development), from the Wiki definition i want to highlight
  > it encourages flexible responses to changes in requirements, resource availability, and understanding of the problems to be solved.

  - So the basic idea is "flexibility", this need for flexibility drove the whole IT landscape including IT infrastructure.

  - DevOps: [Wiki: DevOps](https://en.wikipedia.org/wiki/DevOps),
  > DevOps is a set of practices that combines software development (Dev) and IT operations (Ops). It aims to shorten the systems development life cycle and provide continuous delivery with high software quality

  - So put Agile + DevOps in one sentence = An organization that can react quickly to changes by having flexible IT landscape and short development and delivery cycles.Which is exactly K8s mission statement

- Why Kubernetes?

- Starting with the basics, IaC and GitOps are almost mandatory, why?

- What are the benefits of using such practices?

including deployment strategies                                         5min
    Q&A - Presenting a microservice version to migrate the CRMs
    
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
