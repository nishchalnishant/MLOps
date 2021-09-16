    1. Modeling overview --

    	- Some of the key challenges in producing the ml model deployment

    	- We will be focusing on the modeling part of the ml deployment.

    	- The artificial intelligence development can be
    		□ Model centric artificial intelligence dev.
    		□ Data centric artificial intelligence dev.

    	- For practical purposes , we try to go for data centric approach , this means that we try to get better , normalized data for our models

    2. Key challenges --

    	- Ai system = code [algorithm/ model / hyperparameters ] + data

    	- Doing well on training set

    	- Doing well on the dev / test set

    	- Doing well on business metrics/ projects goal

    	- In each iteration try to improve either model , hyperparameters or data

    3. Why low average error isn't good enough --

    	- There several other problems in mlops --
    		□ Low error rate overall but , fails in key queries
    			□ Ex -- web search queries [ informational and transactional queries , want a group of result or want a specific result ]
    			□ Or navigational queries [ want an exact output ]
    			□ As avg. error rate treat both of them equally , other ideas might not get  treated well

    		□ Performance on key slice of the dataset
    			□ Model doesn't discriminate a certain group of people
    			□ There can be different level of performance depending on the type of data we are working with.

    		□ Rare classes --
    			□ Mostly common in skewed data set, ex -- medical data set we will get a better accuracy , but it wont be any good
    			□ Just working good on the test dataset doesn't guarantee that it will work efficiently in real world


    4. Establish a baseline --

    	- First step in modeling can be to establish a bassline and then improve on that .

    	- Ex-- speech recognition

    		□

    		□ We can use the human level performance as the baseline for our experiments and use ml algorithms to get better result than the human level performance.

    	- best practices for establishing a baseline are quite different, depending on whether you're working on unstructured or structured data.

    		□

    5. Tips for getting started

    	- Model + hyperparameter + data



    		- Being able to start initially gets to project going

    	- Pick up deployment constraints when picking up the model



    	- Sanity check for code and algorithm

    		- Check or train the algorithms for one or two cases after that then try to improve if the model is working as intended




    1. Error analysis example --

    	- one can make the spreadsheet where we have the error listed with different characteristics to the different error we observed , that might have affected the data

    	- This can help use in error analysis , this can be done manually but now there are several mlops tools for the same



    	- For each tag we can use the metrics , to get better insights of tag.

    	- We can also apply a tag to misclassified and correctly classified tags .

    	- This error analysis can be done using the manual process , but now we have several mlops tools where we can analyze the error effectively .

    	- Error analysis also are iterative process as for every update in the model we come over the new types of error analysis

    2. Prioritizing what to work on --

    	- We can also look at the percentage of the data having a particular tag and decide where increase in accuracy could lead to better overall accuracy



    	- Here we can see that the improving in clean speech can lead us to better overall efficiency .

    	-

    	- To improve the performance for a certain tag , we can



    8. Skewed data sets --

    	- One of the better matrices to decide the accuracy of our mode for classification can be confusion matrix , where we have tp, tn, fp ,fn .

    	-

    	- F1 is the harmonic mean of precision and recall.

    	- Greater f1  better model

    9. Performance auditing --

    	- Although the model has good metrics , we must do a final audit on data as it will be final naik in the coffin .

    	- It might also help us recognize the bias  which might be problematic later .

    	- There are several mlops tools for the same

    	-


    10. Data-centric AI development --

    	- Research is model centric view  , while actual implementation has the data centric view



    	- We can improve the data quality using many techniques , one such use case is data augmentation

    11. A useful picture of data augmentation --



    	- we can close the gap between the mlp and hlp in library noise ,café noise, food court noise .

    	- It turns out that for unstructured data problems, pulling up one piece of this rubber sheet is unlikely to cause a different piece of the rubber sheet to dip down really far below.

    	- Instead, pulling up one point causes nearby points to be pulled up quite a lot and far away points may be pulled up a little bit,

    	- To do so we need more data
    		Either we can collect new data or we can just augment the data

    12. Data augmentation --

    - Good for unstructured data , but we need to make a lot of choices to setup the data augmentation .

    -

    - For audio data

    	- We can mix and match several sound
    	- Generally we mix for cases where our model is working badly

    - For image data --

    	- We have very type of the data augmentation
    	- Gans etc. are very complex for these task

    - Data iteration loop --
    	-

    13. Can adding data hurt?

    	- Usually no



    	- An example can be ocr for image recog. For I and 1 where in many cases I is not present and if we use data augmentation with more I then it will be more biased toward I thus will hamer the performance

    14. Adding features --

    • There can be cases when the restaurant recommendation algorithm where , we can have certain hand coded features which can be more beneficial in cases for making artificial person or restaurant








    15. Experiment tracking

    - When we have  a lot of experiments we need to track them to not repeat it .

    		-

    - For tracking we can use following tools [ in order of experience ]

    		-

    	- some examples include Weight &Biases, Comet, MLflow, Sage Maker Studio, Verta.ai Granseal

    	-

    	- We must no worry about which experiment tracking system to use , rather our goal should be to worry about tracking all the goals in what to track

    16. From big data to good data --


