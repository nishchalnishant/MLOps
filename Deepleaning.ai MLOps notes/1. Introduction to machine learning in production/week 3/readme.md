    1. Why is data definition hard?

    	- Same image label can have different labels , but the problem arises when we have a lot of data but if they are labeled inaccurately our algo.  might not  work well.

    2. More label ambiguity examples --

    	- There can be several ways to represent the same data , using the same representation type consistently at all places can enhance the result .

    3. Major types of data problems --

    	-





    	- And so if you are looking for advice on a machine learning project, try to find someone that's worked in the same quadrant as the problem you are trying to solve.

    4. Small data and label consistency

    	- Small data -- noisy labels -- bad performance
    	- Big data -- noisy labels -- better performance
    	- So in case we are having less data , we need to have the consistent label , this can perform as well as the big data with noisy label .

    	-

    	- Rare occurrence in case of big data are still problems with large data set , thus if we have large dataset ,that doesn’t guarantee that we will have better result

    5. Improving label consistency --

    	- There are several ways to get better labeled data

    	-



    	There are not several tools in mlops to label the data consistently , if we  have something like that then we can certainly get better result with lesser data

    6. Human level performance (HLP)

    	- These at like the best we can get , thus can act as the initial target we can achieve .

    	- One we reached this level we can try to try to get better .

    	-

    7. Raising HLP --
    `








    8. Obtaining data


    	Collect initial data quickly and work on it , the as an iterative process collect more data



    	One should look at the inventory data --



    	Don’t increase the data by 10X at a time

    9. Data pipeline --

    	Before data is fed to the model we first preprocess the data , this is done by the data pipelines



    	An application generally goes through the poc [ proff of concept] then it goes through the production phase



    	In poc phase we can just write the preprocessing using some manual code also

    10. Meta-data, data provenance and lineage --



    	- Data pipeline can be more complex than this .

    	- But if after some time we want to make a change in the pipeline , we try to keep a track of data provenance [ where does the data comes from ]  and linage [ sequence of steps ]

    	- Extensive documentation can also hep us .

    	- There are other tools which can solve our problems .

    	- We can also us the meta data for error analysis , spotting , unexpected effect





    11. Balanced train/dev/test splits --

    	- When working with skewed data , try to have same ratio of each example in train / test/ dev set .

    	- This is more important in case of small data set , not to worry in case of larger dataset .

    12. What is scoping?



    	- Some of the ideas can be more valuable than others , we can focus on those to bring a great change in shorter span

    13. Scoping process

    	- How to choose which product to work on with , generally business problem

    	- One can look at problems and think on those problems if they can be solved using ai



    	- There are several common problems , which can have a single solution or it can have a combination of solution .

    	-

    	- To be followed by conversion thinking where you then narrow it down to one or a small handful of the most promising projects to focus on.

    	- One thing I hope you might avoid is working really hard on the project and creating a certain amount of monetary or social value.

    	- If for the same amount of work, there's a different project that could have created 10 times more, monitoring or social or other positive types of value.

    	- And I think this type of scoping process will help you to do that.

    14. Diligence on feasibility and value --





    	- We must always take care that the human looks at the same data which is passed to the algorithm [ processed data] to create a HLP .

    	- One must also take care to look at the data we have , if they are feasible to come to a conclusion .



    15. Diligence on value --





    16. Milestones and resourcing --




