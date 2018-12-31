# Coriander
Selenium Webdriver and Appium extension module framework - this combines some functions of webdriver / appium and include some other functions. 

This is created in 2018 June. Selenoid is part of Coriander where it focus on abstraction for common web and mobile usages.


_Setup (Android / iOS / Webdriver)_ 

selenoid sel = new selenoid (String jsonFile);

jsonFile contains the desired capabilities 



Example of usage
<br><br>

```
public void getAndroidDriver (){

		  selenoid sel = new selenoid (String jsonFile);
		  
		  String jsonFile = "MyApp.json"
		  
		 AppiumDriver<AndroidElement> androidDriver =  (AppiumDriver<AndroidElement>) sel.desiredCapabilitiesConfig(jsonFile, DriverType.Android_Native);
	}
 ```
 DriverType 
public enum DriverType {

	Android_Native , iOS_Native , Web_Chrome , Web_Firefox 
}

You may use either one in Desired Capabilities


# Gestures usage


# Android Gesture
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


# Web 
<br><br>
Web Scroll up or down

void webScroll ( int endx , int endy)

<br><br>
Web search a string in list box , click and. Returns false if cannot find

boolean webClickDropdown(List <WebElement> elems, String searchString)
	
<br><br>
Web find element in second level of iFrame 

WebElement findElementInSecondLeveliFrame (By by)


# General usage
<br><br>
There are a several public properties under this. But I am testing it and expanding it. Will document them here when they passed my tests


<br><br>
Web / Mobile - Check that it is visible / presence before clicking

void clickElement (By by)

<br><br>
Web / Mobile - Check that it is visible / presence before sending text. Will clear text before sending

void sendKeys (By by, String text) 
 
