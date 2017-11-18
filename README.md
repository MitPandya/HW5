# HW5 - Configuration Management and Continuous Deployment

Ansible playbook
* **Setup:** 
    * Refer to [hw5-playbook.yml](hw5-playbook.yml)
    
* **Tasks:**:
    * Refer to [hw5-playbook.yml](hw5-playbook.yml)

* **Concepts**:

**1: Why should developers use configuration management tools to manage their software programs? What can go wrong?**<br />
**Answer :** The fundamental purpose of configuration management is to provide and maintain integrity,evaluation, coordination and implementation in changes of the artifacts, small software pieces, used to construct and maintain software systems. Several configuration management tools such as puppet,chef, ansible etc. are designed to manage IT infrastructure and related application with the up-to-date information on system sunctions and interrelationships between all software and hardware, and are accustomed to ever-changing and complex infrastructure which would be hard to manage otherwise.
Manual configuration of system is error-prone and labor intensive, requires time and effort. With more complex infrastructures it becomes tedious over time. Configuration management tools aims at minimizing manual efforts by automation in configuration. Developers should use the configuration management tools for the following key benefits.
   * Increased efficiencies, stability and control by improving visibility, tracking and powerful documentation.
   * Enhanced system reliability through more rapid detection and correction of improper configurations.
   * Greater agility and decreased risk in building infrastructures.
   * Configuration management tools are easy to learn and master hence ease of usability and provides greater flexibility for developers      in configuration of softwares.

**What can go wrong?**
* Configuration management tools requires developers to have expertise of language it uses and planning of infrastructure ahead. Since cm tools run parallelly from top to down, the tasks needs to be defined in such a way that dependencies needs to be integrated before.
Moreover developers and cm tool needs to be cautious before taking down an environment. If an environment depends on other and taking down the dependent environment may cause the production act wrong or may even crash. 
Another important concern is that developers should define additional check after starting or stopping any environment for e.g. if a cm tool is intended to stop a production like environment after certain tests but fails to stop that and if customer queries are still redirected to production like environments instead of actual production environment then there may be misleading or false data and may affect the users negatively.
* There are many different types of configuration management tools available, each of which has its own advantages and disadvantages hence it is equally important to choose the right type of cm tool suitable to the software infrastructure, cm tools are also hard to debug so developers needs to be cautious while writing automation scripts.

**2 : Explain the difference bewteen continuous integration, continuous delivery, and continuous deployment, in your own words.**<br />
**Answer : Continuous Integration** or CI is a practice in which developers build and test their software based on other software changes committed on source repo. and thus future merges becomes easy and the integration does not become complex at the time of releases. In CI automated regressions are run everytime there is a new commit and hence reduces the bugs at the time of release.
**Continuous Delivery** emphasizes at delivering releases to production like environment after every change that passes tests and regressions. Hence after testing the code in production like environment developers can check how it will work at customer site and can troubleshoot on bugs or error earlier before releases.
**Continuous Deployment** is a one step advance of continuous delivery in which software changes are deployed at production environment after every change that passes production pipeline regressions and tests. In continuous deployment practice releases are made often to customers and customer feedback also becomes often which can be useful for any change or improvement.

* The main differences between each is the levels till which it can communicate. CI lifecycle is Dev->Application test->Integration test, Continuous delivery lifecycle is Dev->Application test->Integration test->Production like environment manually, where as Continuous Deployment lifecycle is Dev->Application test->Integration test->Production environment through automation.
Further CI emphasis on building release but does not produce any release and requires a continuous integration server which monitors changes committed to the main branch of the repo and run the automation tests, developers require to merge their changes frequently generally on daily basis. Continuous delivery requires automated deployments to production like environment but through manual trigger. Developers needs to be cautious as what goes to continuous delivery so that half implemented softwares do not go to production like environments. Continuous deployment requires better test and regression suits since the feature is directly released to production environment and also developers needs to keep up with the documentation since customers needs to understand about new features and how to use them etc. 


## Steps to run ansible and playbook
* Create to vagrant vms called ansible and node0 running at private network 192.168.33.10 and 192.168.33.100 respectively as described in this [workshop](https://github.com/CSC-DevOps/CM/blob/master/VM.md)
* After following steps described in workshop do vagrant ssh inside `\boxes\ansible` folder
* Do `vagrant ssh`
* Follow steps in this [file](https://github.com/CSC-DevOps/CM/blob/master/Ansible.md) till 'Setting up ssh keys'
* Try `ssh -i keys/node0.key vagrant@192.168.33.100`
* If ssh was successful exit and run `ansible-playbook -i inventory hw5-playbook.yml`
* On success you can check output on browser at http://192.168.33.100:8085

## Screencast
#### Configuration Management and Continuous Deployment Demo which performs setup and tasks<br />
[CSC-510: HW5 Screencast](https://youtu.be/FW63sGpN8yw).

#### References
* http://docs.ansible.com/ansible/latest/playbooks.html
* http://docs.ansible.com/ansible/latest/apt_module.html
* http://docs.ansible.com/ansible/latest/git_module.html
* http://docs.ansible.com/ansible/latest/npm_module.html
* http://docs.ansible.com/ansible/latest/file_module.html
* https://en.wikipedia.org/wiki/Software_configuration_management
* https://stackoverflow.com/questions/28608015/continuous-integration-vs-continuous-delivery-vs-continuous-deployment
