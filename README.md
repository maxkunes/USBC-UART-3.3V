# USB C to UART 3.3v Altium schematic and board files (A conversion from USB micro b to USBC)
Just a simple USBC to UART converter with 3.3v logic levels.
I designed this mainly to figure out what is the bare minimum necessary for converting a USB micro B design to USBC as I find that micro b connectors break under very little stress and usually destroy boards when doing so.

Turns out you really only have to do two things:
* Short out the USB differential pins from both sides of the mirrored connector. DP -> DP and DN -> DN. This might work for USB3 SS, but due to the higher (5gbps) data rate, I wouldn't bet on it and a mux should be used instead.

* Add two 5.1k ohm resistors to ground on the CC pins. Two individual resistors. DO NOT SHORT THE CC PINS TOGETHER.

This was quick and dirty so little care was taken about impedance matching the differential pairs. However, they were routed in a differential style, but care should be taken to ensure proper impedance through track size and spacing.

You will find the project files and production ready outputs in the usbc_uart folder.