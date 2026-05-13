# Knowledge-Tome
Transform your AI conversation history into a structured personal knowledge base.

### *What is Knowledge Tome?*
Every conversation you have with an AI assistant contains knowledge - questions you explored, concepts you learned, problems you solved. That knowledge is mostly forgotten the moment the tab is closed.

**Knowledge Tome** ingests your exported chat history (ChatGPT, Claude, Gemini), extracts what you actually learned, organizes it by topic, and builds a living document of your intellectual activity over time.

### *Features*
* **Multi-source ingestion**
* **Automatic topic extraction** : NLP Pipeline identifies and clusters subjects discussed across all conversations
* **Knowledge Graph** : visualizes relationships between topics and how they evolved over time
* **Personal knowledge profile** : A clean, browsable interface showing what you know, how deeply, and when you learned it
* **Semantic similarity matching** : Compare knowledge profiles between users to surface meaningful intellectual overlap

### Tech Stack
|Layer|Technology|
|----------|-----------|
|Ingestion & Processing | Python, Pandas|
|NLP Pipeline|sentence-transformers, scikit-learn|
|Topic Modeling|LDA, K-Means clustering|
|Storage|MongoDB, PostgreSQL|
|Backend API|FastAPI|
|Frontend|HTML / CSS / JavaScript|
|Big Data Processing|Apache Spark|
|Deployment|Docker, cloud instance|


### Getting Started
##### Prerequisites
- Python 3.10+
- MongoDB running locally
- Node.js

##### Installation
```
git clone https://github.com/ebu9/Knowledge-Tome
cd Knowledge-Tome
pip install -r requirements.txt
```

##### Export your conversations
**ChatGPT:** Settings -> Data Controls -> Export Data -> Download -> unzip ->use `conversations.json`
**Claude:** Settings -> Privacy -> Export Data -> use `conversations.json`
**Gemini:** Google Takeout -> select Gemini Apps Activity

##### Run the pipeline
```
#Parse and process your export
python ingest.py --source chatgpt --file path/to/conversations.json

#Launch the interface
python app.py
```
then open `http://localhost:8000`in your browser.

### Project Structure
```
knowledge-tome/
│
├── ingest/
│   ├── parsers/
│   │   ├── chatgpt.py
│   │   ├── claude.py
│   │   └── gemini.py
│   └── cleaner.py
│
├── nlp/
│   ├── embeddings.py
│   ├── topic_extraction.py
│   └── clustering.py
│
├── storage/
│   ├── mongo_client.py
│   └── schema.py
│
├── api/
│   └── app.py
│
├── frontend/
│   ├── index.html
│   ├── profile.html
│   └── static/
│
├── matching/
│   └── similarity.py
│
├── requirements.txt
└── README.md
```

### Roadmap
- [ ] ChatGPT export parser
- [ ] Basic topic extraction
- [ ] MongoDB storage layer
- [ ] Claude and Gemini parsers
- [ ] Knowledge Graph viz
- [ ] User profile page
- [ ] Semantic matching between profiles
- [ ] Browser extension for real-time capture
- [ ] Obsidian / Notion / google keep exports

### Why "Tome"?
A tome is a large, scholarly book: accumulated knowledge that is bound together. That's the goal, A growing record of information relevant to you!

### License
MIT

### Author
Abderrahman JENNATI  
[jennatiabderrahman@gmail.com](mailto:jennatiabderrahman@gmail.com)  
[Linkedin](https://www.linkedin.com/in/abderrahman-j/)  
