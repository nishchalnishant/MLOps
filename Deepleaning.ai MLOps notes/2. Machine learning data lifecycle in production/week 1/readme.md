    	3. Overview --

    		- There are differences between the data in research and business .
    		- Data is the most important thing for any ml process to succeed.

    			□

    			□

    			□

    			□

    			□

    			□

    			□

    		We have well established tools to do the same .

    	4. ML Pipelines --

    			□

    		- Ml pipeline is used to monitor, build  the model end to end

    			□

    		- ml pipeline are always directed acyclic graphs

    			□

    			□

    			□

    			□

    			□

    			□


    			□ ML Pipelines.

    				® ML Pipelines are the heart of any Production ML system.
    				® we'll begin to introduce ML Pipelines and the concept of MLOps.
    				® Now allow us to see how pipeline orchestrators sequence and schedule ML tasks to implement the entire ML training process.

    				® We will be using the tfx to do ml pipelines

    				® What do we mean by the phrase ML Pipeline?

    					◊ Well, remember the iterative ML workflow that we talked about previously.
    					◊ ML Pipeline is a software architecture to implement exactly that.
    					◊ Automating, monitoring, and maintaining this ML workflow from data to a trained model.
    					◊ ML Pipelines form a key component of MLOps architectures.

    			□ There are some differences between different pipeline architectures, but in general they look something like this.

    			□ You'll notice that they basically mirror the ML development process.
    			□ Starting with data ingestion and ending with a trained model.

    			□ ML Pipelines are almost always directed cyclic graph or DAGs.
    			□ Although in some advanced cases they can sometimes includes cycles.

    			□ A DAG is a collection of all the tasks you want to run sequenced in a way that reflects their relationships and dependencies.

    			□ DAG-- graph the edges are directed and there are no cycles.

    			□ Orchestrators


    				® responsible for scheduling the various components in an ML Pipeline based on dependencies defined by a DAG.
    				® Orchestrators help with pipeline automation.
    				® Examples include Argo and Airflow, and Celery and Luigi and Kube flow.

    			□ TFX is an open-source end to end Machine Learning platform, and it's what we use at Google.
    			□ A TFX Pipeline is a sequence of scalable components that can handle large volumes of data.

    			□ Starting on the left, we ingest data and then we move to Data Validation and we do some feature engineering.
    			□ We train a model, we validate it.
    			□ If it's better than what we already have in production, we're going to push it to production.
    			□ Finally, we're serving predictions.

    			□ The sequence of components are designed for  scalable high performance Machine Learning tasks.

    			□ In this course, you'll be using TFX to implement real ML Pipelines exactly as you would for Production Systems.

    			□ TFX in production components are built on top of open-source libraries,  such as

    				® TensorFlow Data Validation, which you'll also learn about later this week.

    				® TensorFlow Transform -- We shall also be working with extensively  later in this course and others, like TensorFlow Model Analysis.

    		- Components leverage those Libraries and form your DAG as you sequence
    		these components and set up the dependency between them,  you create your DAG, which is your ML Pipeline.

    		- This is what we refer to as the Hello World of TFX.

    		- We start on the left with our data and we're going to ingest our data with a TFX component called ExampleGen.

    		- All the boxes in orange that you see here are TFX components.

    		In fact, these are components that come with TFX when you just do a PIP install.
    			□ we generate statistics for our data.

    				® We want to know the ranges of our features,
    				® if they're numerical features, if they're categorical features,
    				® we want to know what are the valid categories and so forth.
    				® What are the types of our features?
    				® Example Validator is used to look for problems in our data.

    			□ SchemaGen is used to generate a schema for our data across our feature vector.

    			□ Transform will do feature engineering.

    			□ Tuner and Trainer are used to train a model and to tune the hyper-parameters for that model.

    			□ Evaluator is used to do deep analysis of the performance of our model.

    			□ Infra Validator is used to make sure that we can actually run predictions using our model on the infrastructure that we have.

    			□ If all of that passes and the model actually performs better than what we might already have in production.
    			□ Then Pusher pushes the model to Production.

    		- What does that mean?
    			□ Well, we might be pushing to a repository like TensorFlow HUB and then using our model later for maybe transfer learning.

    		- We're generating Embeddings.
    		- We could be pushing to TensorFlow JS.
    		- If we're going to be using our model in a web browser or a Node.js application.
    		- We could push to TensorFlow Lite and use our model in a mobile application or on an IOT device.  Or we could push to TensorFlow Serving and User Model on a server or maybe a serving cluster.

    		- The key points here, first of all, Production ML Pipelines are more than just ML code.
    		- They're ML development and software development and a formalized process for  running that sequence of tasks end to end, in a maintainable and scalable way.
    		- TFX is an open-sourced end to end ML platform that we'll be using in this course.

    		From <https://www.coursera.org/learn/machine-learning-data-lifecycle-in-production/lecture/gzWZQ/ml-pipelines>


    	5. Importance of Data --

    		-

    		- Getting better , accurate data , is most important task and can be the factor behind the success and failure of the ml application .

    		-

    		-

    		-

    		-

    	6. Example Application: Suggesting Runs --

    		-

    		-

    		-

    		-

    		-

    		-

    		-

    		-

    		-



    	7. Responsible Data: Security, Privacy & Fairness --


    		-

    		-

    		-

    		-

    		-

    		-

    		-

    		-


    		-

    	7. Case Study: Degraded Model Performance --

    		Suppose clr drops for a particular group , so we try to

    		-

    		The problem can be of 2 types --

    		-

    		Slow problems can be  ---

    		-

    		Sudden problems --

    		-


    		-

    		But after all of this we need to adapt and change accordingly

    	8. Data and Concept Change in Production ML --

    		-

    		-

    		-

    		-


    		-

    		-


    	9. Process Feedback and Human Labeling --

    		-

    		First 2 are most common

    		-


    		-


    		-

    		-

    		-

    		-

    		-


    		-

    		-

    		-

    		-

    		-

    		-

    	11. Detecting Data Issues --

    		-

    		-

    		-


    		-

    		-

    		-

    		-

    		-


    	11. Tensor Flow Data Validation ---

    		-

    		-

    		-

    		-

    		-

    		-

    		-


    		-

    		-


