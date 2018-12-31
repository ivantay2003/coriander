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


# Gestures usage

Android Navigate back button
void androidNavigateBack ()

Android Scroll to UI Text
void androidScrollUIAutomatorText(String text)

Android Swipe - Swipe left / right / up / down
void androidSwipe(AppiumDriver <AndroidElement> driver, int startx, int starty, int endx,int endy,Duration duration)
	
Android scroll down
void androidScrollDown( int startX, int startY,int xOffset, int yOffset )

Android - Find UI by xpath
boolean androidScrollUIUntilFindXPath(By xpath, int NumberOfScrolls)


## iOS gesture
iOS navigate back
void iOSNavigateBack ()

iOs move direction. move can be "left" , "right"
void iOSHorizontalScroll(String move)

iOS Swipe scroll down
void iOSSwipeScroll (IOSDriver <IOSElement> driver, WebElement element, int xOffset, int yOffset)

iOS double tap on element
iOSDoubleTap (IOSElement element)

iOS double tap on x , y
iOSDoubleTap (float x, float y)


WebDriver Wait
