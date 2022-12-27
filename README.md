# Violin Plot for Weather Data <br><br/>

### Dashboard
<p align="center">
<img width="650em" src="https://github.com/Power-BI-Solutions/Violin-Plot-for-Weather-Data/blob/main/Custom%20Visual%20-%20Violin%20Plot.gif" align = "center"/>
</p>
<br><br/>

### Data Source
- [NATIONAL WEATHER SERVICE | National Oceanic and Atmospheric Administration](https://www.weather.gov/wrh/climate?wfo=bou)


### Calendar table
DAX for creating custom calendar table for 2020:

```dax
= CreateDateDim(#date(2020, 1, 1), #date(2021, 1, 1))
``` 

```dax
= Table.TransformColumnTypes(Source,{{"Date", type date}
, {"Year", Int64.Type}, {"Quarter", type text}
, {"Week Number", Int64.Type}
, {"Month Number", Int64.Type}
, {"Month", type text}
, {"Day of Week", type text}})
```

```dax
= Table.AddColumn(#"Changed Type", "Day of Week Number", each Date.DayOfWeek([Date], Day.Monday))
``` 

```dax
= Table.TransformColumnTypes(#"Inserted Day of Week",{{"Day of Week Number", Int64.Type}})
``` 

<br><br/>

### Model

<p align="center">
<img width="650em" src="https://github.com/Power-BI-Solutions/Violin-Plot-for-Weather-Data/blob/main/violin_plot_data.png" align = "center"/>
</p>
<br><br/>

### Acknowledgements
Project source: WoW Power BI (Workout Wednesday)
- [Violin Plot - Custom Visual](https://www.workout-wednesday.com/pbi-2021-w10/)

YouTube video tutorial:
- [Violin Plot - Custom Visual](https://www.youtube.com/watch?v=iOTfg6VRaHM)
