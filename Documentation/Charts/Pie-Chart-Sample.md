# Pie Chart

### Source Code - [See Rendered Output](Rendered-Samples/Pie-Chart-Sample.pdf)

~~~cs
/** Data Setup - For DEMO **/
var data = new[] { new Tuple<string, double>( "Apple", 425 ),
                   new Tuple<string, double>( "Blueberry", 100 ),
                   new Tuple<string, double>( "Mixed Berry", 88 ),
                   new Tuple<string, double>( "Cherry", 218 ),
                   new Tuple<string, double>( "Key Lime", 172 ),
                   new Tuple<string, double>( "Pecan", 277 ),
                   new Tuple<string, double>( "Pumpkin", 199 )
};

// Step 1: Create new StitchDocument
var doc = new StitchDocument();

// Step 2: Create the chart.
var chart = new PieChart();
chart.ChartTitle = "2017 Pie Popularity Survey";
foreach (var record in data)
{ // populate chart with our data.
    chart.AddSlice( record.Item1, record.Item2 );
}

// Step 3: Add the chart to the Stitch doc
doc.Add( chart );

// Render or save the document
var html = doc.Render();
~~~

### Exploding Pie Slices - [See Rendered Output](Rendered-Samples/Pie-Chart-Exploded-Sample.pdf)

To explode a pie slice simply pass in an offset value between 0 and 1, 0 being
no offset and 1 being offset the entire chart radius.

~~~cs
chart.AddSlice( record.Item1, record.Item2, string.Empty, .2 );
~~~
