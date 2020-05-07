# Customer-Feedback-based-on-Facial-expressions
Facial recognition is one of the active research areas from the past few decades. Facial expression recognition is a part of facial recognition. To achieve this, there are many Machine learning and Artificial Intelligence Techniques. In this work, we are using deep learning and image classification. We use Convolutional Neural Network to determine the expression. We use these techniques and recognize different facial expressions for feedback of the products. We are using Amazon Deeplens to identify the customers and their expressions. Further services on Amazon are used to train the datasets and note the feedback.

<h2> Introduction</h2>
Customer Feedback is the main segment in any industry. Although there are many types of questionnaires and other feedback collection techniques, there is no means to take live and immediate feedback update from the customers. Our main goal of this work is to replace a group of people to subjectively give feedback about the food in a restaurant, the reaction for a movie or experience of shopping of customers reactions using Amazon Deeplens to capture it. This can increase the scope of the customers participating in the feedback as we do not need humans to take time in giving the feedback. In this work, we detect the faces and categorize the expressions and aggregate them using our own trained models on Amazon Deeplens and using Amazon services. 

To acheive this we need to identify and localize the faces from the image. The solution takes an input image and a bounding box is created where the face is found. We train the dataset and create a training job for the algorithm. We have used Single Dhot Multi box Detector SSD on Amazon SageMaker. The training dataset is converted into RecordIO Format. We need train.lst and val.lst files to create the record IO format files. These are then uploaded into a S3 bucket and train the model. Once the model is trained we will host and test it. After Successful testing, we can deploy the model to our AWS Deeplens Device.

<h2>Expected Results</h2>
The expected results of this work is to record the feedback of the customer using facial expression that are recorded from Amazon Deeplens. This recorded feedback can be used further to do predictive analysis and draw interesting and necessary conclusions that can enhance the business. 

<h2> AWS Architecture</h2>

We have designed the following architecture for our project:
![Image 1](https://github.com/DivyaSamragniNadakuditi/Customer-Feedback-based-on-Facial-expressions/blob/master/Customer%20Feedback%20based%20on%20Facial%20Emotion%20%20Architecture.png)

<h3> Register your AWS Deeplens device</h3>
Here are the steps to register your AWS Deeplens Device:

![Image 1](https://github.com/DivyaSamragniNadakuditi/Customer-Feedback-based-on-Facial-expressions/blob/master/AWS%20Deeplens.JPG)
![Image 3](https://github.com/DivyaSamragniNadakuditi/Customer-Feedback-based-on-Facial-expressions/blob/master/Register%20Device.JPG)
![Image 7](https://github.com/DivyaSamragniNadakuditi/Customer-Feedback-based-on-Facial-expressions/blob/master/Hardware%20Selection.JPG)
![Image 4](https://github.com/DivyaSamragniNadakuditi/Customer-Feedback-based-on-Facial-expressions/blob/master/configure%20Account.JPG)
![Image 5](https://github.com/DivyaSamragniNadakuditi/Customer-Feedback-based-on-Facial-expressions/blob/master/Download%20certificate.JPG)
![Image 6](https://github.com/DivyaSamragniNadakuditi/Customer-Feedback-based-on-Facial-expressions/blob/master/connect%20your%20device.JPG)

<h3> AWS Sagemaker</h3>
In Sagemaker create a notebookinstace where you can train the model:

![Image 1](https://github.com/DivyaSamragniNadakuditi/Customer-Feedback-based-on-Facial-expressions/blob/master/Aws%20Sagemaker.JPG)
![Image 9](https://github.com/DivyaSamragniNadakuditi/Customer-Feedback-based-on-Facial-expressions/blob/master/Notebook%20Instance.JPG)
![Image 10](https://github.com/DivyaSamragniNadakuditi/Customer-Feedback-based-on-Facial-expressions/blob/master/create%20notebook%20instance.JPG)
![Image 11](https://github.com/DivyaSamragniNadakuditi/Customer-Feedback-based-on-Facial-expressions/blob/master/Set%20IAM%20for%20notebook%20Instance.JPG)
![Image 12](https://github.com/DivyaSamragniNadakuditi/Customer-Feedback-based-on-Facial-expressions/blob/master/Open%20Notebook%20Instance%20in%20Jupyter.JPG)
![Image 13](https://github.com/DivyaSamragniNadakuditi/Customer-Feedback-based-on-Facial-expressions/blob/master/train%20your%20model.JPG)

<h2>Setup and Data preparation in AWS SageMaker</h2>
For preparing the data we would need OpenCV for image size gathering and horizontal flipping of images, and MXNet is required to use im2rec for generating recordIO database of our dataset. So we first install them. Also we would need a S3 bucket to provide training and validation datasets and store trained artifacts model. Also to use the AWS services we need to use the execution role that has been created for the notebook you are using. This includes the access to S3 bucket as well.

Image:

We now have to download the dataset to our instance. I have used the dataset from kaggle. So we first need to install kaggle and then download the dataset and unzip them. We then define the a few parameters to train only a handfull of images. The files that are used define the parameters like names and locations of metadata files of the dataset.

<h2> Generating RecordIO files </h2>
We now extract height and width of each image and store them in a file for future use.We geneerate the Train.lst and val.lst files.Now, we need to create a im2rec database for our dataset.

