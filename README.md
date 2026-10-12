# weather_landscape

## What This Is

Every project needs a shelf of ready answers. product and engineering is one of those shelves, and weather_landscape is the entry on it - the notes, patterns and fixes we reuse when this kind of work comes up.

## Images

[![weather_landscape](images/preview.png)](https://github.com/Swift-Tech-Co/weather_landscape)

## Encoding principles

The landscape depicts a small house in the woods. The horizontal axis of the image represents a 24-hour timeline, starting from the current moment on the left, marked by the house, and extending to the conditions of the next day on the right. Various landscape elements distributed along the vertical axis symbolize weather events and conditions. The further an event is from the present, the farther it is positioned to the right in the image.

[![encode](pic/encode.png)](https://github.com/Swift-Tech-Co/weather_landscape)

The following information can be encoded within the landscape image:

- Time markers to simplify timeline navigation:
  - Sunrise and sunset times
  - Noon and midnight
- Weather forecast information:
  - Wind direction and strength
  - Temperature fluctuations
  - Maximum and minimum temperature values
  - Cloud cover
  - Precipitation
- Current weather conditions:
  - Temperature
  - Atmospheric pressure
- Non weather events:
  - Birthdays
  - Holidays
  

## Implementation

The image generation code is written in Python using the Pillow library and is based on data from OpenWeather. The image is designed specifically for use on a 296x128 E-Ink display. The code tested on Python 3.9.

| Event image | Description |
|----------|------------|
|[![example](pic/sun_00.png)](https://github.com/Swift-Tech-Co/weather_landscape)| Sunrise | 
|[![example](pic/moon_00.png)](https://github.com/Swift-Tech-Co/weather_landscape)| Sunset |
|[![example](pic/cloud_30.png)](https://github.com/Swift-Tech-Co/weather_landscape)| Cloud cover |
|[![example](pic/house_00.png)](https://github.com/Swift-Tech-Co/weather_landscape)| Current time position|
|[![example](pic/flower_00.png)](https://github.com/Swift-Tech-Co/weather_landscape)| Midnight |
|[![example](pic/flower_01.png)](https://github.com/Swift-Tech-Co/weather_landscape)| Midday |
|[![example](pic/sprites_south.png)](https://github.com/Swift-Tech-Co/weather_landscape)| South wind |
|[![example](pic/sprites_east.png)](https://github.com/Swift-Tech-Co/weather_landscape)| East wind |
|[![example](pic/sprites_west.png)](https://github.com/Swift-Tech-Co/weather_landscape)| West wind |
|[![example](pic/sprites_north.png)](https://github.com/Swift-Tech-Co/weather_landscape)| North wind |
|[![example](pic/rain.png)](https://github.com/Swift-Tech-Co/weather_landscape)| Rain|
|[![example](pic/snow.png)](https://github.com/Swift-Tech-Co/weather_landscape)| Snow|
|[![example](pic/pres_high.png)](https://github.com/Swift-Tech-Co/weather_landscape)| High atmospheric pressure |
|[![example](pic/pres_norm.png)](https://github.com/Swift-Tech-Co/weather_landscape)| Normal atmospheric pressure |
|[![example](pic/pres_low.png)](https://github.com/Swift-Tech-Co/weather_landscape)| Low atmospheric pressure |
|[![example](pic/holiday.png)](https://github.com/Swift-Tech-Co/weather_landscape)| [Non-weather event](holiday.md): someone's birthday. |

The taller the trees, the stronger the wind is expected to be. A mix of different tree types in the forest indicates an intermediate wind direction.

## Examples

|&nbsp;Landscape&nbsp;image&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;| Description |
|----------|------------|
|[![example](pic/weather_test.bmp)](https://github.com/Swift-Tech-Co/weather_landscape)| It’s around noon, with clear skies and a few clouds expected. A moderate north wind will develop overnight. Temperatures are currently rising but will begin to fall after sunset, reaching their lowest point before sunrise. During this time, the wind is expected to shift to the northeast.|
|[![example](pic/test_20240903_043826.bmp)](https://github.com/Swift-Tech-Co/weather_landscape)| The sun is rising and it will be a hot sunny day with a light southeast breeze. The temperature will remain high even after sunset, and the wind will shift to the east, becoming stronger throughout the evening.|
|[![example](pic/test_09B0B1083315.bmp)](https://github.com/Swift-Tech-Co/weather_landscape)| It will be cold and rainy throughout the day and night. The south wind will shift to the northwest overnight. Don’t forget that someone’s birthday is tomorrow. |

## How the landscape changed during the day

[![Dynamic](pic/dynamic.gif)](https://github.com/Swift-Tech-Co/weather_landscape)

## Running the code

#### Preparing environment Linux
```
./makevenv.sh
```
```
source .venv/bin/activate
```

#### Preparing environment Windows
```
makevenv.bat
```
```
.venv/Scripts/Activate
```

#### Image creation test

Update **OWM_KEY** variable in the `secrets.py` with your OpenWeather API key.

(optional) Change the coordinates in `secrets.py` to your location.

```
python run_test.py
```

Find generated images in the "tmp" folder.

#### Run server

```
python run_server.py
```

[![Setup](pic/server_start_screenshot.png)](https://github.com/Swift-Tech-Co/weather_landscape)

Access the server page from a browser to see the number of generated images.

## E-Ink module

<!-- [![2.9inch e-Paper Module](pic/eink.jpg)](https://github.com/Swift-Tech-Co/weather_landscape) -->
[![Setup](pic/hardware.jpg)](https://github.com/Swift-Tech-Co/weather_landscape)

The hardware setup includes an ESP32 development board and 2.9inch E-Ink display module. Currently, the setup only displays an image sourced from the internet, updating every 15 minutes. It is uncertain whether the image generation code can be adapted for use with MicroPython on the ESP32 at this time.

[More information](esp32/README.md)

## Phone

[![Setup](pic/landscape_rgb_w.png)](https://github.com/Swift-Tech-Co/weather_landscape)

During the test, several images are generated. The black-and-white images are intended for use with an E-Ink module, while the color images can be placed on a phone's home screen. For Android devices, there is an app called Web Image Widget that allows you to create a widget displaying an image from the internet. To use it, start the server script from the repository and add a widget that points to one of the generated images.

[![Android](pic/color_phone_screenshot.jpg)](https://github.com/Swift-Tech-Co/weather_landscape)

---

## Swift Tech Co.

Built and maintained by Swift Tech Co.

AI Automation | FinTech Platforms | Custom Software and Mobile Apps | SaaS Platforms | Cloud Infrastructure | Cybersecurity | SEO and Marketing | API Integration

**Join our community on Telegram:** [t.me/+Qt_eFvkb2rliMzNh](https://t.me/+Qt_eFvkb2rliMzNh)

Home | Services | Careers | Referral Program | Influencers | About | Contact

**Connect**

- Website: https://github.com/Swift-Tech-Co/weather_landscape
- LinkedIn: [linkedin.com/in/stephenoladoke](https://www.linkedin.com/in/stephenoladoke/)
- LinkedIn (Company): [linkedin.com/company/swift-tech-co](https://www.linkedin.com/company/swift-tech-co)
- X: [@MrOladoke](https://x.com/MrOladoke)
- Instagram: [@mr.oladoke](https://www.instagram.com/mr.oladoke/)
- Organization: [github.com/Swift-Tech-Co](https://github.com/Swift-Tech-Co)

## Sources

Compiled and maintained from upstream [lds133/weather_landscape](https://github.com/lds133/weather_landscape) under permissive open-source license.

---

Maintained by [Swift Tech Co.](https://github.com/Swift-Tech-Co) - [Telegram](https://t.me/+Qt_eFvkb2rliMzNh)

## Sources

Compiled and maintained from upstream [lds133/weather_landscape](https://github.com/lds133/weather_landscape) under permissive open-source license.

---

Maintained by [Swift Tech Co.](https://github.com/Swift-Tech-Co) - [Telegram](https://t.me/+Qt_eFvkb2rliMzNh)

## Sources

Compiled and maintained from upstream [lds133/weather_landscape](https://github.com/lds133/weather_landscape) under permissive open-source license.

---

Maintained by [Swift Tech Co.](https://github.com/Swift-Tech-Co) - [Telegram](https://t.me/+Qt_eFvkb2rliMzNh)