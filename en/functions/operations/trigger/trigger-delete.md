---
title: "How to delete a trigger in {{ sf-full-name }}"
description: "In this tutorial, you will learn how to delete a trigger in {{ sf-full-name }}."
---

# Deleting a trigger in {{ sf-name }}

{% list tabs %}

- Management console

   1. In the [management console]({{ link-console-main }}), select the folder containing your trigger.
   1. Select **{{ sf-name }}**.
   1. On the left-hand panel, select ![image](../../../_assets/functions/triggers.svg) **Triggers**.
   1. Select the trigger you want to update.
   1. In the upper-right corner of the page, click **Delete**.
   1. In the window that opens, click **Delete**.

- CLI

   {% include [cli-install](../../../_includes/cli-install.md) %}

   {% include [default-catalogue](../../../_includes/default-catalogue.md) %}

   {% include [trigger-list-note](../../../_includes/functions/trigger-list-note.md) %}

   Delete the trigger:

   ```bash
   yc serverless trigger delete <trigger name>
   ```

   Result:

   ```text
   id: a1s9q2li6t**********
   folder_id: b1g9hv2loa**********
   created_at: "2023-08-01T12:36:14.321Z"
   name: my-trigger
   description: Trigger for uploaded objects
   rule:
     object_storage:
       event_type:
         - OBJECT_STORAGE_EVENT_TYPE_CREATE_OBJECT
       bucket_id: **********
       batch_settings:
         size: "10"
         cutoff: 10s
       invoke_function:
         function_id: d4e5muirrt**********
         function_tag: $latest
         service_account_id: ajek0fou8e**********
   status: PAUSED
   ```

- {{ TF }}

   For more information about {{ TF }}, [see the documentation](../../../tutorials/infrastructure-management/terraform-quickstart.md#install-terraform).

   {% include [terraform-definition](../../../_tutorials/terraform-definition.md) %}

   To delete a trigger created using {{ TF }}:

   1. Open the {{ TF }} configuration file and delete the fragment with the trigger description.

      Example trigger description in the {{ TF }} configuration:

      ```hcl
      ...
      resource "yandex_function_trigger" "my_trigger" {
        name        = "some_name"
        description = "any description"
        timer {
          cron_expression = "* * * * ? *"
        }
        function {
          id = "tf-test"
        }
      }
      ...
      ```

   1. In the command line, go to the directory with the {{ TF }} configuration file.

   1. Check the configuration using this command:

      ```
      terraform validate
      ```

      If the configuration is correct, you will get this message:

      ```
      Success! The configuration is valid.
      ```

   1. Run this command:

      ```
      terraform plan
      ```

      The terminal will display a list of resources with parameters. No changes are made at this step. If the configuration contains any errors, {{ TF }} will point them out.

   1. Apply the configuration changes:

      ```
      terraform apply
      ```

   1. Confirm the changes: type `yes` into the terminal and press **Enter**.

      You can verify the changes using the [management console]({{ link-console-main }}) or the [CLI](../../../cli/quickstart.md) command below:

      ```
      yc serverless trigger list
      ```

- API

   To delete a trigger, use the [delete](../../triggers/api-ref/Trigger/delete.md) REST API method for the [Trigger](../../triggers/api-ref/Trigger/index.md) resource or the [TriggerService/Delete](../../triggers/api-ref/grpc/trigger_service.md#Delete) gRPC API call.

{% endlist %}
