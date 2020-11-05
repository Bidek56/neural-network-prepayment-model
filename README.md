# neural-network-prepayment-model

Here we build a neural-network based prepayment model to predict a likelihood of prepayments on pools of residential mortgage loans.

Mortgage pools are tradable fixed income securities composed of collections of residential mortgage loans. Here we only consider the so called "agency" mortgage pools, i.e. those whose credit risk (the risk of borrower's default) is guaranteed by one of the GSEs (Government Sponsored Enterprises) which are Fannie Mae, Freddie Mac, and Ginnie Mae. More specifically, we build a prepayment model here for predicting the likelyhood of residential mortgage prepayments for loans guaranteed by Fannie Mae. The same model can be used to predict prepayments on loans guaranteed by Freddie Mac, because they are very similar, but not Ginnie Mae loans, which are somewhat different and require a separate model. 

For more information about this project please, see document ###Proposal.pdf###. It contains more of the background information, problem statement, data description, and our approach to model building. 

## Files included. 

1. ### Proposal.pdf <br/>
      Describes the problem, gives background information, and outlines data structure and solution roadmap. 
1. ### pools_dataset_builder.ipynb  <br/>
      This can only be run by the author. It builds the dataset used in the model from the raw data files which the author has downloaded from a vendor. You won't be able to run this notebook  unless you have access to those files, but running this notebook is not required as all the data is provided. This notebook however, shows how data is cleaned and NAs are filled. 
1. ### ./data  <br/>
      Directory which contains a series of csv files containing the data required for the model training. 
1. ### model_fitting.ipynb  <br/>
      This is the main notebook, which contains all of the analytics work done in this project including data data exploration, model fitting, and model evaluation.
1. ### ProjectReport.pdf  <br/>
      This is a project report required by the Udacity capstone project rubric. It contains the summary of the project and results. 
1. ### nn-ppm-from-csv.h5  <br/>
      If you want to avoid spending time to fit your own model while executing model_fitting notebook (see 4.), you can just load the model from this file. 
