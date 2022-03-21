## Latent Data Workshop

Very wip.

We could also call this *Knowledge Mining Workshop* or *Cognitive Search Workshop*.  

These are broad terms used to describe technological solutions that enable users to find the information they need quickly and easily from a large volume of data - often in a variety of formats and data stores.  Traditionally, this data is _not_ easily found in corporate databases.  Think pdfs of POs, scanned documents, excel and powerpoint files, or even raw images.  This data is quite valuable, but it's difficult to perform analytics on it since it isn't in a traditional data format.  

We will use my hack-y data, but you could also use your data.  In fact, I would recommend this.  

I don't have step-by-step, click-by-click instructions.  I assume you know a little bit about Azure and the portal.  If at any point you are lost or don't understand the instructions (or why you are doing them), **please let me know right way**.  

## Labs

We are going to build something that looks like this workflow:

![](./img/05.jpg)

Lab 000:  Understand the data and use case

* clinical trials data
* davewdemoblobs
* clinical-trials
  * lots of pdfs
* https://davewdemoblobs.blob.core.windows.net/clinical-trials?sv=2019-02-02&st=2019-08-24T12%3A44%3A00Z&se=2025-08-25T12%3A44%3A00Z&sr=c&sp=rl&sig=h6zAqAQ%2BGMdkSJgTNlgUqGo0KkLpHmP5iLVVrX5%2B1PM%3D
* copy the data to your storage account

Objectives:
You will be able to quickly and easily ingest this content, build custom skills to identify and extract specific medical terms related to disease conditions and then either search for information through a web front end or do analytics on the data using something like PowerBI.  
* a fully searchable repository that will allow users to find and extract really powerful information, even if they are not trained medical professionals.
* build an Azure Cognitive Search Index and Knowledge Store repository.
* build custom skills to extend the solution 
* create a basic web page front end to visualize your search results. 
* build a PowerBI dashboard on top of your Knowledge Store so you can use your data store for data visualization and advanced analytics. 
* index data from an AzureSQL data source. 

Lab 001:  Setup Your Dev environment

* choose of dev tools
  * vscode
  * C#, python, javascript
  * [Azure Functions extension](https://marketplace.visualstudio.com/items?itemName=ms-azuretools.vscode-azurefunctions)
  * [Postman](https://www.getpostman.com/downloads/) to create and submit collections of REST requests.

* Install Azure Storage Explorer
  
Lab 002:  Spin Up Necessary Azure Services

* create Azure Storage Account and upload the data to a container using Azure Storage Explorer
* Create an Azure Cognitive Search service account.  **Standard should be fine**
* [Create a Cognitive Services resource](https://docs.microsoft.com/en-us/azure/cognitive-services/cognitive-services-apis-create-account?tabs=multiservice%2Cwindows) so we can do things like Computer Vision, text analytics, LUIS, etc.  

* [Lab 003: Index the PDFs and other files](./Lab003.md)
* [Lab 004: Build a simple search front-end](./Lab004.md)
* [Lab 005: Create a Basic Custom Skill](./Lab005.md)
  * here we build a basic azfunc
* [Lab 006: manipulating AzSearch programmatically](./Lab006.md)
  * now we use the azfunc to populate new fields in an index
* [Lab 007: adding a custom analyzer](./Lab007.md)
  * we will add a phonetic search for the new field
* [Lab 008: Ranking and Scoring Profiles](./Lab008.md)
  * how can you influence the ranking and score algorithms for your custom purpose

### Advanced Labs (optional)

These labs cover custom skills and other "data science" topics.  

* [Lab 010: Identify custom entities](./Lab010/Lab010.md)
  * we use a custom AI skill to extract your "special" entities from your documents, instead of the "canned" entities that are provided out-of-the-box
  * named entity recognition (NER) using BERT and AMLS
  * deploy custom skills

### Analytics Labs

* [Lab 020: analyzing knowledge store data](./Lab020.md)

### Other Optional Labs

* [Lab 050: indexing "Structured" Data](./Lab050.md)
  * we will index data from a SQL Server, but conceptually this is no different for any relational database.  
* [Lab 060: Search Telemetry](./Lab060.md)




## My Notes

* rgAzureSearch
* other topics for the workshop
  * dl:  https://github.com/Microsoft/MCW-Cognitive-Services-and-Deep-Learning
  * classification
  * sentiment analysis
  * text summarization
  * NER
  * annotate text with something like the CIA Cryptonym skill:  https://www.maryferrell.org/php/cryptdb.php

## Alternative datasets

[Some sample pdf, docx, html, png, and jpeg files](https://github.com/Azure-Samples/azure-search-knowledge-mining/tree/master/sample_documents) that you can use if you don't have some data to use.  

## References and Other Documentation

[References](./references.md)

https://github.com/Azure-Samples/azure-search-knowledge-mining
