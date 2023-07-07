---
title: "Home Assistant dashboard: Styling"
category: Home Assistant
tags: Home Assistant, dashboard, lovelace, styling
---
# Home Assistant dashboard: Styling

<a href="index"><img src="images/home_assistant_logo.png" style="float: right;" alt="Home Assistant logo" height="100px"></a>

Here you find Home Assistant (lovelace) dashboard styling examples which you can easily add to your own dashboards.
<br/><br/><br/>

---
## Table of Contents
<!-- TOC -->
* [Changing icon color](#changing-icon-color)
* [Changing status color](#changing-status-color)
* [Changing background color](#changing-background-color)
<!-- TOC -->

---
## Changing icon color

You can change the color of an icon based on its value.

You need the extra HACS module [lovelace-card-mod](https://github.com/thomasloven/lovelace-card-mod).

![Changing icon color](images_styling/colored_icon.png)
```yaml
{% raw %}
# Sourcecode by vdbrink.github.io
type: entities
entities:
  - entity: sensor.knmi_weercode
    tap_action:
      action: url
      url_path: https://www.knmi.nl/nederland-nu/weer/waarschuwingen/overijssel
    card_mod:
      style: |
        :host {
          --card-mod-icon-color:
          {% if is_state('sensor.knmi_weercode', 'Code groen') %}
           #008000;
          {% elif is_state('sensor.knmi_weercode', 'Code rood') %}
           #ff4500;
          {% elif is_state('sensor.knmi_weercode', 'Code geel') %}
           #ffd700;
          {% elif is_state('sensor.knmi_weercode', 'Code oranje') %}
           #ffa500;
          {% else %}
           #44739e
          {% endif %}
         }
  {% endraw %}
```

---
## Changing status color

You can change the color of the sensor status based on its value.

You need the extra HACS module [lovelace-card-mod](https://github.com/thomasloven/lovelace-card-mod).

![Changing text color](images_styling/colored_status.png)
```yaml
{% raw %}
# Sourcecode by vdbrink.github.io
type: entities
entities:
  - entity: sensor.knmi_weercode
    tap_action:
      action: url
      url_path: https://www.knmi.nl/nederland-nu/weer/waarschuwingen/overijssel
    card_mod:
      style: |
        .text-content {
         color:
            {% if is_state('sensor.knmi_weercode', 'Code groen') %}
             #008000;
            {% elif is_state('sensor.knmi_weercode', 'Code rood') %}
             #ff4500;
            {% elif is_state('sensor.knmi_weercode', 'Code geel') %}
             #ffd700;
            {% elif is_state('sensor.knmi_weercode', 'Code oranje') %}
             #ffa500;
            {% else %}
             #44739e
            {% endif %}
        }
  {% endraw %}
```
---
## Changing background color

You can change the color of the background based on its value.

You need the extra HACS module [lovelace-card-mod](https://github.com/thomasloven/lovelace-card-mod).

![Changing text color](images_styling/colored_background.png)
```yaml
{% raw %}
# Sourcecode by vdbrink.github.io
type: entities
entities:
  - entity: sensor.knmi_weercode
    tap_action:
      action: url
      url_path: https://www.knmi.nl/nederland-nu/weer/waarschuwingen/overijssel
    card_mod:
      style: |
        .text-content {
         color:
            {% if is_state('sensor.knmi_weercode', 'Code groen') %}
             #008000;
            {% elif is_state('sensor.knmi_weercode', 'Code rood') %}
             #ff4500;
            {% elif is_state('sensor.knmi_weercode', 'Code geel') %}
             #ffd700;
            {% elif is_state('sensor.knmi_weercode', 'Code oranje') %}
             #ffa500;
            {% else %}
             #44739e;
            {% endif %}
        }
  {% endraw %}
```

---
[^^ Top](#table-of-contents)

[<< See also my other Home Assistant pages](index)