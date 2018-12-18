# VMware Create Guest 

## Description

This role will provision a new Ubuntu 16.04 or CentOS 7 guest in VMware vCenter, provided you have created a template for use for either.  Each template also needs a static IP set.  So I will explain it away by saying it was my first attempt and that I will try to attempt to use other tools (i.e. Packer and/or Terraform).  But for what it is, it works pretty good.  Saves you a bunch of time in deploying single servers, serially. 

## Variables

| Variable           | Description                                                                    |
| ------------------ | ------------------------------------------------------------------------------ |
| **prov_ip_addr**   | IP address of the new VM							      |
| **prov_hostname**  | Hostname of the new VM							      |
| **vcenter_user**   | vCenter username that will be used to create the new VM			      |
| **vcenter_pass**   | Password for the vCenter user; please observe security considerations	      |
| **prov_owner**     | Name to add in the annotation						      |
| **prov_purpose**   | Short description of the VM being created to be added to the annotation	      |
| **vm_mem_size**    | Configured memory for the VM in MB					      |
| **vm_vcpu_num**    | Configured number of vCPUs for the VM					      |
| **vm_disk_size**   | Configured size for the first disk in the VM in MB			      |
| **prov_distro**    | Which Linux distribution to use						      |

Depending on your VMware configuration, you may also need to configure the following variables:

| Variables	         | Description								      |
| ---------------------- | -------------------------------------------------------------------------- |
| **dest_vm_datacenter** | The datacenter that the VM will be created in			      |
| **dest_vm_host**       | The specific ESXi host to create the VM on				      |

A lot of other items can be assigned variables, but for my purposes, it was easier to hard-code it into the role since they would not (or were unlikely to) change (i.e. domain, dns, etc).

## Written By
David Hunter, 2018
