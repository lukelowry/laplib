# laplib
Repository of Graph Laplacians

Note: The data is usable but not consistently formatted as of Jan 2026.

| Dataset | Vertices | Signals | Edges| Signals |
| :--- | :--- | :--- | :--- | :--- |
| [StanfardBunny](./StanfardBunny) | 35947|  `x`,`y`,`z`| 104288|   |
| [SyntheticHawaii](./SyntheticHawaii) | 37| `long`, `lat`|| `length`, `admitt`
| [SyntheticTexas](./SyntheticTexas) | 2000| `long`, `lat` | |`length`, `admitt`|
| [SyntheticEast](./SyntheticEast) | 70000| `long`, `lat` | | `length`, `admitt` |
| [SyntheticEastWest](./SyntheticEastWest) | 78000| `long`, `lat` | |`length`, `admitt`|
| [SyntheticUSA](./SyntheticUSA) | 82000 | `long`, `lat` || `length`, `admitt`|
| [WECC](./WECC) | 240 | |  |`length`, `admitt`|
## Subfolder Structure

Each dataset subfolder should adhere to the following structure:

```text
DatasetName/
├── edges.txt      # Sparse edge list
├── signals.txt    # Vertex features
├── lap.mat        # Graph Laplacian
└── README.md      # Metadata
```

### Edge Data (`edges.txt`)

A space-separated text file with a header line containing graph edges and features.
*   **Dimensions:** `M x (2 + K)` matrix (`M` edges, `K` features).
*   **Columns:** `source`, `target`, followed by `K` feature columns.
*   **Indices:** 0-based integers.
*   **Notes:** Supports multiple edge weights (e.g., resistance, reactance).

### Vertex Signals (`signals.txt`)

A space-separated text file representing an `N x D` matrix of vertex features.
*   **Rows:** `N` vertices, sorted by index (0 to N-1).
*   **Columns:** `D` signal dimensions/features.

### Graph Laplacian (`lap.mat`)

A binary MATLAB Level 5 MAT-file containing the `N x N` graph Laplacian matrix.
*   **Variable:** Must be named `L` or `lap`.
*   **Format:** Compressed Sparse Column (CSC).

### Metadata (`README.md`)

A markdown file containing dataset metadata. Each file should include:
*   Description (`str`)
*   Number of Vertices (`int`)
*   Number of Edges (`int`)
