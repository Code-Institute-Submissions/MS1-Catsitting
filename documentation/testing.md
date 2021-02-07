# **Testing - Katsit London**

Testing has been an on-going process during the coding stage of the project with further tests conducted toward the end on user stories, accessibility and performance as well as html & css validation.

# Issues and solution during development process 

## Navigation 

 - **Issue**: Part of the content was hidden under the fixed navigation bar.  

        Solution: The solution was to create fixed invisible anchors positioned above the start of each section, as per suggestion of [Caktus Group blog post](https://www.caktusgroup.com/blog/2017/10/23/css-tip-fixed-headers-and-section-anchors).
 
 - **Issue**: When navigating to a section of the website, the link in the navigation didn’t show as active.  

        Solution: After browsing bootstrap library, the solution was to implement [bootstrap spyscroll](https://getbootstrap.com/docs/4.5/components/scrollspy/).  

 - **Issue**: Once collapsed, the menu did not collapse back when clicking on menu items.  

        Solution: This was the most challenging issue during development. The solution was to insert data-toggle="collapse" data-target=".navbar-collapse.show" in navigation items as suggested in this [stack overflow post](https://stackoverflow.com/questions/42401606/how-to-hide-collapsible-bootstrap-4-navbar-on-click).
 
 - **Issue**: Navigation menu needed to expand at a different breakpoint than those offered as part of the bootstrap library.  

        Solution: Using Google Inspect, I was able to create a media queries for desired breakpoint and recreate the different elements required for navbar-expand to work. 
 
## Toggle button 

 - **Issue**: Using Google inspect, I did not seem able to target the element to style the toggle button.  

        Solution: The solution was to replace the bootstrap default toggle button by a Font Awsome icon as suggested by [this stack overflow post](https://stackoverflow.com/questions/42586729/bootstrap-4-change-hamburger-toggler-color)

## Jumbotron - font-size

   - **Issue**: Responsive font size such as %, em or rem pretty much resulted in the text to be out of proportion on small or big screens.  
   
            Solution: Solution was to “clamp” the font size between a minimum and maximum value, as suggested in this post from [css-trick](https://css-tricks.com/how-do-you-do-max-font-size-in-css/). This was then changed to a different css function during testing user stories.

## Paddings 

 - **Issue**: As the website was designed for mobile first, spacing was an issue on larger screens and the different sections of the website needed to occupy more space for better balance.  

        Solution: After some research, responsive paddings were applied at different breakpoints using the clamp function as suggested in this [stack overflow post](https://stackoverflow.com/questions/38078957/can-we-define-min-margin-and-max-margin-max-padding-and-min-padding-in-css/38079002). This was then changed to a different css function during testing user stories.

## Background image and i-frame

 - **Issue**: The background image in the "about me" section and the embedded map did not display properly on small screens when occupying the full width.  

        Solution: The solution was in the case of the background image to apply a vmin function to keep the size balanced with the container above. For the frame, a minimum height was applied, so the content of the map displayed properly.


# Testing user stories 

- ### **Introduction**
    The testing of  User Stories is set on the user’s journey across the website and covers interactive elements, as well as the responsiveness of the website across different platforms and browsers.
    
    User stories were tested manually on the following devices and browsers, in addition of Googe inspect and responsive viewer add-on:
    - Devices:  Iphone XR, Samsung S10, Ipad,  MacBook Pro and iMac
    - Browsers: Safari, firefox and Chrome  
    
- ### **As a first time visitor, I want a responsive website so that I can view the website across different devices.**

    - **<ins>T01 - Acceptance criteria</ins>**  

        - When I visit the website using my device, all content is visible and visual elements are displayed proportionally,  

          > **Issues:**   
          > - Responsive paddings were not displayed on tablets
          > - Hero image covering more than viewport heights on mobile, resulting in the jumbotron text not being fully visible and centered, due to top and bottom menus on devices
          > - Responsive font styles in jumbotron text not applied on tablets and mobile
          >  - Buttons on ipad text wrapping on 2 lines
          >  - Phone number links automatically activated on iphones and ipad
          >  - Hero image appeared quite slow to upload
          >  - Some balance issues on very big screens     
          >
          >  **Fix**
          >  - Responsive fonts and paddings were adjusted using a different css function. 
          >  - Additional media queries for landscape screens were set to adjust the hero image and jumbotron text
          >  - Add white-space: nowrap on button as suggested by this [stackoverflow post](https://stackoverflow.com/questions/12707317/ipad-breaks-button-text-into-two-separate-lines/12708061)
          >  - A meta data was added in the header to remove automatic links of phone numbers as suggested by this [blog post](https://n8finch.com/disable-phone-number-linking-ios-safari)
          >  - Maximum height for the hero image was set to -webkit-fill-available so that it doesn’t fill more than the viewport height on mobile as suggested in this [stack overflow post](https://stackoverflow.com/questions/37112218/css3-100vh-not-constant-in-mobile-browser)
          >  - Hero image's size was compressed to optimise performance. 
          >  - Body was set to a maximum  width of 2000px and media queries for medium screens were adjusted so that there’s a better balance on medium, large and extra large screens.

        **T01 Result after fixes: PASS**

    - **<ins>T02 - Acceptance criteria</ins>**
        - When I use a small screen or,
        - When I resize my screen and the menu becomes too large, the navigation bar collapses and,
        - When the navigation is collapsed, a toggler button is displayed to right of the header, and
        - When I click on the toggler button, a vertical menu is displayed,
        - When I click again on the toggler button, the vertical menu collapses back. 
        - When the vertical menu is displayed and I click on any items, the page scrolls to the relevant section and the menu will collapse back.  

        **T02 Result: PASS**
 
- ### **As a first time visitor, I want to be able to easily navigate across the website so that I can quickly find information.**
 
    - **<ins>T03 - Acceptance criteria</ins>** 
       - When I scroll to any section of the website, the navigation remains fixed on top of the page and my position on the page is made clear by the relevant link changing appearance (white bold) in the navigation bar. 
       - When I click on a menu item in the navigation bar, the page scrolls to the top of the relevant section of the webpage without spacing or content being covered by the navigation bar.
    
       **T03 Result: PASS**

- ### **As a first time visitor, I want to read about the company's services so that I can assess whether they fit my needs / As a first time visitor, I want to look at prices so that I can check whether I can afford their services.**
 
    - **<ins>TO4 - Acceptance criteria</ins>**  

        - when I click on the menu item “services” in the navigation bar, the page scrolls to the “services” section of the website.
        - when I view / scroll to the “services” section, an introduction and a list of items included in the services are displayed as well as three text boxes showing pricing information laid out on top of different images, and
        - when I scroll at the bottom of the section, a “contact-us” button is displayed,
        - when I hover over the button, its appearance changes from green to orange. 
        - when I click on the button, the page scrolls to the “contact us” section. 
 
       **T04 Result: PASS**

- ### **As a returning visitor, I want to read customer testimonials so that I can assess if the company is reliable and professional.**
 
    - **<ins>TO5 - Acceptance criteria</ins>**
        - when I click on the menu item “testimonials” in the navigation bar, the page scrolls to the “testimonials” section of the website.
        - When I view / scroll to the “testimonials section”, a carousel with 2 side buttons and a dotted indicator displays an image, a name and text containing the customer recommendations in quotes.
        - When I hover on either side buttons, the buttons appearance changes (to brown) and,
        - When I click on the right button, the carousel moves one slide to the right,
        - When I click on the left button, the carousel moves one slide to the left, and
        - When I click on one of the dotted indicators, the first slide to be displayed is relevant to the position on the dotter indicator. 

        **T05 Result: PASS**
 
- ### **As a returning visitor, I want to read more about the company so that I can assess its credentials, professionalism and cat friendliness.**
 
    - **<ins>T06 - Acceptance criteria</ins>** 
        - when I click on the menu item “credentials” in the navigation bar, the page scrolls to the “credentials” section of the website.
        - When I view / scroll to the testimonials section, text and a background image are visible and displayed responsively.  

        **T06 Result: PASS**
 
- ### **As a returning visitor, I want to access contact options so that I can reach the company for further queries.**
 
    - **<ins>T07 - Acceptance criteria</ins>**
        - when I click on the menu item “contact us” in the navigation bar, the page scrolls to the “contact us” section of the website, 
        - when I view or scroll to the “contact us” section, contact details with a phone number and an email address are displayed as well as a contact form containing “full name”, “email address”, “subject” and “message” fields,

      **T07 Result: PASS**
    
    - **<ins>T08 - Acceptance criteria - Form valid path</ins>**
        - when I enter my name in the “full name” field, and
        - when I enter a valid email address in the “email” field and,
        - when I go to the subject field, I can keep the existing selection “general queries” or select “Arrange a meet & greet” and,
        - when I enter a message in the “message field” and,
        - when I click submit, I am brought back to the top of the page (as the form is not linked with any server)

        **T08 Result: PASS**
    
    - **<ins>T09 - Acceptance criteria - Form invalid path</ins>**
        - when I enter an invalid email address and when I click submit, a message prompts me to enter a valid email address. 
        - when I leave the “full name” field empty and/or 
        - when I leave the “email” field empty and/or
        - when I leave the “message” field empty and/or
        - when I click submit, a message will appear to prompt me to enter the required fields.

        > **Issue:** 
        > - No message appears when the message field is empty.
        >
        > **Fix:** 
        > - Add required to text area element 

        **T09 Result after fixes: PASS**
 
    - **<ins>T10 - Acceptance criteria<</ins>**
        - when I scroll to the footer of the webpage, the company contact details with a phone number and an email address are displayed

        **T10 Result: PASS**
 
- ### **As a returning visitor,I want to view the areas where the company operates so that I can check that they provide services where I live.**
 
    - **<ins>T11 - Acceptance criteria</ins>**
        - when I click on the menu item “area we cover” in the navigation bar, the page scrolls to the section “Area we cover” of the website.
        - when I view / scroll to the “area we cover” section, a list of areas where the business operates is displayed responsively.
        - when I view the “area we cover” section, a map with a designated zone is displayed and I can zoom in and out, as well as searching my postcode.(the zoom and searching option are third party functionalities)
    
    **T11 Result: PASS**

- ### **As a frequent visitor, I want to quickly access the company social media account so that I can further check their credentials.**
 
    - **<ins>T12 - Acceptance criteria</ins>**
        - when I scroll to the footer of the webpage, icons representing facebook, twitter and instagram are displayed and,
        - when I hover over one of the icons, the icon changes in appearance (grow),
        - when I click on one of the icons, I am redirected to the right website in a new tab (ex. Facebook icon redirects to www.facebook.com.).
    
      **T12 - Result: PASS**

- ### **As a frequent visitor, I want to contact the company so that I can arrange a meet & greet.**
 
    - **<ins>T13 - Acceptance criteria</ins>** 
        - When I land on the website, a hero image, jumbotron text and a “contact” us button are displayed responsively,
        - When I hover over the contact us button, it changes in appearance from green to orange.
        - When I click on the “contact us” button, the page scroll to the “contact us” section, 
    
      **T13 - Result: PASS**

    - **<ins>T08 - Acceptance criteria - Form valid path</ins>**  
        - when I view or scroll to the “contact us” section, contact details with a phone number and an email address are displayed, as well as a contact form containing “full name”, “email address”, “subject” and “message” fields, 
        - when I enter my name in the “full name” field, and
        - when I enter a valid email address in the “email” field and,
        - when I go to the subject field, I can select “Arrange a meet & greet” and,
        - when I enter a message in the “message” field and,
        - when I click submit, I am brought back to the top of the page (as the form is not linked with any server)
       
        **T08 Result: PASS**

    - **<ins>T09 - Acceptance criteria - Form invalid path</ins>**  
        - when I enter an invalid “email” address and when I click submit, a message prompts me to enter a valid address. 
        - when I leave the “full name” field empty and/or 
        - when I leave the “email” field empty and/or
        - when I leave the “message” field empty and/or
        - when I click submit, a message will appear to prompt me to enter the required fields  
 
       **T09 Result: PASS (issue resolved earlier)**

    - **<ins>T14 - Acceptance criteria</ins>**
        - when I scroll to the footer of the webpage, the company contact details with a phone number and email address are displayed.  

      **T14 Result: PASS**

# Testing accessibility

  Wave evaluation report was used on the website to assess its accessibility. The report showed the following issues:  

 Initial report can be found [here](documentation/reports/waveinitial.jpg)  

 ![Wave initial report](reports/waveinitial.jpg)


 - ### **Errors:**  
   - **Contrast on buttons** : Change color from #23B06A to #078847 even if it meant compromising slightly the design
   - **Missing aria-labels on links:** Add aria-labels on links and aria-hidden is true to icons as suggested by [Font Awesome](https://fontawesome.com/how-to-use/on-the-web/other-topics/accessibility)

 - ### **Alerts:**
    - **Semantics**: Change headings where necessary and apply heading style to classes  as suggested in this post from [Solodev](https://www.solodev.com/blog/web-design/how-to-adjust-header-styles-with-css-and-bootstrap.stml)
    - **Text align:** Remove text align  
    - **Not sufficient alt text for the logo:** Include additional description
    - **Broken link for the logo:** Change logo link to #home

Wave accessibility final report can be found [here](documentation/reports/wavefinal.jpg).  

![Wave final report](reports/wavefinal.jpg)

# Google lighthouse

The following actions taken to improve performance:
- Compress images using tinyjpg 
- Move scripts to bottom from header to the bottom of the page 

The best performance that could be achieved:

![Google lighthouse](reports/google_lighthouse.png)

# HTML & CSS validation 

 - ## **W3C HTML validation** 

    The [W3C HTML validator](https://validator.w3.org/) service was used to insure there is not syntax errors on index.html. The initial report, which can be found [here](documentation/reports/w3c_html_error.png
    documentation/testing/reports) showed the following mistakes:

    ![W3C HTML Validation errors](reports/w3c_html_error.png)

    **Issues**
    - I-frame: Bad value for width element - digit expected but % is displayed instead 
    - I-frame: Frameborder attribute is obsolete 
    - Stray start tag script 

    **Fixes**
    - Remove frameborder and move width for iframe to css style .mapframe 
    - Move the scripts at the end of the body of html 

    The final report, which can can be found [here](documentation/reports/w3c_html_success.png) shows that all issues were resolved & that HTML code was validated. 
 
 - ## **W3C CSS validation** 

   The [W3C CSS validator](https://jigsaw.w3.org/css-validator/) service was used to insure there is no errors in the css styles. The initial report, which can be found [here](documentation/reports/w3c_css_errors.png) showed the following mistakes:

   ![CSSS Validation error](reports/w3c_css_errors.png)

    - **Issues:** Hide is not value of display.
    - **Fix:** The css was subsequently changed to display:none;
    - **Warnings:** Many of the browers vendor extension were unknown. 
    - **Fix**: The css file was amended and all the redundant vendors' extensions removed.

    The final report, which can be found [here](documentation/reports/w3c_css_success.png), shows that all issues were resolved & that the CSS styles were validated. 

    ![CSS Validation Success](reports/w3c_css_success.png)

  
  