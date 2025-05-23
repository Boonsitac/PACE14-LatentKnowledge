# COMP3850: PACE 14 - LatentKnowledge

The following project is phase 2 of Group 14's prototype on Hierarchical Visualisation Systems (HVS). In essence, it is a backend data pipeline for semantically clustering academic literature and visualising them in 2D and 3D environments. The prototype features unsupervised clustering algorithms and transformer-based embeddings.

The density-based algorithms explored are:
  - HDBSCAN
  - DBSCAN
  - OPTICS

## Aim
- Automatically group thematically similar academic literature.
- Provide researchers, students, and sponsors with an intuitive way to navigate academic papers.
- Assist in identifying emerging trends and literature clusters.

## Input Formatting
Dataset must be a CSV file such as:

    full_renewable_energy_papers.csv
 
### Required Columns
| Column Name | Description                                | Type   |
| ----------- | ------------------------------------------ | ------ |
| `title`     | Title of the research paper                | String |
| `abstract`  | Abstract or summary of the paper's content | String |

### Input location
Replace file path in **D4_Final_Prototype.ipynb** before executing:
  
    df = pd.read_csv('/content/outputs/full_renewable_energy_papers.csv')
    
## Output
The interactive plotly outputs generated have been provided as html files and are located in the **main branch**.

Datapoints belonging to **Cluster -1** are outliers and thus indicated as noise or documents with low-similarity.

### Output File Names
    
  - fig_dbscan_2d.html
  - fig_dbscan_3d.html
  - fig_hdbscan_2d.html
  - fig_hdbscan_3d.html
  - fig_optics_2d.html
  - fig_optics_3d.html

## Configuration Options
The following parameters may be altered in **D4_Prototype_Final.ipynb** prior to execution.

Tunable parameters for clustering:
- min_cluster_size
- eps
- min_samples
- xi

Tunable parameters for UMAP:
- n_components
- n_neighbors

## Licensing
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
