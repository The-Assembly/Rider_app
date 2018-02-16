# Rider_app

Follow the steps to create a ride sharing app both for the passenger and driver. </br> 
To view the presenation slides, click slides </br> 

<b> PART 0 - Prerequisites </b>  

STEP 1: Download android studio and make sure you have the right tools needed as mentioned below:
![Alt text](https://d2mxuefqeaa7sj.cloudfront.net/s_6E04D0395F3E9633E1AA8A9CFF9F8EA297AF4AA1392D072366B2CFB9DE43A3C7_1500610476380_Screen+Shot+2017-07-20+at+3.34.11+PM.png "Optional Title") 

![Alt text](https://blog.pusher.com/wp-content/uploads/2017/08/creating-ride-booking-app-react-native-pusher-sdk-tools.png
 "Optional Title")  
 
 STEP 2: <b>Installing dependencies</b> </br>

WINDOWS USER: </br>
a. Open an Administrator Command Prompt (right click Command Prompt and select "Run as Administrator"), then run the following command: 
```
choco install -y nodejs.install python2 jdk8 
``` 

b. Install the React Native command line interface: 
```
npm install -g react-native-cli 
```

MAC OS USERS: </br>
a. Run the following commands in a Terminal after installing Homebrew:  
```
brew install node
brew install watchman
``` 

b. Install the React Native command line interface:  
```
npm install -g react-native-cli
``` 
c. React Native requires a recent version of the Java SE Development Kit (JDK). Download and install JDK 8 or newer if needed. http://www.oracle.com/technetwork/java/javase/downloads/jdk8-downloads-2133151.html


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

STEP 5: Copy the App.js file from the Driver folder and replace with the existing one (make sure to change the google maps API key). Copy the helper.js file to the grabDriver folder. 

STEP 6: Run the app using: 
```
react-native run-android 
``` 

<b>SOLUTIONS - TO SOME ERRORS THAT MIGHT OCCUR</b>  

1. remove @override from
C:\Users\The Assembly\passenger\node_modules\react-native-google-place-picker\android\src\main\java\com\reactlibrary\RNGooglePlacePickerPackage.java:20: --> remove the @override from the package and module file at line 20

2. Could not find or load main class org.gradle.wrapper.GradleWrapperMain react native - replace android/gradle/wrapper/gradle-wrapper.jar file
 /java.util.concurrent.ExecutionException: com.android.ide.common.process.ProcessException: - replace resources file in android 
 
3. Set JAVA_HOME to jdk path for environment variables
http://www.oracle.com/technetwork/java/javase/downloads/jdk8-downloads-2133151.html

4. Set ANDROID_HOME to android sdk path (get from the sdk manager) 

5. Could not delete path.. - cd android && ./gradlew clean or just gradlew clean
 / looking for index.android.js : npm start -- --reset-cache and reopen the terminal
if not then add the sdk_path/tools and sdk_path/platform-tools to path  

6. cannot find symbol new MapsPackage() in MainApplication --> You need to add import com.airbnb.android.react.maps.MapsPackage; to your MainApplication.java file. 

<b> PART 3 - Creating the Passenger side app 
 
 STEP 1: Go ahead and create a new app: 
 ```
 react-native init grabClone 
 ```
 
 STEP 2: You’d also need to install the same libraries as the driver app plus a couple more: 
 ```
 npm i react-native-google-places --save
 
react-native link react-native-google-places

 npm install --save pusher-js react-native-geocoding github:geordasche/react-native-google-place-picker react-native-loading-spinner-overlay react-native-maps 
 ``` 
 
 STEP 3: 
