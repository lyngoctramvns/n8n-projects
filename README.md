## Project 1: Web Scrapping and EPUB format conversion workflow with N8N

### Input:
```
Website URL:
https://blog-website-url.com/

Start Chapter:
Chapter which we begin to extract

End Chapter:
Chapter which we stop extracting
```
### Pipeline process

1. First, the process get the HTML content from website from HTTP request

2. Extract the chapters links from the website HTML

3. Get the title and content of blog chapters

5. Using AI agent to style the content to proper form

6. Update into Google Docs the styled content, ready to be converted to EPUB form

![Process](</website-to-epub/Convert Website to Epub.png>)

### Result:
![Result](</website-to-epub/image.png>)

## Project 2: CV and Cover Letter Adjustment using n8n

### Input:

1. Job urls extracted from job listing file
2. Your CV
3. Cover Letter Templapte

### Process

![Process](</CL-CV/Process.png>)

1. Extract the URL from the excel column from Google Sheet file

Separate into 3 branches:
* Exract HTML content from URLs and using AI Agent to filter the specific job description
* Get cover letter template
* Get CV content

2. Combine the CV content, cover letter template and job description, parse through AI agents => generate new cover letters and CV alteration suggestion to fit with the applying job.

### Result:

How it works in real life: [Demonstation Video](https://youtu.be/iOw7xoih4Bo)

## Project 3: Read End-to-End RAG pipeline with Pinecone Vector Database.

The project taken in internal documentation from the company, chunked and pass them through embedding models, then when user ask a queries, the RAG agent looks up relevant information on the document an provide accurate, halucination-free answers.

**Structure:**
```
[React-Vite Frontend] 
       │ (Uploads Multi-part Document / Sends Query)
       ▼
[n8n Webhook Gateway]
       │
       ├─► [Ingestion Stage]: Extract Text ──► Chunking ──► Embeddings Model ──► [Pinecone DB]
       │
       └─► [Query Stage]: Embed User Query ──► Vector Search ──► Context Retrieval ──► [AI Chat Agent] ──► Responses
```

**n8n Workflow**

![Workflow](RAG-pipeline-pinecone/workflow.png)

Demonstation:

