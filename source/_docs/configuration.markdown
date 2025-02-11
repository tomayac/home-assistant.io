---
title: "Configuration.yaml"
description: "Configuring Home Assistant via text files."
---

While you can configure most of Home Assistant directly from the user interface under {% my config %}, some parts need you to edit `configuration.yaml`. This file contains {% term integrations %} to be loaded along with their configurations. Throughout the documentation you will find snippets that you can add to your configuration file to enable specific functionality.

If you run into trouble while configuring Home Assistant, refer to the [configuration troubleshooting page](/docs/configuration/troubleshooting/) and the [`configuration.yaml` examples](/examples/#example-configurationyaml).

## Editing `configuration.yaml`

The easiest option to edit `configuration.yaml` is to use the {% my supervisor_addon title="Studio Code Server add-on" addon="a0d7b954_vscode" %}. This add-on runs VS Code, which  offers live syntax checking and auto-fill of various Home Assistant entities. See [here](/common-tasks/supervised/#installing-and-using-the-visual-studio-code-vsc-add-on) for details. If unavailable on your system, use {% my supervisor_addon title="File Editor add-on" addon="core_configurator" %} instead. Again, details can be found [here](/common-tasks/supervised/#installing-and-using-the-file-editor-add-on).

If you prefer to use a file editor on your computer, use the {% my supervisor_addon title="Samba add-on" addon="core_samba" %} to access the files as a network share. More details can be found [here](/common-tasks/supervised/#installing-and-using-the-samba-add-on).

The path to your configuration directory can be found in the Home Assistant {% term frontend %} by going to {% my system_health title="Settings > System > Repairs > System information from the top right menu" %}

![Show system menu option](/images/screenshots/System_information_menu.png)

Right under the version you are running, you will find what path Home Assistant has loaded the configuration from.
![Screenshot showing the top of the system information panel](/images/screenshots/System_information.png)

_If you use {% term "Home Assistant Container" %}, you can find `configuration.yaml` in the config folder that you mounted in your container._

_If you use {% term "Home Assistant Operating System" %}, you can find `configuration.yaml` in the `/config` folder of the installation._

_If you use {% term "Home Assistant Core" %} , you can find `configuration.yaml` in the config folder passed to the `hass` command (default is `~/.homeassistant`)._

## Reloading changes

Most integrations in Home Assistant that do not interact with {% term devices %} or {% term services %} can reload changes made to their configuration in `configuration.yaml`. To do this, go to {% my server_controls title="Developer Tools > YAML" %} and scroll down to the YAML configuration reloading section (alternatively, hit "c" anywhere in the UI and search for it).

If you can't see your integration listed there, you will need to restart Home Assistant for changes to take effect.

<div class='note'>

  To test any changes to your configuration files from the command line, check out the common tasks for [operating system](/common-tasks/os/#configuration-check), [supervised](/common-tasks/supervised/#configuration-check), [container](/common-tasks/container/#configuration-check), [core](/common-tasks/core/#configuration-check) for how to do that. Configuration changes can also be tested using the UI by navigating to {% my server_controls title="Developer Tools > YAML" %} and clicking "Check Configuration". For the button to be visible, you must enable "Advanced Mode" on your {% my profile title="User Profile" %}.

</div>

## Related topics

- [Creating and restoring backups](/common-tasks/os/#backups)
- [Creating backups for Home Assistant Container and Core](/integrations/backup)
