# WifiWizard

Version 0.2.0

This Phonegap plugin enables WiFi management from within Phonegap applications. 

Only Android is in development at this time. iOS is planned to be developed, with other platforms following.

### Installation

Run `phonegap plugin install https://github.com/parsonsmatt/WifiWizard.git` and add `<script src="WifiWizard.js"></script>` in your Phonegap project.

### Usage from within Cordova/Phonegap:

* `WifiWizard.formatWifiConfig(SSID, password, algorithm);` formats the wifi configuration information into a JSON for use with the addNetwork function. Currently, only WPA is supported for the `algorithm` value. 
* `WifiWizard.formatWPAConfig(SSID, password);` is a helper method. It returns an object which can be used to add a WPA wifi network.
* `WifiWizard.addNetwork(wifi, win, fail);` adds the network to the list of available networks that the user can log into. `wifi` needs to be an object as formatted by formatWifiConfig. `win` and `fail` are callback functions to be executed based on the result of the call.
* `WifiWizard.removeNetwork(SSID, win, fail);` removes the network with the given SSID. As above, `win` and `fail` are callback functions.
* `WifiWizard.connectNetwork(SSID, win, fail);` connects the phone to the given Wifi network. 
* `WifiWizard.disconnectNetwork(SSID, win, fail);` disconnects the phone to the given Wifi network. 
* `WifiWizard.listNetworks(listHandler, fail);` retrieves a list of the available networks as an array of strings and passes them to the function listHandler.

### Changelog:

* v0.2.0 - Changed format of wifiConfiguration object to allow more extensibility.
* v0.1.1 - `addNetwork` will now update the network if the SSID already exists.
* v0.1.0 - All functions now work!
* v0.0.3 - Fixed errors in native implementation. Currently, Add and Remove networks aren't working, but others are working as expected.
* v0.0.2 - Changed plugin.xml and WifiWizard.js to attach WifiWizard directly to the HTML. 
* v0.0.1 - Initial commit