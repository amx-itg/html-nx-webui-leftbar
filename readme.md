# AMX HTML Template for use with NX Control Systems

## Details

This file updates the existing package that was released as part of the 
AMX_WebUI_Gatway_dr1_0_0.jar file.  This includes files for:

 - Generic WebUI Gateway
 - Microsoft Teams
 - Google Meet
 - Yealink 

The new file removes the ability to select a layout within the configuration file, and that choice must now be made prior to creating the configuration file.
The configuration file is still used and can be migrated from the old template to the current one if needed, with no changes.  

## URL Configuration Options

The URL can now have multiple parameters that help establish connections and configurations, depending on programming need:

Parameters: 
- No Parameter = The site must be hosted on an NX controller, and the configuration file must be specified in the Netlinx code.
- config=roomID;  The Site must be hosted on an NX Controller, but the configuration file will be found at assets/configuration/roomID.configuration.json;   This is the fastest loading time when hosted on an NX Controller 
- room=roomID; The site can be hosted on any capable web host, and is looking for configuration and controller located at roomID.configuration.json and roomID.controller.json

Examples:

- http://192.168.1.100:8080/web/ui/41100/home/#!/main
- http://192.168.1.100:8080/web/ui/41100/home/#!/main?config=einstein
- http://localhost:63342/index.html?#!/main?room=einstein

## Color/CSS Customization

Relevant Theme colors can be found in the app-theme.min.css file.  The variables are used twice, once for light and once for dark mode:

[data-bs-theme=light] { 

--amx-body-bg: #fafbfe;

--bs-body-color: #838c96;

--bs-body-color-rgb: rgb(131, 140, 150);

--amx-white: #fff;

...

}

[data-bs-theme=dark] {

--amx-body-bg: #343a40;

--bs-body-color: #aab8c5;

--bs-body-color-rgb: rgb(170, 184, 197);

--amx-white: #fff;

...

}

## Packaging for Netlinx

The contents of the site are included in the gui.zip file.  If updates are made, then the new material needs to be updated/added to the gui.zip > app folder 
