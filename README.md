# Frameboard

This is a fork of @Madelena's [Weatherman Dashboard](https://github.com/Madelena/esphome-weatherman-dashboard), adapted to make a little more sense for St Albans. All credit goes to her and her contributors for the meat of this, along with the idea.

## Sensors

You'll need to add the sensors in `template-frameboard.yaml` to your Home Assistant configuration (I keep templates in `templates/` and import using `template: !include_dir_merge_list templates/`). 

In particular you need:

* `home_weather_forecast_hourly` to contain the hourly forecase data. You need to call the `weather.get_forecasts` service to extract this from the Met.no integration.
* `dashboard_refresh_status` to control whether we refresh the dashboard. In this case, I'm using motion sensors from UniFi cameras to control it. These don't have occupancy, hence the extra templates to allow us to detect motion during the past minute.
* `frameboard_data` to contain all the information to push to the dashboad.
