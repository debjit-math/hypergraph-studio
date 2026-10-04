# 🔷 Hypergraph Studio

### Interactive Visualization & Spectral Analysis of Hypergraphs

**Hypergraph Studio** is a lightweight, browser-based environment for **visualizing, transforming, and analyzing hypergraphs**.

It combines interactive visualization with tools for **permutations, automorphisms, incidence matrices, Banerjee adjacency matrices, and spectral analysis** — all in a single HTML file.

> **No installation. No frameworks. No external dependencies. Just open the HTML file and explore.**

## 🌐 Live Demo

🚀 **[Open Hypergraph Studio](https://debjit-math.github.io/hypergraph-studio/)**

Try the interactive hypergraph visualization directly in your browser — no installation required.

## ✨ What can you do?

| 🔹 Feature | 🔹 Description |
|---|---|
| 🎨 **Visualization** | Explore hyperedges and vertices interactively |
| 🔄 **Permutations** | Apply and animate permutations using cycle notation |
| 🧩 **Automorphisms** | Check whether a permutation preserves the hypergraph |
| 📊 **Statistics** | Analyze degrees, uniformity, regularity, components, etc. |
| 🔢 **Matrices** | Inspect incidence and hyperedge-intersection matrices |
| 📐 **Banerjee Matrix** | Construct the hypergraph adjacency matrix |
| 📈 **Spectrum** | Compute adjacency eigenvalues and spectral radius |
| 🔍 **Search** | Find vertices and hyperedges interactively |
| 💾 **Export** | Export visualizations as SVG/PNG and data as JSON |

---

# 🚀 Getting Started

There is **nothing to install**.

Download the HTML file:

```text
hypergraph_studio_banerjee.html
```

and open it directly in a modern browser.

That's it.

The entire application runs locally in the browser.

---

# 🕸️ Enter a Hypergraph

Hyperedges can be entered one per line:

```text
(0,1,2,11)
(0,3,5,6)
(0,7,9,10)
(1,3,4,10)
(1,6,7,8)
(2,3,8,9)
(2,4,5,7)
(4,6,9,11)
(5,8,10,11)
```

Hyperedge labels can be supplied separately:

```text
H1,H2,H3,H4,H5,H6,H7,H8,H9
```

Vertices are detected automatically.

---

# 🔄 Permutation Visualization

Permutations are entered using **cycle notation**.

For example:

```text
1,2,3;5,7
```

represents

\[
(1\ 2\ 3)(5\ 7).
\]

Therefore,

\[
1\rightarrow2,\qquad
2\rightarrow3,\qquad
3\rightarrow1
\]

and

\[
5\leftrightarrow7.
\]

Vertices not mentioned remain fixed.

### 🎬 Animated transformation

When the permutation is applied, the vertices smoothly move to their new positions.

The application preserves:

- vertex identity;
- hyperedge identity;
- hyperedge labels;
- hyperedge colors.

This makes permutation actions and symmetries easy to inspect visually.

---

# 🧩 Automorphism Analysis

Hypergraph Studio can test whether a permutation is an **automorphism**.

For a permutation

\[
\sigma:V\rightarrow V,
\]

each hyperedge is transformed according to

\[
e\mapsto\sigma(e).
\]

The application checks whether

\[
\{\sigma(e):e\in E\}=E.
\]

It also displays the induced hyperedge mapping.

This makes the tool useful for exploring **symmetry and automorphism structure** of hypergraphs.

---

# 📊 Structural Analysis

The application automatically calculates several properties of the hypergraph.

### Vertex statistics

- Vertex degree
- Isolated vertices
- Fixed and moved vertices

### Hyperedge statistics

- Minimum edge size
- Maximum edge size
- Average edge size
- Duplicate hyperedges

### Structural properties

- Uniformity
- Regularity
- Connected components
- Linearity

---

# 🔢 Incidence Matrix

For a hypergraph

\[
H=(V,E),
\]

the incidence matrix \(B\) is defined by

\[
B_{ij}=
\begin{cases}
1,&v_i\in e_j,\\
0,&v_i\notin e_j.
\end{cases}
\]

The complete incidence matrix can be inspected directly in the application.

---

# 🔗 Hyperedge Intersection Matrix

The application also computes the hyperedge intersection matrix:

\[
M_{ij}=|e_i\cap e_j|.
\]

This provides a compact view of how hyperedges overlap.

---

# 📐 Banerjee Adjacency Matrix

Hypergraph Studio includes the adjacency matrix used in the spectral framework of **Banerjee**.

For distinct vertices \(i\) and \(j\),

\[
\boxed{
A_{ij}
=
\sum_{\substack{e\in E\\i,j\in e}}
\frac{1}{|e|-1}
}
\]

with

\[
A_{ii}=0.
\]

Thus, a hyperedge of size \(k\) contributes

\[
\frac{1}{k-1}
\]

to every pair of distinct vertices contained in that hyperedge.

This definition naturally handles **non-uniform hypergraphs**.

---

# 📈 Hypergraph Spectrum

After constructing the Banerjee adjacency matrix \(A\), Hypergraph Studio computes its eigenvalues:

\[
\lambda_1,\lambda_2,\ldots,\lambda_n.
\]

The application displays:

- **Adjacency spectrum**
- **Spectral radius**
- Banerjee adjacency matrix
- Weighted degree / row-sum information

The spectral radius is

\[
\rho(A)=\max_i|\lambda_i|.
\]

Eigenvalues are calculated directly in JavaScript, without requiring an external numerical library.

---

# 🎨 Visualization Modes

Hypergraph Studio provides several ways to view the same structure.

### 1. Hyperedge Hulls

Hyperedges are represented by translucent geometric regions.

### 2. Radial Layout

Vertices are arranged around a circle, which is particularly useful for studying symmetry.

### 3. Incidence Graph

Vertices and hyperedges are displayed as two separate types of nodes, connected according to incidence.

---

# 🔍 Interactive Exploration

The visualization supports:

- 🖱️ Dragging vertices
- 🔎 Searching vertices and hyperedges
- 👆 Clicking vertices
- 👆 Clicking hyperedges
- 🔗 Exploring vertex neighborhoods
- 🔍 Zooming
- ♻️ Re-layout
- 🎯 Highlighting fixed points
- 🔄 Highlighting moved vertices

---

# 📤 Export

Your work can be exported directly from the browser.

### SVG

Ideal for:

- research papers;
- vector editing;
- presentations.

### PNG

Useful for:

- slides;
- reports;
- quick sharing.

### JSON

Save and restore:

- hyperedges;
- labels;
- permutation;
- vertex positions;
- visualization settings.

---

# 🧪 Example Workflow

A typical exploration might look like:

```text
1. Enter hypergraph
        ↓
2. Generate visualization
        ↓
3. Inspect structural statistics
        ↓
4. Apply a permutation
        ↓
5. Observe animated transformation
        ↓
6. Check automorphism
        ↓
7. Inspect incidence matrix
        ↓
8. Construct Banerjee adjacency matrix
        ↓
9. Compute spectrum
        ↓
10. Export results
```

---

# 📚 Mathematical Reference

The spectral component of this project is based on the work of:

**Anirban Banerjee**

> *On the spectrum of hypergraphs*

*Linear Algebra and its Applications*

DOI:

**10.1016/j.laa.2020.01.012**

The original publication should be consulted for the formal mathematical definitions, theorems, and proofs.

---

# 🛠️ Technology

Hypergraph Studio is intentionally minimal.

```text
HTML
CSS
JavaScript
SVG
```

### No external dependencies

❌ React  
❌ D3.js  
❌ jQuery  
❌ Math.js  
❌ npm  
❌ Node.js  
❌ Build tools  

Everything runs directly in the browser.

---

# 📁 Repository

A minimal repository can contain:

```text
hypergraph-studio/
│
├── 📄 hypergraph_studio_banerjee.html
└── 📄 README.md
```

---

# 🤖 Development

The application was developed with assistance from **OpenAI ChatGPT**.

The project direction, mathematical requirements, feature design, testing, and refinement were guided by the project author.

---

# ⚠️ License

**No license is currently provided.**

All rights are reserved by the project author.

The public availability of this repository does **not** grant permission to copy, modify, redistribute, or reuse the source code except where permitted by applicable law.

For permission to use or adapt the code, please contact the project author.

---

# 🌟 Project Goal

Hypergraph Studio aims to provide a simple environment where researchers and students can move between:

\[
\boxed{
\text{Hypergraph}
\rightarrow
\text{Permutation}
\rightarrow
\text{Structure}
\rightarrow
\text{Matrix}
\rightarrow
\text{Spectrum}
}
\]

without needing a specialized software environment.

---

## 🔷 Hypergraph Studio

**Visualize. Transform. Analyze. Explore.**

*An interactive laboratory for hypergraph structure and spectral analysis.*
