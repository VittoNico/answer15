## answer15

import pandas as pd
import numpy as np

data = pd.read_csv('gene_expression_dataset.csv')

data['log2FC'] = np.log2((data['Condition2'] + 1e-8) / (data['Condition1'] + 1e-8))
data_sorted = data.sort_values(by='log2FC', ascending=False)

data_sorted.to_csv('gene_expression_log2fc_sorted.csv', index=False)

print("Log2 fold-changes calculated and data exported to 'gene_expression_log2fc_sorted.csv'.")
