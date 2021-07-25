# Create Your Own Stitch Theme!!!

You can create your own Stitch theme by using the [Stitch Theme Template](Stitch-Theme-Template.css)

An example is the custom theme <bold>"Dark Knight"</bold>. [View Theme CSS](Dark-Knight.css)

### Use the custom theme

~~~cs
// Step 3: Set the theme on the document 
// by passing the path to the theme's CSS
doc.SetTheme( "Resources\\Dark-Knight.css" );
~~~

### All Code - [See Output](Dark-Knight-Custom-Theme-Sample.pdf)

~~~cs
// Step 1: Create new StitchDocument
var doc = new StitchDocument();

// Step 2: Add elements to Stitch document
var dt = new DataTable();
dt.Columns.Add( "First Name" );
dt.Columns.Add( "Last Name" );
dt.Rows.Add( "John", "Doe" );
dt.Rows.Add( "Jane", "Doe" );
doc.Add( new Table( dt ) );

// Show a pie chart to see Theme in action!
var chart = new PieChart();
for (int i = 1; i <= 9; i++)
{
    chart.AddSlice( $"Line {i}", 1 );
}
doc.Add( chart );

// Step 3: Set the theme on the document 
// by passing the path to the theme's CSS
doc.SetTheme( "Resources\\Dark-Knight.css" );

var html = doc.Render();
~~~
