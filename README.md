# OLS_pipeline

A Python package for data preprocessing, model fitting, and VIF calculation in panel data regression analysis.

## Installation

Install the package using pip:
```python
pip install PanelOLSPipeline==0.1.1 
```


## Usage

Here's a quick example of how to use the OLS_pipeline:

```python
import OLS_pipeline.pipeline as OLS_pipe

# Set up your data and parameters
data_path = "path/to/your/data.csv"
dependent_var = 'Target'
independent_vars = ['Feature1', 'Feature2']
normalize_cols = ['Feature3', 'Feature4', 'Feature5']
weight_dict = {
    'Normalized_F3': 0.4, 
    'Normalized_F4': 0.2, 
    'Normalized_F5': 0.4
}
interaction_pairs = [('Feature_x', 'Feature_y')]

# Run the pipeline
results = OLS_pipe.pipeline(
    data_path, 
    dependent_var, 
    independent_vars, 
    normalize_cols, 
    weight_dict, 
    interaction_pairs
)

# Unpack the results
fixed_effects_results, random_effects_model, vif_data = results
