> Specialization overview

- There is a lot of difference in building the model and deployment .
- As there can be many different forms of deployment .
- This specialization has 4 courses
  First -- Overview of lifecycle of production ml project
  Second -- Data -- how it evolves overtime , using tfx
  Third -- Ml modeling pipeline and production
  Fourth Deployment -- serve users the requests

> Introduction to machine learning in production

- Maximum value of a ml model can be achieved when deployed efficiently .
- Edge device -- device which is in factory , which takes the raw data [ as an image , audio , video] which passes the data to a prediction server through an api .
- The server then predicts the value and submits it to the edge device.
- Preferably prediction server is on edge

![Requirements surrounding ML infrastructure](https://github.com/nishchalnishant/MLOps/blob/main/img/S_1_1.png)

- But what goes into prediction server -- our model
- But there can be any problems that can arise , some of them are --
- - Sometimes the training model works very well on the training data , but very bad on the actual data .
- - It can be because of
    There is training , testing data drift
- - There can be several other things in addition to ml code needed for production [ actually 5% code is the ml code , rest of the production things are the deployment code ]
- - Because of these there is a POC [ proof of concept ] to production gap

These components can be --

![Requirements surrounding ML infrastructure](https://github.com/nishchalnishant/MLOps/blob/main/img/S_1_2.png)

> Machine learning Data lifecycle in production

- We will cover the data journey over production system lifecycle.
- Implement feature engineering , transformation and selection using tfx
- Improve data for better training and generalization .
- Main focus is on data , how to get better data for deploying ml systems

> Machine Learning Modelling Pipelines in Production

- This third course is about building and maintaining models for different serving environments.
- The modules covered in this course, will tightly integrate with the data pipelines you built in the second course.
- This course focuses on implementing tools and techniques to effectively manage your modelling resources and best serve batch and real-time inference requests.
- In this course, you'll implement effective search strategies for the best model that will scale for various serving needs while constraining model complexity and hardware requirements.
- You'll optimize and manage this compute storage and IO resources your model needs in production environments during its life cycle.
- In this journey, you will continue to use the TFX library and rely on tools like AutoML for finding the best suitable model and TensorFlow model analysis to address model fairness, explain ability issues, and mitigate bottlenecks.

![Tensorflow model analysis ](https://github.com/nishchalnishant/MLOps/blob/main/img/S_3_1.png)
