<p align="center">
<img src="https://github.com/user-attachments/assets/bf9888ea-4247-412f-bb4f-fef69e679970" alt="DriverShift" width="300" height="300">
</p>

# <p align="center"> DriverShift Design Document </p>


This application is designed to replace the Ares spreadsheet for endurance race scheduling. It will have upto 12 slots for racing drivers to register for the event. It will have specific events listed as well as a custom even for non-iRacing special events.

## Name ideas:

- PitCrew
- RaceRoster
- PitStopPlanner
- Driver Shift (DS) *current leader
- RaceReady

## Planning:

## Requirements
### App Requirements in no particular order:

#### Race information
- Race duration (3hr / 6hr / 12hr / 24hr)
- Race time
- Stint time
- Lap time (Average for all drivers)
  - Wet lap time
    - Dry lap time
- Fuel per stint (Average for all drivers)
- Race start time
- Driver local time
    - GMT time
    - Time of day (ToD) time
- Race end time
- Session start time
- Quali start time
    - Quali duration
- Pit time duration
    - Full fuel no tyres
    - Full fuel all tyres
- Tyre change duration
- Total race laps (total time / average lap time)
- Car class
- Car model
    - Fuel tank size
- Race delta (+ / -)
#
#### Driver information
  - Number of drivers
  - Driver Name
  - Driver time zone (GMT offset)
  - Driver availability (Single stint blocks) 
  - Driver lap time (Average)
  - Driver fuel per lap (Average)
  - Driver fuel per stint (Average)
  - Driver fair share requirement
# 
#### App requirements
- Driver colour throughout
- multiple tabs/pages
  - Overview
      - Race information
  - Driver & Team information
      - Driver information
  - Schedule
  - Roster
  - Driver availability
- Pit start and end buttons (mid stint)
    - Time runs +5 secs over expect pit duration, now add to damage time
- Auto update stints
    - Stint end button
- Auto update race delta from pit duration

#
#### User Requirements:

- User must be able to enter their prefered name (full name, nickname ect) in a single text box.
- The user must be able to easily input all the driver info (lap time, fuel usage ect) into the app
- 

# Behind the scenes

## What to use?
Either C# or Java, leaning towards C#

Using either WPF, WinUI 3 or MAUI to create the UI as the backend can be done with C# and looks modern enough. Need to check if it can meet all the requirements above.

WinUI 3 seems to have a few teething issues, but seems to have enough users that have solved these issues, or workarounds. It uses Win10/11's more modern UI design which is more appealing. 

[Link to WinUI 3 setup info](https://learn.microsoft.com/en-us/windows/apps/windows-app-sdk/set-up-your-development-environment?tabs=cs-vs-community%2Ccpp-vs-community%2Cvs-2022-17-1-a%2Cvs-2022-17-1-b)
[Build your first WinUI 3 app](https://blogs.windows.com/windowsdeveloper/2022/01/28/build-your-first-winui-3-app-part-1/)


