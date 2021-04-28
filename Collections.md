## 2.4 Collections

### 2.4.1 GET

#### Retrieve Single

```
collection/:id
```

#### Retrieve List

```
collections?[parameters]
```

#### Code Example:

```php
<?php
$oauth->fetch(BASE_URI.'/collection/376879');
print_r($oauth->getLastResponse());
```

#### Parameters

| Name | Type  | Required | Description                    | 
|------|-------|----------|--------------------------------| 
| limit | Integer | No | If specified, the maximum number of items returned will be equal to the limit given. | 
| offset | Integer | No | If specified, the results will be offset by the given offset value. | 
| userId | Integer | No | If specified, only items belonging to the given userId will be returned. | 
| id | Integer | No | If specified, will return the single item that corresponds to the given id. | 



#### Request Examples:

```
Base URL = https://www.peoplescollection.wales/rest/vi
```

#### Endpoints

```
/collection/42 
/collection?userId=298 
/collection?offset=1
```

#### Response Example:

```
{​
    "id"​: ​376879​,
    ​"title"​: {​
        "en"​: ​ "Bengali"​,
        ​"cy"​: ​ "Bengaleg"​
    },
    ​"nodeType"​: ​ "collection"​,
    ​"url"​: ​ "https://www.peoplescollection.wales/collections/376879"​,
    ​"created"​: ​1249052139​,
    ​"updated"​: ​1421748647​,
    ​"status"​: ​ "published"​,
    ​"thumbnail"​: ​ "https://www.peoplescollection.wales/"​,
    ​"author"​: {​
        "id"​: ​3075​,
        ​"name"​: ​ "Amgueddfa Cymru ­ National Museum Wales"​
    },
    ​"when"​: ​[]​,
    ​"what"​: ​[]​,
    ​"collection_items"​: ​[​{​
        "nid"​: ​ "1272"​,
        ​"title"​: ​ "Bengali"​,
        ​"type"​: ​ "picture"​,
        ​"author"​: ​ "Amgueddfa Cymru ­ National Museum Wales"​,
        "thumbnail_path"​: ​ "https://www.peoplescollection.wales/sites/default/file s/styles/
        edit_node_thumb_larger / public / images / ​2014​ / February / Bengali.jpg ? itok = ​1​ Dhmu8n D​ "​
    }, {​
        "nid"​: ​ "1273"​,
        ​"title"​: ​ "Sirajul Islam introducing himself in Welsh"​,
        ​"type"​: ​ "video"​,
        ​"author"​: ​ "Amgueddfa Cymru ­ National Museum Wales"​,
        "thumbnail_path"​: ​ "/sites/all/themes/pcw/assets/images/video_thumbnail.jpg"​
    }, {​
        "nid"​: ​ "1274"​,
        ​"title"​: ​ "Sirajul Islam describes his linguistic background"​,
        ​"type"​: ​ "video"​,
        ​"author"​: ​ "Amgueddfa Cymru ­ National Museum Wales"​,
        "thumbnail_path"​: ​ "/sites/all/themes/pcw/assets/images/video_thumbnail.jpg"​
    }, {​
        "nid"​: ​ "1275"​,
        ​"title"​: ​ "Sirajul Islam: translation"​,
        ​"type"​: ​null​,
        ​"author"​: ​ "Amgueddfa Cymru ­ National Museum Wales"​,
        ​"thumbnail_path"​: ​null​
    }​]​,
    ​"description"​: {​
        "en"​: ​ "...",​
        "cy"​: ​ "..."​
    },
    ​"tags"​: ​[]
}
```

### 2.4.2 POST (Creating a Collection)

```
/collection
```

#### Code Example:

```php
<?php

$oauth ​= ​new ​OAuth(
  ​API_CONSUMER_KEY​, ​
  API_CONSUMER_SECRET​, ​
  OAUTH_SIG_METHOD_HMACSHA1​, ​
  OAUTH_AUTH_TYPE_URI 
)​;

$oauth->setToken( ​API_TOKEN​ ​, ​API_TOKEN_SECRET​ ​)​;

$oauth->fetch("https://www.peoplescollection.wales/rest/v1/collection"​, ​$postData​, ​OAUTH_HTTP_METHOD_POST )​;

echo ​$oauth->getLastResponse();
```

#### Parameters

| Name | Type  | Required | Description                    | 
|------|-------|----------|--------------------------------| 
| data | Array | Yes | An array of data for the collection. | 


Within the data array, the following keys are accepted:

| Name | Type  | Required | Description                    | 
|------|-------|----------|--------------------------------| 
| title | Array | Yes | An array of two elements, for both English and Welsh titles (e.g. title[en]​, title[cy]​). | 
| description | Array | Yes | An array of two elements, for both English and Welsh descriptions (e.g. description[en ]​, description[cy ]​). | 
| what | Array | No | An array of ‘n’ what facets | 
| when | Array | No | An array of ‘n’ when facets. | 
| tags | Array | No | An array of ‘n’ tag names, numeric tags (e.g. 1958) are treated as tag names, not tag ID’s. | 
| locations | Array | No | An array of ‘n’ locations based on Latitude and Longitude. For example: lat=51.504789&lon=3.16131 6&radius=10 | 
| onBehalf | Integer | No | An ID representing the user that the collection should be created under (this can only be accessed by those with the Content Administrator role). | 
| image | Integer | No | The cover image for the collection, use the FID returned from a call the file upload endpoint. | 
| items | Array | No | An array of ‘n’ items belonging to the collection | 
| privacy | String | No | public ​or ​private - if not set, public is assumed. | 
| externalUrl | VOID | No | This is not yet implemented, setting this field will cause an exception to be thrown and a non-200 HTTP status to be returned. | 
| guid | String | No | A GUID (Globally Unique Identifier), if this field is set, it must not be an empty string. | 
| created_date | String | No | A comma separated string of dates (a range may be specified) that conforms to the PCW date format. The regular expression is: ^([+-])([0-9]{6})([0 -9]{2})([0-9]{2})([0 -9]{2})([0-9]{2})([0 -9]{2})$ | 
| creator | String | No | A string defining the creator of the collection | 


### POST Data Example

```php
<?php

$postData​[​'title[en]'​] = ​'API Test Title English'​; 
$postData​[​'title[cy]'​] = ​'API Test Title Welsh'​; 
$postData​[​'description[en]'​] = ​'This is the english description'​; 
$postData​[​'description[cy]'​] = ​'This is the welsh description'​; 
$postData​[​'creator'​] = ​'Joe Bloggs'​; 
$postData​[​'owner'​] = ​'Joe Welsh'​;
$postData​[​'tags[0]'​] = ​'Tag1'​; 
$postData​[​'tags[1]'​] = ​'Tag2'​;
```

#### Response Example

```
{​“success” : “TRUE”, “id” : “468718”​}
```
