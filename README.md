# AI-Powered RAG Agent with Google Drive Integration and Vector Database

This project involves building an advanced Retrieval-Augmented Generation (RAG) AI agent with a chat interface, seamlessly integrated into a website. The AI agent can handle user queries by accessing information stored in a vector database, which is continuously updated with files from Google Drive. The `n8n` workflow orchestrates the process, ensuring data is efficiently processed, embedded, and stored in a vector database (Supabase) for quick retrieval.

## Project Objectives
1. **AI-Powered Chat Agent**: To create an interactive chat experience where users can query information, particularly about a specified subject (e.g., "José"), in real-time.
2. **Google Drive Integration**: Automate the process of adding, updating, and managing files in Google Drive, which are subsequently processed and stored in a vector database.
3. **Vector Database Management**: Efficiently store document embeddings in Supabase, allowing the AI to quickly retrieve relevant data based on user queries.

## Components

### 1. RAG AI Agent with Chat Interface
   - **User Chat**: Users can interact with the AI via a chat interface embedded in the website. The chat agent has contextual knowledge of the specific subject.
   - **Webhook Integration**: The system captures and processes incoming chat messages through a webhook.
   - **OpenAI Model**: The AI utilizes OpenAI's Chat Model to generate responses.
   - **Postgres Chat Memory**: The chat context is preserved using a PostgreSQL memory structure, ensuring continuity in conversation.
   - **Response Mechanism**: The RAG AI agent responds to the user via the chat interface, leveraging data from the vector database.

### 2. Agent Tools for RAG
   - **Retrieve Documents**: This tool allows the agent to pull relevant documents from the vector database (Supabase Vector Store) based on user queries.
   - **Embedding Process**: The OpenAI Embeddings API is used to create vector representations of document text for efficient retrieval.

### 3. Google Drive File to Vector Database Tool
   - **File Monitoring**: The system monitors Google Drive for new files or updates, triggering the workflow when a file is created or updated.
   - **File Processing**:
      - **Set File ID**: The workflow sets the file ID for tracking.
      - **Delete Old Document Rows**: When a file is updated, previous embeddings in the database are removed to avoid duplication.
      - **Download and Process Files**: Files are downloaded from Google Drive and classified based on format (PDF, Excel, text files). Each format is processed appropriately.
      - **Text Extraction and Aggregation**: Text is extracted and aggregated, with summarization applied where necessary.
   - **Embedding and Storage**:
      - **Character Text Splitting**: Text is split into manageable chunks for embedding.
      - **Insert into Supabase**: The processed document embeddings are stored in the vector database (Supabase) for later retrieval by the RAG AI agent.

## Integration into the Website
The project includes embedding the RAG AI chat interface on a website, allowing visitors to interact with the AI assistant. The assistant is configured to provide detailed information about "José," responding to user queries 24/7. This integration creates a dynamic and interactive experience for users, backed by real-time data processing and retrieval.

## Technology Stack
- **Frontend**: Custom chat interface integrated into the website.
- **Backend**:
  - **n8n** for workflow automation.
  - **OpenAI API** for language generation and embeddings.
  - **Supabase** as the vector database to store embeddings.
  - **Google Drive API** for file handling.
- **Database**: PostgreSQL for chat memory and session management.

## Workflow Diagram
The workflow diagram illustrates the flow of data and processes within the `n8n` workflow. It showcases the various nodes involved, from Google Drive file monitoring to text extraction, embedding generation, and vector database storage, ultimately supporting the RAG agent’s efficient response generation in the chat interface.

## Future Enhancements
Potential future features include:
- Expanding integration with other file storage systems.
- Adding role-based access control for data within the chat.
- Advanced analytics to track and improve user engagement.

## How to Run
1. **Clone this repository**.
2. **Set up the n8n Workflow**:
   - Ensure you have access to Google Drive and Supabase.
   - Set up OpenAI API credentials.
3. **Integrate with Website**:
   - Embed the chat interface on your website.
   - Configure webhook endpoints as needed.
4. **Monitor and Maintain**:
   - Regularly check the vector database for updates.
   - Monitor chat logs and interactions to improve response accuracy.

This project demonstrates a sophisticated integration of automated document management, AI-powered chat functionality, and real-time data retrieval, providing a seamless and efficient user experience on the website.

