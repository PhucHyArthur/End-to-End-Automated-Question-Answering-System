# End-to-End Automated Question Answering System

## I. Introduction
In this project, we focus on developing an end-to-end automated question-answering system capable of answering questions on any topic. The system we implement in this project comprises two main components: the Retriever and the Reader, aiming to build a comprehensive system capable of extracting information from text and providing answers to questions based on the content of the passage

[Overview of System](./image/2.png)

## II. Methodology
1. Implementation
We will build the program based on the SQuAD2.0 dataset, a reading comprehension dataset, the FAISS vector database, and the BERT model to perform specific tasks within the program. The program's input and output are as follows:

Input: A question.
Output: The corresponding answer.
2. Dataset
The SQuAD2.0 Stanford Question Answering Dataset (SQuAD) is a reading comprehension dataset that includes various passages on multiple topics, each accompanied by a set of short questions. Table 1 provides a detailed description of the SQuAD2.0 dataset structure.
[Illustrative example of the SQuAD2.0 dataset.](./image/3.png)

[Table 1](./image/4.png)
3. Reader (DistilBERT)
First, we will build the Reader model, which serves as the question-answering (QA) model in this project. 
You can see it in solution_DistilBERT_QA.ipynb

4. Retriever: Faiss (Facebook AI Similarity Search)

Faiss is a library developed by the Facebook AI Research Team that supports high-speed, high-accuracy vector similarity search and clustering. Here, we use Faiss as the Retriever module for our end-to-end QA system. Its purpose is to find the most relevant context for the input question. We will configure Faiss as follows:

(a) Using the SQuAD2.0 dataset, we will build a database with an additional column representing the vector embeddings of each question.
(b) Embed the questions using DistilBERT.
(c) Perform similarity search between the vectors in the new column and the input question's vector to identify the most relevant context.

The processing workflow of Faiss in this project can be summarized in the image below:

[Illustration of the steps for building a vector database with Faiss](./image/5.png)

You can see it in solution_HF_Faiss_Search.ipynb