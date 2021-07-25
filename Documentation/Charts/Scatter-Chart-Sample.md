# Scatter Chart

### Source Code - [See Rendered Output](Rendered-Samples/Scatter-Chart-Sample.pdf)

~~~cs
// Step 1: Create new StitchDocument
var doc = new StitchDocument();

// Step 2: Create the chart
var chart = new ScatterChart<double, double>();
chart.MeasuredAxis.AxisTitle = "Weight";
chart.LabeledAxis.AxisTitle = "Age";
chart.ChartTitle = "Age &amp; Weight Comparison of Boys vs Girls";
chart.LegendPosition = LegendPosition.Right;

// Populate chart
chart.AddPoint( "Boys", 7, 64 );
chart.AddPoint( "Boys", 9, 83 );
chart.AddPoint( "Boys", 4, 44 );
chart.AddPoint( "Boys", 5, 50 );
chart.AddPoint( "Boys", 11, 90 );

chart.AddPoint( "Girls", 7, 54 );
chart.AddPoint( "Girls", 9, 73 );
chart.AddPoint( "Girls", 4, 34 );
chart.AddPoint( "Girls", 5, 40 );
chart.AddPoint( "Girls", 11, 80 );

// set group colorings
chart.SetScatterGroupColor( "Boys", "blue" );
chart.SetScatterGroupColor( "Girls", "pink" );

// Step 3: Add the chart to the document.
doc.Add( chart );

// Render or save the document.
var html = doc.Render();
~~~
