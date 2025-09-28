# DAGs and Causal Machine Learning Analysis

This repository contains a comprehensive analysis of Directed Acyclic Graphs (DAGs) and causal inference methods implemented in three programming languages: Python, Julia, and R. The project explores fundamental concepts in causal machine learning through three distinct analytical tasks.

## Repository Structure

```
DAGs_CausalML/
├── Python/
│   ├── scripts/           # Jupyter notebooks for Python analysis
│   │   ├── Part1_Python.ipynb
│   │   ├── Part2_Python.ipynb
│   │   └── Part3_Python.ipynb
│   ├── output/           # Generated plots, data, and results
│   └── requirements.txt  # Python dependencies
├── Julia/
│   ├── scripts/          # Jupyter notebooks for Julia analysis
│   │   ├── Part1_Julia.ipynb
│   │   ├── Part2_Julia.ipynb
│   │   └── Part3_Julia.ipynb
│   ├── output/           # Generated plots, data, and results
│   └── requirements.txt  # Julia dependencies
├── R/
│   ├── scripts/          # Jupyter notebooks for R analysis
│   │   ├── Part1_R.ipynb
│   │   ├── Part2_R.ipynb
│   │   └── Part3_R.ipynb
│   ├── output/           # Generated plots, data, and results
│   └── requirements.txt  # R dependencies
└── README.md            # This file
```

## Analysis Overview

### Part 1: Real Life Examples and Simpson's Paradox (4 points)

**Objective**: Understand fundamental causal structures and demonstrate Simpson's Paradox

**Methods**:
- **Part 1a**: Analysis of three causal structures:
  - **Confounders**: Variables that influence both treatment and outcome
  - **Mediators**: Variables that lie on the causal path between treatment and outcome
  - **Colliders**: Variables that are influenced by both treatment and outcome
- **Part 1b**: Simulation and demonstration of Simpson's Paradox using real-world scenarios

**Key Results**:
- Successfully illustrated how different causal structures require different analytical approaches
- Demonstrated Simpson's Paradox where aggregate trends reverse when data is stratified by a confounding variable
- High-skill group: positive slope (β ≈ 2.30)
- Low-skill group: positive slope (β ≈ 2.33)
- Combined analysis: negative slope (β ≈ -3.95)

### Part 2: Can We Omit Some Controls? (7 points)

**Objective**: Investigate the effects of different control variable combinations on causal estimation

**Methods**:
- Data simulation with known causal structure
- Regression analysis with various combinations of control variables
- Bias analysis comparing estimated vs. true causal effects
- Statistical significance testing

**Key Results**:
- True causal effect: β = 1.0
- Including appropriate controls (Z, U1) yielded nearly unbiased estimates (bias ≈ 0.01)
- Omitting key confounders led to substantial bias (up to 1.01 bias when no controls included)
- Demonstrated the importance of proper confounder identification and control

### Part 3: Damned if You Do, Damned if You Don't (9 points)

**Objective**: Explore complex causal scenarios where controlling for certain variables may introduce bias

**Methods**:
- Advanced DAG analysis with multiple causal pathways
- Comparison of original vs. modified causal structures
- Sensitivity analysis across different model specifications
- Evaluation of causal identification strategies

**Key Results**:
- Successfully identified scenarios where controlling for certain variables can worsen bias
- Demonstrated the critical importance of causal structure understanding before variable selection
- Provided evidence-based recommendations for control variable selection in complex causal scenarios

## Technical Implementation

### Python Implementation
- **Libraries**: NumPy, Pandas, Matplotlib, Seaborn, SciPy, Statsmodels, CausalGraphicalModels
- **Strengths**: Comprehensive statistical analysis, extensive visualization capabilities
- **Key Features**: Advanced plotting, statistical testing, data manipulation

### Julia Implementation  
- **Libraries**: CausalInference.jl, Graphs.jl, GraphPlot.jl, StructuralCausalModels.jl
- **Strengths**: High-performance computing, specialized causal inference tools
- **Key Features**: Efficient graph algorithms, advanced causal inference methods

### R Implementation
- **Libraries**: dagitty, ggdag, dplyr, ggplot2, broom, tidyr
- **Strengths**: Mature statistical ecosystem, excellent DAG visualization
- **Key Features**: Professional statistical graphics, comprehensive model diagnostics

## Main Findings

1. **Causal Structure Matters**: The choice of control variables must be guided by causal theory, not just statistical significance
2. **Simpson's Paradox is Real**: Aggregated analysis can lead to completely opposite conclusions compared to stratified analysis
3. **Language-Specific Advantages**: Each programming language offers unique strengths for causal analysis
4. **Bias-Variance Tradeoff**: Including more controls doesn't always improve causal estimates and can sometimes introduce bias

## Installation and Usage

### Python
```bash
cd Python/
pip install -r requirements.txt
jupyter notebook scripts/
```

### Julia
```bash
cd Julia/
# Install packages listed in requirements.txt
julia -e 'using Pkg; Pkg.add(["CausalInference", "Graphs", "GraphPlot", ...])'
jupyter notebook scripts/
```

### R
```r
# Install required packages
install.packages(c("dagitty", "ggdag", "dplyr", "ggplot2", "broom", "tidyr", "gridExtra", "xtable"))
# Open R notebooks in Jupyter or RStudio
```

## Academic Context

This analysis contributes to the growing field of causal machine learning by providing:
- Comparative implementation across multiple programming languages
- Practical demonstrations of theoretical causal inference concepts
- Reproducible research with complete code and results
- Educational resources for understanding DAGs and causal analysis

## License

MIT License - see LICENSE file for details.
