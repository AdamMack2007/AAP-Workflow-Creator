# Role Name

A playbook to help generate dynamic Workflows within Tower.

This is intended to show how you can dynamically create workflows that may have changing parameters such as inventories, credentials, etc. This prevents the need to have dozens of one-off workflows and instead lets you create these as-needed.

Once the workflow is created and launched it is deleted and the job data will persist in Tower.

This is simply an example template and not intended to be directly ran in an environment.

## Requirements

The following collection needs to be present:

- ansible.tower

## Role Variables

There are example variables in roles/workflow_creator/vars directory.

The {{ wf_structure }} variable is intended to demonstrate the layout of the workflow structure in its sequential order.

## Example Playbook

An example playbook to create and launch a playbook to configure a web server in Dev.

    - hosts: tower
      roles:
         - { role: workflow_creator, environment_type: dev, app_type: web }
