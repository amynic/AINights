## Task 1: Microsoft Azure Cognitive Services - Computer Vision

In this task you will try out the Cognitive Services using the website demo options

Navigate to: [https://azure.microsoft.com/en-gb/services/cognitive-services/directory/vision/](https://azure.microsoft.com/en-gb/services/cognitive-services/directory/vision/?WT.mc_id=ainights-github-amynic)

![Computer Vision website Link highlighted](/docs-images/computer-vision-link.JPG)

There are lots of different demos to try in each section (Scene and Activity Recognition in Images, OCR, Face Detection, Emotion Detection, Video indexer etc)

Select the **Demo** link next to **Scene and activity recognition in images** under **Computer Vision**. There are also other demo links to explore the different services

![Computer Vision Example](/docs-images/computer-vision-demo.JPG)

Now select **Browse** button and upload the **cat.jpeg** or **city.jpeg** image from ```sample-images/computer-vision-web-browser/cat.jpeg```

![Computer Vision Cat Example](/docs-images/cat-sample.JPG)

## Task 2: Microsoft Azure Cognitive Services - Text Analytics via REST

Now you will try using the REST protocol as you would use to integrate these services into an application

First log into [Microsoft Azure](https://azure.microsoft.com/en-gb/?WT.mc_id=ainights-github-amynic) and choose **Portal** in the top right corner.

Once in the portal select **Create a resource** and search **Cognitive Services** and choose Enter. Then select **Create** on the Cognitive Services blade

![Create Cognitive Services Account](/docs-images/cognitive-azure.JPG)

Enter details to create an account:
* **Name:** enter a suitable name for the service (example: ainightscognitive)
* **Subscription:** Choose your subscription
* **Location:** Choose your closest Data Center available
* **Pricing Tier:** S0
* **Resource Group:** Select 'Create new', and provide a sensible name (example ainights)
* **select the checkbox after reading the terms below**
* **select 'Create'**

![Cognitive Services Details](/docs-images/cognitive-details.JPG)

Once created, in your notifications (top right corner) select **go to resource**
![Go to Resource](/docs-images/go-to-resource.JPG)

In the Cognitive Services page, select **Keys** and copy **KEY 1**
![Copy Key](/docs-images/keys.JPG)

Now select **Overview** in the left hand pane and copy the **Endpoint** variable
![Copy Endpoint](/docs-images/endpoint.JPG)

Download and open Postman, an API Development environment on your local machine. 
> Find the download in the [Pre-requisites section](#Pre-requisites-for-your-machine)


Select **Request**

![Create A Request](/docs-images/create-request.JPG)

Enter request details as below and choose the option **create a new collection** and name it "Text Analytics Samples"

![Enter Request Details](/docs-images/save-request.JPG)

Select the newly created collection and choose save

![Save Request](/docs-images/save.JPG)

Now create a request to call your text analytics API:
* Change from a GET request to a POST request in the top left
* Enter your endpoint URL and add ```text/analytics/v2.0/sentiment``` to the end
* Select Headers underneath the URL box
* In Key type ```Ocp-Apim-Subscription-Key``` and in Value add your KEY1 value
* In Key type ```Content-Type``` and in Value type ```application/json```
* ![Headers and URL](/docs-images/url-and-headers.JPG)
* Select Body underneath the URL box
* Select ```raw``` from the radio button options
* Copy JSON sample from ```sample-code/cognitive-services-api-task/sentiment-analysis-text.json``` into the box
* Select the ```Send``` button and review the Response
* ![Body and Submit REST Request](/docs-images/rest-body.JPG)

You can also try other options from the REST API - such as KeyPhrases function. Change the end of the URL from sentiment to keyPhrases and select send to view the key phrases for the example text.

* ![Key Phrases REST Request](/docs-images/keyphrases.JPG)

> Check out the language support for the Text Analytics API [here](https://docs.microsoft.com/en-gb/azure/cognitive-services/text-analytics/language-support/?WT.mc_id=ainights-github-amynic). If your language is supported please edit the JSON file to translate the text and show the functionality of the API above. There is an example of a French JSON file in ```sample-code/text-analytics-demo/sentiment-analysis-text-fr.json``` please edit this file as appropriate

> If you have any issues running Postman, API Development Environment you can always run the REST API requests within the API docs for [sentiment analysis](https://northeurope.dev.cognitive.microsoft.com/docs/services/TextAnalytics.V2.0/operations/56f30ceeeda5650db055a3c9/?WT.mc_id=ainights-github-amynic) and [key phrase extraction](https://northeurope.dev.cognitive.microsoft.com/docs/services/TextAnalytics.V2.0/operations/56f30ceeeda5650db055a3c6/?WT.mc_id=ainights-github-amynic). Select the data centre you are using and then enter your key in the box provided along with the sample body sample used in Postman