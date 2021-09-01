    	- for monitoring models
    	- 3 types
    	○ Amazon sage maker model monitor
    		§ Part of amazon sage maker that enables to build , train and deploy ml models
    		§ Automatically monitor ml model in production and alerts whenever data quality issues appear.
    		§ Helps to save time and resources
    		§ We can use this tool on any endpoint
    		§ We can capture prediction and store in simple storage service s3 bucket .
    		§ Captured data is with metadata
    		§ Launch a monitoring schedule and receive reports that contains statistics and schema info on data received during latest time frame

    	○ Hydrosphere
    		§ Opensource  for managing ml models
    		§ Allows  to monitor production ml in real time
    		§ Use diff statistical and ml methods to check if production distribution matches the training one
    		§ Supports external infrastructure thus we can connect model hosted outside hydrosphere
    		§ Use statistical drift detection to monitor change in data over time
    		§ Monitors anomalies with custom knn metric
    		§ Supports tabular , image and text data
    		§ One gets notified when metrics change

    	○ Cortex
    		§ Already used in model serving
    		§ Open source alternative to serving models with sage maker
    		§ Can deploy any type of model
    		§ Automatically scale api to handle production workloads
    		§ Run inference on any aws instance type
    		§ Deploy multiple models in a single api and update deployed api without downtime
    		§ Monitor api performance and prediction result
