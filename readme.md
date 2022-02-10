# Team Time
Complete documentation available here: https://www.sapdev.eu/team-time-fiori-map/


Joining a large multilocation team can be tricky, because you have to know what time is it at Your colleagues location. During communication with Your colleagues or scheduling a meeting etc. a fast insight can be really helpful.
Other hand if You are not challenged enough professionaly, then  You turn to fun programming in Your freetime to face some challenges and interesting topics. At least this is what I am doing to not loose joy of software development. At the same time this brings You a big benefit to gain experience in innovative areas.

## Solution

This sample app shows the Analytical Map map of SAPUI5 librariy can be used without live API key and connection to a geographical engine. In this case we used to draw local time at locations with labels showing Your colleague name. Let Your creativity fly, and imagine other useful solutions with this great control, like showing global incident maps with semantic colors (red, yellow) of locations and labels (because this is also possible), and so on.

### Keys of the solution

- Project generated with Easy UI5 Generator
- Used control sap.ui.vbm.AnalyticMap
- Offline Countries and regions for the map model/L0.json which are configured in Mainview.Controller.js ```JS AnalyticMap.GeoJSONURL = "model/L0.json";```
- Your colleagues can be configured in model/Buddies.json. under the Spot array used for the same aggregation of the map. Here two properties need to be emphasized.
  - pos:  you can select a location on google map for example and right click to get the coordinated in decimal degrees, but You have to swap, because on SAPs map longitude comes first, follwed by the longitude. The last number is always 0, just in case You do not want to go into space :).
  - the timeZone is just for informational purpose, we're rather more interested in the timeZoneJS. This is what You can actually use in JavaScript for conversions. Look at function ```onRecalcTime``` to see how the local time can be calculated and formatted. You will notice that not a great built-in support in plain JS for the timzones, but here I willingly wanted to ignore using third-party libraries like moment.

## Operation

  To get this up and running, You need a simple web server. I am using github.io. Look at at it [here](https://attilaberencsi.github.io/teamtimelive/)
