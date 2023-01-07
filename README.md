# Урок 9. Способы организации передачи данных между компонентами приложения, протоколы и API. REST, gRPC, очереди

## Задание: Доработать метод `Delete` на уровне модели данных и контроллера.

В классе WeatherForecastModel метод Delete реализован в следующем виде:

public void Delete(DateTime date)
        {
            foreach (WeatherForecast weatherForecast in _list)
            {
                if (weatherForecast.Date == date)
                {
                    _list.Remove(weatherForecast);
                    break;
                }
            }
        }

[WeatherForecastModel](https://github.com/MikhailAkulov/Architecture_home_work_9/blob/main/MyFirstWebApplication/MyFirstWebApplication/Models/WeatherForecastModel.cs)

В классе WeatherForecastController:

[HttpDelete("delete")]
        public IActionResult Delete(DateTime date)
        {
            _weatherForecastModel.Delete(date);
            return Ok();
        }

[WeatherForecastController](https://github.com/MikhailAkulov/Architecture_home_work_9/blob/main/MyFirstWebApplication/MyFirstWebApplication/Controllers/WeatherForecastController.cs)