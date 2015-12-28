#DefaultItemsPerPage

[[_TOC_]]

##About

Gets or sets the number of items per page. Lowering the number will decrease the number of results viewed per page. If this number is lower than the number of results, numbers indicating pagination will appear at the bottom of the report and the addition results will go to the next page. One row will be hyper links showing record ranges in denominations of whatever you set your DefaultItemsPerPage to. A second row will allow you to page forward, backward or enter a page number to jump to.

These items will affect all rows in all tables on the report, in other words both the Summary and Fields tab. The Summary and the Fields tables will not be paginated independently.

![DefaultItemsPerPage](/API/CodeSamples/DefaultItemsPerPage/DefaultItemsPerPage.png)

##Global.asax (C♯)

```csharp
//main class: inherits DatabaseAdHocConfig or FileSystemAdHocConfig
public class CustomAdHocConfig : Izenda.AdHoc.DatabaseAdHocConfig
{
  // Configure settings
  // Add custom settings after setting the license key and connection string by overriding the ConfigureSettings() method
  public static void InitializeReporting() {
    //Check to see if we've already initialized.
    if (HttpContext.Current.Session == null || HttpContext.Current.Session["ReportingInitialized"] != null)
      return;
    AdHocSettings.LicenseKey = "INSERT_LICENSE_KEY_HERE";
    //Creates a connection to Microsoft SQL Server
    AdHocSettings.SqlServerConnectionString = "INSERT_CONNECTION_STRING_HERE";
    AdHocSettings.AdHocConfig = new CustomAdHocConfig();
    AdHocSettings.DefaultItemsPerPage = 100; //The relevant setting
    HttpContext.Current.Session["ReportingInitialized"] = true;
  }
}
```

