# Donut Chart

### Source Code - [See Rendered Output](Rendered-Samples/Donut-Chart-Sample.pdf)

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
chart.PieHole = .3; // Specify how large to make the hole in the pie chart.
foreach (var record in data)
{ // populate chart with our data.
    chart.AddSlice( record.Item1, record.Item2 );
}

// Step 3: Add the chart to the Stitch doc
doc.Add( chart );

// Render or save the document
var html = doc.Render();
~~~
