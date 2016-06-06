## 2.1 File uploads 

Files can be uploaded by performing a POST request to ```/api_gateway/file``` with
the post data containing a files key, of type array. For example:

```php
<?php
$ch = curl_init(); 
$file = curl_file_create('file.jpg', 'image/jpeg', 'file.jpg'); 
$data = array('files[attachment]' => $file);

curl_setopt($ch, CURLOPT_URL, 
            "http://www.peoplescollection.wales/api_gateway/file"); 
curl_setopt($ch, CURLOPT_POST, 1); 
curl_setopt($ch, CURLOPT_POSTFIELDS, $data);
curl_setopt($ch, CURLOPT_RETURNTRANSFER, true);

$result = curl_exec($ch);
```

The endpoint returns a JSON object with the FID (File ID), this ID can then be
passed to other POST endpoints to attach the file upload to a newly created or
updated item.
