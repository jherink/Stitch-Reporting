# Exporting To Other Formats

We provide an interface, [IExporter](../../master/src/Stitch/Export/IExporter.cs), for exporting Stitch documents to a document format of your choice
using your own implementations or a third party tool. 

Stitch provides a [PDF Exporter](../../master/src/Stitch/Export/PDFExporter.cs) that uses 
[wkhtmltopdf](https://wkhtmltopdf.org/) to render it's HTML content to PDF. 

For example if we implemented an export method that exported the HTML to raw text:

~~~cs
using Stitch.Export;

...

public class RawTextExport : IExporter
{
    public byte[] Export( string content )
        {
            return Encoding.UTF8.GetBytes( content );
        }

    public void Export( string content, Stream outputStream )
        {
            new StreamWriter( outputStream ).Write( content );
        }
}
~~~

The custom exporter then can be used to export the Stitch document.

~~~cs
var doc = new StitchDocument();
doc.Add( new Paragraph( "Hello World!" );

// Create exporter
var exporter = new RawTextExport();
var exportPath = Path.ChangeExtension( Path.GetTempFileName(), ".txt" );

doc.Export( exporter, exportPath );
~~~
