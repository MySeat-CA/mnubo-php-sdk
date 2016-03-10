mnubo Python SDK
Table of Content
1. Introduction

2. Architecture

3. Pre-requisites

4. Installation & Configuration

5. Usage

6. Important notes

7. Source code

8. Known limitations

9. References

1. Introduction
To connect your Python application to our API use the mnubo Python SDK.

2. Architecture
OwnerServices

create
claim
update
delete
ObjectServices

create
update
delete
EventServices

send
SearchServices

search
search_datasets
BatchServices

owners
objects
events
3. Pre-requisites
Python 2.7
4. Installation & Configuration
pip install mnubo
5. Usage
Initialize the MnuboClient

from mnubo.mnubo_client import MnuboClient

mnubo = MnuboClient('CLIENT_ID', 'CLIENT_SECRET', 'HOSTNAME')
Use the Owner Services

To create owners on the mnubo SmartObject platform, please refer to the data modeling guide to format correctly the owner's data structure.

Create an Owner

response = mnubo.owner_services.create('OWNER_IN_JSON')
Claim a Smart Object for an Owner

response = mnubo.owner_services.claim('USERNAME', 'DEVICE_ID')
Update an Owner

response = mnubo.owner_services.update('OWNER_IN_JSON')
Delete an Owner

response = mnubo.owner_services.delete('USERNAME')
Use the Smart Objects Services

To create smart objects on the mnubo SmartObject platform, please refer to the data modeling guide to format correctly the smart object's data structure.

Create a Smart Object

response = mnubo.smart_object_services.create('OBJECT_IN_JSON')
Update a Smart Object

response = mnubo.smart_object_services.update('OBJECT_IN_JSON')
Delete a Smart Object

response = mnubo.smart_object_services.delete('DEVICE_ID')
Use the Event Services

To send events to the mnubo SmartObject platform, please refer to the data modeling guide to format correctly the event's data structure.

Send an Event

response = mnubo.event_services.send('EVENT_IN_JSON')
Use the Search Services

To send search queries to the mnubo SmartObject platform, please refer to the Search API documentation to format your queries correctly.

Search Query

response = mnubo.search_services.search('QUERY')
Search Datasets Query

response = mnubo.search_services.search_datasets('QUERY')
Use the Batch Services

To create or update owners or objects in batch, please refer to the Batch section of either the SmartObject or the Owners in the API documentation to format the data correctly.

Batch Owners

response = mnubo.batch_services.owners('OWNERS_IN_JSON')
Batch Objects

response = mnubo.batch_services.objects('OBJECTS_IN_JSON')
Batch Events

'REPORT_RESULTS': is a boolean that specify if a body with the result of each individual event should be returned.

response = mnubo.batch_services.events('EVENTS_IN_JSON', 'REPORT_RESULTS')
6. Important notes
7. Source code
8. Known limitations
9. References
