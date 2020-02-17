## Google sign

# official website
https://github.com/react-native-community/google-signin

# create a project in firebase 
link: https://console.firebase.google.com/u/0/

# create android project
`` package name find at android/app/src/main/AndroidManifest.xml ``
example :
`` package="com.rngooglelogindemo ``
add all the dependience to the project
# go to `` android/build.gradel`` and below code

`` buildscript{    
    ext{
        .....
googlePlayServicesAuthVersion = "16.0.1" // added for google sign in
    }
} ``
`` dependencies{
    ....
classpath 'com.google.gms:google-services:4.3.3' // added for google sign
} 
``
# go to `` android/app/build.gradel`` and below code
`` apply plugin: 'com.google.gms.google-services' ``

`` dependencies{
    ...
     implementation 'com.google.firebase:firebase-analytics:17.2.2' // added for google login
}
``
# download the google-services.json 
pase the downloaded file to ``android/app``

# generate the SHA1 key for debug app 
go to path `` cd android/app `` and run below command to get SHA1 key
`` keytool -list -v -keystore debug.keystore -alias androiddebugkey -storepass android -keypass android ``
# for release key
Note: run the delow command where you have kept your release key 
To genearate the release key run the below command
`` keytool -genkeypair -v -keystore my-upload-key.keystore -alias my-key-alias -keyalg RSA -keysize 2048 -validity 10000 ``
`` keytool -list -v -keystore my-upload-key.keystore -alias my-key-alias ``
`` keytool -list -v -keystore {keystore_name} -alias {alias_name}``

# enable the google sign from project authin
