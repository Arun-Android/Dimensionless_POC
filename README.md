# Quickstart: Recognize speech from a microphone in Java on Android

This sample demonstrates how to recognize speech with Java using the Speech SDK for Android.
See the [accompanying article](https://docs.microsoft.com/azure/cognitive-services/speech-service/quickstarts/speech-to-text-from-microphone?tabs=dotnet%2Cx-android%2Clinux%2Candroid%2Cwindowsinstall&pivots=programming-language-java) on the SDK documentation page which describes how to build this sample from scratch in Android Studio.

> **Note:**
> this sample is *not* for the Speech Devices SDK and the Roobo device.
> If you are looking for further information on these, visit the [Speech Devices SDK](https://docs.microsoft.com/azure/cognitive-services/speech-service/speech-devices-sdk) page.

## Prerequisites

* A subscription key for the Speech service. See [Try the speech service for free](https://docs.microsoft.com/azure/cognitive-services/speech-service/get-started).
* A PC (Windows, Linux, Mac) capable to run Android Studio.
* Version 3.1 of [Android Studio](https://developer.android.com/studio/).
* An ARM-based Android device (API 23: Android 6.0 Marshmallow or higher) [enabled for development](https://developer.android.com/studio/debug/dev-options) with a working microphone.

## Build 

> Note: more detailed step-by-step instructions are available [here](https://docs.microsoft.com/azure/cognitive-services/speech-service/quickstart-java-android).

* **By building this sample you will download the Microsoft Cognitive Services Speech SDK. By downloading you acknowledge its license, see [Speech SDK license agreement](https://aka.ms/csspeech/license201809).**
* [Download the sample code to your development PC.](/README.md#get-the-samples)
* Open this folder as a project in Android Studio.
* Edit the `MainActivity` source:
  * Replace the string `YourSubscriptionKey` with your own subscription key.
  * Replace the string `YourServiceRegion` with the service region of your subscription.
    For example, replace with `westus` if you are using the 30-day free trial subscription.
* Press Ctrl+F9, or select **Build** \> **Make Project**.


```java
// Initialize SpeechSDK and request required permissions.
try {
    // a unique number within the application to allow
    // correlating permission request responses with the request.
    int permissionRequestId = 5;

    // Request permissions needed for speech recognition
    ActivityCompat.requestPermissions(MainActivity.this, new String[]{RECORD_AUDIO, INTERNET}, permissionRequestId);
}
catch (Exception ex) {
    Log.e("SpeechSDK", "could not init sdk, " + ex.toString());
    recognizedTextView.setText("Could not initialize: " + ex.toString());
}
```
