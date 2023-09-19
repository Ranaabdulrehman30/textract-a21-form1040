## Processing forms containing hand-written Form-1040 using Amazon Textract, Amazon A2I and Comprehend


We walk you through the following steps using this Amazon SageMaker Jupyter notebook :

1. Prerequisite step
2. Use Amazon Textract to retrieve key-pair and tabular data from document, inspect and analyze line items from Amazon Textract response.
3. Set up  Amazon A2I human loop to review and change the entries from the Amazon Textract response.
4. Set up Amazon Comprehend to identify custom entities in the form.

## Services Used
This solution uses AI services, and SageMaker.
* Amazon Textract– Uses ML to extract text and data from scanned documents in PDF, JPEG, or PNG formats. 
* Amazon A2I – to get human review of low confidence predictions or a random sample of predictions.
* Amazon Comprehend - to get the entites inside the the document.

## This sample includes:

* README.md - this file

* amazon-textract-a2i-Comprehend-1040Form-Demo.ipynb - Jupyter Notebook containing details of how to use Amazon Textract to extract the content of your documents containing hand-written key-pair and tabular data, setup and send to a human review loop, and augment the extracted invoice content for downstream processing. The template used for creating human in loop is a custom html template. The output of the human in loop is stored as an updated the dataframes at the end which can then be stored in a database.

* amazon-textract-AWS-Template-Demo.ipynb - Jupyter Notebook containing details of how to use Amazon Textract to extract the content of your documents containing hand-written key-pair and tabular data, setup and send to a defalut template human review loop with a limitation that it doesn't incorporate the tables present in the form.

* cfntextracta2i.yaml - this file contains the infrastrcutre code used by AWS CloudFormation to deploy notebook in your aws account.

## How to run the jupyter notebooks:

* Once the notebook instance is launched containing the jupyter notebooks. Open a notebook. The pdf files should in stored in the home directory of the instance where the other notebook files are located. Copy the name of the pdf file and place it in the notebook with a variable name called (documentName). Then Run each cell till the url is generated for the human in loop.

* In order to get access to the human in review you need to add yourself as a worker in the team. Go to Amazon Sagemaker-> Labelling Workforces, Select "Demo" and "Textract Demo" Private teams and add a member to the team. In order to add you need to have an Email and a password.
