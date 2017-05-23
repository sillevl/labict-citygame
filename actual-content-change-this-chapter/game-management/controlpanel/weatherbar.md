# Weatherbar

## Getting the weatherdata

To acquire the local weather, we made use of the [API](http://openweathermap.org/forecast5) of [OpenWeatherMap](http://openweathermap.org/). With this API we had the choice to receive data formatted in JSON or in XML, we went for JSON. The data is stored locally on the server where the website is running on.

## Checking the weatherdata

Before we store the data, it first needs to be checked if the response we've got was ok. For this, we made use of a JSON Validator with the use of [Webmozart's library](https://github.com/webmozart/json).

A short class for this task was used with only one task... validating. \(See snippit below\)

```php
namespace CityGame\CityGame\Models;

use \Webmozart\Json\JsonDecoder;
use \Webmozart\Json\ValidationFailedException;
use \Webmozart\Json\JsonValidator;
/**
 *
 */
class JSON_Validator{

    public function validate ( $path_to_be_validated, $path_to_scheme ){
        $is_valid = false;

        $decoder = new JsonDecoder();
        $validator = new JsonValidator();

        $errors = $validator->validate( json_decode($path_to_be_validated), $path_to_scheme );

        if ( count($errors) == 0 ) {
            //Data did match
            $this->is_valid = true;
        } else{
            $this->is_valid = false;
        }
        return $this->is_valid;
    }
}
```

## Getting the info onto the weatherbar

#### Loading the data

To load the data, we've used XMLHttpRequest.

```js
function loadCachedWeatherData() {
    try {
        var request = new XMLHttpRequest();
        request.open("GET", DIR_CACHED_DATA, false);
        request.send(null);
        this.weatherData = JSON.parse(request.responseText);
    } catch (e) {
        notify("Something went wrong loading the weather.");
    }
}
```

#### Correct forecast

One of the advantage of local stored data is that we can provide weather for 5 days if OpenWeatherMap.org would be down. A algorithm \(see snippit below\) is used to determine what te correct forecast with the most approaching time is. 

```js
function searchCacheForCorrespondingDataArrayLocation(){
    try {
        var currentEpochTime = Math.floor(getCurrentEpochTime() / 1000) - new Date().getTimezoneOffset()*60;
        var tempCachedEpochTimes = getCachedEpochTimes();

        var tmpMostApprTimeDiffArrayIndex = 0;
        var tmpNearestCachedTime = Math.abs(currentEpochTime - tempCachedEpochTimes[0]);
        var tmpEpochDiff = Math.abs( currentEpochTime - tempCachedEpochTimes[0] );
        var tmpSmallestTimeDiff;

        var tmpMostApprTimeDiffArrayIndex;

        for (var i = 0; i < tempCachedEpochTimes.length; i++){
            tmpSmallestTimeDiff = Math.abs( currentEpochTime - tempCachedEpochTimes[i] );

            if(tmpSmallestTimeDiff < tmpEpochDiff){
                tmpEpochDiff = tmpSmallestTimeDiff;
                tmpNearestCachedTime =  tempCachedEpochTimes[i];
                tmpMostApprTimeDiffArrayIndex = i;
            }
        }
        this.mostApprTimeDiffArrayIndex = tmpMostApprTimeDiffArrayIndex;
    } catch (e) {
        notify("Something went wrong loading the weather");
    }
}
```

#### Presenting it to the user

A small customized method that is using `document.getElementById()` is used to present data to the user. The method that brings everything to the user is shown below.

```js
function loadForecastToWidget(){
    try {
        var currentForecast = getMostApprTimeDiffArrayIndex();
        convertEpochToHuman(this.cachedEpochTimes[getMostApprTimeDiffArrayIndex()]);

        setTextById("location", `Weather in ${this.weatherData.city["name"]}, ${this.weatherData.city["country"]}`);
        setTextById("upcoming", "Upcoming ");

        document.getElementById("weatherbar").setAttribute("title", `Expected weather for ${getTimeformat()} and 3 hours in advance.`);

        for(var i = 0; i<2; i++){
            this[`image${i}`] = document.getElementById(`img_${i}`);
            this[`image${i}`].src = ( API_IMG_URL + this.weatherData.list[currentForecast+i].weather[0].icon +  API_IMG_EXTENSION);
            document.getElementById(`img_${i}`).setAttribute("title", capitalizeFirstLetter(this.weatherData.list[currentForecast+i].weather[0].description));

            setTextById(`temp_${i}`, `${(this.weatherData.list[currentForecast+i].main["temp"]).toFixed(0)}°C`);
            setTextById(`windspeed_${i}`, `Wind: ${((this.weatherData.list[currentForecast+i].wind["speed"])*3.6).toFixed(0)} km/h`);
            try {
                if(this.weatherData.list[i].rain != null) {
                    if(this.weatherData.list[i].rain["3h"] != null && typeof this.weatherData.list[i].rain["3h"] != "undefined") {
                        setTextById(`precip_${i}`, `Precipitation: ${(this.weatherData.list[currentForecast+i].rain["3h"]).toFixed(4)} mm`);
                    } else {
                        setTextById(`precip_${i}` , "Precipitation: 0 mm");
                    }
                } else{
                    setTextById(`precip_${i}` , "Precipitation: 0 mm");
                }
            } catch (e) {
                setTextById(`precip_${i}` , "Precipitation: N/A");
                notify("Something went wrong loading the weather");
            }
        }
    } catch (e) {
        notify("Something went wrong loading the weather");
    }
}
```



