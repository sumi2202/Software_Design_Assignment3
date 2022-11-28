## Step 6: Sketch Views and Record Design Decisions 
| | |
| ---- | --- |
|Request Manager and Request Retriever for the client and server side|Allows communication between the client and server, where the cashier can input a certain command, such as canceling the transaction, and this would be received by the system (QA-4).|
|Product Data Retriever for the server side|Allows for the retrieval of data from the data source, which would be the local product database (QA-5).|
|Product Data Mapper for the server side |Takes the data collected and ensures it is delivered to any modules or components within the system that need it; if there is confidential information, the data mapper makes sure this information is secure and only delivered to the aspects of the system that need it (QA-3).|
|Product Data Controller for the server side|Contains the business logic that is related to the product data. This is primarily found in the business layer on the server side.|
|Cashier Interface View for the client side|Displays the main user interface (UI) for the cashier and acts as the main middleman between the cashier and the business layer on the client side.|
|Scanner Access Controller for the client side|Contains the business logic associated with the barcode scanner on the client side.|
|Keyboard Access Controller for the client side|Contains the business logic associated with the keyboard on the client side.|




**Sequence Diagram Method Table**
|**Method Name**|**Description**|**Element**|
| ----- | ------- | ------ |
|start()|Method that starts the application|CashierInterfaceView|
|startTransaction()|Starts the transaction; this is through using the keyboard|KeyboardAccessController|
|Boolean startTransactionValid()|Checks if the transaction is valid and then if true, returns a value back to the interface| CashierInterfaceView|
|scanProduct()|Scans product’s barcode|ScannerAccessController|
|getRequest()|Gets the request from the ScannerAccessController|RequestManager|
|sendRequest()|Sends this request over the server side’s RequestRetriever|RequestRetriever|
|requestProductData()|Requests the product’s data based on the request and information given|ProductDataController|
|mapProductData()|Maps the product data based on the barcode given|ProductDataMapper|
|getProductData()|Gets the price and name, as well as any other associated information|ProductDataRetriever|
|returnProductData()|Returns the retrieved product data to the ProductDataMapper|ProductDataRetriever|
|returnMappedProductData()|Returns the mapped product data received from the ProductDataRetriever|ProductDataMapper|
|validateRequestedProductData()|Validates the requested product data and forwards it to the RequestRetriever|ProductDataController|
|returnRequest()|Returns the request to the RequestManager that exists on the client side|RequestRetriever|
|sendRequestedData()|Sends the requested product data over to the CashierInterfaceView|RequestManager|
|displayProductInfo()|Method that displays information such as the product name and price to the cashier|CashierInterfaceView|
