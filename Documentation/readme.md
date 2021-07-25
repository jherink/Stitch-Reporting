# Getting Started

~~~cs
// Step 1: Create new StitchDocument
var doc = new StitchDocument();

// Step 2: Add elements to the document
doc.Add( new Paragraph( "Hello World!" ) );

// Step 3: Render the document
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
         .w3-btn,.w3-btn-floating,.w3-dropnav a,.w3-btn-floating-large,.w3-btn-block,.w3-navbar a,.w3-sidenav a,.w3-pagination li a,.w3-hoverable tbody tr,.w3-hoverable li,.w3-accordion-content a,.w3-dropdown-content a,.w3-dropdown-click:hover,.w3-dropdown-hover:hover,.w3-opennav,.w3-closenav,.w3-closebtn,*[class*="w3-hover-"]{ -webkit-transition:background-color 0.25s,color 0.15s,box-shadow 0.25s,opacity 0.25s,filter 0.25s,border 0.15s;transition:background-color 0.25s,color 0.15s,box-shadow 0.15s,opacity 0.25s,filter 0.25s,border 0.15s; }
      </style>
      <style type="text/css">
         .ansi-a{ width:8.5in; }
      </style>
   </head>
   <body>
      <div id="pages">
         <div id="a" class="ansi-a" style="margin:0.5in 0.5in 0.5in 0.5in;" page-number="1">
            <p>Hello World!</p>
         </div>
      </div>
   </body>
</html>
~~~
