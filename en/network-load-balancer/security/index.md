---
title: "Access management in {{ network-load-balancer-full-name }}"
description: "Access management in {{ network-load-balancer-full-name }}, a network balancer system. This section describes which resources you can assign roles to, which roles exist in the service, and which roles are required for particular actions."
---

# Access management in {{ network-load-balancer-name }}

In this section, you will learn:
* [Which resources you can assign roles to](#resources).
* [Which roles exist in the service](#roles-list).
* [Which roles are required](#choosing-roles) for particular actions.

{% include [about-access-management](../../_includes/iam/about-access-management.md) %}

## Which resources you can assign roles to {#resources}

{% include [basic-resources](../../_includes/iam/basic-resources-for-access-control.md) %}

## Which roles exist in the service {#roles-list}

The chart below shows which roles are available in the service and how they inherit each other's permissions. For example, the `editor` role includes all `viewer` role permissions. You can find the description of each role under the chart.

![image](../../_assets/network-load-balancer/security/service-roles-hierarchy.svg)

Active roles in the service:

* Service roles:
   * {% include [resource-manager.clouds.owner](../../_includes/iam/roles/short-descriptions/resource-manager.clouds.owner.md) %}
   * {% include [resource-manager.clouds.member](../../_includes/iam/roles/short-descriptions/resource-manager.clouds.member.md) %}
   * {% include [load-balancer.viewer](../../_includes/iam/roles/short-descriptions/load-balancer.viewer.md) %}
   * {% include [load-balancer.privateAdmin](../../_includes/iam/roles/short-descriptions/load-balancer.privateAdmin.md) %}
   * {% include [load-balancer.admin](../../_includes/iam/roles/short-descriptions/load-balancer.admin.md) %}
* Primitive roles:
   * {% include [viewer](../../_includes/iam/roles/short-descriptions/viewer.md) %}
   * {% include [editor](../../_includes/iam/roles/short-descriptions/editor.md) %}
   * {% include [admin](../../_includes/iam/roles/short-descriptions/admin.md) %}

## What roles do I need {#choosing-roles}

The table below lists the roles needed to perform a particular action. You can always assign a role granting more permissions than the role specified. For example, you can assign the `editor` role instead of the `viewer` one.

Any operations with a network load balancer that has a public IP address require the `load-balancer.admin` role. In networks where target groups are located, you can have the `vpc.publicAdmin` role instead. Operations on the internal network load balancer require the `load-balancer.privateAdmin` role and operations on its target groups — the `load-balancer.privateAdmin` or `compute.admin` role.

Operations on target groups located in subnets, where the specified administrative roles are missing, require the `vpc.user` role for these subnets.

| Action | Methods | Required roles |
----- | ----- | -----
| **View data** | |
| View information about any resource | `get`, `list`, `listOperations` | `viewer` for this resource |
| **Manage network load balancers** | |
| [Create](../operations/load-balancer-create.md) and update load balancers in folders | `create` | `load-balancer.privateAdmin` / `load-balancer.admin` or `editor` for the folder and, if the load balancer is public, networks where target groups are located |
| [Delete load balancers](../operations/load-balancer-delete.md) | `update`, `delete` | `load-balancer.privateAdmin` / `load-balancer.admin` or `editor` for the load balancer |
| [Attach target groups](../operations/target-group-attach.md) | `attachTargetGroup` | `load-balancer.privateAdmin` / `load-balancer.admin` or `editor` for the folder and, if the load balancer is public, networks where target groups are located |
| [Detach target groups](../operations/target-group-detach.md) | `detachTargetGroup` | `load-balancer.privateAdmin` / `load-balancer.admin` or `editor` for the load balancer |
| [Get states of target groups](../operations/check-resource-health.md) | `getTargetStates` | `load-balancer.viewer` or `viewer` for the load balancer and the specified target groups |
| [Add](../operations/listener-add.md) and [remove](../operations/listener-remove.md) listeners | `addListener`, `removeListener` | `load-balancer.privateAdmin` / `load-balancer.admin` or `editor` for the load balancer |
| [Stop and start](../operations/load-balancer-start-and-stop.md) a load balancer | `stop`, `start` | `load-balancer.privateAdmin` / `load-balancer.admin` or `editor` for the load balancer |
| **Manage target groups** | |
| [Create](../operations/target-group-create.md) and update target groups in folders | `create` | `load-balancer.privateAdmin` / `load-balancer.admin` or `editor` for the folder and subnets where target groups are located |
| [Delete target groups](../operations/target-group-delete.md) | `update`, `delete` | `load-balancer.privateAdmin` / `load-balancer.admin` or `editor` for the target group and load balancer |
| Add resources in a target group | `addTargets` | `load-balancer.privateAdmin` / `load-balancer.admin` or `editor` for the target group, load balancer, and subnets where target groups are located |
| Remove resources in a target group | `removeTargets` | `load-balancer.privateAdmin` / `load-balancer.admin` or `editor` for the target group |
| **Manage resource access** | |
| [Grant a role](../../iam/operations/roles/grant.md), [revoke a role](../../iam/operations/roles/revoke.md), and view roles granted for the resource | `setAccessBindings`, `updateAccessBindings`, `listAccessBindings` | `admin` for the resource |

#### What's next {what-is-next}

* [How to assign a role](../../iam/operations/roles/grant.md).
* [How to revoke a role](../../iam/operations/roles/revoke.md).
* [Learn more about access management in {{ yandex-cloud }}](../../iam/concepts/access-control/index.md).
* [Learn more about inheriting roles](../../resource-manager/concepts/resources-hierarchy.md#access-rights-inheritance).
