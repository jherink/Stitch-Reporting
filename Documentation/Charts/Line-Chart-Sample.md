# Line Chart

### Source Code - [See Rendered Output](Rendered-Samples/Line-Chart-Sample.pdf)

~~~cs
data.Rows.Add( "NY City", "Monday", 43 );
data.Rows.Add( "NY City", "Tuesday", 53 );
data.Rows.Add( "NY City", "Wednesday", 50 );
data.Rows.Add( "NY City", "Thursday", 57 );
data.Rows.Add( "NY City", "Friday", 59 );
data.Rows.Add( "NY City", "Saturday", 69 );

data.Rows.Add( "Chicago", "Monday", 22 );
data.Rows.Add( "Chicago", "Tuesday", 47 );
data.Rows.Add( "Chicago", "Wednesday", 24 );
data.Rows.Add( "Chicago", "Thursday", 36 );
data.Rows.Add( "Chicago", "Friday", 59 );
data.Rows.Add( "Chicago", "Saturday", 81 );

data.Rows.Add( "Los Angeles", "Monday", 67 );
data.Rows.Add( "Los Angeles", "Tuesday", 71 );
data.Rows.Add( "Los Angeles", "Wednesday", 72 );
data.Rows.Add( "Los Angeles", "Thursday", 84 );
data.Rows.Add( "Los Angeles", "Friday", 64 );
data.Rows.Add( "Los Angeles", "Saturday", 88 );

// Step 1: Create new StitchDocument
var doc = new StitchDocument();
doc.SetTheme( Theme.SeaGreen );

// Step 2: Create the chart.
var chart = new LineChart<string, double>();

chart.LegendPosition = LegendPosition.Right;
chart.ChartTitle = "This Weeks Tempuratures in Major US Cities";
chart.MeasuredAxis.AxisTitle = "Tempurature"; // Label the axis
chart.LabeledAxis.AxisTitle = "Day Of Week";
foreach (DataRow record in data.Rows)
{ // populate the chart.
    chart.AddPoint( record["City"].ToString(), record["Day Of Week"] as string, (double)record["Tempurature"] );
}

// Step 3: Add the chart to the Stitch doc
doc.Add( chart );

// Render or save the document
var html = doc.Render();
~~~
