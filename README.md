SEMANTIC SEARCH ENGINE FOR Q&A USING ELASTIC SEARCH AND DOCKER.

PROBLEM DEFINITION
When we are using stack-overflow if we need to search for an answer we will ask a question in the search box. If we type the question, it will give some related questions. Our problem statement is similar to this only.

Given a question can we find similar questions in a repository of questions and answers that we have.The main objective is to get the searched similar kind-off questions within a small amount of time. Basically, the search engines work in such a way that they will give us the results within less than 500 milliseconds. Ordering of related questions is also very important. The speed is extremely important while designing these kind-off engines.

We want to have high precision and high recall. The computational and server costs should below.

DATASET
We have picked up a dataset known as STACK-SAMPLE from the kaggle.

DESIGN
Using elastic search.

Elastic search gives us an inbuilt implementation of the inverted index. It also gives us default scoring using TFID based schemes and also gives us the flexibility to 
build our scoring function. It is distributed. It runs in realtime so that the latency will be very low.

SENTENCE VECTOR
Many machine learning algorithms require the input to be represented as a fixed-length feature vector. 
Word embeddings are representation of words in an N-dimensional vector space so that semantically similar 
(e.g. “king” — “monarch”) or semantically related (e.g. “bird” — “fly”) words come closer depending on the training method (using words as context or using documents as context). When it comes to texts, one of the most common fixed-length features is the bag-of-words. But this method neglects a lot of information like ordering and semantics of the words.

COSINE SIMILARITY
Cosine similarity is a measure of similarity between two non-zero vectors of an inner product space. 
It is defined to equal the cosine of the angle between them, which is also the same as the inner product of the same vectors normalized to both have length 1.

INSTALLATION
We need to install docker. Within the docker, we need to install an elastic search.

Docker is a set of platform as a service products that use OS-level virtualization to deliver software in packages called containers. 
Containers are isolated from one another and bundle their software, libraries, and configuration files; they can communicate with each other through well-defined channels.

WORKING
The first most thing is we need to convert the sentences to tensor. The whole code keeps the model in memory.

Elastic Search Indexing

From the data folder that we have if we take some questions, and let's assume that we read those questions one after the other. 
For those questions, if we call our model, our model returns us the vector so that we insert it into the elastic search both the question text and vector. 
This whole thing is known as Indexing. 

