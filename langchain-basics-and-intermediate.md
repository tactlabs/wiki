/ [Home](index.md)

## LangChain Basics and Intermediate

**Note:** LC HandsOn



### CH01 LangChain Getting Started
01. Follow the installation video report
02. OpenAI API key issuance and testing
03. LangSmith tracking settings
04. Using the OpenAI API (GPT-4o multimodal)
05. LangChain Expression Language (LCEL)
06. LCEL interface
07. Runnable

### CH02 Prompt
01. Prompt
02. FewShotPromptTemplate
03. LangChain Hub
04. Personalized p
rompt (uploaded to Hub)

### CH03 Output Parsers
01. Pydantic output parser (PydanticOutputParser)
02. Comma SeparatedListOutputParser
03. StructuredOuputParser
04. JSON output parser (JsonOutputParser)
05. Data frame output parser (PandasDataFrameOutputParser)
06. Date format output parser (DatetimeOutputParser)
07. EnumOutputParser
08. OutputFixingParser

### CH04 model (Model)
01. LLM models available
02. Caching (Cache)
03. Model Serialization-Save and Call
04. Check token usage
05. Google Generative AI
06. HuggingFace Endpoints
07. HuggingFace Local
08. HuggingFace Pipeline
09. Olama
10. GPT4ALL
11. Video (Video) Quality Response LLM (Gemini)

### CH05 memory (Memory)
01. ConversationBufferMemory
02. ConversationBufferWindowMemory
03. ConversationTokenBufferMemory
04. ConversationEntityMemory
05. ConversationKGMemory
06. Conversation SummaryMemory
07. Vector Storage Search Memory (VectorStoreRetrieverMemory)
08. Add memory to LCEL Chain
09. Save chat to SQLite
10. Add ChatMessageHistory to RunnableWithMessageHistory

### CH06 Document Loader
01. Structure of Document
02. PDF
03. Hangeul (HWP)
04. CSV
05. Excel
06. Word
07. PowerPoint
08. Web document (WebBaseLoader)
09. Text (TextLoader)
10. JSON
11. Arxiv
12. UpstageLayoutAnalysisLoader
13. LlamaParser


### CH07 text split (Text Splitter)
01. Character text split (CharacterTextSplitter)
02. Securitic text text split (RecursiveCharacterTextSplitter)
03. Token Text Split (TokenTextSplitter)
04. Semantic chunker
05. Code splitting (Python, Markdown, JAVA, C++, C#, GO, JS, Latex, etc.)
06. Markdownheader Text Split (MarkdownheaderTextSplitter)
07. Split HTML header text (HTMLHeaderTextSplitter)
08. Regressive JSON split (RecursiveJsonSplitter)

### CH08 Embedding
01. OpenAIEmbeddings
02. CacheBackedEmbeddings
03. HuggingFace Embeddings
04. UpstageEmbeddings
05. OllamaEmbeddings
06. GPT4ALL embedding
07. Llama CPP embedding

### CH09 VectorStore
01. Chroma
02. FAISS
03. Pinecone
CH10 finder (Retriever)
01. VectorStore-backed Retriever
02. Contextual CompressionRetriever
03. EnsembleRetriever
04. Long context rearrangement (LongContextReorder)
05. ParentDocumentRetriever
06. MultiQueryRetriever
07. MultiVectorRetriever
08. Self Query Retriever
09. Time Weighted Vector StoreRetriever
10. Hangeulocyte analyzer (Kiwi, Kkma, Okt) + BM25 finder
11. EnsembleRetriever with Convex Combination (CC)

### CH11 Reranker
01. Cross Encoder Reranker
02. Cohere Reranker
03. Jina Reranker
04. FlashRank Reranker

### CH12 Retrieval Augmented Generation (RAG)
01. PDF document based QA (Question-Answer)
02. Naver News Agency QA (Question-Answer)
03. Various module utilizers by function of RAG
04. RAPTOR: Long Context Summary
05. RAG chain to remember interactive

### CH13 LangChain Expression Language (LCEL)
01. RunnablePasstrough
02. Runnable structure (graph) review
03. RunnableLambda
04. LLM chain routing (RunnableLambda, RunnableBranch)
05. RunnableParallel
06. Dynamic attribute assignment (configurable_fields, configurable_alternatives)
07. Runnable configuration with @chain decorator
08. RunnableWithMessageHistory
09. Custom generator
10. Runtime Arguments Binding
11. Fallback model designation

### CH14 chain (Chains)
01. Document summary
02. SQL
03. Structured output chain (with_structed_output)

### CH15 Evaluation (Evaluations)
01. Synthetic test dataset generation (RAGAS)
02. Evaluation using RAGAS
03. Upload data set for evaluation generated (HuggingFace Dataset)
04. LangSmith dataset generation
05. LLM-as-Judge
06. Embedding-based evaluation (embedding_distance)
07. Custom LLM evaluation
08. Rouge, BLEU, METEOR, SemScore based heuristic evaluation
09. Experimental (Experiment) evaluation comparison
10. Assessment of the summary method
11. Groundedness (Halucination) Assessment
12. Experimental comparison (Pairwise Evaluation)
13. Repeat evaluation
14. Automating evaluation using online evaluation

### CH16 agent (Agent)
01. Tools
02. Tool Binding (Binding Tools)
03. Agent
04. Agent utilizing Claude, Gemini, Ollama, Together.ai
05. Iteration function and human intervention (Human-in-the-loop)
06. Agentic RAG
07. CSVExcel Data Analysis Agent
08. Toolkits Use Agent
09. RAG + Image Generator Agent (Reporting)
10. Discussion agent with tools (Two Agent Debates with Tools)

### CH17 LangGraph
#### 01. Core function
01. Python grammar often appeared in LangGraph
02. Build chatbots using LangGraph
03. Building an Agent using LangGraph
04. Add memory to Agent
05. Node's step-by-step streaming output
06. Human-in-the-loop (human intervention)
07. State correction and replay through reverting of intermediate intervention
08. Add a node to ask a person
09. Delete message (RemoveMessage)
10. How to call a tool using ToolNode
11. How to generate branches for parallel node execution
12. How to add a conversation history summary
13. How to add and use subgraphs
14. How to convert input and output of subgraph
15. Everything in LangGraph streaming mode
#### 02. Structure design
01. Default graph generation
02. Naive RAG
03. Relevance Checker module added
04. Add web search module
05. Add query rewrite module
06. Agentic RAG
07. Adaptive RAG
#### 03. Use Cases
01. Agent conversation simulation (customer response scenario)
02. User-required port-based meta prompt generation agent
03. CRAG (Corrective RAG)
04. Self-RAG
05. Plan-and-Execute
06. Multi-Agent Collaboration Network
07. Multi-Agent Supervisor
08. Hierarchical Multi-Agent Teams
09. Agent interacting with SQL database
10. Multi-agent for research introducing the STORM concept

### CH18 Other Information
01. StreamEvent type theorem

#### Ref:
https://wikidocs.net/233343