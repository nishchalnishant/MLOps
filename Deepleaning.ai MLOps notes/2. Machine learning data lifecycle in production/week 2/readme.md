    	1. Introduction to Preprocessing --

    		- Most of this we have covered but we are going to do it at scale here .

    		-

    		-

    		-

    		-

    	2. Preprocessing Operations --

    		-

    		-

    		-

    		-

    		-

    		-

    		-

    		There can be different ways of scaling the variables
    			□ like min-max normalization, variance scaling (standardization),
    			□ L1 normalization,
    			□ L2 normalization.

    		From <https://www.element61.be/en/resource/standardization-case-real-time-predictions>

    		-

    		- Therefore, when using the deployed model to generate predictions during its operational lifetime, the previously stored mean and standard deviation of the historical (training) data are used to standardize the test data as well.

    		- During its operational lifetime, the model can be periodically retrained after encountering sufficient novel data and the normalization vectors can be updated based on the joint historical and novel data.

    		From <https://www.element61.be/en/resource/standardization-case-real-time-predictions>



    	3. FEATURE ENGINEERING TECHNIQUES --

    		-

    		-

    		-

    		-

    		- ALSO CALLED AS  min max normalization

    		-

    		One can try both and compare the result

    		-

    		We can try binning with facet

    		-

    		One can also try to group out the features together  to get a better result.

    		We can use



    		To explore high dimensional data

    	4. Feature Crosses --

    		- Expressing some features with les feature

    		-

    		-


    	5. Preprocessing Data at Scale --

    		- Preprocessing the data at scale is totally different than preprocessing the dummy data .
    		- One should always use the ml pipeline for this

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


    	6. TensorFlow Transform ---

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

    		- pre-processing at scale,
    			□ we need good tools.
    			□ TensorFlow Transform is one

    		- We are going to go a bit deeper into how transform works, what it does, and why it does it.

    		- going to look at the benefits of using TensorFlow Transform and how it applies feature transformations, and we are going to look at some of the analysers,
    		and the role they play in doing pre-processing.

    		- tf transform --

    			□ it takes Training Data, and it's going to process it.
    			□ The end result is going to be deployed into the Serving System.
    			□ In the middle, there's a PIPELINE that is used, and there is METADATA that forms a key role in organizing and managing the artefacts that are produced as data is transformed.
    			□ We have our Training Data, that is the input data into the system that forms an artefact, we give that to Transform and it transforms our data.
    			□ It's going to take our raw data and move it into the form that we're actually going to use at our feature engineering.
    			□ That's given to the Trainer which is going to do training.

    		- Transform and Trainer here are both components in a ML pipeline, specifically a TFX ML pipeline.
    		- These are the Trainer, of course as a Trained Model, that is also an artefact.
    		- That gets delivered to the serving system or whatever system we're using, where it's going to be used to run inference.

    		- Looking at this a little differently, we're starting with our training and evaluation data.
    		- We've actually split our dataset.

    			□ We split it with ExampleGen, so ExampleGen does that split.
    			□ Those get fed to StatisticsGen.
    			□ These are both TFX components within a TFX pipeline, so ExampleGen is component, StatisticsGen is a component.
    			□ StatisticsGen calculates statistics for our data.
    			□ For each of the features, if they're numeric features,
    			□ for example, what is the mean of that feature value?

    		- What is the standard deviation?

    			□ The min, the max, so forth.
    			□ Those statistics get fed to SchemaGen which infers the types of each of our features.
    			□ That creates a schema that is then used by downstream components including Example Validator, which takes those statistics and that schema, and it looks for problems in our data.
    			□ We won't go into great detail here about the things that it looks for, but if we have examples that are the wrong type in a particular feature, so maybe we have an integer where we expected a float.
    			□ Now, we're getting into transform.
    			□ Transform is going to take the schema that was generated on the original split dataset, and it's going to do our feature engineering.
    			□ Transform is where the feature engineering happen.
    			□ That gets given the Trainer, there's Evaluator that evaluates the results, a set of Pusher that pushes it to our deployment targets which is, however we're serving our models,

    		- TENSORFLOW SERVING, or JS, or LITE, wherever it is that we're serving our model.

    			□ Internally, if we want to look at the transform component, it's getting inputs from, as we saw, ExampleGen and SchemaGen.

    			□ That is the data that was originally split by Example Gen, and the schema that was generated by SchemaGen.
    			□ That schema, by the way, may very well have been reviewed and improved by a developer who knew more about what to expect from the data than can be really inferred by SchemaGen.

    			□ The result is a TensorFlow graph, which were referred to as the transform graph and the transform data itself.
    			□ The graph expresses all of the transformations that we are doing on our data, has a TensorFlow graph.
    			□ The transform data is simply the result of doing all those transformations.
    			□ Those are given to trainer, which is going to use the transformed data for training and it's going to include the transform graph and we'll take a look at that in a second.

    			□ We apply our transformations during training and as we'll see later, we also apply those transformations at serving time.

    			□ There's a lot of perform optimizations that we apply as well, and we'll take a look at that in a second.

    			□ we have our raw data and we have our transform component , It produces a TensorFlow graph. The result of running that graph is processed data, it's been transformed.

    			□ That gets given in model training, as processed data is given to our trainer component,

    			□ where we use it for training our model , Training our model creates a TensorFlow graph.

    		- Notice now we have two different graphs.
    				® a graph here from transform and
    				®  a graph here from training.

    			□ Using the Tf Transform API, we expressed the feature engineering that we want to do and we give that code, or rather the transform component gives that code to a Apache Beam distributed processing cluster.

    			□ That way we can do, and remember this is all designed to work with potentially terabytes of data.

    			□ That could be quite a bit of processing to do all of that transformation using a distributed processing cluster by using Apache Beam gives us the capacity to do that.

    			□ The result is a saved model.  Saved model is just a format that expresses a trained model as saved model.

    			□ That gets included, we have both the transform graph and the training graph.

    			□ Those are given to our serving infrastructure. Now we have both of those graphs, the feature engineering that we did, and the model itself, the trained model and those are used when we serve requests.

    			□ Looking at this a little differently, we have analysers.

    			□ We're using TensorFlow Ops and a big part of what they do, what an analyser does is it makes a full pass over our dataset in order to collect constants that we're going to need when we do feature engineering.

    			□ For example, if we're going to do a min-max, well, eed to make a full pass through our data to know what the min and the max are for each feature that we're using for that.

    			□ Those are constants that we need to express.

    			□ We're going to use an analyser to make that pass over the data and collect those constants.

    			□ It's also going to express the operations that we're going to do.

    			□ They behave like TensorFlow Ops, but they only were on once during  training and then they're saved off as a graph.

    			□ For example, if we're using the tft.min, which is one of the methods in the transform STK, it'll compute the minimum of a tensor over the training dataset.

    			□ Looking at how that gets applied, we have the graph that is our feature engineering.

    			□ We run an analysis across our dataset to collect the constants that we need.

    			□ so that we can transform individual examples without making a pass over our entire dataset.

    			□ That gets applied during training, and the same exact graph gets applied during serving.

    			□ There is no potential here for training and serving skew or having
    			different code paths when we train our model versus when we serve our model that cause problems and those not be equivalent.

    			□ We're using exactly the same graph in both places, so there is no potential for doing that.

    			□ What is the benefits of that?
    				® Well, the emitted graph that Transform emits is it has all necessary constants and transformations that we're going to need.

    				® The focus is on data pre-processing only at training time.

    				® It's doing that processing as well as generating that graph.

    				® Have works in-line during both training and serving, we prepend it to our trained model.

    				® There's really no need for pre-processing code at serving time.

    				® It consistently applies those transformations irrespective of the deployment platform.

    			□ Remember, we could be deploying our model to a TensorFlow server or a mobile device using TensorFlow Lite or a web browser using TensorFlow Jazz.

    			□ Using the same TensorFlow graph in all places, we're going to get exactly the same transformations.

    			□ The Analysers framework itself has some different aspects.

    			□ First of all, you can do scaling. Things like scaling with a z-score or just  scaling between zero and one, bucketizing.

    			□ We're going to bucketize the quantiles, for example.

    			□ We're going to set up a set of buckets and then we're going to take those values that we have and assign them to the bucket so that we have categorical values for numerical ranges of value or vocabularies.

    			□ Things like running [inaudible] for example, bag of words or n-grams.

    			□ Intact processing need to work with vocabulary.

    			□ You could do dimensionality reduction too.

    			□ You can do a PCA Transform to reduce the dimensionality of your data.

    			□ Now let's look at some code. We're going to create a pre-processing function.

    			□ That bucket feature key is constant, is just a list of the keys for the features that we want to bucketize.

    			□ Imports, well, you're going to import TensorFlow, obviously.

    			□ Apache Beam, you're going to need that because remember, Transform is going to use Apache Beam to distribute processing across a cluster.

    			□ Now you can also just use Beam on a single system or you can just run it on your laptop.

    			□ It has something called the DirectRunner.
    			□ You don't need to actually set up a cluster.

    			□ You can just run it, and there's nothing to move infrastructure to setup. In development that's pretty useful.

    			□ In a deployment, unless you're working with a small amount of data, you probably want more compute horsepower that,  apache_beam.io.iobase is part of that.

    		- It helps us with IO in different formats and different ways reading and writing.

    		- TensorFlow Transform itself, obviously.

    		- Then Transform itself has a Beam part of its modules.
    		- It's often nice to pull out separately and work with.
    		- Those are usually the basic imports that we need to work with Transform.

    		From <https://www.coursera.org/learn/machine-learning-data-lifecycle-in-production/lecture/IV9ja/tensorflow-transform>


    	7. Hello World with tf.Transform --

    		-

    		-

    		-

    		-

    		-

    		-

    		-

    		-

    	8. Feature Spaces ---

    		-

    		-

    		-

    		-

    		-

    		-

    		-

    	9. Feature Selection --

    		- selection some features based on some criteria

    		-

    		-

    		-

    		-

    		-

    		-

    		-

    	10. Filter Methods ---

    		-

    		-

    		-

    		-

    		-

    	11. Wrapper Methods

    		-

    		-

    		-

    		-

    		-

    		-

    		-

    	12. Embedded Methods --

    		-
    	○
    		-

    		-

    		-

    		-

