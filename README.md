<h1 align="center"> Casablanca Daily Weather ETL</h1>
<h3 align="center"> (As Proof Of Concept)</h3>
<p align="center">
  <img src="https://media.giphy.com/media/6U6bUk6HQOfsxxzQDM/giphy.gif" width="300" alt="Pipeline Animation 1" style="display:inline-block;" />
  &nbsp;&nbsp;&nbsp;
</p>

<h2 align="center">Scenario</h2>

You've been tasked by your team to create an automated Extract, Transform, Load (ETL) process to extract daily weather forecast and observed weather data and load it into a live report to be used for further analysis by the analytics team. As part of a larger prediction modelling project, the team wants to use the report to monitor and measure the historical accuracy of temperature forecasts by source and station.

As a proof-of-concept (POC), you are only required to do this for a single station and one source to begin with. For each day at noon (local time), you will gather both the actual temperature and the temperature forecasted for noon on the following day for Casablanca, Morocco.

At a later stage, the team anticipates extending the report to include lists of locations, different forecasting sources, different update frequencies, and other weather metrics such as wind speed and direction, precipitation, and visibility.


<h2 align="center">Data Source</h2>

This project implements an automated **ETL (Extract, Transform, Load)** process using **Linux shell scripting** to collect and store weather data for **Casablanca, Morocco**, via the [`wttr.in`](https://github.com/chubin/wttr.in) weather service.


<h2 align="center">Learning Objectives</h2>

By completing this project, you'll gain experience with:

- Shell scripting for automation
- Using `curl` to extract raw weather data
- Parsing and transforming data using text-processing tools (`grep`, `cut`, etc.)
- Store structured log data using `echo` and tab-separated format
- Use Linux environment variables for accurate time zone management
- Prepare for future automation with `cron`

<h2 align="center">Steps</h2>

Created Log File 
```
touch casablanca_weather_poc.log
```

Added a header to the weather report
```
header=$(echo -e "year\tmonth\tday\tobs_temp\tfc_temp")
echo $header>casablanca_weather_poc.log
```

Created a text file called weather_etl.sh and made it an executable Bash script
```
touch weather_etl.sh; chmod u+x weather_etl.sh
```

Assigned the city name to Casablanca for accessing the weather report and obtain the weather information for Casablanca
```
city=Casablanca; curl -s wttr.in/$city?T --output weather_report
```

Extraction and loading of the required data can be seen directly in the weather_etl.sh script

<h3 align="right">Assigned By</h3>
<p align="right">
  <a href="https://www.coursera.org/account/accomplishments/verify/TG89DJFGV7VD?utm_source=link&utm_medium=certificate&utm_content=cert_image&utm_campaign=sharing_cta&utm_product=course">
    <img width="100" src="https://img.icons8.com/nolan/64/ibm.png" alt="IBM" />
  </a>
</p>

