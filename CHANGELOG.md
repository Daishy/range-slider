# Changelog

# Version 1.0.0
First Release


# Version 1.0.1
---

# Version 1.0.2
* Fixed a bug while setting new boundaries to adjust the current values if necessary.

# Version 1.0.3
* Fixed a bug when hiding and showing the range-slider, the current values were not displayed correctly
* Updated to version 11.1.0 of the noUiSlider-Library

# Version 1.0.4
* Updated to version 11.1.0 of the noUiSlider-Library temporarily reverted until the layouting-Problem 
    can be fixed

    
# Version 1.1.0
Changed the API to use doubles instead of integers. setPrecision is added to control how many
decimal-parts are displayed (precision 2 is 2.12 for example). Precision is 0 by default (normal integers).


# Version 1.1.1
* Added a convenience `toInt`-Methode to the `Range`-Class
* Added a no-arguments constructor to the range-slider