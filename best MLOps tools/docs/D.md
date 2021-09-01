    	○ Dvc
    		§ Opensource version control system for ml
    		§ Experimentation tools that helps us define our pipeline regardless of language
    		§ DVC helps to save time by leveraging code, data versioning, and reproducibility. You can also train your model and share it with your teammates via DVC pipelines.
    		§ We can use any type of storage
    		§ Full code and data provenance helps to track the complete evolution of every ml model
    		§ Tracks metrics
    		§ built in way to connect ml steps into a data and run the full pipeline end to end

    	○ Pachyderm
    		§ Platform that combines data linage with end to end pipelines on kubernetes
    		§ 3 version from open source to paid
    		§ Need to integrate this with infrastructure
    		§ It has following main concepts --
    			□ Repository -- highest level data object  typically each dataset is its own repository
    			□ Commit -- an immutable snapshot of a repo at a particular point in time
    			□ Branch -- an alias to a specific commit , or a pointer that automatically moves as new data is submitted
    			□ File -- these are the actual data in our repository , supports any type , size and a number of files
    			□ Provenance  -- expresses relationship between various commits , branches and repositories

    	○ Kubeflow
    		§ Ml toolkit for kubernetes
    		§ Helps in maintaining ml systems by packaging and managing docker containers .
    		§ Facilitates scaling of ml models by making run orchestration and deployment of ml workflows easier.
    		§ Ui for managing and tracking experiments , jobs ad runs
    		§ Notebooks for interacting with systems using sdk
    		§ Reuse components and pipeline to quickly create end to end solution

Kubeflow pipelines available as a core component of kubeflow or as a stand alone installation
