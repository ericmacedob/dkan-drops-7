# DKAN Workflow
![DKAN Workflow](./dkan_workflow_screenshot.png)

Publishing workflow for [DKAN](https://github.com/GetDKAN/dkan) based on
[Workbench](https://www.drupal.org/project/workbench) and related modules.

## Requirements

* Dkan install. We do use undeclared dependencies used in core Dkan, for example
  the dataset and resource content types, features_role_export...
* All external dependencies other then core Dkan are incapsulated in the
`dkan_workflow.make` file. This includes
[Workbench](https://www.drupal.org/project/workbench) and related modules
([Workbench Moderation](https://www.drupal.org/project/workbench_moderation) for
the content moderation features, [Workbench
Email](https://www.drupal.org/project/workbench_email) for email notifications.)
* Better UX is made possible by using the [Link
  Badges](https://www.drupal.org/project/link_badges) and [Menu
  Badges](https://www.drupal.org/project/menu_badges)

## Installation

This module is disabled by default in a new DKAN installation. After either enabling or disabling DKAN Workflow and its dependencies, you will need to [rebuild content permissions](https://docs.acquia.com/articles/rebuilding-node-access-permissions). If logged in as an admin you should see a message telling you this with a link to the form to do so.

## Known issues:

* Transitions config and Emails templates for "Original Author" could not be
 exported due to a bug in workbench_email.
* Behat tests uses [hhs_implementation](https://github.com/GetDKAN/dkanextension/tree/hhs_implementation)
 dkanextension instead of the master branch.
* Support for OG while sending emails is supported but not clearly documented.

## Documentation

We are working on improving this documentation. Please let us know if you have
any questions in the meantime.

If in any point you want to reimport the workbench email default templates into your site, all you need to do is implement a hook_update_N and execute the function `dkan_workflow_import_email_defaults()` in there.
