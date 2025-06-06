# COMP3850: PACE 14 - LatentKnowledge

The following project is phase 2 of Group 14's prototype on Hierarchical Visualisation Systems (HVS). It is a backend data pipeline for semantically clustering academic literature and visualising them in 2D and 3D environments. The prototype features unsupervised clustering algorithms and transformer-based embeddings. Visual representations have been generated using plotly for interactivity.

In `D4 Final Protoype` the density-based algorithms explored are:
  - HDBSCAN
  - DBSCAN
  - OPTICS

`V2 D4 Prototype` explores the following clustering algorithms whilst simultaneously incorporating query-based filtering:
  - DBSCAN
  - OPTICS

## Aim
- Automatically group thematically similar academic literature.
- Provide researchers, students, and sponsors with an intuitive way to navigate academic papers.
- Assist in identifying emerging trends and literature clusters.

## Project Structure

<pre><code> PACE14-LatentKnowledge/
  
├── D4_Final_Prototype.ipynb                # Final prototype
│
├── V2 D4 Prototype/                        # Final prototype but better  
│   └── V2_Prototype_Phase_2.ipynb
│   ├── outputs/                            # Interactive scatter plots of cluster outputs + similarity score
│     └── fig_dbscan_2d.html
│     └── fig_dbscan_3d.html
│     └── fig_hdbscan_2d.html
│     └── fig_hdbscan_3d.html
│
├── drafts/  
│   └── Draft_1.ipynb                       # Early draft
│   └── Draft_2.ipynb                       # Intermediate prototype
│
├── outputs/                                # Interactive scatter plots of cluster outputs
│   └── fig_dbscan_2d.html
│   └── fig_dbscan_3d.html
│   └── fig_hdbscan_2d.html
│   └── fig_hdbscan_3d.html
│   └── fig_optics_2d.html
│   └── fig_optics_3d.html
│
├── dataset/                                # Input dataset
│   └── full_renewable_energy_papers.csv
│
├── README.md                               # Project overview
└── LICENSE                                 # License file
</code></pre>

## Input Formatting
Dataset must be a CSV file such as:

    full_renewable_energy_papers.csv
 
### Required Columns
| Column Name | Description                                | Type   |
| ----------- | ------------------------------------------ | ------ |
| `title`     | Title of the research paper                | String |
| `abstract`  | Abstract or summary of the paper's content | String |

### Input location
Replace file path in `D4_Final_Prototype.ipynb` before executing:
  
    df = pd.read_csv('/content/outputs/full_renewable_energy_papers.csv')
    
## Output
The interactive plotly outputs generated have been provided as html files and are located in `outputs/`.
  - 2D UMAP Scatter plot with hover labels
  - 3D UMAP Scatter plot with hover labels
  - Datapoints belonging to **Cluster `-1`** = outliers (noise or documents with low-similarity)

## Configuration Options
The following parameters may be altered in `D4_Prototype_Final.ipynb` prior to execution.

Tunable parameters for clustering:
- `min_cluster_size`
- `eps`
- `min_samples`
- `xi`

Tunable parameters for UMAP:
- `n_components`
- `n_neighbors`

## Libraries and Licensing
The prototype utilises the following libraries and models:
| Component                                 | License    |
| ------------------------------------------| ---------- |
| SentenceTransformer *(all-mpnet-base-v2)* | Apache 2.0 |
| UMAP                                      | BSD        |
| HDBSCAN                                   | BSD        |
| Plotly                                    | MIT        |
| scikit-learn                              | BSD        |
| pandas                                    | BSD        |
| numpy                                     | BSD        |
