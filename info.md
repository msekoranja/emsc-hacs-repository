[![GitHub Release][releases-shield]][releases]
[![hacs][hacsbadge]][hacs]
[![BuyMeCoffee][buymecoffeebadge]][buymecoffee]

The `emscrss` sensor retrieves events from a EMSC earthquake RSS feed and shows information of those events filtered by distance and magnitude to Home Assistant.

The reference point for comparing the distance is by default defined by `latitude` and `longitude` in the basic configuration.

Only entries of the feed are considered that define a location as `point` or `polygon` in *georss.org* format or as *WGS84 latitude/longitude*.

The data is updated every 5 minutes.

## Usage:
To enable the events sensor, add the following lines to your `configuration.yaml`.

```yaml
sensor:
  - platform: emscrss
    name: Earthquakes near me
    radius: 300
    magnitude: 3.0
```

Parameters:
```yaml
url:
  description: Full URL of the EMSC feed.
  required: false
  type: string
  default:
name:
  description: Name of the sensor used in generating the entity id.
  required: false
  type: string
  default: https://www.emsc-csem.org/service/rss/rss.php?typ=emsc
latitude:
  description: Latitude of the coordinates around which events are considered.
  required: false
  type: string
  default: Latitude defined in your `configuration.yaml`
longitude:
  description: Longitude of the coordinates around which events are considered.
  required: false
  type: string
  default: Longitude defined in your `configuration.yaml`
radius:
  description: The distance in kilometers around the Home Assistant's coordinates in which events are considered.
  required: false
  type: float
  default: 300km
magnitude:
  description: The magnitude (ML) above which events are considered.
  required: false
  type: float
  default: 3.0
```

<!---->

<a href="https://www.buymeacoffee.com/msekoranja" target="_blank"><img src="https://www.buymeacoffee.com/assets/img/custom_images/black_img.png" alt="Buy Me A Coffee" style="height: auto !important;width: auto !important;" ></a><br>

***

[emscrss]: https://github.com/msekoranja/emsc-hacs-repository
[buymecoffee]: https://www.buymeacoffee.com/msekoranja
[buymecoffeebadge]: https://img.shields.io/badge/buy%20me%20a%20coffee-donate-yellow.svg?style=for-the-badge
[hacs]: https://hacs.xyz
[hacsbadge]: https://img.shields.io/badge/HACS-Custom-orange.svg?style=for-the-badge
[releases-shield]: https://img.shields.io/github/release/cmsekoranja/emsc-hacs-repository.svg?style=for-the-badge
[releases]: https://github.com/msekoranja/emsc-hacs-repository/releases
[user_profile]: https://github.com/msekoranja
