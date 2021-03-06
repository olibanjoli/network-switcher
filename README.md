Network Switcher
=========

Network Switcher allows you to enable/disable network interfaces using hotkeys. It is also possible to create groups of network interfaces to enable/disable multiple interfaces using one hotkey.

### Installation
[Download] the .zip, adjust config.yml to your needs and run `NetworkSwitcher.exe`.
To setup autostart check the [Wiki](../../wiki/Setup-autostart).

###Example Configuration
![](https://raw.githubusercontent.com/olibanjoli/network-switcher/master/images/ncpa.png)
In this example we will configure 3 different hotkeys.
- **Ctrl + NumPad1:** WiFi only
- **Ctrl + NumPad2:** Ethernet only
- **Ctrl + NumPad3:** Wifi and Ethernet

config.yml:
```yml
- Name: Wi-Fi
  Hotkey: Ctrl + NumPad1
  Interfaces:
  - Name: Wi-Fi
- Name: Ethernet
  Hotkey: Ctrl + NumPad2
  Interfaces:
  - Name: Ethernet
- Name: Hybrid
  Hotkey: Ctrl + NumPad3
  Interfaces:
  - Name: Wi-Fi
  - Name: Ethernet
    Metric: 500
```
> **Hotkey:** Add multiple modifiers seperated by a '+' (Ctrl + Alt...) followed by a key.

### Available modifiers
Ctrl, Alt, Shift, Win

### Available keys
See MSDN: [Keys]

### Note
When connected to a wired and a wireless network, Windows will automatically set a Metric value for both interfaces. The wired interface will have a lower Metric by default so that the main traffic goes over the wired interface. You can override the Metric value as it is in the example if you want your main traffic to go through the wireless interface. More information about [Metric].

### Disclaimer
Use at your own risk :-)

[keys]:http://msdn.microsoft.com/en-us/library/system.windows.forms.keys.aspx
[Download]:https://github.com/olibanjoli/network-switcher/blob/master/compiled/Debug.zip
[Metric]:http://support.microsoft.com/kb/299540
