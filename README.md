# Clinical Entity Normalization 


* This is the task 3 for the 2019 n2c2 challenge, worked on as a course project for the BMI:598 Biomedical NLP course.
 
* We predict the UMLS CUI for the given medical entities in the dataset. So if an entity in the dataset is give “Myocardial Infraction”, then it is marked to its corresponding CUI from UMLS which is ‘C0027051’. Training data has 50 discharge summaries with 6684 entities. 

* We try to use training data(A) (2331 unique CUIs so , 2331 items), SNOMED-CT(305927 items)  data and RxNorm (203954 items) data source from UMLS. A test entity is first checked in the above-mentioned sources, if no direct match is found, then using word2vec and cosine similarity, we find the most possible matches and use the clinical BERT models to predict the closest possible CUI for the entity.

* Pre-processing –  we perform lower casing, removing stop words, removing punctuations, abbreviation expansion, spelling corrector using a spell corrector based on the medical data available, and replace the medicine drugs not present in the training data with their chemical composition.

* We used two different BERT models in the sentence similarity configuration to obtain the closest matching CUI for a given entity based on the mentions of the CUI in the dataset. The Two models used were BERT and Clinical BERT, which gave as accuracies of 82.9% and 83.4% respectively.
