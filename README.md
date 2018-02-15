# Rider_app

Follow the steps to create a ride sharing app both for the passenger and driver. </br> 
To view the presenation slides, click slides </br> 

<b> PART 1 - Creating the driver side app </b>  

STEP 1: Setting up the environment:  
   a. To create the folder for the app, run the command in the terminal:
``` 
react-native init grabDriver
```   

   b. Installing the nescessary dependencies: 
``` 
npm install --save pusher-js react-native-maps react-native-geocoding
```
```
react-native link react-native-maps
```  

STEP 2: Create a Google project, get an API key from the [ a Google developer console](https://console.cloud.google.com/), and enable the Google Maps Android API,  Google Maps Geocoding API, Google Places for Android API.   
    
   a. Open the android\app\src\main\AndroidManifest.xml file in your project directory. Under the <application> tag, add a <meta-data> containing the API key.  
   
    <application>
        <meta-data
          android:name="com.google.android.geo.API_KEY"
          android:value="YOUR GOOGLE SERVER API KEY"/>
    </application>

STEP 3: Add the permissions in the same file above the <application>: 
``` 
    <uses-permission android:name="android.permission.ACCESS_NETWORK_STATE"/>
    <uses-permission android:name="android.permission.ACCESS_FINE_LOCATION" /> 
```
 
 
 STEP 4: Ensure the android studio sdk version is 23: 
 
 ```
  <uses-sdk
            android:minSdkVersion="16"
            android:targetSdkVersion="23" />
```
