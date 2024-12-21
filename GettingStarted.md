-Getting started

The lab task notebook files are provided below. You can use these if you have access to an AWS account and if your account has the appropriate settings. Download each file to your local computer, saving them all in the same folder.


The following support files should also be downloaded to your computer and saved in the same location. You will need them for lab setup:

Amazon_SageMaker_FAQs

2022-letter


-Setting up the lab environment in your AWS account

In order to run these demo lab tasks, you will need to request access to the necessary Amazon Bedrock models, then launch Amazon SageMaker to access and set up the Jupyter Labs environment. Finally, you will upload the Task0 notebook to your lab environment. Follow the directions in this notebook to install all of the packages that you need to run Tasks 1 through 6. Once you have finished installing the packages, you will upload the remaining lab task files into their respective folders in Jupyter Labs. 

-Setup demonstration video

The provided directions will walk you through the steps necessary to set up your environment to conduct the labs if you have access to an AWS account. Follow the directions to complete the steps. This video will demonstrate the process.

To start the demonstration, choose the play button. A transcript follows the video:
"In this lab, you step through Jupyter notebooks and make API calls to generative artificial intelligence (generative AI) models that are hosted in Amazon Bedrock. These labs are based on the architecture patterns discussed in the previous modules. The notebooks use Bedrock to generate and summarize text, answer questions, and build a chatbot.

In this first task, you will set up your lab environment so you can complete these labs. This will require you to request model access in Amazon Bedrock as well as set up your lab environment in Amazon SageMaker Studio.

To begin, you will need to download the Jupyter notebook files that you will need to compete the labs. There are 9 notebook files total, as well as 1 .csv and 1 .txt file that will be required for some of the labs.

Once you have downloaded the files to your local computer, note the location. You will need to access the contents to run these labs.

To use Bedrock, account users with the correct IAM Permissions must enable access to available Bedrock foundation models (FMs). In order to select the models you will need, make sure you are in the us-east-1 region.

At the top of the AWS Management Console, in the search bar, search for and choose Amazon Bedrock.

Go to the Amazon Bedrock console page. Choose Get Started.

Select Manage model access.

To add to or update your existing model access, choose Enable specific models.

On the Edit model access page, locate the following models and use the checkboxes to select them if you do not already have access to them:

Titan Embeddings G1 – Text

Titan Text G1 - Express

Titan Text G1 - Premier

Then scroll down.

Note: If you notice that the access status already shows Access granted, no action is required. If you do not see Titan Text G1 – Premier as one of the options, make sure you are in the us-east-1 region.

Next, locate the following models and use the checkboxes to select them if you do not already have access to them:

Claude 3 Sonnet

Llama 3 8B Instruct

Then scroll down.

Once you have verified that all the models you need are selected or already available, choose Next.

Review your selections, if applicable, then choose Submit. By choosing submit,  you are agreeing to the third party models pricing and End User License Agreements as well as the Bedrock Service Terms.

Review your selections, if applicable, then choose Submit.

Once your access has been granted, you will now be able to use these models with the lab notebooks.

In this step, you will launch an Amazon SageMaker Studio application to access your lab environment.

At the top of the AWS Management Console, in the search bar, search for and choose Amazon SageMaker.

To proceed, you will need to set up a domain. Select Set up for single user.

You will see a Preparing SageMaker Domain banner. This is a one time configuration and will take several minutes.

Once your domain shows up as Ready, choose User Profiles tab.

Choose Launch button next to the user profile that was just created, then select Studio.

Once you are Studio, you may see a quick tour popup. Choose Skip tour for now.

To begin, choose the JupyterLab icon.

Select the Create JupyterLab space button.

Enter a name for your JupyterLab space. Leave the Sharing settings as default, and choose Create Space.

Your lab has been created, choose Run Space to begin the lab.

Once the status changes to Running, choose the Open JupyterLab button to launch Studio in a new tab.

In this step, you will prepare your lab resources. This includes uploading notebook files and running updates to the lab environment before you begin your tasks.

Once JupyterLabs opens, you will be working with the root folder. This is where you will upload files and create folders.

Use the New Folder icon and create a folder called Files. Open this folder.

Use the Upload files icon to upload the Task0 notebook file from your local computer to the lab environment. Return back to the root folder.

Use the New folder icon to create a new folder. Name this folder letters. Open this folder.

Upload the 2022-letter.txt file from your local computer into this folder.

Navigate back to the root folder.

Use the New folder icon to create a new folder. Name this folder rag_data. Open this folder.

Upload the Amazon_SageMaker_FAQs.csv file from your local computer into this folder.

Navigate back to the root folder.

Open the Files folder, and then open the Task0 notebook file.

If prompted to select an image and kernel to run this notebook, keep the default settings, which should be Python 3 (ipykernel). Choose Select.

Once the notebook kernel starts, follow the directions in this notebook to install all of the packages that you need to run labs 1 through 6.

Once Task0 has completed, navigate to the menu bar and select Kernel->Restart Kernel.

Choose Restart when prompted.

Your environment is all set up, and you are ready to run the labs.

The final step is to add the rest of the task files to the lab environment. Select the Upload icon.

Select the 8 remaining task notebook files on your local computer, then choose Open.

You should see all the task files uploaded to your lab environment. You are ready to get started!

You have successfully done the following:

Requested access to Amazon Bedrock models.

Launched and configured Amazon SageMaker.

Uploaded setup files for the labs.

Updated the kernel and files in the environment."

-Task demonstration walkthrough

The provided directions will walk you through the steps necessary to run the labs, as well as provide a walkthrough of each task.

To start the demonstration, choose the play button. A transcript follows the video:
The business use case in this demonstration is AnyCompany. They have vast repositories of engineering log data and technical support tickets containing critical insights for optimizing their technology operations and infrastructure.

However, engineers struggle to manually parse through the endless text data to identify important patterns and troubleshooting knowledge. AnyCompany has tasked their development team with leveraging Amazon Bedrock's generative AI suite and LangChain's agent capabilities to rapidly build customized enterprise AI solutions.

In this lab, you step through Jupyter notebooks and make API calls to generative artificial intelligence (generative AI) models that are hosted in Amazon Bedrock. These labs are based on the architecture patterns discussed in the previous modules. The notebooks use Bedrock to generate and summarize text, answer questions, and build a chatbot.

In this task, you run two notebook files: Task1a.ipynb, which invokes an Amazon Bedrock model for text generation using a zero-shot prompt, and Task1b.ipynb, which uses the LangChain framework to communicate with the Amazon Bedrock API and creates a custom LangChain prompt template to add context to the text generation request.

In this notebook, you learn how to use Large Language Model (or LLM) to generate an email response to a customer who provided negative feedback on the quality of customer service they received from the support engineer. In this notebook, you generate an email with a thank you note based on the customer's previous email.

The prompt used in this task is called a zero-shot prompt. In a zero-shot prompt, you describe the task or desired output to the language model in plain language. The model then uses its pre-trained knowledge and capabilities to generate a response or complete the task based solely on the provided prompt.

In this scenario, you are Bob, a Customer Service Manager at AnyCompany. Some of your customers are not happy with the customer service and are providing negative feedback on the service provided by customer support engineers. Now, you would like to respond to those customers apologizing for the poor service and to regain trust. You need the help of an LLM to generate a bulk of emails for you which are human friendly and personalized to the customer's sentiment from previous email correspondence.

In Task1a.1, you set up your environment.

Run the first code cell to begin.

In Task1a.2, you prepare an input for the Amazon Bedrock service to generate an email.

Run the first cell to create the prompt.

Run the second cell to set parameters.

After you run the cell, you can read the items that follow for more information on the Amazon Titan model.

In Task 1a.3, you explore how the model generates an output based on the prompt created earlier.

This email is generated using the Amazon Titan model by understanding the input request and utilizing its inherent understanding of different modalities. The request to the API is synchronous and waits for the entire output to be generated by the model.

Run the first cell to invoke the model.

Run the second cell to create a draft of the email.

The email has been provided as an output for you to use.

Bedrock also supports that the output can be streamed as it is generated by the model in form of chunks. This email is generated by invoking the model with streaming option. `invoke model with response stream` returns a `ResponseStream` which you can read from.

Run this cell to create the output in chunks.

You see here that the letter has been output into labeled chunks.

The stream with response approach helps to quickly obtain the output of the model and allows the service to complete it as you read. This assists in use cases where you request the model to generate longer pieces of text. You can later combine all the chunks generated to form the complete output and use it for your use case.

Run this cell to combine the output chunks.

The chunks have been combined and the letter is ready for use.

You have now experimented with using the boto3 SDK, which provides basic exposure to the Amazon Bedrock API. Using this API, you have seen the use case of generating an email to respond to a customer's negative feedback

You have completed this notebook. Close this notebook file and continue with Task 1b.

In this notebook, you will learn how to generate an email response to a customer who was not happy with the quality of customer service they received from the customer support engineer. You will provide additional context to the model by including the contents of the actual email received from the unhappy customer.

You will add more complexity with the help of PromptTemplates to leverage the LangChain framework for a similar use case. PromptTemplates allow you to create generic shells which can be populated with information later and obtain model outputs based on different scenarios.

Due to the additional context in the prompt, the content produced in this notebook is of much better quality and relevance than the content produced earlier through zero-shot prompts. The prompt used in this notebook creates a custom LangChain prompt template for adding context to the text generation request.

In this scenario, you are still a Customer Service Manager at AnyCompany, and you can leverage the power of LangChain's PromptTemplates to create a generic shell for generating personalized email responses based on the customer's previous email. The PromptTemplate will incorporate the customer's original email content, allowing the LLM to understand the context and sentiment, and then generate a relevant and customized response.

In Task1b.1, you set up your environment.

Run the code cell to create a service client by name using the default session.

In Task 1b2, you create an instance of the Bedrock class from LLMs. This expects a `model_ID` which is the Amazon Resource Name (ARN) of the model available in Amazon Bedrock.

Optionally, you can pass a previously created boto3 client as well as some `model kwargs` which can hold parameters such as `temperature`, `top p`, `max token count`, or `stop sequences`.

Run the code cell to invoke and configure the Bedrock LLM model.

In Task 1b.3, you will create a template for the prompt that you can pass different input variables on every run. This is useful when you have to generate content with different input variables that you may be fetching from a database.

In the previous task, we hardcoded the prompt. It might be the case that you have multiple customers sending similar negative feedback, and you now want to use each of those customers' emails and respond to them with an apology, but you also want to keep the response a bit personalized. In the following cell, you will explore how you can create a `PromptTemplate` to achieve this pattern.

Run this code cell to create a prompt template that has multiple input variables.

The code will also pass in values to the input variables.

Run this code cell to get the number of tokens.

After the code is finished running the cell, you can observe the results. After everything has been analyzed, you know that your prompt has 156 tokens.

Run the next code cell to invoke the model.

Finally, run this last code cell to configure a chain to parse output and create a letter.

The apology letter has been created as output for your review.

You have successfully learned that invoking the LLM without any context might not yield the desired results. By adding context and further using the prompt template to constrain the output from the LLM, you were able to successfully obtain your desired output.

You have completed this notebook. Close this notebook file and continue with Task 2.

In this task, you run two notebook files: Task2a.ipynb, which summarizes the text with small files using Titan Text Premier, and Task2b.ipynb, which uses chunking to summarize long texts with Amazon Titan.

In this notebook, you ingest a small string of text directly into the Amazon Bedrock API (using the Titan Text model) and instruct it to summarize the input text. You can apply this approach to summarize call transcripts, meeting transcripts, books, articles, blog posts, and other relevant content when the input text length is within the context size limits of the model.

In Task2a.1, you set up your environment.

Run the first code cell to begin.

In Task2a.2, you use a short passage of text with fewer tokens than the maximum length supported by the foundation model. As a sample input text for this lab, you use a paragraph from an AWS blog post announcing Amazon Bedrock.

The prompt starts with an instruction `Please provide a summary of the following text.`. Run the code cell.

In Task 2a.3, you create a request body with the above prompt and inference parameters

Run the code cell to create the request body.

In Task 2a.4, you send an API request to Amazon Bedrock specifying the request parameters: `modelID`, `accept`, and `contentType`. Following the provided prompt, the foundation model in Amazon Bedrock then summarizes the input text.

By default, the Amazon Bedrock service generates the entire summary for a given prompt in a single output. This can be slow if the model output contains many tokens.

Run the code cell to configure and invoke the model.

The summary of the blog post has been output for your review.

Next, you explore how to use Amazon Bedrock's invoke model with response stream API to stream model outputs so users can consume outputs as they are generated. Rather than generating the full output at once, this API returns a ResponseStream that sends smaller output chunks from the model as they are produced. You can display these streaming outputs in a continuous, consumable view.

Run this first code cell to invoke the model and stream the output.

The output chunks are streamed as they are generated.

Run the next code cell.

Run this code cell to create a streaming output summary.

The summary is generated as streaming output. Here it is being output one word at a time.

The stream is complete and the summary is finished and ready for use.

You have now experimented with using the boto3 SDK to access the Amazon Bedrock API. This SDK provides basic programmatic access to Bedrock capabilities. By leveraging this API, you were able to implement two use cases:

Generating an entire text summary of AWS news content at once,

and 2) Streaming the summary output in chunks for incremental processing.

You have completed this notebook. Close this notebook file and continue with Task 2b.

In this notebook, you manage challenges arising in large document summarization - input text can exceed model context lengths, generate hallucinated outputs, or trigger out-of-memory errors.

To mitigate these issues, this notebook demonstrates an architecture using prompt chunking and chaining with the LangChain framework, a toolkit enabling applications leveraging language models.

You explore an approach addressing scenarios when user documents surpass token limits. Chunking splits documents into segments under context length thresholds before sequentially feeding them to models. This chains prompts across chunks, retaining prior context. You apply this approach to summarize call transcripts, meetings transcripts, books, articles, blog posts, and other relevant content.

In Task2b.1, you set up your environment.

Run the first code cell to begin.

In Task 2b.2, you need to specify the LLM for the LangChain Bedrock class and pass arguments for inference.

Run the code cell to configure LangChain with Boto3.

In Task 2b.3, you will use the text file of Amazon's CEO letter to shareholders in 2022 that is in the Letters directory. The following cell loads the text file and counts the number of tokens. You will see a warning indicating the number of tokens in the text file exceeds the maximum number of tokens for this model.

Run the code cell to load the letter and get the number of tokens.

The total number of tokens has been out as 6526.

Note that you can safely ignore any warnings and proceed to the next cell.

In Task 2b.4, you split the text into smaller chunks because it is too long to fit in the prompt. `RecursiveCharacterTextSplitter` in LangChain supports splitting long text into chunks recursively until the size of each chunk becomes smaller than `chunk size`. A text is separated with `separators=["\n\n", "\n"]` into chunks, which avoids splitting each paragraph into multiple chunks.

Using 6,000 characters per chunk, you can get summaries for each portion separately. The number of tokens, or word pieces, in a chunk depends on the text.

Run the code cell to begin chunking the text.

Run the second code cell to learn how many documents have been created and how many chunks the first one has.

The totals have been output for your review. According to the output, there are 10 documents, and the first one has 439 tokens.

In Task 2b.5, assuming that the number of tokens is consistent in the other documents, you should be good to go. You can use LangChain's `load summarize chain` to summarize the text. `load summarize chain` provides three ways of summarization: `stuff`, `map reduce`, and `refine`.

`stuff`: puts all the chunks into one prompt. Thus, this would hit the maximum limit of tokens.

`map reduce`: summarizes each chunk, combines the summaries, and summarizes the combined summary. If the combined summary is too large, it would raise an error.

`refine`: summarizes the first chunk, and then summarizes the second chunk with the first summary. The same process repeats until all chunks are summarized.

Both map reduce and refine invoke the LLM multiple times and take time for obtaining the final summary. You can try map reduce here.

Run the first code cell to use map reduce for the summary.

Run the second code cell to invoke the chain.

Finally, run the last code cell to output the final summary.

The final summary is created as output for your review.

You have now experimented with using prompt chunking and chaining with the LangChain framework to summarize large documents while mitigating issues arising from long input text.

You have completed this notebook. Close this notebook file and continue with Task 3.

In this task, you utilize the Bedrock Titan model to provide factual responses to queries by sending context-included requests and receiving relevant responses.

In this notebook, you learn how to use the Bedrock Titan model to provide information responses to queries by sending the request with the full relevant context to the model and expecting the response back, addressing the challenge of having the model return factual answers for questions without needing to prepare and index documents beforehand.

This notebook simulates what Retrieval-Augmented Generation (or RAG) would do, but not actually using RAG. This approach works with short documents or single-ton applications; it might not scale to enterprise-level question answering where large enterprise documents cannot all be fit into the prompt sent to the model.

Question Answering (or QA) is an important task that involves extracting answers to factual queries posed in natural language. Typically, a QA system processes a query against a knowledge base containing structured or unstructured data and generates a response with accurate information. Ensuring high accuracy is key to developing a useful, reliable, and trustworthy question answering system, especially for enterprise use cases.

In this scenario, you try modeling a situation at AnyCompany where you ask a question answering model to provide information about changing tires for a specific vehicle model they manufacture. You first query the model using a "zero shot" approach to see if it can provide relevant answers based just on its training data.

However, you realize the model seems to be "hallucinating" more generic answers, as evidenced when you try a fake vehicle model and get similar responses. This implies the need to augment the model's training with Example Company's actual vehicle manuals to give specifics on tires for each model.

In this lab, you simulate such a RAG approach without external data. You provide a detailed manual excerpt explaining how to change the tires on the AnyCompany Model Z vehicle. You test if the model can now give a customized, accurate answer leveraging this in-context example content.

In Task 3.1, you set up your environment.

Run the first code cell to begin.

In this section we try to use a model provided by Bedrock service to answer questions based on the knowledge it gained during the training phase.

In Task 3.2, you use the invoke_model() method of the Amazon Bedrock client. The mandatory parameters required to use this method are model ID, which represents the Amazon Bedrock model ARN, and body, which is the prompt for your task.

The body prompt changes depending on the foundation model provider you select.

You try to use models provided by the Bedrock service to answer questions based on the knowledge gained during the training phase.

Run the code cell to set the parameters for the prompt.

In Task 3.3, you invoke the model by passing the JSON body to generate the response.

Run the code cell to invoke the model.

A list is generated as output for your review.

The model gives you an answer outlining the process of changing the car's flat tire, but the same explanation could be valid for any car. Unfortunately, this is not the right answer for an AnyCompany AC8, which does not have a spare tire. This occurs because the model has been trained on data containing instructions about changing tires on cars.

Another example of this issue can be seen by trying to ask the same question for a completely fake car brand and model, say an Amazon Tirana.

Run the code cell to change the prompt to specifically ask about an Amazon Tirana.

Given the prompt question, the model is unable to provide a realistic answer.

To fix this issue and have the model provide answers based on the specific instructions valid for your car model, you can augment the model's knowledge on-the-fly by providing an additional knowledge base as part of the prompt.

Let's see how you can use this to improve your application.

Assume the following is an excerpt from the manual of the AnyCompany AC8. In reality, it is not the real manual, but you can treat it as such.

This document is also conveniently short enough to fit entirely in the Titan Large context window.

Run this code cell to create context using the AC8 manual you provide.

Now, run this code cell to pass the whole excerpt to the model together with the question.

In Task 3.4, you invoke the model via boto3 to generate the response.

Run the code cell to generate the AC8 change tire process output.

The output is created for your review. You can observe that the output is specific to the AnyCompany AC8, and that is comes from the manual you provided.

Since the model takes a while to understand the context and generate a relevant answer for you, this might lead to a poor user experience as they have to wait for a response for some seconds.

Bedrock also supports streaming capability where the service generates output as the model generates tokens. Here is an example of how you can implement that.

Run the first code cell.

Run the second code cell the stream the output.

The response provides summarized, step-by-step instructions on how to change the tires.

You have now learned how you can leverage the RAG process to generate a curated response tailored to the specific context and information provided.

You have completed this notebook. Close this notebook file and continue with Task 4.

In this task, you build a conversational interface using the FMs in Amazon Bedrock and use llama3-8b-instruct and titan-text-premier as your FMs for building the chatbots.

Conversational interfaces such as chatbots and virtual assistants can enhance the user experience for your customers. Chatbots use natural language processing (or NLP) and machine learning algorithms to understand and respond to user queries. You can use chatbots in a variety of applications, such as customer service, sales, and e-commerce, to provide quick and efficient responses to users. Users can access them through various channels such as websites, social media platforms, and messaging apps.

In conversational interfaces such as chatbots, remembering previous interactions becomes highly important, both at a short-term and long-term level.

The LangChain framework provides memory components in two forms. First, LangChain provides helper utilities for managing and manipulating previous chat messages. These are designed to be modular. Secondly, LangChain provides easy ways to incorporate these utilities into chains, allowing you to easily define and interact with different types of abstractions, which make powerful chatbots easy for you to build.

The first process in building a context-aware chatbot is to generate embeddings for the context. Typically, you have an ingestion process which runs through your embedding model and generates the embeddings, which will then be stored in a vector store. In this notebook, you use the Titan Embeddings model for this.

The second process is user request orchestration, interaction, invoking, and returning the results. This involves orchestrating the user request, interacting with the necessary models and components to gather information, invoking the chatbot to formulate a response, and then returning the chatbot's response back to the user.

In Task 4.1, you set up your environment.

Run the first code cell to begin.

Run the second code cell to format instructions into a conversational prompt and complete the setup process.

In Task 4.2, you enable the chatbot to carry conversational context across multiple interactions with users. Having a conversational memory is crucial for Chatbots to hold meaningful, coherent dialogues over time.

You implement conversational memory capabilities by building on top of LangChain's InMemoryChatMessageHistory class. This object stores the conversations between the user and the chatbot, and the history is available the chatbot agent so that it can leverage the context from a previous conversation.

Run the code cell to start the conversation.

The model has responded with an initial message.

Run the code cell to ask the model for tips on starting a new garden.

The model provides a list of tips that will help start a garden.

Now, run the next code cell to ask a question without mentioning the word garden to see if the model can understand the previous conversation.

The new output shows that the model still understands that you are talking about bugs in the context of gardening.

Run this last code cell to finish the conversation.

The output shows that the conversation is over, and the model has some nice parting words for the user.

In Task 4.3, you use the default PromptTemplate that is responsible for the construction of this input. LangChain provides several classes and functions to make constructing and working with prompts easy.

Run the first code cell to get started.

Run the second code cell to continue.

Next, run the last code cell to start a chat.

The output is a chat prompt that is ready for user interaction.

Asking "What is your name?" provides some information on the model. The model shares some background on its existence.

Run the final code cell.

The output is a log of the interaction with the chat interface.

In Task 4.4, the artificial Intelligence (or AI) assistant plays the role of a career coach. You can inform the chatbot about its persona (or role) using a system message. Continue to leverage the InMemoryChatMessageHistory class to maintain conversational context.

Run the first cell to create the persona.

The AI career coach provides a list of career options in the AI field.

Now, run the next code cell to ask a question that is not within this persona's specialty. The model should not answer that question and should give a reason for that.

The AI career coach states it cannot give advice on fixing a car because it doesn't have the expertise.

Now, run this final code cell.

The output is a history of the interaction with this chat persona.

In Task 4.5, you ask the chatbot to answer questions based on context that was passed to it. You take a CSV file and use the Titan embeddings model to create a vector representing that context. This vector is stored in Facebook AI Similarity Search (or FAISS). When the chatbot is asked a question, you will pass this vector back to the chatbot and have it retrieve the answer using the vector.

Embeddings represent words, phrases, or any other discrete items as vectors in a continuous vector space. This allows machine learning models to perform mathematical operations on these representations and capture semantic relationships between them. You use embeddings for RAG.

Run this code cell to configure the model.

In order to use embeddings for search, you need a store that can efficiently perform vector similarity searches. In this notebook, you use FAISS, which is an in-memory store. To permanently store vectors, you can use Knowledge Bases for Amazon Bedrock, pgVector, Pinecone, Weaviate, or Chroma.

Run this code cell to create the vector store.

A summary of the documents and the vector store is provided as output.

You can use a Wrapper class provided by LangChain to query the vector database store and return the relevant documents.

Run the code cell to run a QA Chain with all default values.

The low code test is completed and the results presented as output.

For the chatbot, you need context management, history, vector stores, and many other components.

You start by building a Retrieval Augmented Generation (RAG) chain that supports context.

This uses the create_stuff_documents_chain and create_retrieval_chain functions.

Run this code cell to begin.

The output show the document chunks consulted to come up with the answer.

Next, run the code cell to start a chat.

The chatbot is created and ready to have a conversation.

You have utilized Titan LLM to create a conversational interface with following patterns:

- Chatbot (Basic - without context)

- Chatbot using prompt template(Langchain)

- Chatbot with personas

- Chatbot with context

You have completed this notebook. Close this notebook file and continue with Task 5.

In this task, you use a LLM to generate code based on a text prompt.

The prompt used in this notebook is a zero-shot prompt, as we are not providing any examples of text other than the prompt itself.

To demonstrate the code generation capability of models in Amazon Bedrock, you take the use case of code generation. You explore using the Boto3 client to communicate with the Amazon Bedrock API and provide the API with an input consisting of a task, an instruction and an input for the model under the hood to generate an output without providing any additional example. The purpose here is to demonstrate how the powerful LLMs easily understand the task at hand and generate compelling outputs.

In this scenario, you are a Data Analyst, at AnyCompany. The company wants to understand its sales performance for different products over the past year. You have been provided a dataset named sales.csv. The dataset contains the following columns:

Date (YYYY-MM-DD) format

Product ID (unique identifier for each product)

Price (price at which each product was sold)

In this notebook, you learn how to generate code for a given prompt. You use the Meta LLama 3 using the Amazon Bedrock API with Boto3 client.

In Task 5.1, you set up your environment.

Run the first code cell to begin.

In Task 5.2, you prepare an input for the Amazon Bedrock service to generate python program for your use-case.

Run this code cell to create a sample sales.csv data file for this lab.

The output shows that the file has been created, and we can see it in our list of files on the left.

In Task 5.3, you analyze sales with an Amazon Bedrock-generated Python program.

Run the first code cell to define the prompt template.

Run the second code cell to create the prompt and analyze sales.

Finally, run the third code cell to complete the analysis.

In Task 5.4, you invoke the model to generate code.

The code has been generated as output.

In this optional section, you can copy and paste the generated code and run it for validation.

The code has been copied into the test cell.

After running it, the output shows the product of the analysis. You can use this information to evaluate the generated code.

You have now experimented with using the boto3 SDK, which provides a vanilla exposure to Amazon Bedrock API. Using this API you generated a Python program to analyze and visualize the given sales data.

You have completed this notebook. Close this notebook file and continue with Task 6.

In this task, you learn how to use a plan-and-execute agent that determines the order of actions and implements them using the tools available to the agents.

Certain applications demand an adaptable sequence of calls to the language models and various utilities to answer a user's question. The Langchain Agent interface is flexible and can integrate external tools with LLM's reasoning. Agents can select the tool to use based on the user input. Agents are capable of using multiple tools and utilizing the output of one tool as the input for the next.

In Task 6.1, you set up your environment.

Run the first code cell to begin.

Next, you create an instance of LangChain's ChatBedrock class, which allows you to interact with a conversational AI model hosted on Amazon Bedrock.

Run the code cell to continue.

Finally, run the third code cell to invoke the model, asking it "What is AWS?", and limiting the answer to a single sentence.

The output provided shows additional information like tokens, model ID, and more.

In Task 6.2, the ReAct framework enables large language models to interact with external tools to obtain additional information that results in more accurate and fact-based responses.

Large language models can generate both explanations for their reasoning and task-specific responses in an alternating fashion.

Producing reasoning explanations enables the models to infer, monitor, and revise action plans, and even handle unexpected scenarios. The action step allows the models to interface with and obtain information from external sources such as knowledge bases or environments.

Run this code cell to start the task.

In the next cell, you define a function `get_product_price` that serves as a tool within the Langchain framework and retrieves the price of the product specified in the query from `sales.csv` file created from the previous task. It is a simple implementation to illustrate how tools can be designed to work with the Langchain framework.

Run this code cell to continue.

In the next cell, you define a function calculator that serves as a tool within the Langchain framework. This tool enables a language model to perform mathematical calculations by evaluating a given expression using Python's numexpr library. The tool is designed to handle cases where the expression is invalid. In that case, the tool asks the model to rethink its approach to the calculation.

Run this cell to continue.

Run the next cell to continue.

Run this code cell to run helper functions to print trace output to a file.

In Task 6.3, you will be creating an agent graph for a conversational AI system that can interact with external tools. The agent graph is a state machine that defines the flow of the conversation and the interaction with the tools.

In this code cell, you define nodes with associated functions that update the state based on input. Connect nodes using edges, where the graph transitions from one node to the next. Incorporate conditional edges to route the graph to different nodes based on specific conditions. Finally, compile the agent graph to prepare it for execution, handling transitions and state updates as defined.

Run the cell to continue.

Next, you visualize the compiled graph. Observe the transition out of the agent node is conditional as indicated by the dotted line.

Run the code cell to continue.

The output is the generated visualization, just as expected.

In the next cell, you run helper function to print the graph output.

Run the code cell to continue.

Next, add one or more questions you want to ask the agent about product pricing from the sales.csv file you created in the previous notebook.

Run the code cell to continue.

To understand the steps involved in reasoning, enable trace. However, keep the trace output manageable by commenting out all but one question in the list above. Alternatively, you can disable trace and run all the questions.

Run the code cell to continue.

In the final step, you invoke the agent with the question from the list above. The question the agent will answer is "How much will it cost to buy 3 units of P002 and 5 units of P003?"

Run the code cell to continue.

The agent begins running the calculations and produces output in a step-by-step manner.

The calculations are finished, and the agent has an answer: "The total cost to buy 3 units of P002 and 5 units of P003 is $530."

You have completed this notebook. Close this notebook file and continue the course.

After completing these tasks, you will have successfully done the following:

Performed text generation.

Created text summarization.

Used Amazon Bedrock for question answering.

Built a chatbot.

Used Amazon Bedrock models for code generation.

Integrated Amazon Bedrock Models with LangChain Agents.

Thank you!
