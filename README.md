# Ansible Modules for VAST Data 
The Ansible Modules for VAST Data allow Data Center and IT administrators to use RedHat Ansible to automate and orchestrate the configuration and management of VAST Data arrays.

The Ansible Modules for VAST Data support the following features:
- Create user, groups, filesystem, NFS export, smart quotas, SMB share, snapshot and snapshot schedule of a filesystem.
- Modify user, groups, filesystem, access zone, NFS export, smart quotas, SMB share, snapshot and snapshot schedule of a filesystem.
- Delete user, groups, filesystem, NFS export, smart quotas, SMB share, snapshot and snapshot schedule of a filesystem.
- Get details of user, groups, node, filesystem, access zone, NFS export, smart quotas, SMB share, snapshot and snapshot schedule of a filesystem.
- Get details of SyncIQ policies, SyncIQ jobs, SyncIQ reports, SyncIQ target reports and SyncIQ performance rules of the cluster.
- Add, modify and remove Active Directory and LDAP to Authentication providers list.
- Map or unmap Active Directory and LDAP Authentication providers to Access zone.
- Create, modify and delete SyncIQ policy.
- Create job on SyncIQ policy and modify the state of SyncIQ Job.
- Create, modify and delete SyncIQ performance rule.
- Create, modify and delete Groupnet, Subnet, Network Pool and Network Rule.
- Get details of Groupnet, Subnet, Network Pool and Network Rule.
- Modify cluster email settings.
- Get cluster email settings and NTP Server details.
- Add and remove NTP Servers
- Create an access zone.
- Get network and smart pool settings.
- Modify network and smart pool settings.
- Get attributes and entities of the array.

The tasks can be executed by running simple playbooks written in yaml syntax.

## License


## Support


## Supported Platforms
  * All VAST Data releases 4.1+

## Prerequisites
This table provides information about the software prerequisites for the Ansible Modules for Dell PowerScale.

| **Ansible Modules** | **VAST Data Version** | **Red Hat Enterprise Linux** | **Python version** | **Python SDK version** | **Ansible** |
|---------------------|-----------------------|------------------------------|--------------------|----------------------------|-------------|
| v1.0 | 4.1 <br> 4.2 <br> 4.4 | 8.4 <br> 8.5 | 3.5 <br> 3.6 <br> 3.9 | 8.1.1 <br> 9.0.0 | 2.10 <br> 2.11 <br> 2.12 | 

## Idempotency
The modules are written in such a way that all requests are idempotent and hence fault-tolerant. It essentially means that the result of a successfully performed request is independent of the number of times it is executed.

## List of Ansible Modules for VAST Data


## Building Collections
  1. Use the following command to build the collection from source code:
    
    ansible-galaxy collection build

   For more details on how to build a tar ball, please refer: [Building the collection](https://docs.ansible.com/ansible/latest/dev_guide/developing_collections_distributing.html#building-your-collection-tarball)


## Installing Collections
#### Online Installation of Collections 
  1. Use the following command to install the latest collection hosted in galaxy:

	ansible-galaxy collection install dellemc.powerscale -p <install_path>

  #### Offline Installation of Collections
  1. Download the latest tar build from either of the available distribution channels [Ansible Galaxy](https://galaxy.ansible.com/dellemc/powerscale) /[Automation Hub](https://console.redhat.com/ansible/automation-hub/repo/published/dellemc/powerscale) and use the following command to install the collection anywhere in your system:

	ansible-galaxy collection install brettdellandre-vast_ansible-1.0.tar.gz -p <install_path>

  2. Set the environment variable:

	export ANSIBLE_COLLECTIONS_PATHS=$ANSIBLE_COLLECTIONS_PATHS:<install_path>

## Using Collections
  1. In order to use any Ansible module, ensure that the importing of a proper FQCN (Fully Qualified Collection Name) must be embedded in the playbook. Refer to the following example:

	collections:
	- vastdata

  2. In order to use an installed collection specific to the task use a proper FQCN (Fully Qualified Collection Name). Refer to the following example:

	tasks:
    - name: Get filesystem details
	  vastdata.filesystem

  3. For generating Ansible documentaion for a specific module, embed the FQCN  before the module name. Refer to the following example:

	ansible-doc vastdata.info

## Running Ansible Modules

## SSL Certificate Validation

* Export the SSL certificate using KeyStore Explorer tool or from the browser in .crt format.
* Append the SSL certificate to the Certifi package file cacert.pem.
    * For Python 3.5 : cat <> >> /usr/local/lib/python3.5/dist-packages/certifi/cacert.pem
    * For Python 2.7 : cat <> >> /usr/local/lib/python2.7/dist-packages/certifi/cacert.pem

## Results
Each module returns the updated state and details of the entity. 
For example, if you are using the group module, all calls will return the updated details of the group.
Sample result is shown in each module's documentation.
