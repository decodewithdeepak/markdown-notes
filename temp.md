# Unit 2: Web Search and Information Retrieval

**Course:** PEC-CSE-405G | **Author:** [Deepak Modi](https://deepakmodi.tech)

**Syllabus:**      
Information Retrieval Models, Web Search and IR, Text Mining, Latent Semantic Indexing, Web Spamming, Clustering and Classification of Web Pages, Information Extraction, Web Content Mining.

---

## 🎯 PYQ Analysis for Unit 2

### High Priority Topics ⭐⭐⭐
1. **Information Retrieval Models** (2022-Feb, 2022-Jul, 2022-Dec, 2023, 2024-May, 2024-Dec)
2. **Latent Semantic Indexing (LSI)** (2022-Feb, 2022-Jul, 2023, 2024-May, 2024-Dec)
3. **Clustering and Classification of Web Pages** (2022-Feb, 2023, 2024-May, 2024-Dec)

### Medium Priority Topics ⭐⭐
4. **Web Content Mining** (2022-Dec, 2023, 2024-Dec)
5. **Web Spamming** (2022-Feb, 2022-Dec, 2023, 2024-May, 2024-Dec)
6. **Text Mining** (2022-Jul, 2023, 2024-Dec)

### Short Answer Topics ⭐
7. **Information Retrieval** (2023, 2024-May, 2024-Dec)
8. **Web Search** (2024-Dec)
9. **Information Extraction** (2022-Feb)

---

## **1. Information Retrieval (IR)**

> PYQ: What is information retrieval in web mining? (2022-Feb, 8 marks)      
> PYQ: Define information retrieval with the help of its architecture. (2022-Dec, 15 marks)      
> PYQ: Write short notes on Information retrieval. (2023, 2024-May, 2024-Dec - 2.5 marks)

### ✅ Definition

**Information Retrieval (IR)** is the process of finding relevant documents from a large collection based on user queries.

### ✅ IR System Architecture

```
User Query → Query Processing → Matching → Ranking → Results
                  ↑                          ↑
            Indexing ←── Document Collection
```

**Components:**
| Component | Function |
|-----------|----------|
| **Document Collection** | Raw documents to search |
| **Indexing** | Creates inverted index for fast lookup |
| **Query Processor** | Parses and processes user query |
| **Matching** | Finds documents matching query |
| **Ranking** | Orders results by relevance |

### ✅ IR Process Steps

1. **Query Formulation** - User enters search query
2. **Query Processing** - Tokenize, remove stop words, stem
3. **Matching** - Compare query with indexed documents
4. **Ranking** - Score and rank documents
5. **Result Presentation** - Display ranked results

### ✅ Issues in IR

> PYQ: Explain the issues in the process of information retrieval. (2022-Jul, 7 marks)

| Issue | Description |
|-------|-------------|
| **Synonymy** | Different words, same meaning (car = automobile) |
| **Polysemy** | Same word, different meanings (bank) |
| **Vocabulary Mismatch** | Query terms differ from document terms |
| **Scalability** | Handling large document collections |
| **Relevance** | Subjective nature of relevance |

---

## **2. Information Retrieval Models**

> PYQ: Discuss various information retrieval models in detail. (2022-Dec, 2023, 2024-May, 2024-Dec - 15 marks)      
> PYQ: What type of model is used for text retrieval? (2022-Feb, 8 marks)

### ✅ Classification of IR Models

```
IR Models
├── Boolean Model
├── Vector Space Model (VSM)
├── Probabilistic Model
└── Language Model
```

---

### ✅ 1. Boolean Model

**Concept:** Uses Boolean operators (AND, OR, NOT) for exact matching.

**Example:**
```
Query: "data AND mining NOT web"
Doc1: {data, mining, algorithm}     → RELEVANT ✓
Doc2: {data, mining, web}           → NOT RELEVANT ✗
```

| Advantages | Disadvantages |
|------------|---------------|
| Simple to implement | No ranking |
| Fast processing | No partial matching |
| Precise results | All terms equal weight |

---

### ✅ 2. Vector Space Model (VSM)

**Concept:** Documents and queries as vectors; similarity = cosine of angle.

**TF-IDF Weighting:**
| Term | Formula | Meaning |
|------|---------|---------|
| TF | count of term in doc | Term frequency |
| IDF | log(N/df) | Inverse document frequency |
| TF-IDF | TF × IDF | Combined weight |

**Cosine Similarity:**
```
cos(θ) = (d · q) / (||d|| × ||q||)
```

| Advantages | Disadvantages |
|------------|---------------|
| Partial matching | Assumes term independence |
| Ranked results | Ignores word order |
| Term weighting | No semantic understanding |

---

### ✅ 3. Probabilistic Model

**Concept:** Estimates probability that a document is relevant to query.

**Formula:** P(R|d,q) = Probability document d is relevant to query q

| Advantages | Disadvantages |
|------------|---------------|
| Theoretical foundation | Complex |
| Probabilistic ranking | Needs training data |

---

### ✅ 4. Language Model

**Concept:** Models probability of generating query from document.

**Formula:** P(q|d) = ∏ P(t|d) for all terms t in query

---

### ✅ Comparison of IR Models

| Model | Matching | Ranking | Weights | Best For |
|-------|----------|---------|---------|----------|
| Boolean | Exact | No | No | Precise queries |
| VSM | Partial | Yes | TF-IDF | General search |
| Probabilistic | Probabilistic | Yes | Yes | Research |
| Language | Probabilistic | Yes | Frequency | Modern search |

---

## **3. Web Search and IR**

> PYQ: Differentiate between information retrieval and web search. (2022-Jul, 8 marks)      
> PYQ: What are the searching techniques commonly used in web search? (2022-Feb)

### ✅ Web Search vs Traditional IR

| Aspect | Traditional IR | Web Search |
|--------|---------------|------------|
| Scale | Thousands of docs | Billions of pages |
| Data Type | Plain text | HTML with links |
| Quality | Curated | Variable |
| Users | Experts | General public |
| Authority | Equal | Link-based (PageRank) |

### ✅ Web Search Techniques

| Technique | Description |
|-----------|-------------|
| Keyword Search | Match query terms with content |
| Boolean Search | AND, OR, NOT operators |
| Phrase Search | Exact phrase ("web mining") |
| Link Analysis | PageRank, HITS |
| Personalized Search | Based on user history |

---

## **4. Text Mining**

> PYQ: Write short notes on Text mining. (2022-Jul, 2023, 2024-Dec - 2.5-3 marks)

### ✅ Definition

**Text Mining** is extracting meaningful patterns from unstructured text using NLP and ML techniques.

### ✅ Text Mining Process

```
Text Collection → Preprocessing → Feature Extraction → Analysis → Knowledge
```

### ✅ Techniques

| Technique | Application |
|-----------|-------------|
| Classification | Spam detection |
| Clustering | Document grouping |
| Sentiment Analysis | Opinion mining |
| NER | Entity extraction |
| Summarization | Document summaries |

---

## **5. Latent Semantic Indexing (LSI)**

> PYQ: What is latent semantic indexing and where can it be applied? (2022-Feb, 15 marks)      
> PYQ: How does latent semantic analysis work? (2022-Feb, 15 marks)      
> PYQ: Latent semantic indexing. (2022-Jul, 2023, 2024-May, 2024-Dec - 2.5-7.5 marks)

### ✅ Definition

**LSI (Latent Semantic Indexing)** uses Singular Value Decomposition (SVD) to discover hidden semantic relationships between terms and documents.

### ✅ Why LSI?

| Problem | LSI Solution |
|---------|--------------|
| Synonymy (car = automobile) | Maps to same concept |
| Vocabulary mismatch | Semantic matching |
| Noise in data | Dimensionality reduction |

### ✅ How LSI Works

**Step 1:** Create Term-Document Matrix
```
        D1  D2  D3
data     2   1   0
mining   1   2   1
web      0   1   3
```

**Step 2:** Apply SVD
```
A = U × Σ × Vᵀ

A = Term-Document matrix
U = Term-Concept matrix
Σ = Singular values (importance)
V = Document-Concept matrix
```

**Step 3:** Reduce Dimensions
- Keep top k concepts (k=100-300 typically)
- Removes noise, captures semantics

**Step 4:** Query in Reduced Space
- Transform query to concept space
- Compare with document vectors

### ✅ LSI Example

```
Documents about vehicles:
D1: "car automobile vehicle"
D2: "car motor engine"
D3: "truck vehicle engine"

After LSI with k=2:
Concept 1: Motorized vehicles (car, motor, engine)
Concept 2: Transportation (vehicle, automobile)

Query: "automobile" → Returns D1, D2, D3
(Even D2, D3 don't contain "automobile" - synonymy handled!)
```

### ✅ LSI for SEO

> PYQ: How to use LSI keywords to boost SEO? (2022-Feb)

| Strategy | Description |
|----------|-------------|
| Use related terms | Include synonyms naturally |
| Topic coverage | Cover topic comprehensively |
| Avoid keyword stuffing | Write naturally |

### ✅ Applications

- Search engines (semantic matching)
- Document clustering
- Plagiarism detection
- Recommendation systems

### ✅ Advantages & Disadvantages

| Advantages | Disadvantages |
|------------|---------------|
| Handles synonymy | Computationally expensive |
| Reduces noise | Hard to interpret concepts |
| Improves recall | Difficult to update |

---

## **6. Web Spamming**

> PYQ: Define web spamming. (2022-Feb, 1.875 marks)      
> PYQ: Write short notes on Web spamming. (2022-Dec, 2023, 2024-May, 2024-Dec - 2.5-5 marks)

### ✅ Definition

**Web Spamming** is deliberately manipulating search engine rankings through deceptive techniques.

### ✅ Types of Web Spam

```
Web Spam
├── Content Spam
│   ├── Keyword stuffing
│   ├── Hidden text
│   └── Doorway pages
├── Link Spam
│   ├── Link farms
│   ├── Paid links
│   └── Comment spam
└── Cloaking
    └── Different content for users vs crawlers
```

### ✅ Spam Techniques

| Technique | Description |
|-----------|-------------|
| **Keyword Stuffing** | Overusing keywords unnaturally |
| **Hidden Text** | White text on white background |
| **Link Farms** | Networks of sites linking to each other |
| **Cloaking** | Show different content to crawlers |
| **Doorway Pages** | Pages only for ranking, redirect users |

### ✅ Spam Detection

| Method | Approach |
|--------|----------|
| Content Analysis | Detect keyword density, hidden text |
| Link Analysis | Identify link farm patterns |
| Machine Learning | Train classifiers on spam features |
| TrustRank | Propagate trust from seed sites |

---

## **7. Clustering and Classification of Web Pages**

> PYQ: What is clustering in web mining? How is clustering different from classification? (2022-Feb, 7 marks)      
> PYQ: Classification of web pages. (2023, 7.5 marks)      
> PYQ: Clustering of web pages. (2024-May, 7.5 marks)      
> PYQ: Write short notes on Classification and clustering. (2024-Dec, 2.5 marks)

### ✅ Classification vs Clustering

| Aspect | Classification | Clustering |
|--------|---------------|------------|
| **Type** | Supervised | Unsupervised |
| **Labels** | Predefined categories | No predefined labels |
| **Training** | Needs labeled data | No training data |
| **Goal** | Assign to known category | Discover groups |
| **Example** | Spam/Not Spam | Group similar pages |

### ✅ Web Page Classification

**Definition:** Assigning web pages to predefined categories.

**Process:**
```
Training Data → Feature Extraction → Model Training → Classification
```

**Features Used:**
| Feature Type | Examples |
|--------------|----------|
| Content | Words, TF-IDF, topics |
| Structure | HTML tags, headings |
| Link | Inlinks, outlinks, anchor text |
| URL | Domain, path keywords |

**Algorithms:** Naive Bayes, SVM, Decision Trees, Neural Networks

**Applications:**
- Topic categorization (Sports, News, Tech)
- Spam detection
- Sentiment classification
- Age-appropriate filtering

### ✅ Web Page Clustering

**Definition:** Grouping similar web pages without predefined categories.

**Process:**
```
Web Pages → Feature Extraction → Similarity Calculation → Clustering
```

**Algorithms:**
| Algorithm | Description |
|-----------|-------------|
| K-Means | Partition into k clusters |
| Hierarchical | Build tree of clusters |
| DBSCAN | Density-based clustering |

**Challenges in Web Clustering:**

> PYQ: What are the challenges in clustering of the web? (2022-Feb)

| Challenge | Description |
|-----------|-------------|
| High dimensionality | Many features (words) |
| Sparse data | Most words don't appear |
| Noise | Ads, navigation, boilerplate |
| Scale | Billions of pages |
| Heterogeneity | Different formats, languages |

**Applications:**
- Search result grouping
- Duplicate detection
- Topic discovery
- Website organization

---

## **8. Information Extraction**

> PYQ: Discuss the term information extraction. (2022-Feb, 1.875 marks)

### ✅ Definition

**Information Extraction (IE)** is automatically extracting structured information from unstructured text.

### ✅ IE Tasks

| Task | Description | Example |
|------|-------------|---------|
| **Named Entity Recognition** | Find entities | "Apple Inc." → Organization |
| **Relation Extraction** | Find relationships | "Jobs founded Apple" |
| **Event Extraction** | Find events | "Conference on Dec 5" |
| **Template Filling** | Fill predefined slots | Extract product specs |

### ✅ IE vs IR

| Aspect | Information Extraction | Information Retrieval |
|--------|----------------------|----------------------|
| Output | Structured data | Ranked documents |
| Goal | Extract specific info | Find relevant docs |
| Processing | Deep NLP | Keyword matching |

---

## **9. Web Content Mining**

> PYQ: Write short notes on Web content mining. (2022-Dec, 3 marks)      
> PYQ: Web content mining. (2023, 7.5 marks; 2024-Dec, 5 marks)

### ✅ Definition

**Web Content Mining** is extracting useful information from the content of web pages (text, images, audio, video).

### ✅ Types of Web Content

| Type | Examples |
|------|----------|
| Text | Articles, product descriptions |
| Multimedia | Images, videos, audio |
| Structured | Tables, lists, forms |
| Metadata | Title, description, keywords |

### ✅ Techniques

| Technique | Application |
|-----------|-------------|
| Text Mining | Topic extraction, sentiment |
| NLP | Entity recognition, summarization |
| Image Mining | Object detection, classification |
| Structured Data Extraction | Table extraction, wrapper induction |

### ✅ Applications

- Search engines
- News aggregation
- Product comparison
- Knowledge base construction
- Opinion mining

---

## **Summary Table**

| Topic | Key Points |
|-------|------------|
| **IR** | Finding relevant docs from collection |
| **IR Models** | Boolean, VSM (TF-IDF), Probabilistic, Language |
| **LSI** | SVD for semantic matching, handles synonymy |
| **Web Spamming** | Content spam, link spam, cloaking |
| **Classification** | Supervised, predefined categories |
| **Clustering** | Unsupervised, discover groups |
| **Text Mining** | Patterns from unstructured text |
| **Web Content Mining** | Mining page content (text, images) |

---

## **Expected Questions**

### 15 Marks
1. Information Retrieval Models (all 4 with comparison)
2. LSI with example and applications
3. Clustering and Classification of web pages

### 7-8 Marks
1. IR components and process
2. Web Search vs IR
3. Web Spamming types
4. Web Content Mining

### 2.5-3 Marks
1. Define IR / Text Mining / LSI
2. Web Spamming
3. Classification vs Clustering

---

*Notes by [Deepak Modi](https://deepakmodi.tech) | December 2024*
