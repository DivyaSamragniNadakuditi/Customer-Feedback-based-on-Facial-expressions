# Customer-Feedback-based-on-Facial-expressions
Facial recognition is one of the active research areas from the past few decades. Facial expression recognition is a part of facial recognition. To achieve this, there are many Machine learning and Artificial Intelligence Techniques. In this work, we are using deep learning and image classification. We use Convolutional Neural Network to determine the expression. We use these techniques and recognize different facial expressions for feedback of the products. We are using Amazon Deeplens to identify the customers and their expressions. Further services on Amazon are used to train the datasets and note the feedback.

<h2> Introduction</h2>
Customer Feedback is the main segment in any industry. Although there are many types of questionnaires and other feedback collection techniques, there is no means to take live and immediate feedback update from the customers. Our main goal of this work is to replace a group of people to subjectively give feedback about the food in a restaurant, the reaction for a movie or experience of shopping of customers reactions using Amazon Deeplens to capture it. This can increase the scope of the customers participating in the feedback as we do not need humans to take time in giving the feedback. In this work, we detect the faces and categorize the expressions and aggregate them using our own trained models on Amazon Deeplens and using Amazon services.

<h2>Methods</h2>
We use Amazon Deeplens for the customers reactions, Convolutional Neural Network is used to categorize the expression in the frame and the results are aggregated using IoT. Before training the model, we will use Amazon Rekognition for labeling the images. OpenCV’s Haar Cascades for image cropping. We then train the Convolutional Neural Network and output the model into S3. Based on face recognition, we then run a lambda function to detect faces and then optimize the cropped face in recognizing the facial expression.

<h2>Expected Results</h2>
The expected results of this work is to record the feedback of the customer using facial expression that are recorded from Amazon Deeplens. This recorded feedback can be used further to do predictive analysis and draw interesting and necessary conclusions that can enhance the business. 

<h2> AWS Architecture</h2>

We have designed the following architecture for our project:
![Image 1](https://github.com/DivyaSamragniNadakuditi/Customer-Feedback-based-on-Facial-expressions/blob/master/Customer%20Feedback%20based%20on%20Facial%20Emotion%20%20Architecture.png)
