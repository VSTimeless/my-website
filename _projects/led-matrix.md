---
layout: page
title: "LED Matrix Display"
description: "An 8x8 RGB LED matrix with Arduino-controlled patterns and animations."
image: "/assets/images/led-matrix.jpg"
---

# LED Matrix Display

This project features an 8x8 RGB LED matrix that displays various patterns and animations controlled by an Arduino microcontroller.

## Features

- 64 individually addressable RGB LEDs
- Multiple animation patterns
- Sound reactivity mode
- Custom 3D-printed enclosure
- Web interface for pattern selection

## Technical Details

The display uses WS2812B LEDs (NeoPixels) arranged in an 8x8 grid. An Arduino Nano controls the display, with patterns stored in program memory. A small electret microphone and amplifier circuit enables sound reactivity.

## Code Highlights

```cpp
void rainbowCycle(uint8_t wait) {
  uint16_t i, j;

  for(j=0; j<256*5; j++) { // 5 cycles of all colors on wheel
    for(i=0; i< strip.numPixels(); i++) {
      strip.setPixelColor(i, Wheel(((i * 256 / strip.numPixels()) + j) & 255));
    }
    strip.show();
    delay(wait);
  }
}
```

## Future Plans

I plan to expand this project by:
- Adding WiFi control via ESP32
- Creating a mobile app for custom patterns
- Implementing machine learning for pattern generation
- Scaling up to a larger 16x16 display
