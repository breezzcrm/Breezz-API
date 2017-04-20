# Delete

To delete a row in your Breezz account you only need to send a reuqest to this URL:

```
https://app.breezz.io/api/record/{object}/{ID}
```

## JSON: 

```javascript
no data
```

## PHP:

```php
$objectid = '332DB2BF-3694-4F80-B82F-99F8712345';		
$url =https://app.breezz.io/api/record/account/'.$objectid;
    $ch = curl_init();
    curl_setopt($ch, CURLOPT_URL,$url);
    curl_setopt($ch, CURLOPT_CUSTOMREQUEST, "DELETE");
	curl_setopt($ch, CURLOPT_HTTPHEADER, array(                                                                          
    'Content-Type: application/json',
    'tokenid: 0588209E-2715-419F-A913-732DABBDFE61',                                                                                
    'Content-Length: ' . strlen($data_string))                                                                       
); 
    $result = curl_exec($ch);
    $httpCode = curl_getinfo($ch, CURLINFO_HTTP_CODE);
    curl_close($ch);
```

## python:

```python
import requests
import json

url = 'https://app.breezz.io/api/record/account/'
token_id = '73994acf-cd16-48bd-b8e1-17bc8f'
object_id = '12345f-cd16-48bd-b8'

headers = {'Content-type': 'application/json', 'tokenId': token_id, 'utc_time' : str(1)}
response = requests.delete(url + str(object_id), headers=headers)
return json.loads(response.content)['data']
```

## ASP.net:

```c#
using System.Collections.Specialized;
using System.Net;
using System.Web.Script.Serialization;
using System.IO;

 using (WebClient client = new WebClient())
            {
                string tokenid = "0588209E-2715-419F-7777-732DA123456"; 
                string objectid = "332db2bf-3694-4f80-7777-99f87b123456";
                client.Encoding = System.Text.Encoding.UTF8;
                client.Headers.Set("tokenId", tokenid);
                string result = client.UploadString("https://app.breezz.io/api/record/account/" + objectid, "DELETE", "");
            }
```
