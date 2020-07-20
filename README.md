# ansible-tower-f5

Ansible Tower Overview¶
Before looking at the details of the onboarding process, let’s discuss the new components Ansible Tower introduces to our toolchain. Some of the components are general Ansible terms and not specific to Tower. As mentioned earlier we will be focusing primarily on the concepts within Tower itself.

Ansible Tower Term Reference¶
Inventory: Device(s) to perform action against. In this lab we will be using bigip_a_mgmt as the inventory object.
Playbook: A group of plays/tasks to be performed against devices within the Inventory.
Project: A collection of Ansible Playbooks within tower. In this lab were are using a GIT Repo to store the playbooks.
Templates: A template provides the ability to supply parameters to a playbook. Templates are what will provide the Abstraction to AS3.
Credentials: Used to authenticate Tower to the destination device within the Inventory.
Role Based Access Control (RBAC)¶
Ansible Tower provides a control hierarchy with the terms below:

Organization (AS3 Tenant): An organization is a logical collection of Users, Teams, Projects, and Inventories. It is the highest level in the Tower object hierarchy.
Team: A subdivision of an organization with associated Users, Projects, Credentials, and Permissions.
User: A User is usually associated with a Team to allow for group based RBAC control.
Example of the RBAC structure being used in this lab:

Tenant1 (Organization)
T1-Admins (Team)
T1-admin-user (User)
T1-Ops (Team)
T1-ops-user (User)
Source-of-Truth¶
As discussed in Module 2, it is key to keep source-of-truth in mind as Tower will be making changes through F5’s declarative AS3 interface. For this lab we have created an AS3 declaration (source-of-truth) file for each of the primary Service Examples from the previous Module. The intent here is to demonstrate the ability of Tower to manage and push source-of-truth declarations from within its Project (GIT SCM).
