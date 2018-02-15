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

STEP 3: 



