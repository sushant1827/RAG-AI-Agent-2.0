# RAG AI Agent 2.0

###  Google Drive trigger 

This workflow is triggered when a new file is created in a specified Google Drive folder.
The file content is extracted based on its type (PDF, Text, Excel, Doc, Docx, etc.).
MS Word files are converted to Google Docs using Google APIs, saved back to the same folder, and the original file is deleted.
MS Excel files are aggregated and transformed into a comma-separated text format.
The extracted text is then chunked, embedded, and stored in a Supabase vector database.
This setup enables efficient semantic search and retrieval of relevant information in response to user queries.

Nodes Used:

`Google Drive (fileCreated), Google Drive (download: file), Switch (to route files based on file types), Supabase Vector Store, OpenAI Embeddings, Default Data Loader, Recursive Character Text Splitter`

![image](https://github.com/user-attachments/assets/04e320ed-3319-4a96-ac2e-35186a1749fd)

---

### RAG AI Agent

The AI agent leverages the Supabase vector database from the prior workflow to retrieve and answer user queries with relevant information.

Nodes Used:

`Chat Message (trigger), AI Agent, OpenAI Chat Model, Postgres Chat Memory, Supabase Vector Store, OpenAI Embeddings`

![image](https://github.com/user-attachments/assets/0735131a-2459-4f97-bb4b-a3968bbc509f)

---
