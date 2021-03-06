---
layout: page
title: Series
---

Series is the content that displays the data in the plot.

// TODO //

### Title

The title of the series is shown in the legend box. If you don't want the series to show up in the legend box, keep the default value `null`.

### Tracker format string

A format string for the tracker (trackers are only implemented for WPF/Silverlight)

### LineSeries

{Images\LineSeries.png}

``` csharp
var model = new PlotModel { Title = "LineSeries" };
var lineSeries = new LineSeries();
lineSeries.Points.Add(new DataPoint(0, 0));
lineSeries.Points.Add(new DataPoint(10, 4));
lineSeries.Points.Add(new DataPoint(30, 2));
lineSeries.Points.Add(new DataPoint(40, 8));
model.Series.Add(lineSeries);
```

Set the `Smooth` property to render a canonical spline:

``` csharp
lineSeries.Smooth = true;
```

{Images\LineSeriesSmoothed.png}


### TwoColorLineSeries

{Images\TwoColorLineSeries.png}

### ScatterSeries

ScatterSeries shows a set of points. The points can also have a size and color value.

{Images\ScatterSeries.png}

``` csharp
var model = new PlotModel { Title = "ScatterSeries" };
var scatterSeries = new ScatterSeries { MarkerType = MarkerType.Circle };
var r = new Random(314);
for (int i = 0; i < 100; i++)
{
    var x = r.NextDouble();
    var y = r.NextDouble();
    var size = r.Next(5, 15);
    var colorValue = r.Next(100, 1000);
    scatterSeries.Points.Add(new ScatterPoint(x, y, size, colorValue));
}

model.Series.Add(scatterSeries);
model.Axes.Add(new LinearColorAxis { Position = AxisPosition.Right, Palette = OxyPalettes.Jet(200) });
```

### AreaSeries

{Images\AreaSeries.png}

### ContourSeries

{Images\ContourSeries.png}

### HeatMapSeries

{Images\HeatMapSeries.png}

### BoxPlotSeries

{Images\BoxPlotSeries.png}

### StemSeries
{Images\StemSeries.png}

### StairStepSeries

{Images\StairStepSeries.png}

### HighLowSeries

{Images\HighLowSeries.png}

### CandleStickSeries

{Images\CandleStickSeries.png}

### BarSeries

{Images\BarSeries.png}

### ColumnSeries

{Images\ColumnSeries.png}

### ErrorColumnSeries

{Images\ErrorColumnSeries.png}

### IntervalBarSeries

{Images\IntervalBarSeries.png}

### RectangleBarSeries

{Images\RectangleBarSeries.png}

### TornadoBarSeries

{Images\TornadoBarSeries.png}

### PieSeries

{Images\PieSeries.png}

### Custom series

You can create your own custom series by implementing the ISeries interface, or by deriving from one of the existing Series classes.
To make the series available for the tracker, you should also implement the ITrackableSeries interface.

### Base classes

- XYAxisSeries - base class for series that use X and Y axes.
- DataPointSeries - base class for series that contain a collection of DataPoints.