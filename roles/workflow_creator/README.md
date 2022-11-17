# Role Name

A playbook to help generate dynamic Workflows within Tower/Automation Controller.

This is intended to show how you can dynamically create workflows that may have changing parameters such as inventories, credentials, etc. This prevents the need to have dozens of one-off workflows and instead lets you create these as-needed.

Once the workflow is created and launched it is deleted and the job data will persist in Tower/Controller.

This is simply an example template and not intended to be directly ran in an environment.

## Requirements

One of the following collections need to be present:

- ansible.controller
- ansible.tower
- awx.awx

## Role Variables

There are example variables in roles/workflow_creator/vars directory.

This is an example of using a lookup table to map parameters for a particular environment (Dev vs Prod) and application type (web vs database).

## Example Playbook

An example playbook to create and launch a playbook to configure a web server in Dev.

    - hosts: controller
      roles:
         - { role: workflow_creator, environment_type: dev, app_type: web }
