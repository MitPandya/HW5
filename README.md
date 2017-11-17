# HW5 - Configuration Management and Continuous Deployment

* **Concepts**:

* Why should developers use configuration management tools to manage their software programs? What can go wrong
**Answer :* The fundamental purpose of configuration management is to provide and maintain integrity,evaluation, coordination and       implementation in changes of the artifacts, small software pieces, used to construct and maintain software systems. Several configuration management tools such as puppet,chef, ansible etc. are designed to manage IT infrastructure and related application with the up-to-date information on system sunctions and interrelationships between all software and hardware, and are accustomed to ever-changing and complex infrastructure which would be hard to manage otherwise.
Manual configuration of system is error-prone and labor intensive, requires time and effort. With more complex infrastructures it becomes tedious over time. Configuration management tools aims at minimizing manual efforts by automation in configuration. Developers should use the configuration management tools for the following key benefits.
   * Increased efficiencies, stability and control by improving visibility and tracking and powerful documentation.
   * Enhanced system reliability through more rapid detection and correction of improper configurations.
   * Greater agility and decreased risk in building infrastructures.
   * Configuration management tools are easy to learn and master hence ease of usability and provides greater flexibility for developers      in configuration of softwares.

* Explain the difference bewteen continuous integration, continuous delivery, and continuous deployment, in your own words.

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
