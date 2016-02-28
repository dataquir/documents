Apppendix
=========

Event Tracking Script
---------------------
Most of the search analytics are readily available on the dashboard as soon as you integrate dataQuir search API with your application except the following:

* Stats related to page view
* Stats related to search result click
* Stats related to auto-complete

To get the complete report on the analytics dashboard you need to install dataQuir event tracking javascript The dataQuir JavaScript (JS) embed code is optimized for integration on both desktop and mobile web sites.

* Get the JS embed code from Dashboard -> Settings -> Integration -> Account IDs, SDKs.
* Copy/paste it verbatim inside the <head></head> section of your website.
* your code should look like this:

::

	var dataquir = dataquir || {event:[], user:[], engine:[]};
		(function () {
                var dq = document.createElement('script');
                dq.type = 'text/javascript';
                dq.async = true;
                dq.src = ('https:' == document.location.protocol ? 
                                 'https://events.dataquir.com/dc/resources' : 'http://events.dataquir.com/dc/resources')+                                        '/js/dq-event-recorder.js';           
                var  s = document.getElementsByTagName('script')[0];
                s.parentNode.insertBefore(dq, s);
			})();

	dataquir.engine.push({"engineId":"Engine Id", "apiKey": "Your dataQuir engine public API Key"});
	dataquir.user.push({"userId": "Website's user identifier", "sessionId": "Session Id set by website"});
	
*Note:*

* All JS calls in dataQuir are asynchronous, support SSL, and will not slow down your website.
* The dataQuir JS embed code doesn’t depend on the presence of JQuery or any other third party JS library.

Events
******
An event is an action that a user takes in your mobile application or on your website. dataQuir records the action using an Event Type and optional associated key:value-based Event attributes. 

Currently dataQuir event tracking script tracks following events:

* Page View Event
* Search Result Click Event
* Auto-complete Click Event

Page View Event
***************

Event Type: **page_view**

Event Attributes:

* itemId
* itemName
* pType
* categoryId

::

	dataquir.event.push({
			"page_view":{
				"itemId": "Test01",
				"itemTitle": "Test Product",
				"pType": "idp", //idp - Item Detail Page
				"categoryId": "Cat01"
			}
		   });


Search Result Click Event
*************************

Event Type: **clk_srp**

Event Attributes:

* query
* position
* itemId
* itemTitle

::

	dataquir.event.push({
		"clk_srp":{
			"query": "Test Product",
			"position":2,
			"itemId":"itemId321",
			"itemTitle":"iPhone S6"
			}
		});


Auto-complete Click Event
*************************

Event Type: **clk_auto**

Event Attributes:

* query
* position

::

	dataquir.event.push({
		"clk_auto":{    
			"query": "Test Product",
			"position":2
			}
		});
		   
   