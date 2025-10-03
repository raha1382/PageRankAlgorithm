# PageRank Implementation and Analysis  

This project implements and analyzes the **PageRank algorithm** using different approaches and compares their accuracy, efficiency, and interpretability.The project focuses on implementing and analyzing the PageRank algorithm using the Berkeley-Stanford Web Graph dataset.  

## 🛠️ Languages & Tools Used

![Python](https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white)![Jupyter](https://img.shields.io/badge/Jupyter-F37626?style=for-the-badge&logo=jupyter&logoColor=white)![Bash](https://img.shields.io/badge/Bash-4EAA25?style=for-the-badge&logo=gnu-bash&logoColor=white)

## Features  

- **Custom PageRank Implementation**  
  - Eigen decomposition (`numpy.linalg.eig`)  
  - Power iteration method  
- **NetworkX Integration**  
  - Construct graph and compute PageRank using `networkx.pagerank`  
  - Compare results with custom implementations  
- **Damping Factor (α) Experiments**  
  - Explore the effect of different α values (0.25, 0.5, 0.75, 0.99)  
- **Toy Example Validation**  
  - Small handcrafted adjacency matrix tested with both custom and NetworkX methods  

## Dataset  

- Uses the **Berkeley–Stanford Web Graph** (`web-BerkStan.mtx`)  
- Due to size, experiments run on the first 1000 nodes (`Data[:1000, :1000]`)  

## Code Overview  

- **`pagerank_lib(matrix, alpha)`**: PageRank via eigen decomposition  
- **`pagerank_powermethod(matrix, alpha, num_iterations=100)`**: Iterative power method  
- **NetworkX Comparison**: PageRank computed using `networkx.pagerank`  
- **Accuracy Metrics**: Evaluates how closely each method satisfies the PageRank stationary condition  
- **Runtime Comparison**: Execution time measured for each approach  

## Results  

### Top 20 Pages (Eigen Decomposition)  
Page ID: 39, Score: 0.04936
Page ID: 860, Score: 0.03811
Page ID: 767, Score: 0.03721
...

### Top 20 Pages (Power Iteration)  
Page ID: 860, Score: 0.03734
Page ID: 767, Score: 0.03409
Page ID: 39, Score: 0.03126
...

### Top 20 Pages (NetworkX)  
Page ID: 860, Score: 0.03680
Page ID: 767, Score: 0.03423
Page ID: 39, Score: 0.03127
...


### Performance Comparison  
- Accuracy (`‖Qr - r‖`):  
  - Eigen decomposition: **4.30**  
  - Power method: **0.014**  
- Runtime:  
  - Eigen decomposition: **~1.02s**  
  - Power method: **~0.03s**  
  - NetworkX: **~0.014s**  

### Damping Factor (α) Effects  
- α = 0.25 → 0.0904  
- α = 0.50 → 0.0531  
- α = 0.75 → 0.0241  
- α = 0.99 → 0.0022  

Lower α increases randomness; higher α emphasizes link structure.  

### Toy Graph Example  
Validation on a small adjacency matrix confirmed consistent ranking with both custom and NetworkX methods.  

## Requirements
numpy>=1.23
scipy>=1.10
networkx>=3.1

## Installation & Usage  

```bash
git clone https://github.com/raha1382/PageRankAlgorithm.git
cd PageRankAlgorithm
pip install -r requirements.txt
```

## Setting Up a Virtual Environment (Optional but Recommended)

1. Create a virtual environment:

```bash
python -m venv venv
```
2. Activate the virtual environment:

Windows:
```bash
venv\Scripts\activate
```
Linux / macOS:
```bash
source venv/bin/activate

```
3. Install dependencies:
```bash
pip install -r requirements.txt
```
