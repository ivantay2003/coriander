# Coriander
Selenium Webdriver and Appium extension module framework - this combines some functions of webdriver / appium and include some other functions. 

This is created in 2018 June. Selenoid is part of Coriander where it focus on gestures / UI interactions for common web and mobile usages.


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

void androidSwipe(AppiumDriver <AndroidElement> driver, int startx, int starty, int endx,int endy,Duration duration)

<br><br>
Android scroll down

void androidScrollDown( int startX, int startY,int xOffset, int yOffset )

<br><br>
Android - Find UI by xpath

boolean androidScrollUIUntilFindXPath(By xpath, int NumberOfScrolls)


## iOS gesture
<br><br>
iOS navigate back

void iOSNavigateBack ()

<br><br>
iOs move direction. move can be "left" , "right"

void iOSHorizontalScroll(String move)

<br><br>
iOS Swipe scroll down

void iOSSwipeScroll (IOSDriver <IOSElement> driver, WebElement element, int xOffset, int yOffset)

<br><br>
iOS double tap on element

iOSDoubleTap (IOSElement element)

<br><br>
iOS double tap on x , y

iOSDoubleTap (float x, float y)


<br><br>
iOS single tap on element

void iOSTap (IOSElement element)

<br><br>
iOS single tap on x, y coordinates

void  iOSTap (float x, float y)

<br><br>
iOS two finger tap on Element

void  iOSTwoFingersTap (IOSElement element)

<br><br>
iOS general two finger tap

void  iOSTwoFingersTap ()

<br><br>
iOS drag and drop

void iOSDragAndDrop (float x1, float y1, float x2, float y2, IOSElement element)

<br><br>
iOS PickelWheel

void iOSPickerWheel (IOSElement element, String order , float offset)


## Web 
<br><br>
Web Scroll up or down

void webScroll ( int endx , int endy)

<br><br>
Web search a string in list box , click and. Returns false if cannot find

boolean webClickDropdown(List <WebElement> elems, String searchString)
	
<br><br>
Web find element in second level of iFrame 

WebElement findElementInSecondLeveliFrame (By by)

<br><br>
Web switch to another tab in browser 

void webSwitchTab (boolean closeOriginalTab)

<br><br>

Web select dropdrown and click the successful search string element

webClickDropdown(List <WebElement> elems, String searchString)
	
<br><br>
Web Use action to move to element and click

void clickAction (By by)

<br><br>



# General usage
<br><br>
There are a several public properties under this. But I am testing it and expanding it. Will document them here when they passed my tests


<br><br>
Web / Mobile - Check that it is visible / presence before clicking

void clickElement (By by)

<br><br>
Web / Mobile - Check that it is visible / presence before sending text. Will clear text before sending

void sendKeys (By by, String text) 

<br><br>
Web / Mobile - Check that it is visible / presence before sending text. Will clear text before sending. Use this is sendKeys do not work

void setValue (By by, String text)

<br><br>
Web / Mobile - Check that it is visible / presence before sending text. The send keys do not include enter like sendKeys()

void sendKeysNoEnter (By by, String text)

<br><br>
Web / Mobile - Get element text. This will also check for presence before execution

public String getElementText (By by)

<br><br>
Web / Mobile - Explicit wait Presence. Return true if found. False otherwise

public boolean isPresence(By by)

<br><br>
Web / Mobile - Explicit wait clickable. Return true if found. False otherwise

public boolean isClickable(By by)

<br><br>
Web / Mobile - Explicit wait visible. Return true if found. False otherwise

public boolean isVisible (By by)

<br><br>
Web / Mobile - Explicit wait invisibility. Return true if found. False otherwise

public boolean isInvisible (By by)

<br><br>
Web / Mobile - Explicit wait by XPath string. Return true if found. False otherwise

public boolean isPresenceXPath (String xpath_element)

<br><br>

 
