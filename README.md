# coriander
Selenium Webdriver and Appium extension module framework - this combines some functions of webdriver / appium and include some other functions. 


Setup (Android / iOS / Webdriver)

selenoid sel = new selenoid (String jsonFile);

jsonFile contains the desired capabilities 



Example of usage
public void getAndroidDriver (){
		config = new Configuration();
		
		  String jsonFile = "MyApp.json"
		  
		 AppiumDriver<AndroidElement> androidDriver =  (AppiumDriver<AndroidElement>) sel.desiredCapabilitiesConfig(jsonFile, DriverType.Android_Native);
	}
  
 DriverType 
public enum DriverType {

	Android_Native , iOS_Native , Web_Chrome , Web_Firefox 
}

You may use either one in Desired Capabilities



        

WebDriver Wait
