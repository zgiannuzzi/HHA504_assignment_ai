# HHA504_assignment_ai

## 1. Work with Pre-trained Speech Models

### GCP 

- See attached speech_rec.ipynb for output on text reconginition 
### Steps 

1. Installed google cloud speech sdk.
2. Imported cloud speech and cloud text recognition.
3. Added my project ID (didnt include for security purposes). 
4. Added my link for audio file and ran program successfully. 

- output for speech to text 
```python
the stale smell of old beer lingers it takes heat to bring out the odor
 a cold dip restores health and zest a salt pickle tastes fine with ham tacos al pastor are my favorite a zestful food is the hot cross bun

```
## 2. Work with Pre-trained Vision Models

### GCP 

- See attached speech_rec.ipynb for output on image

### Steps 
1. Intalled the vision sdk. 
2. I tried using the code provided but had no luck.
3. See error in speech_rec.ipynb.
4. I tried enabling the vision api but it still would not work. 
5. Wasn't ssuccesful in getting this to work.

```python
{
	"name": "PermissionDenied",
	"message": "403 Cloud Vision API has not been used in project 1057398310658 before or it is disabled. Enable it by visiting https://console.developers.google.com/apis/api/vision.googleapis.com/overview?project=1057398310658 then retry. If you enabled this API recently, wait a few minutes for the action to propagate to our systems and retry. [links {
  description: \"Google developers console API activation\"
  url: \"https://console.developers.google.com/apis/api/vision.googleapis.com/overview?project=1057398310658\"
}
, reason: \"SERVICE_DISABLED\"
domain: \"googleapis.com\"
metadata {
  key: \"consumer\"
  value: \"projects/1057398310658\"
}
metadata {
  key: \"service\"
  value: \"vision.googleapis.com\"
}
]",
	"stack": "---------------------------------------------------------------------------
_InactiveRpcError                         Traceback (most recent call last)
/usr/local/lib/python3.10/dist-packages/google/api_core/grpc_helpers.py in error_remapped_callable(*args, **kwargs)
     75         try:
---> 76             return callable_(*args, **kwargs)
     77         except grpc.RpcError as exc:

/usr/local/lib/python3.10/dist-packages/grpc/_channel.py in __call__(self, request, timeout, metadata, credentials, wait_for_ready, compression)
   1180         )
-> 1181         return _end_unary_response_blocking(state, call, False, None)
   1182 

/usr/local/lib/python3.10/dist-packages/grpc/_channel.py in _end_unary_response_blocking(state, call, with_call, deadline)
   1005     else:
-> 1006         raise _InactiveRpcError(state)  # pytype: disable=not-instantiable
   1007 

_InactiveRpcError: <_InactiveRpcError of RPC that terminated with:
\tstatus = StatusCode.PERMISSION_DENIED
\tdetails = \"Cloud Vision API has not been used in project 1057398310658 before or it is disabled. Enable it by visiting https://console.developers.google.com/apis/api/vision.googleapis.com/overview?project=1057398310658 then retry. If you enabled this API recently, wait a few minutes for the action to propagate to our systems and retry.\"
\tdebug_error_string = \"UNKNOWN:Error received from peer ipv4:172.217.214.95:443 {created_time:\"2024-11-01T16:59:57.584913147+00:00\", grpc_status:7, grpc_message:\"Cloud Vision API has not been used in project 1057398310658 before or it is disabled. Enable it by visiting https://console.developers.google.com/apis/api/vision.googleapis.com/overview?project=1057398310658 then retry. If you enabled this API recently, wait a few minutes for the action to propagate to our systems and retry.\"}\"
>

The above exception was the direct cause of the following exception:

PermissionDenied                          Traceback (most recent call last)
<ipython-input-58-049272be9d9e> in <cell line: 8>()
      6 image = vision.Image(content=content)
      7 
----> 8 response = client.text_detection(image=image)
      9 texts = response.text_annotations
     10 print(\"Texts:\")

/usr/local/lib/python3.10/dist-packages/google/cloud/vision_helpers/decorators.py in inner(self, image, max_results, retry, timeout, metadata, **kwargs)
    110             copied_features[\"max_results\"] = max_results
    111         request = dict(image=image, features=[copied_features], **kwargs)
--> 112         response = self.annotate_image(
    113             request, retry=retry, timeout=timeout, metadata=metadata
    114         )

/usr/local/lib/python3.10/dist-packages/google/cloud/vision_helpers/__init__.py in annotate_image(self, request, retry, timeout, metadata)
     74         elif len(request.features) == 0:
     75             request.features = self._get_all_features()
---> 76         r = self.batch_annotate_images(
     77             requests=[request], retry=retry, timeout=timeout, metadata=metadata
     78         )

/usr/local/lib/python3.10/dist-packages/google/cloud/vision_v1/services/image_annotator/client.py in batch_annotate_images(self, request, requests, retry, timeout, metadata)
    800 
    801         # Send the request.
--> 802         response = rpc(
    803             request,
    804             retry=retry,

/usr/local/lib/python3.10/dist-packages/google/api_core/gapic_v1/method.py in __call__(self, timeout, retry, compression, *args, **kwargs)
    129             kwargs[\"compression\"] = compression
    130 
--> 131         return wrapped_func(*args, **kwargs)
    132 
    133 

/usr/local/lib/python3.10/dist-packages/google/api_core/grpc_helpers.py in error_remapped_callable(*args, **kwargs)
     76             return callable_(*args, **kwargs)
     77         except grpc.RpcError as exc:
---> 78             raise exceptions.from_grpc_error(exc) from exc
     79 
     80     return error_remapped_callable

PermissionDenied: 403 Cloud Vision API has not been used in project 1057398310658 before or it is disabled. Enable it by visiting https://console.developers.google.com/apis/api/vision.googleapis.com/overview?project=1057398310658 then retry. If you enabled this API recently, wait a few minutes for the action to propagate to our systems and retry. [links {
  description: \"Google developers console API activation\"
  url: \"https://console.developers.google.com/apis/api/vision.googleapis.com/overview?project=1057398310658\"
}
, reason: \"SERVICE_DISABLED\"
domain: \"googleapis.com\"
metadata {
  key: \"consumer\"
  value: \"projects/1057398310658\"
}
metadata {
  key: \"service\"
  value: \"vision.googleapis.com\"
}
]"
}

```
### Azure 

- Was able to create a key and get sample code running.
- Tried both the image to object extraction and the image to text extraction .
- There is ai_vision.py and ocr.py.
- Output of ocr.py.

```python
===== Read File - remote =====
9:35 AM
[130.0, 129.0, 215.0, 130.0, 215.0, 149.0, 130.0, 148.0]
Conference room 154584354
[131.0, 153.0, 224.0, 153.0, 224.0, 161.0, 131.0, 160.0]
Town Hall
[545.0, 179.0, 589.0, 180.0, 589.0, 190.0, 545.0, 189.0]
9:00 AM - 10:00 AM
[545.0, 192.0, 596.0, 193.0, 596.0, 200.0, 545.0, 199.0]
Aston Buien
[545.0, 201.0, 581.0, 202.0, 581.0, 208.0, 545.0, 208.0]
Daily SCRUM
[537.0, 258.0, 572.0, 258.0, 572.0, 265.0, 537.0, 265.0]
10:00 AM-11:00 AM
[537.0, 266.0, 590.0, 266.0, 590.0, 272.0, 537.0, 272.0]
Charlathe de Crum
[538.0, 274.0, 584.0, 273.0, 584.0, 279.0, 538.0, 279.0]
Quarterly NI Hands
[538.0, 296.0, 589.0, 296.0, 589.0, 302.0, 538.0, 302.0]
11:00 AM-12:00 PM
[537.0, 303.0, 590.0, 303.0, 590.0, 309.0, 537.0, 309.0]
Bebek Shaman
[538.0, 310.0, 577.0, 310.0, 577.0, 317.0, 538.0, 316.0]
Thuare
[505.0, 316.0, 518.0, 316.0, 517.0, 320.0, 505.0, 320.0]
Weekly stand up
[538.0, 333.0, 582.0, 332.0, 582.0, 339.0, 538.0, 339.0]
12:00 PM-1:00 PM
[538.0, 339.0, 586.0, 339.0, 586.0, 345.0, 538.0, 345.0]
Delle Marckre
[537.0, 347.0, 584.0, 346.0, 584.0, 353.0, 537.0, 353.0]
Product review
[538.0, 370.0, 577.0, 370.0, 577.0, 376.0, 538.0, 375.0]

```
- output of ai_vision.py

```python
Image analysis results:
 Caption:
   'a person pointing at a screen', Confidence 0.7768
 Read:
   Line: '9:35 AM', Bounding box [{'x': 131, 'y': 130}, {'x': 214, 'y': 130}, {'x': 214, 'y': 148}, {'x': 131, 'y': 148}]
     Word: '9:35', Bounding polygon [{'x': 132, 'y': 130}, {'x': 172, 'y': 131}, {'x': 171, 'y': 149}, {'x': 131, 'y': 148}], Confidence 0.9770
     Word: 'AM', Bounding polygon [{'x': 180, 'y': 131}, {'x': 203, 'y': 131}, {'x': 202, 'y': 149}, {'x': 180, 'y': 149}], Confidence 0.9980
   Line: 'Conference room 154584354', Bounding box [{'x': 132, 'y': 153}, {'x': 224, 'y': 153}, {'x': 224, 'y': 161}, {'x': 132, 'y': 160}]
     Word: 'Conference', Bounding polygon [{'x': 143, 'y': 153}, {'x': 174, 'y': 154}, {'x': 174, 'y': 161}, {'x': 143, 'y': 161}], Confidence 0.6930
     Word: 'room', Bounding polygon [{'x': 176, 'y': 154}, {'x': 188, 'y': 154}, {'x': 188, 'y': 161}, {'x': 176, 'y': 161}], Confidence 0.9590
     Word: '154584354', Bounding polygon [{'x': 192, 'y': 154}, {'x': 224, 'y': 154}, {'x': 223, 'y': 161}, {'x': 192, 'y': 161}], Confidence 0.7050
   Line: ': 555-123-4567', Bounding box [{'x': 133, 'y': 164}, {'x': 183, 'y': 164}, {'x': 183, 'y': 170}, {'x': 133, 'y': 170}]
     Word: ':', Bounding polygon [{'x': 134, 'y': 165}, {'x': 137, 'y': 165}, {'x': 136, 'y': 171}, {'x': 133, 'y': 171}], Confidence 0.1620
     Word: '555-123-4567', Bounding polygon [{'x': 143, 'y': 165}, {'x': 182, 'y': 165}, {'x': 181, 'y': 171}, {'x': 143, 'y': 171}], Confidence 0.6530
   Line: 'Town Hall', Bounding box [{'x': 545, 'y': 178}, {'x': 588, 'y': 179}, {'x': 588, 'y': 190}, {'x': 545, 'y': 190}]
     Word: 'Town', Bounding polygon [{'x': 545, 'y': 179}, {'x': 569, 'y': 180}, {'x': 569, 'y': 190}, {'x': 545, 'y': 190}], Confidence 0.9880
     Word: 'Hall', Bounding polygon [{'x': 571, 'y': 180}, {'x': 589, 'y': 180}, {'x': 589, 'y': 190}, {'x': 571, 'y': 190}], Confidence 0.9900
   Line: '9:00 AM - 10:00 AM', Bounding box [{'x': 545, 'y': 191}, {'x': 596, 'y': 191}, {'x': 596, 'y': 199}, {'x': 545, 'y': 198}]
     Word: '9:00', Bounding polygon [{'x': 546, 'y': 191}, {'x': 556, 'y': 192}, {'x': 556, 'y': 199}, {'x': 546, 'y': 199}], Confidence 0.7580
     Word: 'AM', Bounding polygon [{'x': 558, 'y': 192}, {'x': 565, 'y': 192}, {'x': 564, 'y': 199}, {'x': 558, 'y': 199}], Confidence 0.9890
     Word: '-', Bounding polygon [{'x': 567, 'y': 192}, {'x': 570, 'y': 192}, {'x': 569, 'y': 199}, {'x': 567, 'y': 199}], Confidence 0.8960
     Word: '10:00', Bounding polygon [{'x': 571, 'y': 192}, {'x': 585, 'y': 192}, {'x': 585, 'y': 199}, {'x': 571, 'y': 199}], Confidence 0.7970
     Word: 'AM', Bounding polygon [{'x': 587, 'y': 192}, {'x': 594, 'y': 193}, {'x': 593, 'y': 199}, {'x': 586, 'y': 199}], Confidence 0.9940
   Line: 'Aaron Blaion', Bounding box [{'x': 542, 'y': 201}, {'x': 581, 'y': 201}, {'x': 581, 'y': 207}, {'x': 542, 'y': 207}]
     Word: 'Aaron', Bounding polygon [{'x': 545, 'y': 201}, {'x': 560, 'y': 202}, {'x': 560, 'y': 208}, {'x': 545, 'y': 208}], Confidence 0.7180
     Word: 'Blaion', Bounding polygon [{'x': 562, 'y': 202}, {'x': 579, 'y': 202}, {'x': 579, 'y': 207}, {'x': 562, 'y': 207}], Confidence 0.2740
   Line: 'Daily SCRUM', Bounding box [{'x': 537, 'y': 258}, {'x': 574, 'y': 259}, {'x': 574, 'y': 266}, {'x': 537, 'y': 265}]
     Word: 'Daily', Bounding polygon [{'x': 538, 'y': 259}, {'x': 551, 'y': 259}, {'x': 551, 'y': 266}, {'x': 538, 'y': 265}], Confidence 0.4040
     Word: 'SCRUM', Bounding polygon [{'x': 553, 'y': 259}, {'x': 570, 'y': 260}, {'x': 570, 'y': 265}, {'x': 553, 'y': 266}], Confidence 0.6970
   Line: '10:00 AM-11:00 AM', Bounding box [{'x': 535, 'y': 266}, {'x': 589, 'y': 265}, {'x': 589, 'y': 272}, {'x': 535, 'y': 273}]
     Word: '10:00', Bounding polygon [{'x': 539, 'y': 267}, {'x': 553, 'y': 266}, {'x': 552, 'y': 273}, {'x': 539, 'y': 274}], Confidence 0.2190
     Word: 'AM-11:00', Bounding polygon [{'x': 554, 'y': 266}, {'x': 578, 'y': 266}, {'x': 578, 'y': 272}, {'x': 554, 'y': 273}], Confidence 0.1750
     Word: 'AM', Bounding polygon [{'x': 580, 'y': 266}, {'x': 587, 'y': 266}, {'x': 586, 'y': 272}, {'x': 580, 'y': 272}], Confidence 1.0000
   Line: 'Charlene de Crum', Bounding box [{'x': 538, 'y': 272}, {'x': 588, 'y': 273}, {'x': 588, 'y': 279}, {'x': 538, 'y': 279}]
     Word: 'Charlene', Bounding polygon [{'x': 538, 'y': 273}, {'x': 562, 'y': 273}, {'x': 562, 'y': 280}, {'x': 538, 'y': 280}], Confidence 0.3220
     Word: 'de', Bounding polygon [{'x': 563, 'y': 273}, {'x': 569, 'y': 273}, {'x': 569, 'y': 280}, {'x': 563, 'y': 280}], Confidence 0.9100
     Word: 'Crum', Bounding polygon [{'x': 570, 'y': 273}, {'x': 582, 'y': 273}, {'x': 583, 'y': 280}, {'x': 571, 'y': 280}], Confidence 0.8710
   Line: 'Quarterly NI Handa', Bounding box [{'x': 537, 'y': 295}, {'x': 588, 'y': 295}, {'x': 588, 'y': 302}, {'x': 537, 'y': 302}]
     Word: 'Quarterly', Bounding polygon [{'x': 539, 'y': 296}, {'x': 563, 'y': 296}, {'x': 563, 'y': 302}, {'x': 538, 'y': 302}], Confidence 0.6030
     Word: 'NI', Bounding polygon [{'x': 564, 'y': 296}, {'x': 570, 'y': 296}, {'x': 571, 'y': 302}, {'x': 564, 'y': 302}], Confidence 0.7300
     Word: 'Handa', Bounding polygon [{'x': 572, 'y': 296}, {'x': 588, 'y': 296}, {'x': 588, 'y': 302}, {'x': 572, 'y': 302}], Confidence 0.9050
   Line: '11.00 AM-12:00 PM', Bounding box [{'x': 538, 'y': 303}, {'x': 587, 'y': 303}, {'x': 587, 'y': 309}, {'x': 538, 'y': 309}]
     Word: '11.00', Bounding polygon [{'x': 539, 'y': 303}, {'x': 552, 'y': 303}, {'x': 553, 'y': 309}, {'x': 539, 'y': 310}], Confidence 0.6710
     Word: 'AM-12:00', Bounding polygon [{'x': 554, 'y': 303}, {'x': 578, 'y': 303}, {'x': 578, 'y': 309}, {'x': 554, 'y': 309}], Confidence 0.6560
     Word: 'PM', Bounding polygon [{'x': 579, 'y': 303}, {'x': 586, 'y': 303}, {'x': 586, 'y': 309}, {'x': 580, 'y': 309}], Confidence 0.4540
   Line: 'Bobek Shemar', Bounding box [{'x': 538, 'y': 310}, {'x': 577, 'y': 310}, {'x': 577, 'y': 316}, {'x': 538, 'y': 316}]
     Word: 'Bobek', Bounding polygon [{'x': 539, 'y': 310}, {'x': 554, 'y': 311}, {'x': 554, 'y': 317}, {'x': 539, 'y': 317}], Confidence 0.6320
     Word: 'Shemar', Bounding polygon [{'x': 556, 'y': 311}, {'x': 576, 'y': 311}, {'x': 577, 'y': 317}, {'x': 556, 'y': 317}], Confidence 0.2190
   Line: 'Weekly aband up', Bounding box [{'x': 538, 'y': 332}, {'x': 583, 'y': 333}, {'x': 583, 'y': 339}, {'x': 538, 'y': 338}]
     Word: 'Weekly', Bounding polygon [{'x': 539, 'y': 333}, {'x': 557, 'y': 333}, {'x': 557, 'y': 339}, {'x': 539, 'y': 339}], Confidence 0.5750
     Word: 'aband', Bounding polygon [{'x': 558, 'y': 334}, {'x': 573, 'y': 334}, {'x': 573, 'y': 339}, {'x': 558, 'y': 339}], Confidence 0.4750
     Word: 'up', Bounding polygon [{'x': 574, 'y': 334}, {'x': 580, 'y': 334}, {'x': 580, 'y': 339}, {'x': 574, 'y': 339}], Confidence 0.8650
   Line: '12:00 PM-1:00 PM', Bounding box [{'x': 538, 'y': 339}, {'x': 585, 'y': 339}, {'x': 585, 'y': 346}, {'x': 538, 'y': 346}]
     Word: '12:00', Bounding polygon [{'x': 539, 'y': 339}, {'x': 553, 'y': 340}, {'x': 553, 'y': 347}, {'x': 539, 'y': 346}], Confidence 0.7090
     Word: 'PM-1:00', Bounding polygon [{'x': 554, 'y': 340}, {'x': 575, 'y': 340}, {'x': 575, 'y': 346}, {'x': 554, 'y': 347}], Confidence 0.9080
     Word: 'PM', Bounding polygon [{'x': 576, 'y': 340}, {'x': 583, 'y': 340}, {'x': 583, 'y': 346}, {'x': 576, 'y': 346}], Confidence 0.9980
   Line: 'Danielle MarchTe', Bounding box [{'x': 538, 'y': 346}, {'x': 583, 'y': 346}, {'x': 583, 'y': 352}, {'x': 538, 'y': 352}]
     Word: 'Danielle', Bounding polygon [{'x': 539, 'y': 347}, {'x': 559, 'y': 347}, {'x': 559, 'y': 352}, {'x': 539, 'y': 353}], Confidence 0.1960
     Word: 'MarchTe', Bounding polygon [{'x': 560, 'y': 347}, {'x': 582, 'y': 347}, {'x': 582, 'y': 352}, {'x': 560, 'y': 352}], Confidence 0.5710
   Line: 'Product reviret', Bounding box [{'x': 537, 'y': 370}, {'x': 578, 'y': 370}, {'x': 578, 'y': 375}, {'x': 537, 'y': 375}]
     Word: 'Product', Bounding polygon [{'x': 539, 'y': 370}, {'x': 559, 'y': 370}, {'x': 559, 'y': 376}, {'x': 539, 'y': 375}], Confidence 0.7000
     Word: 'reviret', Bounding polygon [{'x': 560, 'y': 370}, {'x': 578, 'y': 371}, {'x': 578, 'y': 375}, {'x': 560, 'y': 376}], Confidence 0.2180

```

## 3. Overall thoughts 

- Ran into some road blocks trying to find documentation for both google and azure API's.
- Because I could get the vision for GCP to work cant really make comparison.
- I do think that GCP is more user friendly and it was easier to find documentation than Azure.







