# Coriander
Selenium Webdriver and Appium extension module framework - this combines some functions of webdriver / appium and extend  other functions. 

This is created in 2018 June, updated regularly as I work along different projects. Selenoid is part of Coriander where it focus on gestures / UI interactions for common web and mobile usages.


_Setup (Android / iOS / Webdriver)_ 

selenoid sel = new selenoid (String jsonFile);

jsonFile contains the desired capabilities 



Example of usage
<br><br>

```
public AppiumDriver<AndroidElement> getAndroidDriver (){

		  selenoid sel = new selenoid (String jsonFile);
		  
		  String jsonFile = "MyApp.json"
		  
		 return  (AppiumDriver<AndroidElement>) sel.desiredCapabilitiesConfig(jsonFile, DriverType.Android_Native);
	}
 ```
 <br><br>
 DriverType . This are the enums for DriverTypes currently
 ```
public enum DriverType {

	Android_Native , iOS_Native , Web_Chrome , Web_Firefox 
}
```
<br><br>
You may use either one in Desired Capabilities

<br><br><br>
Example of JSON file
```
{
"deviceName": "iPhone 11",
"platformName": "IOS",
"automationName": "XCuiTest",
"platformVersion": "13.1",
"app": "/Users/Download//UICatalog.app",
"noReset": "true",
"forceMjsonwp": "true",    
}

```

# Gestures usage


## Android Gesture
<br><br>
Android Navigate back button

void androidNavigateBack ()

<br><br>
Android Scroll to UI Text

void androidScrollUIAutomatorText(String text)

<br><br>
Android Swipe - Swipe left / right / up / down

_void androidSwipe(AppiumDriver <AndroidElement> driver, int startx, int starty, int endx,int endy,Duration duration)_

<br><br>
Android scroll down

_void androidScrollDown( int startX, int startY,int xOffset, int yOffset )_

<br><br>
Android - Find UI by xpath

_boolean androidScrollUIUntilFindXPath(By xpath, int NumberOfScrolls)_


## iOS gesture
<br><br>
iOS navigate back

_void iOSNavigateBack ()_

<br><br>
iOs move direction. move can be "left" , "right"

_void iOSHorizontalScroll(String move)_

<br><br>
iOS Swipe scroll down

_void iOSSwipeScroll (IOSDriver <IOSElement> driver, WebElement element, int xOffset, int yOffset)_

<br><br>
iOS double tap on element

_iOSDoubleTap (IOSElement element)_

<br><br>
iOS double tap on x , y

_iOSDoubleTap (float x, float y)_


<br><br>
iOS single tap on element

_void iOSTap (IOSElement element)_

<br><br>
iOS single tap on x, y coordinates

_void  iOSTap (float x, float y)_

<br><br>
iOS two finger tap on Element

_void  iOSTwoFingersTap (IOSElement element)_

<br><br>
iOS general two finger tap

_void  iOSTwoFingersTap ()_

<br><br>
iOS drag and drop

_void iOSDragAndDrop (float x1, float y1, float x2, float y2, IOSElement element)_

<br><br>
iOS PickelWheel

_void iOSPickerWheel (IOSElement element, String order , float offset)_


## Web 
<br><br>
Web Scroll up or down

_void webScroll ( int endx , int endy)_

<br><br>
Web search a string in list box , click and. Returns false if cannot find

_boolean webClickDropdown(List <WebElement> elems, String searchString)_
	
<br><br>
Web find element in second level of iFrame 

_WebElement findElementInSecondLeveliFrame (By by)_

<br><br>
Web switch to another tab in browser 

_void webSwitchTab (boolean closeOriginalTab)_

<br><br>

Web select dropdrown and click the successful search string element

_webClickDropdown(List <WebElement> elems, String searchString)_
	
<br><br>
Web Use action to move to element and click

_void clickAction (By by)_

<br><br>



# General usage
<br><br>
There are a several public properties under this. But I am testing it and expanding it. Will document them here when they passed my tests


<br><br>
Web / Mobile - Check that it is visible / presence before clicking

_void clickElement (By by)_

<br><br>
Web / Mobile - Check that it is visible / presence before sending text. Will clear text before sending

_void sendKeys (By by, String text)_ 

<br><br>
Web / Mobile - Check that it is visible / presence before sending text. Will clear text before sending. Use this is sendKeys do not work

_void setValue (By by, String text)_

<br><br>
Web / Mobile - Check that it is visible / presence before sending text. The send keys do not include enter like sendKeys()

_void sendKeysNoEnter (By by, String text)_

<br><br>
Web / Mobile - Get element text. This will also check for presence before execution

_public String getElementText (By by)_

<br><br>
Web / Mobile - Explicit wait Presence. Return true if found. False otherwise

_public boolean isPresence(By by)_

<br><br>
Web / Mobile - Explicit wait clickable. Return true if found. False otherwise

_public boolean isClickable(By by)_

<br><br>
Web / Mobile - Explicit wait visible. Return true if found. False otherwise

_public boolean isVisible (By by)_

<br><br>
Web / Mobile - Explicit wait invisibility. Return true if found. False otherwise

_public boolean isInvisible (By by)_

<br><br>
Web / Mobile - Explicit wait by XPath string. Return true if found. False otherwise

_public boolean isPresenceXPath (String xpath_element)_

<br><br>

 
<br><br><br><br>
I can be contacted by [Linkedin](http://www.linkedln.ivantay.org) or Skype : *tay.phones* if you want more details
