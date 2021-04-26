## News

## About

SciReC2021 - Scientific Recommendations Challenge is the first challenge with the goal of benchmarking a new recommendation dataset in the fields of Health and Chemistry. 
SciReC2021 is organized by [LASIGE](https://www.lasige.pt/), Faculty of Sciences, University of Lisbon, Portugal, and KNODIS, University Automona/Politecnica of Madrid, Spain. 

Recommender systems (RS) have been successfully explored in a vast number of domains, e.g. movies and TV shows, music, or e-commerce. In these domains we have a large number of datasets freely available for testing and evaluation of new recommender algorithms. For example, for movies we have Movielens and Netflix datasets. In music, we find datasets provided by Spotif, and for e-commerce, Amazon has been relentless in the promotion of these datasets, which translates in a large number of algorithms applied to these fields. 

In scientific fields, such as Health and Chemistry, standard and open access datasets with the information about the preferences of the users are scarce. Thus, if we wish to develop an algorithm for recommending chemical compounds, we do not have access to a dataset with information about the past preferences of a group of users. Given this limitation, we developed a methodology (called [LIBRETTI](https://ieeexplore.ieee.org/abstract/document/8924687)), whose goal is the creation of <user, item, rating> datasets, related with scientific fields. These datasets are created based on the major resource that Science has: scientific literature. We consider the users as the authors of the publications, the items as the scientific entities (for example chemical compounds or diseases), and the ratings as the number of publications an author wrote about an entity. 
Since this is a new methodology, these kind of datasets are not yet widely assessed. 

For this workshop we propose a challenge whose goal is benchmarking one of these datasets. 
We will provide a standard dataset of implicit feedback focused in the fields of Health and Chemistry, specially developed from a corpus of documents related to COVID-19 disease. The items in the dataset are diseases from the Disease Ontology (DO) and chemical compounds from the Chemical Entities of Biological Interest ontology ([CHEBI](https://www.ebi.ac.uk/chebi/init.do)), with correspondence to the [DrugBank](https://go.drugbank.com/). The goal of the participants will be, given a set of users with a set of items ordered sequentially, to provide a ranked list with the possibilities of the next item for each one of those users. 


With this challenge we have as goals:

- Spread the use of recommender systems in the fields of Health and Chemistry;
- Improve the quality of the datasets;
- Help in the fight to COVID-19. 

The best results will be presented at the 1st workshop on Scientific Recommendations Challenge hosted by [ACM-BCB 2021 conference](https://acm-bcb.org/2021/index.php). 

## Participation

We invite everyone interested in scientific fields and recommendations systems to participate in this challenge. 

### Data collection 
The dataset was created using the LIBRETTI methodology, from research literature related to COVID-19 disease.

The input used for creating the recommendation dataset is the [COVID-19 Open Research Dataset](https://www.kaggle.com/allen-institute-for-ai/CORD-19-research-challenge). CORD-19 was created by the Allen Institute for AI (AI2), in collaboration with The White House Office of Science and Technology Policy, the National Library of Medicine, the Chan Zuckerburg Initiative, Microsoft Research and Kaggle, coordinated by Georgetown University's Center for Security and Emerging Technology, with the goal of helping in the development of new tools for the extraction of relevant information in the fight of COVID-19 disease. 
The last version of CORD-19 includes over 150,000 articles with full text about COVID-19, SARS-CoV-2 and related coronavirus.
The pipeline used to create the dataset was as follows: 
- CORD-19 retrieval; 
- Named Entity Recognition (NER) of the entities of the DO and ChEBI (with link to DrugBank);
- Extraction of the authors and publication date.

The dataset has the format of <user, item, item_name, publication_date>, where the users are unique authors, the items are DO and ChEBI entities recognized in the articles in the NER phase. The dataset is sorted in ascending order by the user and followed by the year of publication.

### Evaluation 

For the evaluation of recommender algorithms presented by the participants we select a leave-one-out method, i.e., for each user in the evaluation test set, we hide one of the items rated by the user. 
This item is not random, being the last one in the sequence of the items. The goal is, given that sequence of items, which one do you predict to be the next one. 
The dataset will be split into training, validation and test set. The training and validations set will be available in the first phase of the challenge, and the test set in the last phase. An example is presented in the nex table:

| User | Items |   |   |   |   |            |
|------|:-----:|:-:|:-:|:-:|:-:|------------|
| 1    | a     | b | c | a |   |    Train   |
| 2    | c     | d | e | f | g |            |
| 3    | a     | b | d | ? |   | Validation |
| 4    | d     | e | b | ? |   | Test       |


For the test and final phase, the participants must provide a ranked list with the top@10 recommendations for each user in the test set, with the format: user, [list of 10 IDs of the entities].
For the final evaluation, the participants must submit the ranked list of recommendations.
The evaluation metric is the [Mean Reciprocal Ranking](https://en.wikipedia.org/wiki/Mean_reciprocal_rank). 

### Download

For access to the datasets, please fill this [form](https://forms.gle/Bik6h6Zz62HG3YxYA).

First we will release the train and the validations sets, and then the test set, according to the timeline. 


## Timeline


- Training and validation set release: April 26th, 2021
- Test set release: May 31st, 2021
- Final Evaluation: June 14th, 2021
- Participants final results: June 21st, 2021
- Paper submission deadline: July  5th , 2021
- Reviewer deadline: July 12nd, 2021
- Author notification: July 18, 2021
- Camera-ready version deadline: July 25th, 2021
- Workshop: August 1st, 2021

## Submissions

The participants are invited to submit a paper describing their solutions for the challenge.
All submissions must be written in English following Springer [LNCS](http://www.springer.com/gp/computer-science/lncs/conference-proceedings-guidelines) 
author guidelines  and submitted as PDF files (maximum 6 pages excluding references) to 
[EasyChair]( scirec2021@easychair.org). 
A compilation of the accepted papers will be submitted to an issue of [CEUR-WS](http://ceur-ws.org/). 

At least one author per paper needs to register to [ACM-BCB conference](https://acm-bcb.org/2021/index.php) and attend the workshop to present the work. 

## Awards
[Unicage](https://unicage.eu/) will support this event by contributing with a prize for the
team that achieves the best MRR. 
The prize is expected to be an open-source microcontroller board, such as arduino or similar.
The winning team has to submit the article describing their system, and at least one member has to attend the workshop to present it.

## Organization

### Organization committee

- Márcia Barros, Faculdade de Ciências, Universidade de Lisboa, Portugal
- Francisco M. Couto, Faculdade de Ciências, Universidade de Lisboa, Portugal
- Ángel González-Prieto, Universidad Autónoma de Madrid, Spain
- Raúl Lara-Cabrera, Universidad Politécnica de Madrid, Spain
- Matilde Pato, Faculdade de Ciências, Universidade de Lisboa, Portugal
- Fernando Ortega Requena, Universidad Politécnica de Madrid, Spain

### Program committee

- To be announced

## Venue
Registration at [ACM-BCB conference](https://acm-bcb.org/2021/index.php)

## Contacts

Email: scirec2021@easychair.org

## Acknowledgements
This work was supported by FCT through funding of Deep Semantic Tagger (DeST) project (ref. PTDC/CCI-BIO/28685/2017), LASIGE Research Unit (ref. UIDB/00408/2020 and ref. UIDP/00408/2020), and PhD Scholarship ref. SFRH/BD/128840/2017, KNODIS, and [Unicage](https://unicage.eu/). 

