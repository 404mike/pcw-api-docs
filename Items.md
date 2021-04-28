## 2.2 Items

### 2.2.1 GET

#### Retrieve Single

```
item/:id
```

#### Retrieve List

```
item?[parameters]
```

#### Code Example:

```php
<?php
$oauth->fetch(BASE_URI.'item/346');
print_r($oauth->getLastResponse());
```

### Parameters

| Name          | Type    | Required | Description   |
|---------------|---------|----------|---------------|
| limit         | Integer | No       | If specified the maximum number of items returned will be equal to the limit given. | 
| offset        | Integer | No       | If specified the results will be offset by the given offset value. | 
| userId        | Integer | No       | If specified only items belonging to the given userId​ will be returned. | 
| itemType      | string  | No       | If specified results will be limited to the given.| 
| containsTag   | String  | No       | If specified only results that contain the given tag​ will be returned.  | 
| id            | Integer | No       | If specified will return the single item that corresponds to the given ​id​. | 
| byOwner       | string  | No       | If specified only items belonging to the given owner will be returned. | 
| byPublisher   | string  | No       | If specified only items belonging to the given publisher will be returned. | 
| byCreator     | string  | No       | If specified only items belonging to the given creator will be returned. | 
| createdAfter  | string  | No       | If specified only items created after the given date will be returned. | 
| createdBefore | string  | No       | If specified only items created before the given date will be returned. | 
| updatedAfter  | string  | No       | If specified only items updated after the given date will be returned. | 
| updatedBefore | string  | No       | If specified only items updated before the given date will be returned.  | 
| latitude      | float   | No       | If given along with a longitude and a radius results will be limited to the computed geospatial area. | 
| longitude     | float   | No       | If given along with a latitude and radius results will be limited to the computed geospatial area. | 
| radius        | float   | No       | If given along with a latitude and longitude results will be limited to the computed geospatial area. | 
| query         | string  | No       | If specified only items with a title or description containing the given string will be returned. | 




#### Request Examples:

```
Base URL = https://www.peoplescollection.wales/rest/v1
```

#### Endpoints

```
/item/426 
/item?userId=249 
/item?userId=249&containsTag[0]=foo&containsTag[1]=bar 
/item?userId=249&containsTag[0]=foo&containsTag[1]=bar&limit=5 
/item?lat=51.504789&lon=-3.161316&radius=10
```



#### Response Example:

```
{
  "id": 346,
  "title": {
    "en": "The Rhydygwystyl Creamery, 31 March 1955",
    "cy": "Hufenfa Rhydygwystyl, 31 Mawrth 1955"
  },
  "nodeType": "item",
  "url": "https://dev.peoplescollectionwales.co.uk/items/346",
  "created": 1248797894,
  "updated": 1265364551,
  "status": "draft",
  "type": "item",
  "description": {
    "en": "<p>This photograph was taken by Geoff Charles and appeared 
           in Y Cymro&#039;s Agricultural supplement in March 
           1955.</p>",
    "cy": "<p>Tynnwyd y llun hwn gan Geoff Charles ac fe ymddangosodd 
           mewn atodiad amaethyddol yn &#039;Y Cymro&#039;, 31 Mawrth 
           1955.</p>"
  },
  "author": {
    "id": 2889,
    "name": "Casglu'r Tlysau / Gathering The Jewels"
  },
  "creator": "Charles, Geoff",
  "owner": "The National Library of Wales",
  "publisher": "",
  "copyright": [
    {
      "holder": {
        "en": "The National Library of Wales",
        "cy": "Llyfrgell Genedlaethol Cymru"
      },
      "year": "2001",
      "type": "copyright"
    }
  ],
  "license": {
    "reproducedPermission": {
      "en": "The National Library of Wales",
      "cy": "Llyfrgell Genedlaethol Cymru"
    },
    "additionalText": [],
    "type": "ARR"
  },
  "tags": [
    "Agriculture",
    "Dairies",
    "Dairy",
    "Dairying",
    "Dairy products"
  ],
  "when": [],
  "what": [
    "Agricultural machinery and implements",
    "OTHER: Arts + Culture",
    "OTHER: Physical Environment"
  ],
  "learn": [],
  "locations": [
    {
      "lat": "52.928863413385",
      "lon": "-4.373197227759",
      "node": [
        {
          "target_id": "346"
        }
      ]
    }
  ],
  "files": [
    {
      "originalFilename": "GTJ11630_2.jpg",
      "url": "https://dev.peoplescollectionwales.co.uk/sites/pcw/files/
              images/2014/February/GTJ11630_2.jpg",
      "type": "image",
      "target_id": "319501"
    }
  ],
  "original_item_url": {
    "en": "https://www.gtj.org.uk/en/small/item/GTJ11630",
    "cy": ""
  },
  "guid": "33f0f0a1-37a4-4f20-8aca-3d70384cae65"
}
```

### 2.2.2 POST (Creating an Item)

### /item

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
        "https://www.peoplescollection.wales/rest/v1/item", 
        $postData, 
        OAUTH_HTTP_METHOD_POST
);

echo $oauth->getLastResponse();
```

#### Parameters

| Name | Type  | Required | Description                    | 
|------|-------|----------|--------------------------------| 
| data | Array | Yes      | An Array of data for the item. | 


Within the data array the following are accepted:

| Name | Type  | Required | Description                    | 
|------|-------|----------|--------------------------------| 
| title | Array | Yes | An array of two elements, for both English and Welsh titles (e.g. title[en]​ and title[cy]​) | 
| description | Array | Yes | An array of two elements, for both English and Welsh descriptions (e.g. description[en ]​ and description[cy ]) | 
| owner | String | No | The owner of the item. | 
| rights | Array | No | Currently Undocumented. | 
| file | Array | No | An array of ‘n’ files. Each element must have the key name​. | 
| what | Array | No | An array of ‘n’ what facets. | 
| when | Array | No | An array of ‘n’ when facets. | 
| type | Integer | No | The type ID, the ID will be validated against internal ID’s within the database. For example: video, picture, audio, 3d_object_file, office_file, bbx_xml_file | 
| tags | Array | No | An array of ‘n’ tag names, numeric tags (e.g. 1958) are treated as tag names, not tag ID’s. | 
| locations | Array | No | An array of ‘n’ locations based on Latitude and Longitude. For example: 'locations[0][ lat]' => '52.414211', 'locations[0][ lon]' => '­4.068224', 'locations[0][ description][en]' => 'English location', 'locations[0][ description][cy]' => 'Welsh location' , | 
| original_url | Array | No | The original URL as an array. Contains both the original_url[en] ​and original_url[cy]​. | 
| bbc_xml_file | String | No | The BBC XML  URL as a string. The string will be validated as a correctly formed URL. | 
| guid | String | No | A GUID (Globally Unique Identifier), if this field is set. It must not be an empty string. | 
| onBehalf | Integer | No | Use this parameter to create items under the account of an alternative user. The use of this parameter requires that the authenticated user have the role of Content Administrator. | 
| creator | String | No | A string defining the creator of the trail. | 

#### POST Data Example:

```php 
<?php
$postData['title[en]'] = 'API Test Title English'; 
$postData['title[cy]'] = 'API Test Title Welsh'; 
$postData['description[en]'] = 'This is the english description'; 
$postData['description[cy]'] = 'This is the welsh description'; 
$postData['creator'] = 'John Smith'; 
$postData['owner'] = 'Dave Johnson';
```

##### Response Example

```
{
  "id": 468716
}
```
