# Knowledge-graph-representation-learning-and-NLP-for-concept-based-Biomedical-Question-Answering
 ##  Contributors
 1) OULDBOUYA Ziad
 2) MOURCHID Mohcine 
 
 # Supervisor
 Fahd Kalloubi

 ## Abstract
Biomedical knowledge graphs (KGs) represent a network of biological entities and illustrate
the relationships between them. The goal of the Biomedical Knowledge Graph Question
Answering System (KGQA) is to help biologists and scientists obtain useful information by
asking questions in natural language. Understanding the question first, then asking KG for the
right set of nodes and relationships, will help you find relevant answers. Transformers such as
RoBERTa, BioELECTRA, and BioBERT are used to understand the context of questions to
represent the query. KGs are often incomplete with many missing links, which causes problems
for KGQA. Missing link prediction is performed using KG integration approaches to reduce
KG sparsity. Missing link prediction is performed using KG integration approaches to reduce
KG sparsity.
A less than ideal limitation imposed by previous multi-hop KGEA methods is the requirement
to select responses within a predefined neighborhood, which is relaxed by EmbedKGQA. In
this report, we demonstrate a benchmark of different KGE techniques on hetionet which is a
readily available KG that integrates biological knowledge from 29 distinct databases of genes,
chemicals, disorders and more. Additionally, on our KG which we build from the PubMed
question/answer dataset.
An integrated system that combines language models and KG embeddings to provide highly
appropriate replies to free-form inquiries posed by biologists in an easy-to-use interface is the
main contribution of this project
 ## Workflow
![Alt text](images/workflow.png)

## Process of the project

- Data collection PubMed and Hetionet
- Coreference resolution
- Name Entity Recognition
- Relation extraction
- Name Entity Linking
- Knowledge Graph Construction
- Knowledge Graph Embedding
- Question Embedding module
- Answer scoring module
- Text generation
