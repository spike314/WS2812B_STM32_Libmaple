# WS2812B_STM32_Libmaple
WS2812B (Neopixel) library for Arduino STM32 (Libmaple core)

Written by Roger Clark www.rogerclark.net, from first principals

This library uses SPI DMA to control a strip of WS2812B (NeoPixel) LEDS

It should be generally compatible with the Adafruit NeoPixel library, 

For additional technical details see: <https://github.com/rogerclarkmelbourne/WS2812B_STM32_Libmaple/blob/master/README.md>

Updated with modificatons by Aram Prez to support SPI2.
See: <http://www.stm32duino.com/viewtopic.php?f=9&t=3706&p=46063&hilit=ws2812b#p46063>

Added getPixelColor() function.
Roger's library sets up a bit steam where each bit in an rgb color is represented by 3 bits; 110 for high, 100 for low.
Each r, g, or b byte is then represented by 24 bits in the stream.  Bits are sent to pixels in g b r order with the high bit sent first.
The getPixelColor() function uses bitwise AND on the middle bit of the 3-bit sequence which returns true if that bit is 1 and false if it is zero.  If it is a 1, a bitwise OR mask is used to set the corresponding bit on the r, g, or b variable.
