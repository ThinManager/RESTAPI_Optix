This repo includes a modified Optix Boiler Demo application that includes examples of calling the ThinManager REST API, including Logix PinPoint.

There is a Model folder called ThinManager that includes a number of variables used by the project.  You can specify the default IP address of the ThinManager Server (apiIPAddress), the default port number used by the ThinManager API (apiPortNumber), as well as the API key (apiKey).  Additionally, the ThinManager terminals to be exposed for management through Optix are included in the Terminals object.

The ThinManager REST API endpoints that are called in the NetLogic (ThinManagerAPINetLogic):

1. /api/system/versions
2. /api/system/synchronization/status
3. /api/system/licensing/mode
4. /api/system/licensing/status
5. /api/terminals/terminal/#/status
6. /api/terminals/terminal/#/calibrate
7. /api/terminals/terminal/#/disable
8. /api/terminals/terminal/#/enable
9. /api/terminals/terminal/#/poweroff
10. /api/terminals/terminal/#/restart
11. /api/terminals/terminal/#/reboot
12. /api/events/post

Almost all of the configurable elements of ThinManager are exposed through the REST API.  Once you have enabled the REST API through the ThinManager Server Configuration Wizard, you can explore all of the end points via https://ThinManagerIP:Port/api/documentation with the built-in Swagger User Interface.  This demo application requires that you create an HTTPS Server Certificate in ThinManager, which can then be imported into the machine where the Optix application is running as a Trusted Root Certification Authority.  Certificates can be created in ThinManager from the Manage tab in the Admin Console by clicking the TLS Certificate icon.

This Optix demo application also demonstrates how to make Logix PinPoint calls through the ThinManager REST API from Optix through the existing AlarmsPage.  The TMLogixPinPoint NetLogic utilizes the ACD file included in the ProjectFiles/LogixCode folder of the uploaded Optix application.  The C# code is looking for the Oven_and_BoilerDemo_L85_Echo.ACD file in a c:\Lab Files folder.

