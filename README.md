Random Notes on dc converters


See this, there is no clear winner for all loads
https://www.analog.com/en/technical-articles/synchronous-or-nonsynchronous-topology-boost-system-performance-with-the-right-dcdc-converter.html


Easy to make negative rail from DC DC buck converter with coupled inductor

Easy to make split rail from DC DC boost converter with trifilar inductor

In both cases, be carefull not to let inductor current to drop to zero, i.e. go into DCM mode. Once inductor 
current is zero, there is no flux. Use dummy load resistors to guarantee minumum current.

Don't need to do it for a typical configuration, when the "primary and the only one" inductor is in series with load.

XL6009 seems to NOT have UVLO, despite what the datasheet says. Need an external zener and resistor to manipulate EN pin to OFF when voltage is less than minimum datasheet value.


There has to be ripple inductor current for DC DC convertor to operate. This is why it's recommended to have
0.2-0.4 from the max inductor current. This calculator uses the "magic number" 0.3


Older chips like mc3406 always operate in DCM for boost operations. Alldgedly they use (voltage?) histeresis control. Be aware of it. They might not be suitable for coupled inductor split rail.