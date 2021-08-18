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

  - [**Infrastructure Elasticity & self healing**](https://kubernetes.io/docs/concepts/overview/what-is-kubernetes/), is the magic word. K8s provides an easy way to scale applications, it restarts containers that fail, replaces containers, kills containers that don't respond to your user-defined health check, and doesn't advertise them to clients until they are ready to serve.


including deployment strategies                                         5min

- Presenting a microservice version to migrate the CRMs

**Q&A**

- Considering the current setup, why would it be better to split the sites into dedicated workload?

  - One of the main characteristics of microservices is [Single Responsibility Principle](https://microservices.io/patterns/decomposition/decompose-by-business-capability)

    > A service must be small enough to be developed by a small team and to be easily tested. A useful guideline from object-oriented design (OOD) is the Single Responsibility Principle (SRP). The SRP defines a responsibility of a class as a reason to change, and states that a class should only have one reason to change. It make sense to apply the SRP to service design as well and design services that are cohesive and implement a small set of strongly related functions.

- What not splitting the sites in dedicated workload would have an impact?

  - Modification of any site will impact rest of sites. Release of any site may cause down time for other independent sites.

- What is the concept of deployment strategies?
  - Deployment Strategy is the techniques of how a new release of the application affect continuity of the application downtime and last-minute failure or rollback. Take for example the typical case where you bring your previous version down, and do the midnight down time to deploy an new version.
  Most famous deployment strategies
    - Recreate: Version A is terminated then version B is rolled out.
    - Rolling-update: Version B is slowly rolled out and replacing version A. So at some point both versions are running.
    - Blue/Green: Version B is released alongside version A, then the traffic is switched to version B. Useful in case of the need to quickly roll back.
    - Canary: Version B is released to a subset of users, then proceed to a full rollout. the canary technique targets certain users to receive access to the new application version, rather than certain servers in the Rolling-update technique.

- Why should we care?
  - Business continuity is one of the main reason for advancing IT industry. So the less downtime and the agility of deployment techniques is very critical for business.

Presenting persistent data challenges due to k8s design
- storage type (block, file, object)
- access mode (rwo, rwx, rox)
- data migration approaches
- backup                                                                10min
Presenting persistent data challenges due to k8s design

**Q&A**
- Why is persistent data important?

- What are the different storage type and their usage?

- In k8s, there is the concept of access mode? What are the differences between each others?

- Migrating data is a pain. Is it different with k8s?

- What the major differences between traditional environment/VM or bare metal based backups vs k8s?

Reminding the audience of the key take away
Q&A
