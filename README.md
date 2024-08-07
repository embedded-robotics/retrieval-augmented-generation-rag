# Retrieval Augmented Generation (RAG) based Chat Bot

This repository deals with the development of a Retrieval Augmented Generation (RAG) based chatbot using OpenAI Large Language Model (LLM). Specifically, three different chatbots are developed:

*1. Text File Description (`RAG Chatbot Text/rag_chatbot_text.ipynb`):*

This chat bot reads the information about the company given in the form of a text (.txt) file. It then goes on to create overlapping chunks of text, embeds these chunks and then upsert the embeddings into a PineCone Index. Finally, the user can ask a query for which a valid answer is returned by the LLM (OpenAI) by using the relevant context from the chunks stored in the Pinecone vector database

*2. Question Answer Pairs (`RAG Chatbot QA/rag_chatbot_qa.ipynb`):*

This chat bot reads the question/answers about a specific data from an excel or csv file. It then goes on to create individual chunks of text for each question/answer pairs , embeds these chunks and then upsert the embeddings into a PineCone Index. Finally, the user can ask a query for which a relevant question/answer pair is returned from the PineCone vector database. This relevant question/answer pair is passed as a context alongside the query to the LLM (OpenAI) which generates the final answer using this specialized knowledge base


*3. Raw Chatbot (`RAG Chatbot Raw/rag_chatbot_raw.ipynb`):*

This chatbot firstly creates a bot which does not use RAG. It then shows that LLM is unable to generate a valid response for the specialized knowledgebase which usually most of the companies have. Then we create a vector database of specialized knowledegebase into the Pinecone. Finally, the relevant context from Pinecone database is passed in the context of a query to the LLM after which LLM is able to generate the valid response


# Execution Instructions

Clone the repository:

```
git clone https://github.com/embedded-robotics/retrieval-augmented-generation-rag.git\
cd retrieval-augmented-generation-rag
```

Prepare your environment by executing the following commands on the terminal

```
conda create -n rag-chatbot python=3.11
conda activate rag-chatbot
pip install requirements.txt
```

Run the RAG Chatbot for different use cases by going into their relevant folders:\

- RAG Chatbot using Textfile Description -> `RAG Chatbot Text/rag_chatbot_text.ipynb`
- RAG Chatbot using Question/Answer Data -> `RAG Chatbot QA/rag_chatbot_qa.ipynb`
- RAG Chatbot using RAW Operation -> `RAG Chatbot Raw/rag_chatbot_raw.ipynb`

# References
[1]. https://docs.pinecone.io/integrations/langchain \
[2]. https://medium.com/@3rdSon/how-to-build-rag-applications-with-pinecone-serverless-openai-langchain-and-python-d4eb263424f1#87a9\
[3]. https://github.com/adshyam/RAG-Chatbots-with-Langchain-and-Pinecone-Vector-DB/blob/main/rag_chatbot.ipynb\
[4]. https://docs.pinecone.io/guides/get-started/build-a-rag-chatbot\
[5]. https://www.datacamp.com/tutorial/how-to-build-chatbots-using-openai-api-and-pinecone\
[6]. https://scalexi.medium.com/implementing-a-retrieval-augmented-generation-rag-system-with-openais-api-using-langchain-ab39b60b4d9f\
[7]. https://medium.com/@alisha3/build-your-first-llm-chatbot-77456438f57b\
[8]. https://realpython.com/build-llm-rag-chatbot-with-langchain/\