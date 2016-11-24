# JIRA_ISP_TimeCounter
Integration of tools for time counter

The idea is to record time using HCP via a SAPUI5 frame, storing the data in HANA database instances and replicate the data to time recording tools such as JIRA or ISP.

The initial approach was to follow two relevant blog posts:
A) how to create oDATA service in HANA trial: https://blogs.sap.com/2015/03/17/how-to-create-a-new-odata-service-using-the-web-based-workbench/
B) how to consume: https://blogs.sap.com/2015/03/18/how-to-consume-a-hana-xs-datasource-on-the-hana-trial-landscape/

Those blogs were written back in 2015, and some instructions are not needed anymore (that's easier now). I will list them here and send the list to the blog owner afterwards.
A) 1- There is not "HANA XS <shared>" option in HCP trial. We have to use "HANA MCD";    
    2- I could not run the SQL commanf "SELECT SCHEMA_NAME FROM "HCP"."HCP_DEV_METADATA";", so I skipped that step;
    3 - All references to <NEO_schema_name> were changed to SCHEMA name displayed in the header of the page
    4 - My file structure in SAP HANA Web-based Development Workbench: Catalog did not have the folders <username> -> <dev>, so I created the folder "myproducts" diectly under "Content" folder. So, some steps that refer to the path <username>.dev.myproducts must be adapted.
    5 - The whole step 4 (user roles and privileges) was skipped. I could not activate some file due to lack of authorization.

B) 1 - For the consumption of the OData, there was no need to install proxy in my local machine. It seems that now the connection is native to the HCP.
   2 - The same for Cloud Connector settings. It was not needed at all.
   3 - For destination configuration, the following fields were filled with different values:
       ProxyType:	Internet
       
Going until the end of the tutorial, I could bind and show the Master-Details Fiori page, with my tables data - there were some issues, which I am still investigating.


