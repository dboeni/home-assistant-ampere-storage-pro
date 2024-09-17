An easy-to-use YAML-based integration for several Ampere.Storage.Pro inverters for Home Assistant.

There are two ways to read the data from an Ampere.Storage.Pro. Both options are explained here.
- Variant 1: Via Modbus
- Variant 2: Via Rest (the Ampere.IQ Box is required here)
- Variant 3: Custom Integration over HACS [link](https://github.com/dboeni/home-assistant-ampere-storage-pro-modbus)

# Requirements:
- HomeAssistant with Visual Studio Server or File Editor Addon
- Ip addresses of inverter and IQ box (optional)

# Variant 1:
The inverter can be read out via Modbus TCP (port 502).
Add or update the values from secrets.yaml to your Home Assistant.

# Variant 2:
The Ampere.IQ Box can be read out via a REST interface.
The following placeholders must be replaced in the [rest_ampere_storage_pro.yaml](rest_ampere_storage_pro.yaml) file:
- [IP]: Ip address of the Ampere.IQ Box
- [SN]: Serial number of the inverter. This can be read out using this REST URL: http://[IP]/rest/things

# Integrate into HomeAssistant
Copy the YAML file of the selected variant into the "integrations" directory.

Include "modbus_sungrow.yaml" by adding the follwing lines to your "configuration.yaml":

```
homeassistant:
  packages: !include_dir_named integrations
```

Now check your configuration (Developer Tools -> "check configuration" and perform a restart. The entries will then be available.
