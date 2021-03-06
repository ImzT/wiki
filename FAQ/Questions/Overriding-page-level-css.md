#Overriding page level css

[[_TOC_]]

##Report Viewer

###Toolbar

Izenda does not currently offer a simple method of editing this portion of the report viewer. However, it is still possible. To edit the CSS for the toolbar on the Report Viewer page, follow the steps below:

* Create a new file in your **resources/css** directory on your website called reportviewer.css
* Open ReportViewer-Head.ascx in **Resources/html**
* Insert the following line into the page: ``<link rel="stylesheet" type="text/css" href="./Resources/css/reportviewer.css" />``
* Insert the following class overrides into the reportviewer.css file

```css
/*Controls the style of the entire toolbar*/
.nav-tabs {

}

/*Controls the style of just the buttons section of the toolbar*/
.btn-toolbar {

}

/*Controls each button's div element*/
.btn-toolbar div {

}

/*Controls the tabs on the toolbar: Filters, Fields, Pivots*/
.nav-tabs li {

}
```

To override other classes that are not included in this sample, you can easily add the appropriate override by using the developer tools that come with different browsers to inspect the HTML and pick out the elements you wish to modify the CSS for.

##Report Designer

###Tabs

Download the [[css.zip|http://www.izenda.com/Site/KB/uploads/attachments/css.zip]] file and extract the **tabs.css** file to the resources/css folder within your application. Make sure that it is named tabs.css, then enter the dynamically generated tabs.css link into your browser (example:  "/your_site_url/resources/css/tabs.css"). 

There are two ways that you can set this property in your application. 

A. Set [[TabsCssUrl|/API/CodeSamples/TabsCssUrl]] = "your_site_url/resources/css/tabs.css" in ``InitializeReporting()`` in your global.asax.

**-OR-**

B. On the Settings.aspx page, go to the **Appearance (images and css)** tab and insert the absolute path to the tabs.css file in the **Tabs CSS URL** text box (example: your_site_url/resources/css/tabs.css) . We recommend option A to adhere to best practices.

Once you have set the path to tabs.css, you can use the program of your choice to edit it to match your company's colors or fonts.

* [[HeaderStyleCss:|/API/CodeSamples/HeaderStyle]] This is also applicable to the report designer and should facilitate customization.

###Toolbar

With the zip file you downloaded from the last section, extract the **toolbar.css** file into the resources/css folder within your application. Ensure the file is still named toolbar.css, then enter the link generated into your browser (example /your_site_url/resources/css/toolbar.css).

You can either set the [[ToolbarCssUrl|/API/CodeSamples/ToolbarCssUrl]] setting to your new URL or you can enter it into the **Toolbar CSS URL** text box on **settings.aspx**

##Report List

To use custom CSS for the Report List page, you can use the method described above for the Report Viewer to obtain the desired results. However, the file will be called ``reportlist.css`` and the page it should be included on is **ReportList-Head.ascx**. The include statement should look similar to the following:
``<link rel="stylesheet" type="text/css" href="./Resources/css/reportlist.css" />``

The CSS classes you will have to override will also be different than the ReportViewer page CSS classes. Here are some examples of classes that can be overridden.

###Pre version 6.7

Before version 6.7, the HTML element styles were hard-coded into the application, but could be overridden by placing a style tag into the page right after the end of the form. Here is a code sample.

```css
<uc1:Header ID="Header1" runat="server" />
<form id="Form1" method="post" runat="server">
<cc1:ReportList runat="server" id="reportList"></cc1:ReportList>
</form>
<style type='text/css'>
		                
A:link {font-family: Verdana, Geneva, Arial, Helvetica;}
A:visited {font-family: Verdana, Geneva, Arial, Helvetica;}
A:active {font-family: Verdana, Geneva, Arial, Helvetica;}
A:hover {font-family: Verdana, Geneva, Arial, Helvetica;}
		                
table.ReportsListTable
{
    border-color:white;
    border-style:solid;
    border-width:2px;			
    font-family: Verdana, Geneva, Arial, Helvetica;
}
table.ReportsListTable tr
{
    background-color:red;
}
tr.ReportsListHeader td
{
    border-width:1px;
    border-style:solid;
    border-color:white;
    background-color:silver;
}
</style>
```

###Version 6.7+

As of version 6.7, the downloadable RI includes two files in the Resources -> html folder called ReportList-Body.ascx and ReportList-Head.ascx. To change CSS in this model, generally you will simply have to open the page body and insert your style. Below is an example of styling you can use. Simply insert the following at the bottom of the ReportList-Body.ascx file, or you can create a new CSS file and include that into the head or body portion in a CSS tag.

```css
<style type="text/css">
.blue-panel
{
  background-color:#0d70cd;
    border-color:#0d70ff;
    border-style:solid;
    border-width:2px;		
    border-radius:25px;
}
		                
.blue-panel ul
{	
    font-family: Verdana, Geneva, Arial, Helvetica;
    list-style-type: none;
    padding: 0px;
    margin: 0px;
}

.blue-panel ul li
{
    background-color:#0d70cd;
    background-image: url('../../rs.aspx?image=ModernImages.report-icon.png');
    background-repeat: no-repeat;
    background-position: 0px 5px; 
    padding-left: 14px; 
}

.blue-panel ul li a
{
  color: white;
}

.blue-panel h2
{
    border-width:1px;
    border-style:solid;
    border-color:white;
    background-color:silver;
}

.blue-panel a:hover
{
  background-color:#0d70ff !Important;
  color: white;
}

.blue-panel a.selected
{
  background-color: #4540b9;
  color:white;
}
#RL_QuickSearchBox
{
  font-family: 'Comic Sans MS' !Important;
}
</style>
```

##Dashboards

You can override page CSS on the Dashboards.aspx page by using the following properties to include a CSS file you specify, or you can open **Dashboards-head.ascx** and **Dashboards-body.ascx** and include your own CSS using the methods described above for the Report Viewer and Report List.

AdHocSettings Properties applicable to Dashboards.aspx

* [[DashboardsCssUrl|/API/CodeSamples/DashboardsCssUrl]]

_**Note:** You may need to append the **!Important** flag onto certain CSS properties so they will override the existing styles._

##CSS Configuration

You can make changes to css by adding a custom.css file to the dependency chain

````html
<!DOCTYPE html>
<head>
...
<link rel='stylesheet' href='Resources/css/custom.css' />
...
</head>
````

Then, in the custom.css file you created, you can make any edits you need to overwrite Izenda's styles; this includes bootstrap stylings. You may find it necessary to use !important in some cases.

````css
.whatever-class {
font-size: 130% !important;
}

#whatever-id {
background-color: rgba(0,0,0,.7);
}
````

You will also notice that we now are minifying the css files; the js files will follow suit down the road. The min.css extension should be visible as a reference in the views.

````
<link rel='stylesheet' href='Resources/css/whatever.min.css' />

````

