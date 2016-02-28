Getting Started
==========================
Simplest way to integrate dataQuir Search & Engagement Service, you need to follow four easy steps
	* Create `Search & Engagement  Engine`
	* Define Feed Plan
	* Upload Feed
	* Integrate Search / Engagement APIs in your application


Create Engine
-------------
The very first step to get started with dataQuir services is to create a `Search & Engagement Engine` for your application.
You need to provide following details:
	* Engine Name \- Any name by which you can easily identify your application
	* Engine Type \- There are two options for the engine type, one is `Custom` and the other is `Crawl`.  With `Custom` engine type, you are required to provide the feed definition and upload feed for getting the engine fully functional. On the other hand with `Crawl` engine type, you not worry about anything, your feed plan is automatically created and content is crawled by dataQuir crawler.
	* Website Url \- This url is used as base url if you have chosen engine type as `Crawl`.
	* Time Zone \- Time Zone is required so that the search and engagement analytics reports are created as per your time zone.
	* Business Type
	
	.. image:: images/create-engine.png
	
**Note**:
For each engine a unique `engine-id` is created that is used in all your search / engagement API paths


Define Feed Plan
----------------
Next you need to define the feed plan depending upon the nature of your business, such as a product feed plan for an E-Commerce application or news feed plan for a News Portal.  While defining the feed plan you are required to provide the list of fields and some details for each of the field such as \- data type, whether the field  will be used for search and if field values can be single valued or multi-valued.  Once you define and save the feed plan, a link to download sample feed is created for the engine. 

**Note**
	* Feed can be uploaded the either CSV format or JSON format.
	* For CSV format fields are supposed to be comma separated.
	* Single vs MultiValued fields 
	* A single valued field is used for which there can be just one value for the field, e.g. movie_title, there can be only one title for a movie.
	* A multivalued field is required when there are more than one value present for the field, e.g. movie_genre, there can be multiple genres associated with a movie. 
	* In case of multi-valued field, all the field valued need to be separated by pipe(|). 

Upload Feed
-----------
Third step is to upload your feed. You can download the sample feed file for your engine, create your item feed similar to the sample feed and upload through the dashboard. Feed upload takes some time depending upon the size of the feed. Once feed upload is finished, your search APIs are ready for the integration

API Integration
---------------
Fourth and final step is to integrate search / engagement APIs in your application.
After successful feed upload you can immediately test your search API using 'Try Now'. 

Your
	* Search API: http://api.dataquir.com/v1/engines/<your-search-engine-id>/search?q=<query string>
	* Auto-complete API: http://api.dataquir.com/v1/engines/<your-search-engine-id>/search?q=<query string>
For details of advanced search and auto-complete API parameters such as filter / facet / geo-queries / spell check, please refer our API documentation. See :doc:`api`.
