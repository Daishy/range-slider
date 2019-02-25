# RangeSlider Add-on for Vaadin 8

RangeSlider is a UI component add-on for Vaadin 8 that currently displays a
slider with a lower and upper handle, to select a range of values. The Slider is based on Vaadins HasValue 
and can be used with a Binder.

This addon is based massivly on the great noUiSlider-javascript-component, see
https://refreshless.com/nouislider/ or https://github.com/leongersen/noUiSlider/ 
for more infos. 

## Features
* changing the step size between values
* Setting the displayed decimal-precision for values.
* changing the minimal and maximal difference allowed between the lower and upper value
* Value-Tooltips can be displayed never, always, on-focus or on-change.
* slider can be read-only.
* slider integrates in the vaadin-8 binder

## Known Limitations
* Styling adapted to valo, other themes may require some tuning. See the range-slider.css for more infos. 

## Building and running demo

git clone git://github.com/daishy/range-slider.git
mvn clean install
cd range-slider-demo
mvn spring-boot:run

To see the demo, navigate to http://localhost:8080/

## Release
(More of a note for me ...)

vaadin-addons-release: `mvn clean deploy -Pvaadin-release`
central-release: `mvn clean deploy -Poss-release`
    
    
 
   
 
## License & Author

Add-on is distributed under Apache License 2.0. For license terms, see `LICENSE`.

## Usage and Examples

Create a new field as you would any other vaadin-field-component via the provided constructors.


Binding field via a binder:
```java
RangeSlider slider = new RangeSlider("cost-range", new Range(0.0, 200.0));

Binder<> binder = new Binder<Data>();
binder.forField(slider).bind(Data::getCostRange, Data::setCostRange);
```

Setting a minimal and maximal difference between the values:
```java
RangeSlider slider = new RangeSlider("cost-range", new Range(0.0, 200.0));
slider.setMinimalDifference(10); // values must be at least 10 appart
slider.setMaximalDifference(50); // but no more than 50 appart
```

Setting the precision and step-size to allow decimal values:
```java
RangeSlider slider = new RangeSlider("cost-range", new Range(0.0, 10.0));
slider.setStep(0); // Any steps are allowed
slider.setPrecision(2); // Show values as 2.24, 5.23 etc.
```

Set the allowed step-size: 
```java
RangeSlider slider = new RangeSlider("cost-range", new Range(0.0, 10.0));
slider.setStep(2); // only 0, 2, 4, 6, 8, 10 are selectable
```

Show Tooltips for the selected values:
```java
RangeSlider slider = new RangeSlider("cost-range", new Range(0.0, 10.0));
slider.setTooltips(RangeSliderState.Tooltips.NEVER); // Never showing the selected values
slider.setTooltips(RangeSliderState.Tooltips.ON_CHANGE); // Show selected values if slider is moved
slider.setTooltips(RangeSliderState.Tooltips.ALWAYS); // Always show the selected values
slider.setTooltips(RangeSliderState.Tooltips.ON_FOCUS); // Show if component focused
```

