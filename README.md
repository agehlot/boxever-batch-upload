# boxever-batch-upload
You need to follow the below steps to successfully upload the orders to Boxever.
# Installing the python
- Install the latest python on your local machine.
- Replace clientKey and apiToken values in the python script file.
# Preparing the batch file
1. Copy the sample order json from Sitecore documentation repository
   [https://doc.sitecore.com/cdp/en/developers/sitecore-customer-data-platform--data-model-2-0/sitecore-cdp-order-data-model-for-batch-api.html]()
1. Convert the formatted json into single line json (as currently this is required to successfully parsed by Boxever server). You can use this online tool for single line conversion. [https://tools.knowledgewalls.com/online-multiline-to-single-line-converter]()
1. Copy the single line json content, create ```batchUploadOrder.json``` file on your current folder, paste the copied json and save the file.
1. Apply gzip compression on the **single line json** ```batchUploadOrder.json``` using 7-zip tool of any other tool that can produce .gz file like ```batchUploadOrder.json.gz```
1. On the command prompt, reach to the current directory of these files
1. Execute the below command to start the processing.
   phthon.exe is the executable
   batchUpload.py is python script
   batchUploadOrder.json.gz is the file to be upload in .gz format
   ```python.exe batchUpload.py batchUploadOrder.json.gz```
1. Follow the url you are getting from the response of this execution to check the status of uploaded batch file using Postman along with proper Authorization header. Something like this.
   https://api.boxever.com/v2/batches/86450d28-0cad-4128-8887-8a5b12f7aba7

