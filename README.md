# ���� 9. ������� ����������� �������� ������ ����� ������������ ����������, ��������� � API. REST, gRPC, �������

## �������: ���������� ����� `Delete` �� ������ ������ ������ � �����������.

� ������ WeatherForecastModel ����� Delete ���������� � ��������� ����:

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

� ������ WeatherForecastController:

[HttpDelete("delete")]
        public IActionResult Delete(DateTime date)
        {
            _weatherForecastModel.Delete(date);
            return Ok();
        }

[WeatherForecastController](https://github.com/MikhailAkulov/Architecture_home_work_9/blob/main/MyFirstWebApplication/MyFirstWebApplication/Controllers/WeatherForecastController.cs)