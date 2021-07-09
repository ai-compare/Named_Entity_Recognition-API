# Named_Entity_Recognition - Eden AI API
## Description
This repositery provides code to implement Eden AI Speech-to-text API. Eden AI Speech-to-text API allows to call Speech-to-text APIs from multpile speech-to-text providers. It permits to get results from these providers, compare the results, siwtch between providers or combine them.

## What is Eden AI ?
[Eden AI](https://www.edanai.co/) is a SaaS providing APIs connected to big (AWS, GCP, etc.) and small AI providers for vision, text, audio, OCR, prediction and translation AI engines. Our solution allows users to compare the performance of these providers APIs according to their data and use them directly via our API thus offering great flexibility and making it very easy to change supplier. In particular, we offer better performance with the "Genius" feature that cleverly combines results from multiple providers.

Eden AI offers community offer (free) when you [create your account for free](https://app.edenai.run/user/login). You can then use [APIs](https://api.edenai.run/v1/redoc/), use the [interface](https://app.edenai.run/bricks/default), manage your account, access to cost management.

You can find APIs documentation here : https://api.edenai.run/v1/redoc/

## Usage
### Initialization
Enter your access token and select your API endpoint. You can get your token on your account manager [here](https://www.ai-compare.com/accounts/login/?next=/my_apis/my_account).
```python
import requests
headers = {  'Authorization': 'Bearer your API Key'}
url = 'https://api.edenai.run/v1/pretrained/text/named_entity_recognition'
```
### Select parameters 
Set your text, the language, the attempted result, and providers APIs you want to run :
```python
payload = {'providers': '[\'ibm\', \'microsoft\', \'aws\', \'google_cloud\']','text':'I am angry today', 'entities_to_find': '','language': 'en-US'}
```
### Get results
```python
response = requests.request("POST", url, headers=headers, data = payload)
print(response.text.encode('utf8'))
```

## Response example
<details>
<summary>

```json
[
  {
    "solution_name": "Google Cloud",
    "execution_time": "1.13098",
    "result": {
      "text": "The score of a document's sentiment indicates the overall emotion of a document. The magnitude of a document's sentiment indicates how much emotional content is present within the document, and this value is often proportional to the length of the document.",
      "entities": [
        "sentiment",
        "score",
        "emotion",
        "document",
        "document",
        "length",
        "document",
        "value",
        "sentiment",
        "magnitude"
      ],
      "importances": [
        0.26029906,
        0.23038922,
        0.12310704,
        0.10606962,
        0.07379026,
        0.057927556,
        0.047217775,
        0.03690446,
        0.033434283,
        0.030860726
      ],
      "categories": [
        "OTHER",
        "OTHER",
        "OTHER",
        "OTHER",
        "OTHER",
        "OTHER",
        "OTHER",
        "OTHER",
        "OTHER",
        "OTHER"
      ],
      "urls": [
        "\nnull,\nnull,\nnull,\nnull,\nnull,\nnull,\nnull,\nnull,\nnull,\nnull\n"
      ],
      "classification": {
        "OTHER": [
          {
            "entity": "sentiment",
            "importance": 0.26029906,
            "url": "null"
          },
          {
            "entity": "score",
            "importance": 0.23038922,
            "url": "null"
          },
          {
            "entity": "emotion",
            "importance": 0.12310704,
            "url": "null"
          },
          {
            "entity": "document",
            "importance": 0.10606962,
            "url": "null"
          },
          {
            "entity": "document",
            "importance": 0.07379026,
            "url": "null"
          },
          {
            "entity": "length",
            "importance": 0.057927556,
            "url": "null"
          },
          {
            "entity": "document",
            "importance": 0.047217775,
            "url": "null"
          },
          {
            "entity": "value",
            "importance": 0.03690446,
            "url": "null"
          },
          {
            "entity": "sentiment",
            "importance": 0.033434283,
            "url": "null"
          },
          {
            "entity": "magnitude",
            "importance": 0.030860726,
            "url": "null"
          }
        ]
      }
    },
    "api_response": {
      "entities": [
        {
          "name": "sentiment",
          "type": "OTHER",
          "metadata": {},
          "salience": 0.26029906,
          "mentions": [
            {
              "text": {
                "content": "sentiment",
                "beginOffset": 26
              },
              "type": "COMMON"
            }
          ]
        },
        {
          "name": "score",
          "type": "OTHER",
          "metadata": {},
          "salience": 0.23038922,
          "mentions": [
            {
              "text": {
                "content": "score",
                "beginOffset": 4
              },
              "type": "COMMON"
            }
          ]
        },
        {
          "name": "emotion",
          "type": "OTHER",
          "metadata": {},
          "salience": 0.12310704,
          "mentions": [
            {
              "text": {
                "content": "emotion",
                "beginOffset": 58
              },
              "type": "COMMON"
            }
          ]
        },
        {
          "name": "document",
          "type": "OTHER",
          "metadata": {},
          "salience": 0.10606962,
          "mentions": [
            {
              "text": {
                "content": "document",
                "beginOffset": 71
              },
              "type": "COMMON"
            }
          ]
        },
        {
          "name": "document",
          "type": "OTHER",
          "metadata": {},
          "salience": 0.07379026,
          "mentions": [
            {
              "text": {
                "content": "document",
                "beginOffset": 248
              },
              "type": "COMMON"
            }
          ]
        },
        {
          "name": "length",
          "type": "OTHER",
          "metadata": {},
          "salience": 0.057927556,
          "mentions": [
            {
              "text": {
                "content": "length",
                "beginOffset": 234
              },
              "type": "COMMON"
            }
          ]
        },
        {
          "name": "document",
          "type": "OTHER",
          "metadata": {},
          "salience": 0.047217775,
          "mentions": [
            {
              "text": {
                "content": "document",
                "beginOffset": 180
              },
              "type": "COMMON"
            }
          ]
        },
        {
          "name": "value",
          "type": "OTHER",
          "metadata": {},
          "salience": 0.03690446,
          "mentions": [
            {
              "text": {
                "content": "value",
                "beginOffset": 199
              },
              "type": "COMMON"
            }
          ]
        },
        {
          "name": "sentiment",
          "type": "OTHER",
          "metadata": {},
          "salience": 0.033434283,
          "mentions": [
            {
              "text": {
                "content": "sentiment",
                "beginOffset": 111
              },
              "type": "COMMON"
            }
          ]
        },
        {
          "name": "magnitude",
          "type": "OTHER",
          "metadata": {},
          "salience": 0.030860726,
          "mentions": [
            {
              "text": {
                "content": "magnitude",
                "beginOffset": 85
              },
              "type": "COMMON"
            }
          ]
        }
      ],
      "language": "fr-FR"
    },
    "found_entities": 0
  },
  {
    "solution_name": "IBM",
    "execution_time": "1.641283",
    "result": {
      "text": "The score of a document's sentiment indicates the overall emotion of a document. The magnitude of a document's sentiment indicates how much emotional content is present within the document, and this value is often proportional to the length of the document.",
      "entities": [],
      "importances": [],
      "categories": [],
      "urls": [],
      "classification": {}
    },
    "api_response": {
      "usage": {
        "text_units": 1,
        "text_characters": 257,
        "features": 1
      },
      "language": "en",
      "entities": []
    },
    "found_entities": 0
  },
  {
    "solution_name": "Microsoft Azure",
    "execution_time": "0.919437",
    "result": {
      "text": "The score of a document's sentiment indicates the overall emotion of a document. The magnitude of a document's sentiment indicates how much emotional content is present within the document, and this value is often proportional to the length of the document.",
      "entities": [],
      "importances": [],
      "categories": [],
      "urls": [],
      "classification": {}
    },
    "api_response": {
      "documents": [
        {
          "id": "1",
          "entities": [],
          "warnings": []
        }
      ],
      "errors": [],
      "modelVersion": "2020-04-01"
    },
    "found_entities": 0
  },
  {
    "solution_name": "Amazon Web Services",
    "execution_time": "0.451091",
    "result": {
      "text": "The score of a document's sentiment indicates the overall emotion of a document. The magnitude of a document's sentiment indicates how much emotional content is present within the document, and this value is often proportional to the length of the document.",
      "entities": [],
      "importances": [],
      "categories": [],
      "urls": [],
      "classification": {}
    },
    "api_response": {
      "Entities": [],
      "ResponseMetadata": {
        "RequestId": "bf8cf2e7-29a9-4659-ac7f-e0b124465ecb",
        "HTTPStatusCode": 200,
        "HTTPHeaders": {
          "x-amzn-requestid": "bf8cf2e7-29a9-4659-ac7f-e0b124465ecb",
          "content-type": "application/x-amz-json-1.1",
          "content-length": "15",
          "date": "Wed, 05 Aug 2020 08:58:48 GMT"
        },
        "RetryAttempts": 0
      }
    },
    "found_entities": 0
  }
]

```

</details>

## Blog articles
We provides on our website some [blog articles on AI engines](https://www.edenai.co/blog)

## Contact
If you have any question or request, you can contact us at contact@edenai.com

## Terms of use
You can access to our terms [here](https://www.edenai.co/terms) on our website.

#
![Screenshot](https://github.com/ai-compare/Speech_to_text-API/blob/ba9d4f1668d8758141f24240d1287640b4211c63/Logo%20complet%20Eden%20AI%20-%20format%20PNG.png)
