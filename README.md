# watsonvisioninstagramclassifygeneral

Use the code snippets below to classify images against your model.
For reference, the full API specification is available here.
pip

pip install --upgrade "watson-developer-cloud>=2.4.1"
Authentication

from watson_developer_cloud import VisualRecognitionV3

visual_recognition = VisualRecognitionV3(
    version='{version}',
    iam_apikey='{apikey}'
)
Classify an image

import json
from watson_developer_cloud import VisualRecognitionV3

visual_recognition = VisualRecognitionV3(
    '2018-03-19',
    iam_apikey='{iam_api_key}')

with open('./fruitbowl.jpg', 'rb') as images_file:
    classes = visual_recognition.classify(
        images_file,
        threshold='0.6',
	classifier_ids='default').get_result()
print(json.dumps(classes, indent=2))
