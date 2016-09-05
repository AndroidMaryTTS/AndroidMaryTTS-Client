# Android MaryTTS-Client
Android TTS client application based on MaryTTS, using gradle and maven repository centers. Actually support only ENG language but in feature will other ones. Can add your own hmm based voice as speaker with using [Marytts Andorid](https://github.com/AndroidMaryTTS/AndroidMaryTTS).

If you want to quicky check app on mobile device, you can simply download it from [Play Store](https://play.google.com/store/apps/details?id=com.marytts.android).

#How to use: 

1) Add below script to build.gradle(app) file : 

```groovy
  android {
  	    defaultConfig {
        		multiDexEnabled true
        		packagingOptions {
        		    exclude 'META-INF/LICENSE.txt'
        		    exclude 'META-INF/NOTICE.txt'
        		    exclude 'META-INF/LICENSE'
        		    exclude 'META-INF/NOTICE'
        		    exclude 'META-INF/DEPENDENCIES'
  	     	      }
  	    }
  }
```

2) Also, other one to build.gradle (module) where tts will use : 

```groovy
	dependencies {
	    compile 'com.marytts.android:marylib:1.0.1'
	}
```

3) Load code marytts-android voise and language models on startup your project. It takes a few seconds. But in future will be so fast : 

```java
	MaryLink.load(Context context); 
```

4) Last one to speak or stop what you write : 

```java
 	MaryLink.getInstance().startTTS(text);
	
	MaryLink.getInstance().stopTTS();
```
