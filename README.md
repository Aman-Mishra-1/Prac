# Information Retrieval Practicals – Quick Viva + Algorithm Cheat Sheet

---

# Practical 1 – Document Indexing and Retrieval (Inverted Index)

## Algorithm
1. Take a set of documents as input.
2. Convert all text to lowercase to maintain uniformity.
3. Tokenize the documents into individual words (tokens).
4. Remove stopwords such as "is", "the", "and".
5. Create an empty dictionary to store the inverted index.
6. For each term:
   - Identify the documents in which it appears.
   - Store the document IDs in the dictionary.
7. Display each term with the list of documents that contain it.

## Dumb Questions

**What is tokenization?**  
Tokenization is the process of splitting text into smaller units called tokens, usually words.

**What are stopwords?**  
Stopwords are very common words such as "the", "is", and "and" that usually do not carry significant meaning in search.

**What does lowercase conversion do?**  
It converts all characters into lowercase so that words like "Apple" and "apple" are treated as the same term.

**What is a document in Information Retrieval?**  
A document is any unit of text such as a webpage, article, or file that can be searched.

## Basic Questions

**What is an inverted index?**  
An inverted index is a data structure that stores a mapping from terms to the list of documents containing those terms.

**Why remove stopwords?**  
Stopwords are removed to reduce index size and improve search efficiency.

**What is indexing?**  
Indexing is the process of organizing data so that it can be searched quickly.

**What is document retrieval?**  
Document retrieval is the process of finding relevant documents from a collection based on a user query.

## Good Questions

**Why is inverted index efficient for search engines?**  
Because it allows direct lookup of documents containing a term instead of scanning all documents.

**What data structure is used for an inverted index?**  
Usually a dictionary or hash table mapping terms to lists of document IDs.

**What happens if stopwords are not removed?**  
The index becomes larger and search efficiency decreases due to many unnecessary entries.

## Tricky Questions

**What is the time complexity of searching using an inverted index?**  
Searching is very fast and generally close to O(1) for term lookup using hash structures.

**How would this work for millions of documents?**  
Large-scale systems use distributed storage, compression techniques, and parallel processing.

**How does Google store inverted indexes?**  
Google stores inverted indexes across distributed servers using highly optimized storage and compression methods.

---

# Practical 2 – Retrieval Models (Boolean Retrieval)

## Algorithm
1. Take a collection of documents.
2. Split each document into terms.
3. Build an inverted index mapping term → document IDs.
4. Accept a Boolean query from the user.
5. Apply Boolean operations:
   - AND → intersection of document sets
   - OR → union of document sets
   - NOT → difference of document sets
6. Return the final list of matching documents.

## Dumb Questions

**What is AND?**  
AND returns documents that contain all the specified terms.

**What is OR?**  
OR returns documents that contain at least one of the specified terms.

**What is NOT?**  
NOT excludes documents containing a specific term.

## Basic Questions

**What is the Boolean retrieval model?**  
It is a retrieval model that uses Boolean logic to match documents with user queries.

**What is a query?**  
A query is a request made by the user to search for information.

**What are operands?**  
Operands are the terms on which Boolean operations are applied.

## Good Questions

**Why use sets for Boolean retrieval?**  
Because Boolean operations like AND and OR can be efficiently performed using set operations.

**What are advantages of the Boolean model?**  
It is simple, easy to implement, and provides exact matching results.

**What are limitations of Boolean retrieval?**  
It cannot rank results and may return too many or too few documents.

## Tricky Questions

**Why can't Boolean retrieval rank documents?**  
Because it only checks whether conditions are satisfied, not how relevant a document is.

**How do modern search engines improve Boolean models?**  
They combine Boolean logic with ranking algorithms and relevance scoring.

---

# Practical 3 – Spelling Correction (Edit Distance)

## Algorithm
1. Take two strings as input.
2. Compare the last characters of both strings.
3. If they are the same, move to the next characters.
4. If they are different, calculate the minimum of:
   - Insert
   - Delete
   - Replace
5. Add one operation to the minimum value.
6. Continue until one string becomes empty.

## Dumb Questions

**What is a string?**  
A string is a sequence of characters used to represent text.

**What is recursion?**  
Recursion is a programming technique where a function calls itself to solve smaller parts of a problem.

## Basic Questions

**What is edit distance?**  
Edit distance is the minimum number of operations required to convert one string into another.

**What are edit operations?**  
The operations are insertion, deletion, and substitution of characters.

## Good Questions

**Where is edit distance used?**  
It is used in spell checking, search engines, and text correction systems.

**Why is edit distance useful in search engines?**  
It helps correct user queries when spelling mistakes occur.

## Tricky Questions

**What is the complexity of recursive edit distance?**  
The basic recursive solution has exponential time complexity.

**How can dynamic programming optimize this?**  
Dynamic programming stores intermediate results to reduce complexity to O(m × n).

---

# Practical 4 – Evaluation Metrics

## Algorithm
1. Take the set of retrieved documents.
2. Take the set of relevant documents.
3. Calculate:
   - True Positive (TP)
   - False Positive (FP)
   - False Negative (FN)
4. Compute:
   Precision = TP / (TP + FP)  
   Recall = TP / (TP + FN)
5. Compute F1 Score:
   F1 = 2 × Precision × Recall / (Precision + Recall)

## Dumb Questions

**What is a metric?**  
A metric is a standard measurement used to evaluate system performance.

**What is evaluation?**  
Evaluation is the process of measuring how well a system performs.

## Basic Questions

**What is precision?**  
Precision measures the proportion of retrieved documents that are relevant.

**What is recall?**  
Recall measures the proportion of relevant documents that were retrieved.

**What is F-measure?**  
F-measure or F1 score is the harmonic mean of precision and recall.

## Good Questions

**Why is F1 score important?**  
It balances precision and recall into a single performance measure.

**Difference between precision and recall?**  
Precision focuses on accuracy of retrieved results, while recall focuses on coverage of relevant results.

## Tricky Questions

**When do we prefer high precision vs high recall?**  
High precision is preferred when accuracy is important, while high recall is preferred when missing relevant results is unacceptable.

**Why are both metrics needed?**  
Because relying on only one metric does not provide a complete evaluation of system performance.

---

# Practical 5 – Text Categorization (Naive Bayes)

## Algorithm
1. Load the dataset from a CSV file.
2. Combine text columns into a single feature.
3. Split the dataset into training and testing data.
4. Convert text into numerical vectors using CountVectorizer.
5. Train a Naive Bayes classifier.
6. Predict the category labels for test data.
7. Evaluate model performance using accuracy and classification reports.

## Dumb Questions

**What is classification?**  
Classification is the process of assigning items into predefined categories.

**What is training data?**  
Training data is the dataset used to train a machine learning model.

## Basic Questions

**What is Naive Bayes?**  
Naive Bayes is a probabilistic machine learning algorithm based on Bayes theorem.

**What is supervised learning?**  
Supervised learning is a method where the model learns from labeled training data.

## Good Questions

**Why is Naive Bayes good for text classification?**  
Because it works well with high-dimensional text data and is computationally efficient.

**What is the bag-of-words model?**  
It represents text as a collection of word frequencies without considering word order.

## Tricky Questions

**Why is it called "Naive" Bayes?**  
Because it assumes that features are independent of each other.

**What independence assumption does Naive Bayes make?**  
It assumes that each feature contributes independently to the probability of a class.

---

# Practical 6 – Clustering for Information Retrieval (K-Means)

## Algorithm
1. Take a set of documents.
2. Convert the documents into numerical vectors using TF-IDF.
3. Choose the number of clusters K.
4. Randomly initialize K centroids.
5. Assign each document to the nearest centroid.
6. Recalculate centroids based on assigned documents.
7. Repeat until cluster assignments no longer change.
8. Output the cluster labels.

## Dumb Questions

**What is clustering?**  
Clustering is the process of grouping similar data points together.

**What is a cluster?**  
A cluster is a group of data items that are similar to each other.

## Basic Questions

**What is K-Means?**  
K-Means is an unsupervised machine learning algorithm used to group data into K clusters.

**What is a centroid?**  
A centroid is the central point of a cluster.

## Good Questions

**What is unsupervised learning?**  
Unsupervised learning is a machine learning method where data has no labeled outputs.

**Why use TF-IDF before clustering?**  
Because it converts textual data into numerical form while giving importance to significant words.

## Tricky Questions

**How do you choose K?**  
Methods such as the Elbow Method or Silhouette Score can be used.

**What happens if K is too large or too small?**  
Too small K merges unrelated documents, while too large K creates unnecessary clusters.

---

# Practical 7 – Web Crawling and Indexing

## Algorithm
1. Start with a seed URL.
2. Send an HTTP request to retrieve the webpage.
3. Parse the HTML content using BeautifulSoup.
4. Extract hyperlinks from the page.
5. Convert relative URLs into absolute URLs.
6. Visit newly discovered links recursively.
7. Maintain a visited set to avoid revisiting pages.
8. Add delays between requests to avoid server overload.

## Dumb Questions

**What is a URL?**  
A URL is the address used to access a resource on the internet.

**What is HTML?**  
HTML is the standard language used to structure web pages.

## Basic Questions

**What is a web crawler?**  
A web crawler is a program that automatically browses the web to collect information.

**What is indexing?**  
Indexing is the process of storing web content in a structured form for fast retrieval.

## Good Questions

**Why respect robots.txt?**  
Because it specifies which parts of a website should not be accessed by crawlers.

**What is crawl depth?**  
Crawl depth refers to how many levels of links the crawler follows from the starting page.

## Tricky Questions

**What problems occur in web crawling?**  
Common issues include duplicate pages, broken links, large data volumes, and server overload.

**How do search engines avoid crawling duplicate pages?**  
They use URL normalization, hashing, and duplicate content detection techniques.

---

# Practical 8 – Link Analysis and PageRank

## Algorithm
1. Represent web pages as nodes in a graph.
2. Initialize PageRank values for each page.
3. For each iteration:
   - Calculate rank contributions from incoming links.
4. Apply a damping factor (commonly 0.85).
5. Repeat the process until values converge.
6. Output the final PageRank scores.

## Dumb Questions

**What is a graph?**  
A graph is a data structure consisting of nodes connected by edges.

**What is a link?**  
A link is a connection from one webpage to another.

## Basic Questions

**What is PageRank?**  
PageRank is an algorithm used to measure the importance of web pages based on links.

**What is a damping factor?**  
The damping factor represents the probability that a user continues clicking links.

## Good Questions

**Why do important pages pass rank to others?**  
Because links from important pages indicate trust and relevance.

**Why is iterative computation required?**  
Because PageRank values depend on the ranks of other pages.

## Tricky Questions

**What happens with pages having no outgoing links?**  
They are treated as linking to all pages to avoid rank loss.

**Why was PageRank revolutionary for Google?**  
Because it ranked pages based on link importance instead of only keyword matching.

---

# Ultra Short Memory Hacks

Inverted Index → word mapped to documents  

Boolean Model → uses set operations  

Edit Distance → insert, delete, replace operations  

Evaluation → precision and recall  

Naive Bayes → probabilistic text classification  

K-Means → unsupervised clustering algorithm  

Crawler → recursively fetch web pages  

PageRank → rank pages using link structure
