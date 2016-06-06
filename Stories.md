## 2.3 Stories

## 2.3.1 GET

#### Retrieve Single

```
story/:id
```

#### Retrieve List

```
story?[parameters]
```

#### Code Example

```php
<?php
$oauth->fetch(BASE_URI.'story/378092');
print_r($oauth->getLastResponse());
```

#### Parameters

| Name | Type  | Required | Description                    | 
|------|-------|----------|--------------------------------| 
| offset | Integer | No | If specified, the results will be offset by the given offset value. | 
| limit | Integer | No | If specified, the maximum number of items returned will be equal to the limit given. | 
| userId | Integer | No | If specified, only items belonging to the given userId will be returned. | 
| id | Integer | No | If specified, will return the single item that corresponds to the given ​id​. | 


#### Request Example

```
Base URL = www.peoplescollection.wales/rest/vi
```

#### Endpoints

```
/story/426 
/story?userId=249 
/story?offset=1
```

#### Response Example

```
{
  "id": 493287,
  "title": {
    "en": "Ynysywern Farm and the Upper Boat Power Station",
    "cy": "Ynysywern Farm and the Upper Boat Power Station"
  },
  "nodeType": "story",
  "url": "http://dev.peoplescollectionwales.co.uk/story/493287",
  "created": 1452782182,
  "updated": 1452857820,
  "status": "published",
  "description": {
    "en": "Ynysywern farm dating at least from the 18th century, was 
           part of the Bute estate. At the start of the 20th century, 
           the farm was sold to provide a location for the new Upper 
           Boat Power Station.  More recently the remains of the farm 
           and the power station have vanished completely under the 
           Treforest Trading Estate."
  },
  "thumbnail": "http://dev.peoplescollectionwales.co.uk/",
  "author": {
    "id": 3106,
    "name": "Royal Commission on the Ancient and Historical Monuments 
             of Wales"
  },
  "content": {
    "en": "<div>\n\t&nbsp; &nbsp; &nbsp;</div>\n<div>\n\tLeft are 
           images including of mapping showing the changes over time 
           at Ynysywern; an aerial view of the South Wales Electric 
           Company, Upper Boat Power Station towering over Ynysywern 
           farm seen in the foreground, and views of haymaking at 
           Ynysywern Farm circa 1902-10 showing power station in the 
           background.</div>\n<div>\n\t&nbsp;</div>\n<div>\n<p>\n\t\t
           <strong>Ynysywern Farm, Llantwit Fardre, near Pontypridd
           </strong> was taken over to provide a site for building 
           the Upper Boat Power Station.&nbsp; More recently the 
           remains of the farm and the power station have vanished 
           completely under the Treforest Trading Estate."
  },
  "collection_items": [
    {
      "nid": "422744",
      "title": " SOUTH WALES ELECTRIC COMPANY, UPPER BOAT POWER 
               STATION",
      "type": "picture",
      "author": {
        "id": 3106,
        "name": "Royal Commission on the Ancient and Historical 
                 Monuments of Wales"
      },
      "thumbnail_path": "http://dev.peoplescollectionwales.co.uk/
                         sites/pcw/files/styles/
                         edit_node_thumb_larger/public/images/2015/
                         February/%20WPW032552.jpg?itok=pNcaUQu2"
    },
    {
      "nid": "493240",
      "title": "View of Ynysywern Farm circa c.1902-10",
      "type": "picture",
      "author": {
        "id": 3106,
        "name": "Royal Commission on the Ancient and Historical 
                 Monuments of Wales"
      },
      "thumbnail_path": "http://dev.peoplescollectionwales.co.uk/
                         sites/pcw/files/styles/
                         edit_node_thumb_larger/public/images/2016/
                         January/DI2012_0464.jpg?itok=gWDbVat2"
    },
    {
      "nid": "493242",
      "title": "View of haymaking at Ynysywern Farm circa 1902-10",
      "type": "picture",
      "author": {
        "id": 3106,
        "name": "Royal Commission on the Ancient and Historical 
                 Monuments of Wales"
      },
      "thumbnail_path": "http://dev.peoplescollectionwales.co.uk/
                         sites/pcw/files/styles/
                         edit_node_thumb_larger/public/images/2016/
                         January/DI2012_0466.jpg?itok=8RZ20FuK"
    },
    {
      "nid": "493248",
      "title": "View of congregation outside Carmel CM Chapel, Upper 
                Boat",
      "type": "picture",
      "author": {
        "id": 3106,
        "name": "Royal Commission on the Ancient and Historical 
                 Monuments of Wales"
      },
      "thumbnail_path": "http://dev.peoplescollectionwales.co.uk/
                         sites/pcw/files/styles/
                         edit_node_thumb_larger/public/images/2016/
                         January/DI2012_0472.jpg?itok=cqBpnVDl"
    },
    {
      "nid": "493282",
      "title": "Ordnance Survey (OS) mapping extracts showing changes 
                over time at Ynysywern Farm and the Upper Boat Power 
                Station",
      "type": "picture",
      "author": {
        "id": 3106,
        "name": "Royal Commission on the Ancient and Historical 
                 Monuments of Wales"
      },
      "thumbnail_path": "http://dev.peoplescollectionwales.co.uk/
                         sites/pcw/files/styles/
                         edit_node_thumb_larger/public/images/2016/
                         January/mapping.jpg?itok=rqYjPbc4"
    }
  ]
}
```

### 2.3.2 POST (Creating a Story)

```
/story
```

#### Code Example:

 ```php 
<?php

$oauth = new OAuth(
  API_CONSUMER_KEY,
  API_CONSUMER_SECRET,
  OAUTH_SIG_METHOD_HMACSHA1,
  OAUTH_AUTH_TYPE_URI 
);

$oauth->setToken(API_ACCESS_TOKEN, API_ACCESS_TOKEN_SECRET);

$oauth->fetch(
    "http://www.peoplescollection.wales/rest/v1/story", 
    $postData, 
    OAUTH_HTTP_METHOD_POST
);

echo $oauth->getLastResponse();
```

#### Parameters

| Name | Type  | Required | Description                    | 
|------|-------|----------|--------------------------------| 
| data | Array | Yes | An array of data for the story. | 


Within the data array, the following keys are accepted:

| Name | Type  | Required | Description                    | 
|------|-------|----------|--------------------------------| 
| title | Array | Yes | An array of two elements, for both English and Welsh titles (e.g. title[en]​, title[cy]​). | 
| description | Array | Yes | An array of two elements, for both English and Welsh descriptions (e.g. description[en]​, description[cy]​). | 
| content | Array | Yes | An array of two elements, for both English and Welsh body content (e.g. content[en]​, content[cy]​). | 
| what | Array | No | An array of ‘n’ what facets. | 
| when | Array | No | An array of ‘n’ when facets. | 
| tags | Array | No | An array of ‘n’ tag names, numeric tags (e.g. 1958) are treated as tag names, not tag ID’s. | 
| locations | Array | No | An array of ‘n’  locations based on Latitude and Longitude. For example: lat=51.504789&lon=3.16131 6&radius=10 | 
| image | Integer | No | The cover image for the story, use the FID returned from a call the file upload endpoint. | 
| items | Array | No | An array of ‘n’ items belonging to the story. | 
| externalURL | VOID |  | No This is not yet implemented. Setting this field will cause an exception to be thrown and a non-200 HTTP status to be returned. | 
| guid | String | No | A GUID (Globally Unique Identifier), if this field has been set. It must not be an empty string. | 
| created_date | String | No | A comma separated string of dates (a range may be specified) that conforms to the PCW date format. The regular expression is: ^([+-])([0-9]{6})([0 -9]{2})([0-9]{2})([0 -9]{2})([0-9]{2})([0 -9]{2})$ | 
| creator | String | No | A string defining the creator of the story. | 


#### POST Data Example:

```php
<?php
$postData['title[en]'] = 'API Test Title English'; 
$postData['title[cy]'] = 'API Test Title Welsh'; 
$postData['description[en]'] = 'This is the english description'; 
$postData['description[cy]'] = 'This is the welsh description'; 
$postData['creator'] = 'John Smith'; 
$postData['owner'] = 'Dave Johnson';
$postData['tags[0]'] = 'Tag1'; 
$postData['tags[1]'] = 'Tag2';
$postData['created_date'] = '+0020141001140000';
$postData['content[en]'] = 'Lorem ipsum dolor sit amet, consectetur 
    adipiscing elit. Integer non turpis id tellus venenatis 
    ultricies.'; 
$postData['content[cy]'] = 'Lorem ipsum dolor sit amet, consectetur 
    adipiscing elit. Integer non turpis id tellus venenatis 
    ultricies.';
```

#### Response Example:

```
{
    "id" : 468717, 
    "success" : true, 
    "items" : " "
}
```
