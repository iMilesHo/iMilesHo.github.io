---
layout: page
title: IoT Home Sleep Better iOS APP
description: An iOS application for the IoT Home Sleep Better project.
img: assets/img/IoTAPP.png
importance: 2
category: fun
related_publications: false
---

# IOTHomeSleepBetter_iOSAPP

This is the repository for the SEP 769 project's iOS application. The primary aim of the app is to enhance sleep quality using IoT by providing functionalities ranging from user authentication to iOS HealthKit integration.

## Features:

- **User Authentication**: Secure sign-in process to protect user data and preferences.
- **Personal Data Management**: Allow users to manage and update their personal data within the app.
- **Dashboard of Collected Data**: Provides a visual representation of the collected data for users to review and analyze.
- **Remote Control of Smart Plug**: Users can remotely control the smart plug, turning devices on or off.
- **Sleep Quality Feedback**: After analyzing the data, the app provides feedback about the user's sleep quality.
- **iOS HealthKit Integration**: The app is integrated with iOS HealthKit to fetch and store health-related metrics.

## Demonstration:

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/hadwareOFIoT.png" title="Hardware" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    The hardware of the IoT Home Sleep Better project.
</div>

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/archtectureOfIoT.png" title="Hardware" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    The architecture of the IoT Home Sleep Better project.
</div>

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/IoTAPP.png" title="Hardware" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    The iOS application of the IoT Home Sleep Better project.
</div>

## Getting Started:

### Prerequisites:

- Xcode (latest version recommended)
- An iOS device running a supported version of iOS.
  
### Setup:

1. Clone this repository:
   ```bash
   git clone [repository-link]
   ```

2. Navigate to the project directory and pod:
   ```bash
   cd IOTHomeSleepBetter_iOSAPP
   pod install
   ```

3. Open the project in Xcode.

4. **Important**: The `GoogleService-Info.plist` and `Info.plist` are not included in this repository due to security concerns. Ensure you have your own versions of these files and add them to the project before attempting to build.

5. Build and run the project in Xcode.

## Contributing:

Contributions are welcome! Please ensure that you test any changes thoroughly before creating a pull request.


## Acknowledgements:

- Everyone who provided feedback and helped in testing.

