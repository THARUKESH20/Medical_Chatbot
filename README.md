HealthCare ChatBot 🧑🏽‍⚕️
This project implements an intelligent healthcare chatbot using LangChain, Streamlit, and Hugging Face models. The chatbot is designed to help users ask questions related to mental health and provide informative responses based on a PDF document containing relevant information.

Features
Document-based Conversational Agent: The chatbot uses a pre-loaded PDF document on mental health to answer user queries.
Conversational Memory: The chatbot maintains a memory of the conversation history for more relevant and personalized responses.
Customizable: The chatbot is capable of using different pre-trained models from Hugging Face for embeddings and transformers for generating responses.
User-friendly Interface: Streamlit is used for building the front-end interface, allowing users to easily interact with the chatbot.
Tech Stack
LangChain: A framework for building applications with language models. It helps in document processing, embedding generation, vector search, and conversational AI.
Streamlit: A framework for creating interactive web apps directly from Python scripts.
Hugging Face Transformers: Pre-trained models from Hugging Face are used for embeddings and transformers (e.g., sentence-transformers/all-MiniLM-L6-v2 for embedding and llama-2-7b-chat for response generation).
FAISS: Used for efficient similarity search over large datasets of embeddings.
spaCy: Optional for text preprocessing if needed.
Setup Instructions
Prerequisites
Ensure you have Python 3.7+ installed on your system.

Clone the repository:

bash
Copy code
git clone https://github.com/yourusername/healthcare-chatbot.git
cd healthcare-chatbot
Create a virtual environment and activate it:

bash
Copy code
python -m venv env
source env/bin/activate  # On Windows use `env\Scripts\activate`
Install the required dependencies:

bash
Copy code
pip install -r requirements.txt
Make sure to set up the Hugging Face API token in your environment:

bash
Copy code
export HUGGINGFACEHUB_API_TOKEN='your_hugging_face_api_token'
Running the Application
Place your PDF document (e.g., mental_health_Document.pdf) in the specified directory.

Run the Streamlit app:

bash
Copy code
streamlit run app.py
Visit the app in your browser (usually at http://localhost:8501) to start interacting with the chatbot.

How It Works
The PDF document is loaded using LangChain's PyPDFLoader and processed into chunks of text using RecursiveCharacterTextSplitter.
The chunks are then embedded into vectors using HuggingFaceEmbeddings.
FAISS is used to store the embeddings and allows for efficient similarity search to retrieve relevant answers to user queries.
The conversation is handled by the ConversationalRetrievalChain, which fetches the most relevant responses based on user input and the conversation history.
Chatbot Interaction
The user asks a question related to mental health via the Streamlit interface.
The chatbot processes the query, retrieves relevant information from the PDF document, and generates a response.
The chatbot's memory is updated with the user query and its generated response for a coherent conversation flow.
Contributing
Feel free to fork the repository, open issues, or submit pull requests. If you have any suggestions or improvements, please submit them via GitHub Issues.

License
This project is licensed under the MIT License - see the LICENSE file for details.
