## Step 6: Sketch Views and Record Design Decisions 


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
