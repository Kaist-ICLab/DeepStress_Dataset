## Overview
This dataset was collected as part of the study titled: "DeepStress: Supporting Stressful Context Sensemaking in Personal Informatics Systems Using a Quasi-experimental Approach," which will be published in ACM CHI 2024 (to appear).
Over approximately six weeks, data were gathered from 24 university students with diverse academic backgrounds.
The dataset includes passively collected smartphone data (app usage behavior, GPS, physical activity) and participants' self-reported perceived stress levels. Detailed descriptions of each data type are provided below.

## Passive Data

### App Usage Event
*app_usage_event.csv*

When participants use a mobile application installed on their smartphones, the following information is automatically recorded:
* timestamp: The exact time an event related to a specific application occurred, recorded in Unix time and measured in milliseconds.
* packageName: The unique package name of the application.
* type: The type of usage event (e.g., ACTIVITY_RESUMED), which indicates the state change of a component. More details can be found at [UsageEvents.Event](https://developer.android.com/reference/android/app/usage/UsageEvents.Event).
* isSystemApp: Indicates whether the application is a system application, i.e., pre-installed on the device.
* isUpdatedSystemApp: Indicates whether the application is an updated system application.

### GPS
*location.csv*

The location of participants is collected using a GPS sensor, including the following information:
* timestamp: The exact time when the GPS data was collected, recorded in Unix time and measured in milliseconds.
* altitude, longitude, latitude: The altitude, longitude, and latitude values for a given coordinate. Note that these values are anonymized by adding random numbers to the original coordinates due to potential privacy issues.
* accuracy: The estimated horizontal accuracy radius in meters of this location at the 68th percentile confidence level. More details can be found at [getAccuracy](https://developer.android.com/reference/android/location/Location.html#getAccuracy()).
* speed: The speed at the time of the location measurement in meters per second. More details can be found at [getSpeed](https://developer.android.com/reference/android/location/Location.html#getSpeed()).

### Physical Activity
*physical_activity.csv, physical_activity_transition.csv*

* timestamp: The exact time when the physical activity data was collected, recorded in Unix time and measured in milliseconds.
* TILTING, UNDEFINED, IN_VEHICLE, ON_BICYCLE, ON_FOOT, WALKING, RUNNING, STILL: Each represents the detected physical activity from the smartphone, recorded by their confidence level. More details can be found at [DetectedActivity](https://developers.google.com/android/reference/com/google/android/gms/location/DetectedActivity)
* isEntered (in physical_activity_transition.csv): Indicates whether a specific physical activity type has commenced.

## Self-reported Data

### Stress Levels
*esm.csv*

* timestamp: The exact moment when the stress level was reported, recorded in Unix time and expressed in milliseconds.
* stress: The perceived stress level, rated on a 5-point Likert scale.
