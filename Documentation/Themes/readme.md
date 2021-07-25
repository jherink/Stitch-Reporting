# Using Themes

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

// Step 3: Set the theme on the document.
// NOTE: This can be done any time before rendering.
doc.SetTheme( Theme.NeonGreen );

var html = doc.Render();
~~~

### HTML Raw Output
~~~HTML
<html lang="en">
   <head>
      <title></title>
      <meta name="viewport" content="width=device-width, initial-scale=1" />
      <meta content="text/html; charset=utf-8" http-equiv="content-type" />
      <style type="text/css">
         html{ box-sizing:border-box; }
         *,*:before,*:after{ box-sizing:inherit; }
         html{ -ms-text-size-adjust:100%;-webkit-text-size-adjust:100%; }
         body{ margin:0; }
         html,body{ font-family:Verdana,sans-serif;font-size:15px;line-height:1.5; }
         html{ overflow-x:hidden; }
         .w3-table,.w3-table-all{ border-collapse:collapse;border-spacing:0;width:100%;display:table; }
         .w3-table-all{ border:1px solid #CCC; }
         .w3-bordered tr,.w3-table-all tr{ border-bottom:1px solid #DDD; }
         .w3-striped tbody tr:nth-child(even){ background-color:#F1F1F1; }
         .w3-table-all tr:nth-child(odd){ background-color:#FFF; }
         .w3-table-all tr:nth-child(even){ background-color:#F1F1F1; }
         .w3-table td,.w3-table th,.w3-table-all td,.w3-table-all th{ padding:8px 8px;display:table-cell;text-align:left;vertical-align:top; }
         .w3-table th:first-child,.w3-table td:first-child,.w3-table-all th:first-child,.w3-table-all td:first-child{ padding-left:16px; }
         .w3-btn,.w3-btn-floating,.w3-dropnav a,.w3-btn-floating-large,.w3-btn-block,.w3-navbar a,.w3-sidenav a,.w3-pagination li a,.w3-hoverable tbody tr,.w3-hoverable li,.w3-accordion-content a,.w3-dropdown-content a,.w3-dropdown-click:hover,.w3-dropdown-hover:hover,.w3-opennav,.w3-closenav,.w3-closebtn,*[class*="w3-hover-"]{ -webkit-transition:background-color 0.25s,color 0.15s,box-shadow 0.25s,opacity 0.25s,filter 0.25s,border 0.15s;transition:background-color 0.25s,color 0.15s,box-shadow 0.15s,opacity 0.25s,filter 0.25s,border 0.15s; }
      </style>
      <style type="text/css">
         .stitch-theme{ color:#FFF;background-color:#16D620 !important;fill:#16D620; }
      </style>
      <style type="text/css"></style>
   </head>
   <body style="max-width:1024px !important;margin-right:25px;margin-left:25px;">
      <table class="w3-table w3-table-all">
         <caption></caption>
         <thead>
            <tr class="stitch-theme">
               <th>First Name</th>
               <th>Last Name</th>
            </tr>
         </thead>
         <tbody>
         </tbody>
         <tbody>
            <tr>
               <td>John</td>
               <td>Doe</td>
            </tr>
            <tr>
               <td>Jane</td>
               <td>Doe</td>
            </tr>
         </tbody>
         <tfoot>
         </tfoot>
      </table>
   </body>
</html>
~~~
