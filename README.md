# Facebook Social Network Analysis (Stanford SNAP)

> **Interactive Social Network Analysis using NetworkX, Louvain Community Detection, and PyVis**

---

## 📌 Project Overview

This project presents a **comprehensive Social Network Analysis (SNA)** of the Facebook social network dataset released by the **Stanford Network Analysis Project (SNAP)**. The objective is to understand how **structure, influence, and communities** emerge in a real-world social network using graph-theoretic methods.

The project intentionally focuses on **conceptual clarity and methodological rigor**, progressing from graph construction to **centrality analysis**, **community detection**, and a **fully dynamic interactive visualization** hosted via GitHub Pages.

---

## 📂 Dataset

- **Source:** Stanford Network Analysis Project (SNAP)
- **Dataset name:** `facebook_combined.txt`
- **Graph type:** Undirected, unweighted
- **Nodes:** Facebook users (anonymized IDs)
- **Edges:** Mutual friendship relations

Each line in the dataset represents a friendship:

```text
node_i  node_j
```

---

## 🎯 Objectives

- Represent a real-world social system as a graph
- Examine global structural properties of the network
- Identify influential and structurally important users
- Detect latent community (social circle) structure
- Build an **interactive HTML-based visualization** for exploratory analysis

---

## 🧠 Methodology

### 1️⃣ Graph Construction

- Loaded the edge list using **NetworkX**
- Constructed an **undirected graph** (friendships are reciprocal)
- Focused analysis on the **largest connected component** to ensure meaningful path-based metrics

---

### 2️⃣ Degree Distribution Analysis

- Computed node degrees and degree centrality
- Visualized degree distributions using **Plotly**
- Observed a **right-skewed (heavy-tailed) distribution**, typical of social networks

**Key insight:**
> Most users have few connections, while a small fraction act as hubs.

---

### 3️⃣ Centrality Analysis

The following centrality measures were computed:

- **Degree Centrality** – captures local popularity
- **Betweenness Centrality (approximated)** – identifies bridge nodes that control information flow
- **Closeness Centrality** – measures reachability within the network

Betweenness centrality was **approximated using random sampling** due to the computational cost of exact computation on large graphs.

**Key insight:**
> Highly connected users are not necessarily the most structurally powerful.

---

### 4️⃣ Community Detection

- Applied the **Louvain algorithm** to detect communities
- Evaluated community structure using **modularity**
- Identified multiple densely connected clusters representing social circles

**Interpretation:**
> The Facebook network exhibits strong modular structure, a hallmark of real-world social systems.

---

### 5️⃣ Fully Dynamic Community Visualization

- Implemented a physics-based interactive network using **PyVis (vis.js)**
- Visualization characteristics:
  - Nodes sized by **betweenness centrality**
  - Nodes colored by **community membership**
  - Interactive physics, zooming, dragging, and hover tooltips

The visualization is exported as a standalone **HTML file** and hosted using **GitHub Pages**.

🔗 **Live interactive visualization:**  
[Facebook Networks By Pranav Alok](https://pranav-alok.github.io/facebook-sna-analysis/facebook_communities_dynamic.html)

---

## 🛠 Tools & Libraries

- **Python**
- **NetworkX** – graph modeling and network metrics
- **Pandas / NumPy** – data handling
- **Plotly** – statistical visualizations
- **PyVis** – interactive network visualization
- **python-louvain** – community detection

---

## 📈 Key Results

- The network shows **sparse connectivity with hub nodes**
- Presence of **high-betweenness bridge users** linking communities
- Strong and interpretable **community structure**
- Dynamic visualization reveals meso-scale social organization intuitively

---

## 📁 Project Structure

```text
facebook-sna-analysis/
│
├── data/
│   └── raw/
│       └── facebook_combined.txt
│
├── notebooks/
│   ├── 01_data_loading.ipynb
│   ├── 02_network_metrics.ipynb
│   ├── 03_centrality_analysis.ipynb
│   ├── 04_community_detection.ipynb
│
├── outputs/
│   ├── tables/
│   └── interactive/
│       └── facebook_communities_dynamic.html
│
├── docs/
│   └── index.html   # GitHub Pages entry point
│
├── requirements.txt
├── README.md
└── .gitignore
```

---

## 🚀 How to Run Locally

1. Clone the repository:
```bash
git clone https://github.com/<your-username>/facebook-sna-analysis.git
cd facebook-sna-analysis
```

2. Install dependencies:
```bash
pip install -r requirements.txt
```

3. Place the dataset inside:
```text
data/raw/facebook_combined.txt
```

4. Run notebooks in sequence to reproduce results
5. Open `docs/index.html` in a browser for interactive exploration

---

## 🔮 Future Extensions

- Ego-network analysis of influential users
- Temporal or weighted network analysis
- Comparative analysis with other social platforms
- Application of this pipeline to **policy, ESG, and sustainability networks**

---

## 📚 References

- Leskovec, J., & McAuley, J. (2012). *Learning to Discover Social Circles in Ego Networks*. NIPS.
- Stanford Network Analysis Project (SNAP): https://snap.stanford.edu

---

## 👤 Author

**Pranav Alok**  
B.Sc. Analytics & Sustainability Studies  
Tata Institute of Social Sciences (TISS), Mumbai

---

> ⚠️ **Note on learning approach:**  
> This project was developed as a guided learning exercise in Social Network Analysis. Emphasis was placed on understanding concepts, methodological choices, and interpretation rather than implementing algorithms from scratch.
