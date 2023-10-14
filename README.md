# GEN-AI---PDFChat
PDFChat: A Conversational Agent for PDF Documents
Have you ever wished you could ask questions about a PDF document and get instant answers? Maybe you are reading a research paper and want to know more about the methods, results, or implications. Or maybe you are browsing a product catalog and want to compare different features, prices, or reviews. Or maybe you are studying for an exam and need some help with understanding the concepts, formulas, or examples.
Whatever your use case, PDFChat is the solution for you. PDFChat is a conversational agent that can answer questions about content in PDF using the power of natural language processing (NLP). PDFChat uses Cohere, a platform that provides state-of-the-art NLP models and APIs, to create a conversational interface that can understand your queries and generate relevant responses.

How does PDFChat work?
Brief
PDFChat works by using Langchain Framework, Chromadb and Cohere embeddings to represent the content of the PDF document and the user’s query in a high-dimensional vector space. 

Cohere embeddings are learned from large-scale text corpora and capture the semantic and syntactic information of natural language. Thus the embeddings are stored in vectordb. By using Cohere embeddings, PDFChat can measure the similarity(semantic search) between the query and the document, and find the most relevant passages or sentences that can answer the question.
PDFChat also uses Cohere’s best-in-class generative models to produce natural and fluent responses that are tailored to the user’s query. Cohere’s generative models are trained on diverse and rich text data, and can handle various types of questions, such as factual, opinion-based, comparative, or hypothetical. PDFChat can also generate follow-up questions or suggestions to engage the user and provide additional information.

Cohere
Cohere is a platform that allows you to build natural language interfaces for any application using state-of-the-art language models. You can use Cohere to generate text, understand text, or complete text using simple API calls. You can also customize the language model’s behavior by providing examples or feedback.
I have used cohere to extract the information from the pdf embeddings in vectordb by semantic search and use that content to answer the query asked by user.
Cohere(cohere_api_key='API_KEY')

Chromadb
Chromadb is an open-source vector store and embeddings database designed to make it easy to build AI applications with embeddings. Embeddings are numerical representations of text or other data that can be used for similarity search, clustering, or feeding into large language models (LLMs). Chromadb allows you to store embeddings along with metadata, such as the source, date, or category of the data. You can also use Chromadb to convert text into embeddings using built-in or custom embedding functions.
I have used chromadb to store the pdf embeddings into vector database and use those embeddings to answer the questions
vectordb = Chroma.from_documents(pages, embedding=embeddings, persist_directory=".")

Cohere Embeddings
Cohere Embeddings is a service that allows you to create high-quality embeddings for any text using Cohere’s language models. You can use Cohere Embeddings to encode text into vectors that capture its meaning and context. You can also use Cohere Embeddings to compare texts based on their semantic similarity.
I have used cohere embeddings to convert the pdf into embeddings of vector size 768
embeddings = CohereEmbeddings(cohere_api_key='API_Key')

LangChain
LangChain is a framework for developing applications powered by language models. Language models are computer programs that can generate or understand natural language, such as text or speech. LangChain provides modular components and interfaces that make it easy to connect a language model to other sources of data, such as databases, APIs, or web pages. LangChain also allows a language model to interact with its environment, such as sending messages, executing commands, or updating data. LangChain supports different languages and platforms, such as Python, JavaScript, TypeScript, and more.
I have used Langchain to execute the chromadb, chatvectordbchain to call llm and feed embeddings stored in vectordb into it and to take query as an input and answer accordingly and cohere llm.
ChatVectorDBChain.from_llm(
    Cohere(cohere_api_key='API_Key'),
    vectordb,
    return_source_documents=True

How to use PDFChat?
Using PDFChat is very simple and intuitive. All you need to do is upload a PDF document that you want to chat with, and start asking questions in natural language. PDFChat will analyze the document and the query, and generate a response in seconds. You can ask as many questions as you want, and PDFChat will try to answer them as best as it can. You can also give feedback to PDFChat by rating its responses or providing comments.
Here are some examples of questions and answers that PDFChat can handle:
•	Q: What is the main contribution of this paper?
•	A: This paper describes the Diameter Overload Indication Control (DOIC) protocol, which is used to manage overload situations in Diameter networks.
•	Q: How does this product compare to its competitors?
•	A: This document does not provide a direct comparison of Oracle's Diameter signaling router to its competitors. However, it does highlight some key characteristics and features of the product, such as support for various Diameter applications, interworking with different networks, and a scalable and flexible architecture
•	Q: What are some applications of this concept in real life?
•	A: The concept of topology hiding is used in LTE service providers to protect their networks. The feature removes or hides all Diameter addresses from messages being routed out of the home network.
Why choose PDFChat?
PDFChat is an innovative project that combines the power of Cohere and NLP to create an interactive agent that can answer questions about content in PDF.
 PDFChat can help you:
•	Save time and effort by finding the information you need quickly and easily.
•	Enhance your understanding and learning by asking questions and getting feedback.
•	Enjoy your reading experience by having a conversation with the document.

Conclusion
In this blog post, I have explained how I built a real-time PDF collaboration tool using Cohere, Chromadb, Cohere Embeddings, and LangChain. These technologies enabled me to create project for users to chat naturally in real-time using natural language. I think this project demonstrates the power and potential of using language models to build AI applications that are easy to use and fun to interact with.
If you are interested in trying out pdfchat you can access it from 
Github : https://github.com/NITHISH-Projects/GEN-AI---PDFChat I would love to hear your feedback and suggestions on how to improve pdfchat.
I hope you enjoyed reading this blog post and learned something new. I am very passionate about AI and natural language processing, and I would love to learn from you and work with you on more exciting projects. Thank you for your time and attention. 

