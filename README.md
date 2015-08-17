# Word add-in: Loading data into custom XML parts bound to content controls in a Word document

**Table of contents**

* [Summary](#summary)
* [Prerequisites](#prerequisites)
* [Key components of the sample](#components)
* [Description of the code](#codedescription)
* [Build and debug](#build)
* [Troubleshooting](#troubleshooting)
* [Questions and comments](#questions)
* [Additional resources](#additional-resources)

<a name="summary"></a>
##Summary

In this sample we show you how to use the [JavaScript API for Office](https://msdn.microsoft.com/library/b27e70c3-d87d-4d27-85e0-103996273298(v=office.15)) to write data to a set of custom XML parts that are bound to content controls within a Word document. The following is a  picture of the scenario in question.

![Screenshot of running sample](https://cloud.githubusercontent.com/assets/8550529/9298298/4b980684-4461-11e5-8c00-8f86701e55c2.PNG)

We are creating packing slips from customer order data. The packing slip document is shown on the left of the preceding screen shot, with our Office Add-in on the right as a task pane app. When you select an order using the order id drop-down in the task pane on the right and then click the Populate button, the packing slip document is populated with data from that order.  The sample uses the Javascript API for Office to interact with the Word document by populating custom XML parts defined in the document with order data. These custom XML parts are bound to content controls that define the UI or the document. To simplify this sample, the order data is stored in the same JavaScript file that creates the add-in. However, in a real application, that data could come from a data source anywhere on the web.


<a name="prerequisites"></a>
##Prerequisites
This sample requires the following:  

  - Visual Studio 2013 with Update 5 or Visual Studio 2015.  
  - Word 2013 or later
  - Internet Explorer 9 or later, which must be installed but doesn't have to be the default browser. To support Office Add-ins, the Office client that acts as host uses browser components that are part of Internet Explorer 9 or later.
  - One of the following as the default browser: Internet Explorer 9, Safari 5.0.6, Firefox 5, Chrome 13, or a later version of one of these browsers.
  - Familiarity with JavaScript programming and web services.

<a name="components"></a>
##Key components

* [InvoiceManagerSample/InvoiceManagerManifest/InvoiceManager.xml](https://github.com/OfficeDev/Word-Add-in-JavaScript-InvoiceManager/blob/master/InvoiceManagerSample/InvoiceManagerManifest/InvoiceManager.xml)
* [InvoiceManagerSample/PackingSlip.docx](https://github.com/OfficeDev/Word-Add-in-JavaScript-InvoiceManager/blob/master/InvoiceManagerSample/PackingSlip.docx)

•The InvoiceManagerWeb project, including the following files:

•Home.html file


•Home.js file

<a name="codedescription"></a>
##Description of the code

The second function, initializeOrder, does most of the important work. When the Populate button is chosen, this function first calls the  getByNamespaceAsync method of the  CustomXmlParts object to determine whether the packing slip form is already populated. If it is, the function calls the  deleteAysnc method of the  CustomXmlPart object to delete the existing data in the form. Then it calls the  addAsync method of the  CustomXmlParts object to repopulate the form with the selected data.

<a name="build"></a>
##Build the sample


Choose the F5 key in Visual Studio 2012 to build and deploy the app and open it in Word 2013.

Run and test the sample


1.Open the InvoiceManager.sln file in Visual Studio 2012.


2.Choose the F5 key in Visual Studio 2012 to build and deploy the app.


3.In the app task pane, select an order in the Order ID drop-down list.


4.Choose Populate to populate the forms in the Word document with information from the selected order.


You can view a list of the custom XML parts in a document by opening the XML Mapping pane in Word (Developer tab).

<a name="troubleshooting"></a>
## Troubleshooting

- If the add-in starts with a blank document, ensure that the **Start Document** property of the InvoiceManager project is set to *PackingSlip.docx* and not just to Word.
![](https://cloud.githubusercontent.com/assets/8550529/9298211/b29908a8-445f-11e5-8887-0b3e6a9c8649.png)
- If the add-in does not appear in the task pane, Choose **Insert > My Add-ins >  InvoiceManagerSample**.

<a name="questions"></a>
## Questions and comments

- If you have any trouble running this sample, please [log an issue](https://github.com/OfficeDev/Word-Add-in-JavaScript-InvoiceManager/issues).
- Questions about Office Add-ins development in general should be posted to [Stack Overflow](http://stackoverflow.com/questions/tagged/office-addins). Make sure that your questions or comments are tagged with [office-addins].


<a name="additional-resources"></a>
## Additional resources ##

- [Office Add-ins](http://msdn.microsoft.com/library/office/jj220060.aspx)
- [Bindings object (JavaScript API for Office)](http://msdn.microsoft.com/library/office/apps/fp160966.aspx)
- [Binding to regions in a document or spreadsheet](http://msdn.microsoft.com/library/office/apps/fp123511(v=office.15).aspx)


## Copyright
Copyright (c) 2015 Microsoft. All rights reserved.


