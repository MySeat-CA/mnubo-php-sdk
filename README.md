# mnubo PHP SDK

Table of Content
================

[1. Introduction](#section1)

[2. Architecture](#section2)

[3. Pre-requisites](#section3)

[4. Usage](#section4)

---
#<a name="section1"></a>1. Introduction

To connect your PHP application to our API use the mnubo PHP SDK.

---
#<a name="section3"></a>2. Architecture


* `OwnerServices`
  - `create`
  - `claim`
  - `update`
  - `delete`

* `ObjectServices`
  - `create`
  - `update`
  - `delete`

* `EventServices`
  - `send`
  
* `SearchServices`
  - `search`
  - `search_datasets`
  
* `BatchServices`
  - `owners`
  - `objects`
  - `events`


---
#<a name="section3"></a>3. Pre-requisites

- PHP 5.4
- PHP-CURL


---
#<a name="section4"></a>4. Usage

### Initialize the MnuboClient

```PHP
$mnubo = new \Mnubo\Client('CLIENT_ID', 'CLIENT_SECRET', 'HOSTNAME');
```

### Use the Owner Services
To create owners on the mnubo SmartObject platform, please refer to
the data modeling guide to format correctly the owner's data structure.

#### Create an Owner
```PHP
$response = $mnubo->owner_services->create($OWNER_as_array);
```

#### Claim a Smart Object for an Owner
```PHP
$response = $mnubo->owner_services->claim('USERNAME', 'DEVICE_ID');
```

#### Update an Owner
```PHP
$response = $mnubo->owner_services->update($OWNER_as_array);
```

#### Delete an Owner
```PHP
$response = $mnubo->owner_services->delete('USERNAME');
```

### Use the Smart Objects Services
To create smart objects on the mnubo SmartObject platform, please refer to
the data modeling guide to format correctly the smart object's data structure.

#### Create a Smart Object
```PHP
$response = $mnubo->smart_object_services->create($OBJECT_as_array);
```

#### Update a Smart Object
```PHP
$response = $mnubo->smart_object_services->update($OBJECT_as_array);
```

#### Delete a Smart Object
```PHP
$response = $mnubo->smart_object_services->delete('DEVICE_ID');
```

### Use the Event Services
To send events to the mnubo SmartObject platform, please refer to
the data modeling guide to format correctly the event's data structure.

#### Send an Event
```PHP
$response = $mnubo->event_services->send('EVENT_IN_JSON');
```

### Use the Search Services
To send search queries to the mnubo SmartObject platform, please refer to
the Search API documentation to format your queries correctly.

#### Search Query
```PHP
$response = $mnubo->search_services->search('QUERY');
```

#### Search Datasets Query
```PHP
$response = $mnubo->search_services->search_datasets('QUERY');
```

### Use the Batch Services
To create or update owners or objects in batch, please refer to the Batch section
of either the SmartObject or the Owners in the API documentation to format the data correctly.

#### Batch Owners
```PHP
$response = $mnubo->batch_services->owners($OWNERS_as_array);
```

#### Batch Objects
```PHP
$response = $mnubo->batch_services->objects($OBJECTS_as_array);
```

#### Batch Events
'REPORT_RESULTS': is a boolean that specify if a body with the result of each individual event should be returned.
```PHP
$response = $mnubo->batch_services->events($EVENT_as_array, 'REPORT_RESULTS');
```
