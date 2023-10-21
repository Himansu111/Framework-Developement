# Framework-Development
- [Bsics of framework](#Basics of framework)



##Basics of framework
_Test Data_


_Configuration_


_Code Reusability_


_Reprting_
*Spark Reporter
ExtentReports extentReports=new ExtentReports();

File file=new File(Spark.html);

ExtentSparkReporter sparkReporter = new ExtentSparkReporter("./TestUtilites\Spark.html"); //File to be stored in 

extentReports.attachReporter(sparkReporter);

Desktop.getDesktop().broswe(new File(report.html).toURI());

* Log levels
  
  -Fail
  _fail(Markup m)
  _fail(Media media) MediaEntityBuilder
  _fail(String details)
  _fail(Throwable t)
  _fail(String details, Media media)
  _fail(Throwable t, Media media)
  -Skip
  -Warning
  -Pass
  -info
  * Log different types of info to Extent Reports
    -Test -Bold,Italic
    extentReports.createTest("Text Based Test")
    .log(Status.Info, "<b>Info</b>");
    
    -XML
    String xmlData=xml file data;
    .log(Status.INFO,xmlData);
    .info(MarkupHelper.createCodeBlock(xmlData, CodeLanguage.XML));
    
    -JSON
    .log(Status.INFO, MarkupHelper.createCodeBlock(jsonData,CodeLanguage.json));
    
    -Collection Data(List,Set and Map)
    .log(Status.INFO, MarkupHelper.createOrderedList(mpaData));
    .log(Status.INFO, MarkupHelper.createUnorderedList(mpaData));
    
    -Highlight any message
    .log(Status.INFO, MarkupHelper.createLabel("This is hilighted message", ExtentColor.RED);
  
    -Exception
    Try {
        int i=5/0;
    } catch(Exception e) {
        extentReports
        .createTest("Exception Test1")
        .info(e);
    }

    Throwable t=new RuntimeException("This is custom Exception");
     extentReports
        .createTest("Exception Test2")
        .info(t);


    *Adding screenshot

    extentReports
    .createTest("ScreenShot 1","This for attaching ss")
    .info("This is a info message")
    .addScreenCaputreFromBase64String(base64Code);

    .addScreenCaputreFromBase64String(String s)
    .addScreenCaputreFromBase64String(String s,String title)
On clicking image will be display
  
    .addScreenCaputreFromBase64String(String path)
    .addScreenCaputreFromBase64String(String path, String title)
It will display preview

*Different attributes available for test in extentReports

_Author_

_Category_

_Device_

extentReports
    .createTest("Test 1","This for test desc ")
    .assignAuthor("Carlo")
    .assignCategory("Smoke")
    .assignDevice("chrome11")
    .fail("This is filled testcase");








    
    

  



