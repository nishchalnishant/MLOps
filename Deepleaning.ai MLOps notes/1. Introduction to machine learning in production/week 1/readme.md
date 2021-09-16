    3. Steps of an ML Project --

    	- One should plan out all the steps we need to take to complete the ml project to an end .

    	- As ml is an iterative process we may need to go back again and again to augment the data , model based on our need .

    		• Scoping
    			□ Define project ( X -> y )

    		• Data
    			□ Define data and establish a baseline
    			□ Label and organize the data

    		• Modeling
    			□ Select and train the model
    			□ Preform and error analysis

    		• Deployment
    			□ Deploy in production
    			□ Monitor and maintain the system

    		•

    4. Case study: speech recognition --

    	- Scoping

    		□ Define project ( X -> y )
    		□ Decide to work on speech recognition for voice search
    		□ Decide on key metrics
    			□ Accuracy latency , throughput
    		□ Estimate the resources and timeline etc.

    	- Data

    		□ Getting better data gives us the better result than using better coding
    		□ Define data and establish a baseline
    		□ Label and organize the data
    		□ Is the data labeled consistently

    			□

    			□ The data transcription must be done using the same convention

    			□

    		□ How much silence before / after each clip .
    		□ How to perform volume normalization .

    	- Modeling

    		□ Select and train the model
    		□ Preform and error analysis
    		□ Here we need to take care of
    			□ Code (model/ algorithm)
    			□ Hyper parameters
    			□ Data
    		□ In research work  we tend to fix the data and vary the code and Hyperparameters.
    		□ For the product teams we have fix code , and we tend to vary the hyperparameters and data
    		□ In production environment varying data and hyperparameters can give us greater reward than varying code
    		□ We can perform error analysis on the data to improve the quality of the data .
    		□
    			□ Research -- model centric approach
    			□ Product -- data centric approach [ targeted data better than more data ]

    	- Deployment

    		□ Deploy in production
    		□ Monitor and maintain the system
    		□ There are various option for deployment , depending on the situation we can select the best option
    		□ In this case we can use something like

    			□

    		□ Challenges during deployment --
    			□ Concept drift
    				® The actual is not similar to the data on which the model was trained on
    				® If size of house doesn’t change but price change due to inflation
    			□ Data drift
    				® Over time the data on which the model is making predictions starts differing from the original data on which it was trained on .
    				® If price doesn’t change but size of house change

    5. Course outline [ what we learnt till now ] --

    	- it can be easy if we move backwards from deployment to modeling to data to scoping

    	- This course has following types
    		□ Week 1 -- deployment
    		□ Week 2 -- modeling
    		□ Week 3 -- data , scoping

    	- Whole set of activities can be grouped under a topic called Mlops --
    		□ It is an emerging discipline and comprises a set of tools and principals to support progress through the ml project lifecycle

    	-

    6. Key challenges  [ deployment ]

    	- What makes deployment hard
    		□ Machine learning issues [ data / concept drift ]
    			□ Change in data distribution
    				® Gradual change
    				® Rapid change [ shock ] change in credit card fraud system

    			□ Concept drift, which is when the definition of what is y given x changes. As well as Data drift, which is if the distribution of x changes, even if the mapping from x or y does not change.

    				□ Concept drift

    					® Change in the distribution data .
    					® Sometimes the change in data is gradual while in some cases there are sudden changes
    					® If size of the houses remains same but the price of house

    				□ Data drift

    					◊ but sometimes the term data drift is used to describe if the input distribution x changes, such as if a new politician or celebrity suddenly becomes well known and he's mentioned much more than before.
    					◊ The term concept drift refers to if the desired mapping. From x to y changes such as if, before COVID-19.
    					◊ Credit card fraud during covid and before covid


    			□ Training data is from past 2 years but the validation data is from past 2 month

    		□ Software engineering issues

    			These issues can be dealt using checklist for several questions

    				- Realtime or batch

    				- Cloud vs edge
    					◊ Cloud if we need more compute
    					◊ Edge if connection is not guaranteed , if data privacy is important

    				- Compute resources [gpu/cpu/memory]
    					◊ Similar resources for training and practical output

    				- Latency throughput [QPS]

    				- Logging
    					◊ when building your system it may be useful to log as much of the data as possible for analysis and review as well as to provide more data for retraining your learning algorithm in the future.

    				- Security and privacy
    					◊ There can be different level of security and privacy needed depending on use cases

    	- Deployment has 2 tasks --
    		□ Deploy in production
    			□ Software
    		□ Monitor and maintain the system
    			□ Check for concept / data drift

    	- So the deployment can be divided into 2 phases , practices in these 2 phases are totally different
    		□ Deployment
    		□ Maintenance

    7. Deployment patterns --

    	- There are  use cases and several patterns  for deployment

    		□ New production / capability
    			□ Gradual ramp up with monitoring as the algo is not fully proven , this is called canary deployment .
    			□ We run with a small percentage of the data early on Roll back if not working

    		□ Automate / assist with manual task
    			□ Shadow mode -- run the ml model  with the human judgement
    			□ We can sample the output to see if our ml model is doing good

    		□ Replace previous ml system
    			□ Blue green deployment
    			□ We have both model running where we suddenly switch the traffic to the new server and check if the model is working perfectly or not
    			□ We can deploy these using complete deployment or gradual increase in deployment

    		□ Key ideas --
    			□ Gradual ramp up with monitoring
    			□ Rollback

    		□ There are several mlops tools which can help us in these deployments

    	- Degree of automation --
    		□ We must think deployment not as a binary value [ deployment or nor ] but instead we can use degree of automation where both automation and human task remains .
    		□ Partial automation can be the best use case for us .
    			□ Human only
    			□ Shadow mode
    			□ Ai assistance
    				- Human in the loop
    			□ Partial automation
    				- Human in the loop deployment
    			□ Full automation

    8. Monitoring

    	- Monitoring dash board
    		□ May monitor different metrics
    		□ To find the metrics which we need to monitor , we must brainstorm what can go wrong and decide the metric which can show that problem

    		□ The metrics to be monitored can be divided into
    			□ Software metrics [ many mlops software come in built with this ]
    				- Memory
    				- Compute
    				- Latency
    				- Throughput
    				- Server load
    			□ Input metrics [ metrics about the incoming data for our mlops application ]
    				- Avg. input length
    				- Avg. input volume
    				- Number missing values
    				- Avg. image brightness
    			□ Output metrics [ metrics about the outgoing data for our mlops application ]
    				- Times return ' ' [ null]
    				- Times user redoes search
    				- Times user switches to typing
    				- Click through rate

    	- Just as ml modeling is iterative, so is the deployment



    	- In addition to monitoring the metrics we can set a threshold for alarms
    	- Based on metric we need to adapt to it , it can be software adaptation or hardware adaptation
    	- Model maintenance can be done in
    		□ Manual retraining
    		□ Automatic retraining

    9. Pipeline monitoring --

    	- Generally the ml models are implemented using pipelines where the data cleaning , augmentation takes place .
    	- We use pipeline so that we can pass better data or data as expected by our model for prediction .
    	- In addition to model , input and output monitoring we may also need to monitor the pipeline monitoring .
    	- We can use the same types of metrics earlier applies in pipeline monitoring also.

