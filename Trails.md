## 2.5 Trails

## 2.5.1 GET

#### Retrieve Single

```
trail/:id
```

#### Retrieve List

```
trails?[parameters]
```

#### Code Example

```php
<?php

$oauth​­>​fetch​(​BASE_URI​.​'trail/378385'​)​;
print_r(​$oauth​­>​getLastResponse​())​;
```

#### Parameters

| Name | Type  | Required | Description                    | 
|------|-------|----------|--------------------------------| 
| limit | Integer | No | If specified, the maximum number of items returned will be equal to the limit​ given. | 
| offset | Integer | No | If specified, the results will be offset by the given ​offset value. | 
| userId | Integer | No | If specified, only items belonging to the given userId​ will be returned. | 
| id | Integer | No | If specified, will return the single item that corresponds to the given ​id​. | 


#### Request Examples:

````
Base URL = www.peoplescollection.wales/rest/vi
```

#### Endpoints

```
/trail/1026
/trail?userId=249 
/trail?offset=1
```

#### Response Example:

```
{​
    "id"​: ​378385​,
    ​"title"​: {​
        "en"​: ​ "Aberystwyth Prom ­ 'Kicking the bar'"​,
        ​"cy"​: ​ "Prom Aberystwyth ­ 'Cicio'r bar'"​
    },
    ​"nodeType"​: ​ "trail"​,
    ​"url"​: ​ "http://www.peoplescollection.wales/trails/378385"​,
    ​"created"​: ​1260195645​,
    ​"updated"​: ​1393450436​,
    ​"status"​: ​ "draft"​,
    ​"thumbnail"​: ​ "http://www.peoplescollection.wales/sites/default/files/​
    trail­ images / ​2014​ / February / prom_aber_0.jpg​ ", ​"
    author "​:{​
    "id"​: ​1042​,
    ​"name"​: ​ "Dafydd Tudur"​
}, ​"when"​: ​[]​, ​"what"​: ​[]​, ​"learn"​: ​[]​, ​"collection_items"​: ​[]​, ​"description"​: {​
    "en"​: ​ "...​",
    ​"cy"​: ​ "..."​
}, ​"trail_path"​: ​[​{​
        "lat"​: ​ "0.00047078139069825"​,
        ​"lon"​: ​ "­3.6745178672846E­5"​
    }, {​
        "lat"​: ​ "0.00047078068514944"​,
        ​"lon"​: ​ "­3.6744022127557E­5"​
    }, {​
        "lat"​: ​ "0.00047078150828972"​,
        ​"lon"​: ​ "­3.6742094552073E­5"​
    }, {​
        "lat"​: ​ "0.00047079079787572"​,
        ​"lon"​: ​ "­3.6735926310528E­5"​
    },
    {​
        "lat"​: ​ "0.00047079150339908"​,
        ​"lon"​: ​ "­3.6738432158655E­5"​
    }, {​
        "lat"​: ​ "0.00047079855861997"​,
        ​"lon"​: ​ "­3.6733034947303E­5"​
    }, {​
        "lat"​: ​ "0.00047081337416529"​,
        ​"lon"​: ​ "­3.6730336341628E­5"​
    }, {​
        "lat"​: ​ "0.00047082466183936"​,
        ​"lon"​: ​ "­3.6737468370913E­5"​
    }, {​
        "lat"​: ​ "0.0004708425333125"​,
        ​"lon"​: ​ "­3.6754045520067E­5"​
    }, {​
        "lat"​: ​ "0.00047084223937836"​,
        ​"lon"​: ​ "­3.6754045520067E­5"​
    }, {​
        "lat"​: ​ "0.00047084306240413"​,
        ​"lon"​: ​ "­3.6753949141293E­5"​
    }, {​
        "lat"​: ​ "0.00047084370904907"​,
        ​"lon"​: ​ "­3.6752599838455E­5"​
    }, {​
        "lat"​: ​ "0.00047084365025969"​,
        ​"lon"​: ​ "­3.6742769203492E­5"​
    }, {​
        "lat"​: ​ "0.00047084365025969"​,
        ​"lon"​: ​ "­3.6739685082719E­5"​
    }, {​
        "lat"​: ​ "0.00047084447327275"​,
        ​"lon"​: ​ "­3.673621544685E­5"​
    }, {​
        "lat"​: ​ "0.0004708471774185"​,
        ​"lon"​: ​ "­3.6733131326078E­5"​
    }, {​
        "lat"​: ​ "0.00047085258568457"​,
        ​"lon"​: ​ "­3.6729276175112E­5"​
    }, {​
        "lat"​: ​ "0.00047085517220069"​,
        ​"lon"​: ​ "­3.6725999296791E­5"​
    }, {
        "lat"​: ​ "0.00047085711209733"​,
        ​"lon"​: ​ "­3.6716554176924E­5"​
    }, {​
        "lat"​: ​ "0.00047085981615403"​,
        ​"lon"​: ​ "­3.6710000420283E­5"​
    }, {​
        "lat"​: ​ "0.0004708642837138"​,
        ​"lon"​: ​ "­3.6702000982029E­5"​
    }, {​
        "lat"​: ​ "0.00047086933904008"​,
        ​"lon"​: ​ "­3.6696700149451E­5"​
    }, {​
        "lat"​: ​ "0.00047087327743188"​,
        ​"lon"​: ​ "­3.6694001543776E­5"​
    }, {​
        "lat"​: ​ "0.00047087839143303"​,
        ​"lon"​: ​ "­3.6691688453196E­5"​
    }, {​
        "lat"​: ​ "0.00047088256486783"​,
        ​"lon"​: ​ "­3.6691592074422E­5"​
    }, {​
        "lat"​: ​ "0.00047088967724966"​,
        ​"lon"​: ​ "­3.6693808786227E­5"​
    }, {​
        "lat"​: ​ "0.00047089138184885"​,
        ​"lon"​: ​ "­3.6693905165001E­5"​
    }, {​
        "lat"​: ​ "0.00047089479102181"​,
        ​"lon"​: ​ "­3.6693134134808E­5"​
    }, {​
        "lat"​: ​ "0.0004709051359413"​,
        ​"lon"​: ​ "­3.669294137726E­5"​
    }, {​
        "lat"​: ​ "0.00047091054340587"​,
        ​"lon"​: ​ "­3.6693616028679E­5"​
    }, {​
        "lat"​: ​ "0.00047091395241343"​,
        ​"lon"​: ​ "­3.6694194301324E­5"​
    }, {​
        "lat"​: ​ "0.00047091589201745"​,
        ​"lon"​: ​ "­3.669457981642E­5"​
    }, {​
        "lat"​: ​ "0.0004709158332408"​,

        "lon"​: ​ "­3.6694483437646E­5"​
    }​
]​, ​"tags"​: ​[]
}
```

### 2.5.2 POST (Creating a Trail)

#### /trail

#### Code Example:

```php
<?php

$oauth ​= ​new ​OAuth(
  ​API_CONSUMER_KEY​, ​
  API_CONSUMER_SECRET​, ​
  OAUTH_SIG_METHOD_HMACSHA1​, ​
  OAUTH_AUTH_TYPE_URI 
)​;

$oauth​­>​setToken​( ​API_TOKEN​ ​, ​API_TOKEN_SECRET​ ​)​;

$oauth​­>​fetch​("http://www.peoplescollection.wales/rest/v1/trail"​, ​$postData​, ​OAUTH_HTTP_METHOD_POST )​;

echo ​$oauth​­>​getLastResponse​()​;
```

#### Parameters

| Name | Type  | Required | Description                    | 
|------|-------|----------|--------------------------------| 
| data | Array | Yes | An Array of data for the trail. | 

Within the data array the following keys are accepted:

| Name | Type  | Required | Description                    | 
|------|-------|----------|--------------------------------| 
| description | Array | Yes | An array of two elements, for both English and Welsh descriptions (e.g. description[en]​, description[cy]​) | 
| guid | String | No | A GUID (Globally Unique Identifier), if this has been set. It must not be an empty string. | 
| image | Integer | No | The cover image for the trail. Use the FID returned from a call the file upload endpoint. | 
| items | Array | No | An array of ‘n’ items belonging to the trail. | 
| locations | Array | No | An array of ‘n’ locations based on Latitude and Longitude. For example: lat=51.504789&lon=3.16131 6&radius=10 | 
| tags | Array | No | An array of ‘n’ tag names, numeric tags (e.g. 1958) are treated as tag names, not tag ID’s. | 
| title | Array | Yes | An array of two elements, for both English and Welsh titles (e.g. title[en], title[cy]). | 
| trail_path | Array | Yes | An array of coordinates representing the latitude and longitude of the points on the trail. | 
| what | Array | No | An array of ‘n’ what facets. | 
| when | Array | No | An array of ‘n’ when facets. | 
| creator | String | No | A string defining the creator of the trail. | 
| gpx | integer | No | A FID (File ID) returned from the uploading of a GPX file to the API gateway. | 

#### POST Data Example

```php
<?php

$postData​[​'title[en]'​] = ​'API Test Title English'​; 
$postData​[​'title[cy]'​] = ​'API Test Title Welsh'​; 
$postData​[​'description[en]'​] = ​'This is the english description'​; 
$postData​[​'description[cy]'​] = ​'This is the welsh description'​; 
$postData​[​'creator'​] = ​'John Smith'​; 
$postData​[​'owner'​] = ​'Dave Johnson'​;
$postData​[​'tags[0]'​] = ​'Tag1'​; 
$postData​[​'tags[1]'​] = ​'Tag2'​; 
$postData​[​'created_date'​] = ​'+0020141001140000'​;
$postData​[​'content[en]'​] = ​'Lorem ipsum dolor sit amet, consectetur adipiscing elit. $postData​[​'content[cy]'​] = ​'Lorem ipsum dolor sit amet, consectetur adipiscing elit.
$postData​[​'trail_path[]'​] = ​array​(​'0.0004,­3.6745'​, ​'0.3942,­3.6123'​)​;
```

#### Response Example

```
{​"id":​468719​,"success":"true","items":""​}
```

