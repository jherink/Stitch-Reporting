# Bar Chart (With Multiple Bar Groups)

### Source Code - [See Rendered Output](Rendered-Samples/Multiple-Bar-Groups-Chart-Sample.pdf)

~~~cs
/** Data Setup - For DEMO **/
var data = new DataTable();
data.Columns.AddRange( new[] { new DataColumn( "Year", typeof( int ) ),
                               new DataColumn( "Pie", typeof( string ) ),
                               new DataColumn( "Votes", typeof( int ) ) } );

data.Rows.Add( 2015, "Apple", 377 );
data.Rows.Add( 2015, "Blueberry", 112 );
data.Rows.Add( 2015, "Mixed Berry", 68 );
data.Rows.Add( 2015, "Cherry", 225 );
data.Rows.Add( 2015, "Key Lime", 144 );
data.Rows.Add( 2015, "Pecan", 300 );
data.Rows.Add( 2015, "Pumpkin", 220 );

data.Rows.Add( 2016, "Apple", 398 );
data.Rows.Add( 2016, "Blueberry", 106 );
data.Rows.Add( 2016, "Mixed Berry", 75 );
data.Rows.Add( 2016, "Cherry", 250 );
data.Rows.Add( 2016, "Key Lime", 199 );
data.Rows.Add( 2016, "Pecan", 244 );
data.Rows.Add( 2016, "Pumpkin", 220 );

data.Rows.Add( 2017, "Apple", 425 );
data.Rows.Add( 2017, "Blueberry", 100 );
data.Rows.Add( 2017, "Mixed Berry", 88 );
data.Rows.Add( 2017, "Cherry", 218 );
data.Rows.Add( 2017, "Key Lime", 172 );
data.Rows.Add( 2017, "Pecan", 277 );
data.Rows.Add( 2017, "Pumpkin", 199 );

// Step 1: Create new StitchDocument
var doc = new StitchDocument();

doc.SetTheme( Theme.Purple ); // mix it up.

// Step 2: Create the chart.
var chart = new BarChart();
chart.AxisOrientation = Orientation.Vertical;
chart.LegendPosition = LegendPosition.Right;
chart.ChartTitle = "Pie Popularity Poll Results";
chart.MeasuredAxis.AxisTitle = "Number of People"; // Label the axis
foreach (DataRow record in data.Rows)
{ // populate the chart.
    chart.AddToBarGroup(record["Year"].ToString(), record["Pie"] as string, (int)record["Votes"]);
}

// Step 3: Add the chart to the Stitch doc
doc.Add( chart );

// Render or save the document
var html = doc.Render();
~~~
