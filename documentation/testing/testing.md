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

