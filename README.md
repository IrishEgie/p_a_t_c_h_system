# PATCH System
The PATCH System represents a solution that uses Artificial Intelligence (AI) to transform the way we navigate highways. At its core, the system employs AI algorithms to detect road potholes in real-time. While you're on the road, the system continuously scans the pavement ahead, instantly identifying potholes and potential hazards. If a pothole is detected, you receive immediate alerts, allowing you to adapt your driving and avoid these obstacles safely.

However, the PATCH System goes beyond alerts. It encourages active user participation. If you encounter a pothole that hasn't been reported, the system allows you to easily notify the community. Moreover, if road conditions change – for example, if a reported pothole gets repaired – users can update this information, ensuring the system remains accurate and up to date. The PATCH System promotes collective road safety efforts, resulting in safer highways for all. 

This system is designed and collaborated by BSCPE Students of Samar State University as a partial requirement in the completion of their capstone work.

## Developer Build Logs ##
### 1.0.13 Version Update - Stable - 06-30-2023
- Reports page:
    - Complete with list-to-grid view as well as a search feature for the pothole reports from various locations of the scope of the study.
    - Complete with reverese Geocoding API to view the address of the pothole report as well as in the reports creation page.  
- Notes:
    - Initial build version with fully functional reports page & navigation page with Firestore & Firebase storage capability as well as user account authentication service.
    - AI model is still to be integrated in the detection page as well as the Reports creation sub-pages.
### 1.0.14 Version Update - Stable - 07-02-2023

- Detection Page:
    - Added Camera functionality using the camera: ^0.10.5+2 flutter package.
    - Added Camera control functionality such as zoom & exposure
    - Added Tensorflow Lite platform for YOLOv8 model & YOLOv4, this uses the real-time object detection 
    on the tflite: ^1.1.2
    - Camera orientation & ratio is skewered expect fix on next update
### 1.0.15 Version Update - Unstable - 07-06-2023
- Detection Page
    - Fixed the camera resolution but causes instability when using the detection page, 
    immediate crash on high resolution plus real-time object detection.
    - Working Object detection with real-time updates via labels, no current bounding box present. 
    - Camera orientation is fixed & ratio is corrected, resolution is set to medium by default (to be fixed on next update)
- Reports Creation Page:
    - Added image detection on the reports creation page when an image is uploaded.
- Notes:    
    - Instance where upon loading of the detection page the app can crash.
### 1.0.16 Version Update - Unstable - 07-13-2023
- Reports Page:
    - Updated the UI: To be more consistent & readable
- Detection Page:
    - Switched to Google ML Kit (google_mlkit_object_detection: ^0.9.0), 
    Detection Page can now detect & capture potholes in realtime using MobileNetV2.
- Bugs: 
    - Navigation returns blank.
    - Reports page also returns blank in this version.
    - Firebase Reports page compatibiilty is unsuable
    - Firebase Authentication is unable to authenticate
    - Expect bug Fixes on next update
### 1.0.17 Version Update - Unstable - 07-17-2023 ==> 07-22-2023 
- Reports Page:
    - Updated the current pothole detection model (MobileNetV2)
- Notes: 
    - Blank Main Pages is still prominent
    - Firebase Firestore & Authentication bug is still prominent in some instances
### 1.0.18 Version Update - Stable - 07-23-2023 == 07-30-2023
- Optimization:
    - App is optimized, reduced overall size of the system from 281 MB down to 27 MB for better debugging & performance 
- Bug Fixes: 
    - Firebase Reports page compatibility is fixed
    - Firebase Authentication is now able to authenticate and use the app in its full functionality
- Notes: 
    - During Account Creation can sometimes skip & leave the user profile blank with only the email & username. 
### 1.0.19 Version Update - Stable - 08-23-2023
- UI:
    - You can now long press most buttons to see their function or description 
    - Updated most alert dialog to custom versions for consistent design
    - Updated the Detection page UI with location service 
- Detection Page:
    - Updated the Pothole Detection model 
### 1.0.20 Version Update - Stable - 08-28-2023
- UI:
    - Reworked the User account pages to have a different UI design, actions & interaction confirmations.
- Authentication:
    - User is now blocked from exiting the account creation page unless the fields of the form are completed.
### 1.0.21 Version Update - Stable - 08-31-2023
- UI:
    - Removed some extra animations for consistent animation features throughout the app.
- Reports Creation:
    - Added user confirmation for discarding of the pothole reports in the sub creation pages.
    - confirm_exit widget is added to app_components .
    - Added a null value to the Save report button for additional condition when saving .
    a pothole report ensuring that a pothole report is detected before saving to the system.
### 1.0.22 Version Update - Stable - 09-02-2023
- Notes: 
    - Re-Added the image capture feature in the Detection Page which was bugged out from versions 1.0.17 - 1.0.21.
### 1.0.23 Version Update - Stable - 09-07-2023
- Notes: 
    - Added a Terms & Conditions Page as well as updated the User Manual Page
    - Added a new widget called Confirm Acc as a confirmation when opening the Terms & Conditions from the create acc or login page
### 1.0.24 Version Update - Unstable - 09-18-2023
- Notes: 
    - Added Report Sharing via Published Web App of the Flutter App. This of course does not contain the AI Model when sharing the model, 
    merely the link of the app & report page. Update for specific site location. 
    - Added Report Downloading. Downloads the report information as well as some of the basic User Information of the Reporter from the Pothole Report as a Printable PDF.
    - Ordered the Pothole reports based on recency of the reports
- Bug Fixes:
    - Fixed the Stackoverflow bug on the reports page whenever passing the detection variable from the hosted pothole image detection.
    - Fixed the referencing bug, wherein whenever the user reports multiple potholes & tries to edit it, the app features a different report
    this causes incorrect referencing & edits or deletes on the selected pothole reports is difficult 
    - Fixed the black screen navigation bug whenever the user logs in to their account
### 1.0.25 Version Update - Stable - 09-24-2023 ==> 10-1-2023
- UI:
    - Added an error image & an empty list asset for the reports page
    - Added show bottom sheet action on marker tap on the navigation page to display the report details on the markers.
    - Added a location tracking button in the Navigation Page wherein the user can use the tracker to orient back to their current location, as well as a serve as a guide for auto-updating the map tracking while they are on the move.
- Auth: 
    - User can now freely change their Photos or Username compared to previous version
    - Created User Profile page is so that it is now a split page compared to the previous version where the edit user profile is just re-used
- Reports Page: 
    - - Added an archive section in the reports page to store pothole reports with a 'Fixed' status
- Notes: 
    - Added a disclaimer page for the nearby deployment of the PATCH system for use.
    - Increased the performance of the download report option significantly, by removing the backup of PDF to the Firebase
    - Added a periodic action wherein the Notification for Opening the Wifi & Location Permission pops up always even if the user doesn't load the 
    page to initialize the action

- Bug Fixes: 
    - Fixed the inconsistent reporting error where the user cannot post a pothole report even when the form is filled, 
    fixed by changing the detection variable input value to a specific value since the json value outputs an 'Unhandled variable' Error 
    - Fixed the Deleting report option to have a more accurate document deletion by passing the correct reference to the confirm delete alert dialog box
    - Fixed Authentication Bugs where the user cannot save changes when editing their User Profile
### 1.0.26 Version Update - Stable - 10-2 ==> 10-23-2023
- General: 
    - App bar changes to the non-main pages (Authentication pages, & Help pages) changed the background color from Primary Background to transparent for a general cleaner look
    - Added a shimmer effect for all the Collection Query in the Poll & Reports page.
    - Added a Poll Page which contains the the Flagged pothole reports for Archival. This contains the poll view containing the details of the Flagged Report as well as the number of votes. Note that the user that has voted on a flagged report cannot vote again in the same report.
    - Added a tutorial page after the Disclaimer notice after creating a user account.
    - Added an End Page when the PATCH System Application closes. 
- Detection Page:
    - Updated the Detection page with a higher accuracy Detection Model, MobileNetV2 140.224, Pothole Detection Model v5, with 90% training accuracy score.
- Help Pages
    - Added a jump function to the User Manual & the Terms & Condiitions pageview tab to skip directly to the pages, index in the table of content.
- Authentication Pages
    - UI: Removed the default App bars for a cleaner look
- Report Search
    - Updated the search function in the reports page by properly referencing the indexed document selected by the user.
    - Report can now be opened without the need for the reports page, this ensures transition neatness instead of navigating to another page.
    - User can now easily dismiss the search button by tapping outside the content area.
- Reports Archival Flag:
    - Added an Archival section wherein users can now flag a report if it is outdated or if the pothole has been fixed, which needs to be confirmed by multiple users before being removed from the Pothole Map
    - Added a checker to check if the document has already been flagged to prevent duplication in the Archival.
    - If a poll for Archival has reached 'x' amount of votes, the report will be updated & moved to Archived section which will remove the marker in the map
- Report Details
    - Added a background blur for the reports page
    - Added Animation for the new Report Details UI 
    - Centered the reports details with a general height of 75% to showcase the details of a report.
- Created a custom action that will filter nearby markers & show a snackbar whenever a pothole around 100 meters is nearby.
- Added a custom voiceline, AI Amy from Narakeet, to sound & alert the user when the device location is within a 100 meter radius from a pothole
- Bug Fixes: 
    - Fixed the persistent add report bug where the application would output a single double value instead of a list/array of double values, this causes a 
    bad element error, due to the missing list variable. This was fixed by creating a datatype & creating an app state basically utilizing the system's 
    memory to store the recent json response in the memory as a list type double but filtering the 1st most response of the highest confidence rating. 
    Then outputing this through the appstate confResponse. 
    - Fixed the black screen bug during track mode in the navigation page by removing the close all action when user is not within radius of a nearby pothole
    - Fixed the lag when switching between onPress state & onDoublePress state, on the user Track button by utilizing the loop action instead of Periodic action
    - Removed the double filtering to reduce lag in the navigation page Google Map load
