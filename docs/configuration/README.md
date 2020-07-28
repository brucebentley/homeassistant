# Configuring Home Assistant

When launched for the first time, Home Assistant will create a default configuration file enabling the web interface and device discovery. It can take up to a minute after startup for your devices to be discovered and appear in the user interface.

The web interface can be found at [`http://ip.ad.dre.ss:8123/`](http://ip.ad.dre.ss:8123/) - for example if your Home Assistant system has the IP address `192.168.0.40` then you’ll find the web interface as [`http://192.168.0.40:8123/`](http://192.168.0.40:8123/).

The location of the folder differs between operating systems:

| **OS**         | **Path**           |
|:---------------|:-------------------|
| Home Assistant | `/config`          |
| Docker         | `/config`          |
| macOS          | `~/.homeassistant` |
| Linux          | `~/.homeassistant` |

If you want to use a different folder for configuration, use the configuration command line parameter: hass `--config path/to/config`.

Inside your configuration folder is the file `configuration.yaml`. This is the main file that contains integrations to be loaded with their configurations. Throughout the documentation you will find snippets that you can add to your configuration file to enable functionality.

If you run into trouble while configuring Home Assistant, have a look at the [configuration troubleshooting page](https://www.home-assistant.io/getting-started/troubleshooting-configuration/) and at the [`configuration.yaml` examples](https://www.home-assistant.io/cookbook/#example-configurationyaml).

> ℹ️ **Note**
> Test any changes to your configuration files from the command line with `hass --script check_config`. This script allows you to test changes without the need to restart Home Assistant. Remember to run this as the user you run Home Assistant as.

## Editing `configuration.yaml`

There are many ways you can edit `configuration.yaml`. Here are three options to get you started:

The simplest is to use the “File Editor” add-on. This will allow you to edit your configuration from within Home Assistant itself.

You can also use Samba _( you may need to install the “Samba” add-on )_ and your favorite file editor.

The most basic is to use SSH to connect to the system _( you may need to install the SSH add-on )_ and then use `nano` _( or `vim` )_ to edit the file.

## Reloading changes

You will have to restart Home Assistant for most changes to `configuration.yaml` to take effect. You can load changes to [automations](https://www.home-assistant.io/docs/automation/), [core](https://www.home-assistant.io/docs/configuration/customizing-devices/), [groups](https://www.home-assistant.io/integrations/group/), [input_booleans](https://www.home-assistant.io/integrations/input_boolean/), [input_datetimes](https://www.home-assistant.io/integrations/input_datetime/), [input_numbers](https://www.home-assistant.io/integrations/input_number/), [input_selects](https://www.home-assistant.io/integrations/input_select/), [input_texts](https://www.home-assistant.io/integrations/input_text/), [persons](https://www.home-assistant.io/integrations/person/), [scenes](https://www.home-assistant.io/integrations/scene/), [scripts](https://www.home-assistant.io/integrations/script/), [timers](https://www.home-assistant.io/integrations/timer/) and [zones](https://www.home-assistant.io/integrations/zone/) without restarting..

> ⚠️ Warning
> If you’ve made any changes, remember to [check your configuration](https://www.home-assistant.io/docs/configuration/troubleshooting/#problems-with-the-configuration) before trying to reload or restart.

## Migrating To A New System

If you want to migrate your configuration to a new system then you can copy the contents of your configuration folder from the current system to the new system. Be aware that some of the files you need start with `.`, which is hidden by default from both `ls` _( in SSH )_, in Windows Explorer, and macOS Finder. You’ll need to ensure that you’re viewing all files before you copy them.
