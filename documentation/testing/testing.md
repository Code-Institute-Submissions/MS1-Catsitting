# **Testing - Katsit London**

Testing has been an on-going process during the coding stage of the project with further tests conducted toward the end on user stories, accessibility as well as html & css validation.

# Issues and solution during development process 

## Navigation 

Issue | Solution 
------------ | -------------
After inserting the links to the navigation, part of the content was hidden under the fixed navigation bar | The solution was to create fixed invisible anchors positioned above the start of each section, as per suggestion of [Caktus Group blog post](https://www.caktusgroup.com/blog/2017/10/23/css-tip-fixed-headers-and-section-anchors).
When navigating to a section of the website, the link in the navigation didn’t show as active. | After browsing bootstrap library, the solution was to implement [bootstrap spyscroll](https://getbootstrap.com/docs/4.5/components/scrollspy/). 
Once collapsed, the menu did not collapse back when clicking on menu items. | This was the most challenging issue during development. The solution was to insert data-toggle="collapse" data-target=".navbar-collapse.show" in navigation items as suggested in this [stack overflow post](https://stackoverflow.com/questions/42401606/how-to-hide-collapsible-bootstrap-4-navbar-on-click).
Navigation menu needed to expand at a different breakpoint than those offered as part of the bootstrap library. | Using Google Inspect, I was able to create a media queries for desired breakpoint and recreate the different elements required for navbar-expand to work. 

## Toggle button 

Issue | Solution 
------------ | -------------
Using Google inspect, I did not seem able to target the element to style the toggle button. | The solution was to replace the bootstrap default toggle button by a Font Awsome icon as suggested by [this stack overflow post](https://stackoverflow.com/questions/42586729/bootstrap-4-change-hamburger-toggler-color)

## Jumbotron - font-size

Issue | Solution 
------------ | -------------
Responsive font size such as %, em or rem pretty much resulted in the text to be out of proportion on small or big screens. | Solution was to “clamp” the font size between a minimum and maximum value, as suggested in this post from [css-trick](https://css-tricks.com/how-do-you-do-max-font-size-in-css/)

## Paddings 

Issue | Solution 
------------ | -------------
As the website was designed for mobile first, spacing was an issue on larger screens and the different sectionS of the website needed to occupy more space for better balance. | After some research, responsive paddings were applied at different breakpoints using the clamp function as suggested in this [stack overflow post](https://stackoverflow.com/questions/38078957/can-we-define-min-margin-and-max-margin-max-padding-and-min-padding-in-css/38079002).

## Background image and i-frame

Issue | Solution 
------------ | -------------
The background image in about me section and i-frame of embedded map did not display properly on small screens when occupying the full width. | The solution was in the case of the background image to apply a vmin function to keep the size balanced with the container above. For the frame, a minimum height was applied, so the content of the map displayed properly and tools of the map did not interfere with the content on the map.


# Testing user stories 

- ### **Introduction**
    The testing of  User Stories is set on the user’s journey across the website and covers interactive elements, as well as the responsiveness of the website across different platforms and browsers.User stories were tested manually on the following devices and browsers:
    - Devices:  Iphone XR, Samsung S10, Ipad,  MacBook Pro and iMac
    - Browsers: Safari, firefox and Chrome  
    
- ### **As a first time visitor, I want a responsive website so that I can view the website across different devices.**

    **T01 - Acceptance criteria**  
    - When I visit the website using my device, all content is visible and visual elements are displayed proportionally,  

        **Issues:**   
        - Responsive paddings were not displayed on tablets
        - Hero image covering more than viewport heights on mobile, resulting in the jumbotron text not being fully visible and centered, due to top and bottom menus on devices
        - Responsive fonts style in jumbotron text not applied on tablets and mobile
        - Phone number links automatically activated on iphones and ipad
        - Hero image appeared quite slow to upload
        - Some balance issues on very big screens 
        
        **Fix**
        - Responsive fonts and paddings were adjusted using a different css function. 
        - Additional media queries for landscape screens were set to adjust the hero image and jumbotron text
        - A meta data was added in the header to remove automatic links of phone numbers
        - Maximum height for the hero image was set to -webkit-fill-available so that it doesn’t fill more than the viewport height on mobile. 
        - Background image size was compressed to optimise performance. 
        - Body was set to a maximum  width of 2000px and media queries for medium screens were adjusted so that there’s a better balance on medium, large and extra large screens.

    **Result after fixes: PASS**

    **T02 - Acceptance criteria**
    - When I use a small screen or,
    - When I resize my screen and the menu becomes too large, the navigation bar collapses and,
    - When the navigation is collapsed, a toggler button is displayed to right of the header, and
    - When I click on the toggler button, a vertical menu is displayed,
    - When I click again on the toggler button, the vertical menu collapses back. 
    - When the vertical menu is displayed and I click on any items, the page scrolls to the relevant section and the menu will collapse back.  

    **Result: PASS**
 
- ### **As a first time visitor, I want to be able to easily navigate across the website so that I can quickly find information.**
 
    **T03 - Acceptance criteria** 
    - When I scroll to any section of the website, the navigation remains fixed on top of the page and my position on the page is made clear by the relevant link changing appearance (white bold) in the navigation bar. 
    - When I click on a menu item in the navigation bar, the page scrolls to the top of the relevant section of the webpage without spacing or content being covered by the navigation bar.
    
    **Result: PASS**

- ### **As a first time visitor, I want to read about the company's services so that I can assess whether they fit my needs / As a first time visitor, I want to look at prices so that I can check whether I can afford their services.**
 
    **TO4 - Acceptance criteria**
    - when I click on the menu item “services” in the navigation bar, the page scrolls to the “services” section of the website.
    - when I view / scroll to the “services” section, an introduction and a list of items included in the services are displayed as well as three text boxes showing pricing information laid out on top of different images, and
    - when I scroll at the bottom of the section, a “contact-us” button is displayed,
    - when I hover over the button, its appearance changes from green to orange. 
    - when I click on the button, the page scrolls to the “contact us” section. 
 
    **Result: PASS**

- ### **As a returning visitor, I want to read customer testimonials so that I can assess if the company is reliable and professional.**
 
    **TO5 - Acceptance criteria**
    - when I click on the menu item “testimonials” in the navigation bar, the page scrolls to the “testimonials” section of the website.
    - When I view / scroll to the “testimonials section”, a carousel with 2 side buttons and a dotted indicator displays an image, a name and text containing the customer recommendations in quotes.
    - When I hover on either side buttons, the buttons appearance changes (to brown) and,
    - When I click on the right button, the carousel moves one slide to the right,
    - When I click on the left button, the carousel moves one slide to the left, and
    - When I click on one of the dotted indicators, the first slide to be displayed is relevant to the position on the dotter indicator. 

    **Result: PASS**
 
- ### **As a returning visitor, I want to read more about the company so that I can assess its credentials, professionalism and cat friendliness.**
 
    **T06 - Acceptance criteria** 
    - when I click on the menu item “credentials” in the navigation bar, the page scrolls to the “credentials” section of the website.
    - When I view / scroll to the testimonials section, text and a background image are visible and displayed responsively.  

    **Result: PASS**
 
- ### **As a returning visitor, I want to access contact options so that I can reach the company for further queries.**
 
    **T07 - Acceptance criteria**
    - when I click on the menu item “contact us” in the navigation bar, the page scrolls to the “contact us” section of the website, 
    - when I view or scroll to the “contact us” section, contact details with a phone number, an email address and list of social media accounts is displayed as well as a contact form containing “full name”, “email address”, “subject” and “message” fields,

    **Result: PASS**
    
    **T08 - Acceptance criteria - Form valid path**
    - when I enter my name in the “full name” field, and
    - when I enter a valid email address in the “email” field and,
    - when I go to the subject field, I can keep the existing selection “general queries” or select “Arrange a meet & greet” and,
    - when I enter a message in the “message field” and,
    - when I click submit, I am brought back to the top of the page (as the form is not linked with any server)

    **Result: PASS**
    
    **T09 - Acceptance criteria - Form invalid path**
    - when I enter an invalid email address and when I click submit, a message prompts me to enter a valid email address. 
    - when I leave the “full name” field empty and/or 
    - when I leave the “email” field empty and/or
    - when I leave the “message” field empty and/or
    - when I click submit, a message will appear to prompt me to enter the required fields.

    **Issue:** 
    - No message appears when the message field is empty.

    **Fix:** 
    - Add required to text area element 

    **Result after fixes: PASS**
 
    **T10 - Acceptance criteria**
    - when I scroll to the footer of the webpage, company contact details with a phone number and an email address are displayed

    **Result: PASS**
 
- ### **As a returning visitor,I want to view the areas where the company operates so that I can check that they provide services where I live.**
 
    **T11 - Acceptance criteria**
    - when I click on the menu item “area we cover” in the navigation bar, the page scrolls to the section “Area we cover” of the website.
    - when I view / scroll to the “area we cover” section, a list of areas where the business operates is displayed responsively.
    - when I view the “area we cover” section, a map with a designated zone is displayed and I can zoom in and out, as well as searching my postcode.(the zoom and searching option are third party functionalities)
    
    **Result: PASS**

- ### **As a frequent visitor, I want to quickly access the company social media account so that I can further check their credentials.**
 
    **T12 - Acceptance criteria**
    - when I scroll to the footer of the webpage, icons representing facebook, twitter and instagram are displayed and,
    - when I hover over one of the icons, the icon changes in appearance (grow),
    - when I click on one of the icons, I am redirected to the right website in a new tab (ex. Facebook icon redirects to www.facebook.com.).
    
    **Result: PASS**

- ### **As a frequent visitor, I want to contact the company so that I can arrange a meet & greet.**
 
    **T13 - Acceptance criteria** 
    - When I land on the website, a hero image, jumbotron text and a “contact” us button are displayed responsively,
    - When I hover over the contact us button, it changes in appearance from green to orange.
    - When I click on the “contact us” button, the page scroll the “contact us” section, 
    
    **Result: PASS**

    **T08 - Acceptance criteria - Form valid path**  
    - when I view or scroll to the “contact us” section, contact details with a phone number, an email address and a list social media accounts is displayed, as well as a contact form containing “full name”, “email address”, “subject” and “message” fields, 
    - when I enter my name in the “full name” field, and
    - when I enter a valid email address in the “email” field and,
    - when I go to the subject field, I can select “Arrange a meet & greet” and,
    - when I enter a message in the “message” field and,
    - when I click submit, I am brought back to the top of the page (as the form is not linked with any server)
       
     **Result: PASS**

    **T09 - Acceptance criteria - Form invalid path**  
    - when I enter an invalid “email” address and when I click submit, a message prompts me to enter a valid address. 
    - when I leave the “full name” field empty and/or 
    - when I leave the “email” field empty and/or
    - when I leave the “message” field empty and/or
    - when I click submit, a message will appear to prompt me to enter the required fields  
 
    **Result: PASS (issue resolved earlier)**

    **T14 - Acceptance criteria**
    - when I scroll to the footer of the webpage, the company contact details with a phone number and email address are displayed.  

    **Result: PASS**

# Testing user stories 

 Wave evaluation report was used on the website to assess its accessibility. The report showed the following issues:  

 Initial report can be found [here](documentation/testing/reports/waveinitial.jpg)  

![Wave initial report](/workspace/MS1-Catsitting/documentation/testing/reports/waveinitial.jpg)


 - ### **Errors:**  
   - Contrast on buttons : Change color from to #078847 even if it meant compromising slightly the design
   - Missing aria-labels on links: Add aria-labels on links and aria-hidden is true to icons as suggested by [Font Awesome] (https://fontawesome.com/how-to-use/on-the-web/other-topics/accessibility)

 - ### **Alerts:**
    - Semantics: Change headings where necessary and apply heading style to classes  as suggested in this post from [Solodev](https://www.solodev.com/blog/web-design/how-to-adjust-header-styles-with-css-and-bootstrap.stml)
    - Text align: Remove text align  
    - Not sufficient alt text for the logo: Include additional description
    - Broken link for the logo: Change logo src to #home

Wave accessibility final report can be found [here](documentation/testing/reports/wavefinal.jpg).  

![Wave final report](/workspace/MS1-Catsitting/documentation/testing/reports/wavefinal.jpg)


# Google lighthouse

Main action taken to improve performance:
- Compress images using tinyjpg 
- Move scripts to bottom from header to the bottom of the page 

/*Include image report*/



