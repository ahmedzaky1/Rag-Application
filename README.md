# Overview
we'll demonstrate how to seamlessly integrate your PDF documents with an LLM, 
enabling it to retrieve relevant information and generate accurate answers to your questions—straight from your PDFs.

_________________________________________________________________________________________________________________________________________________________________

# Import Libs
1. os
   
2. dotenv
   * helps manage environment variables in your Python application.
   * The load_dotenv function reads the .env file and adds those key-value pairs to the system's environment variables.
  
3. Langchain
   * ChatOpenAI ( to generate text or answer questions. )
   * PromptTemplate ( helps you define structured prompts for the LLM, including information like context and desired output format. )
   * StrOutputParser ( used to parse the LLM's output as a string, making it easier to work with the generated text. )
   * PyPDFLoader ( allows to load and process PDF documents, likely extracting the text content. )
   * RecursiveCharacterTextSplitter ( used to split the extracted PDF text into smaller chunks for further processing. )
   * OpenAIEmbeddings ( used to generate embeddings (numerical representations) of text from the PDF content or LLM output, enabling vector-based search. )
   * FAISS ( provide functionalities for indexing and searching based on vector representations (embeddings). )
  
_________________________________________________________________________________________________________________________________________________________________

# Steps
1. Load model and api key.
   
2. Using ChatOpenAI to interact with a large language model (LLM) to get information about convolutional neural networks (Question)
   * invoke acts as a trigger, initiating communication with the LLM and requesting its expertise on the provided prompt.
  
3. Used StrOutputParser.
   * This parser's role is likely to handle the output from the LLM and ensure it's treated as a string.
   * chain = model | parser ( the model object and the parser object. The pipe operator ( | ) creates a processing pipeline. The output from the left operand (model) is fed as the input 
     to the right operand (parser). Essentially, this code defines a two-step pipeline: ).
     
4. Load PDF and Spilt with RecursiveCharacterTextSplitter.

5. Using Faiss to store in vector after doing Embeddings.

6. Create a prompt to template.

_______________________________________________________________________________________________________________________________________________________________________
![ragdiagram](https://github.com/ahmedzaky1/Rag-Application/assets/103897664/68ee50a5-d746-4e50-83df-30e4df37093a)

