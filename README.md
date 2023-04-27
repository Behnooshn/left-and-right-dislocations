# left-and-right-dislocations
z-tests for Master2 project (LD vs RD)
import numpy as np
from scipy import stats

# Set the values for the number of successes and trials for each group (LD)
google_no_copy = 46
google_total = 67
deepl_no_copy = 51
deepl_total = 67

# Calculate the sample proportions for each group
google_prop = google_no_copy / google_total
deepl_prop = deepl_no_copy / deepl_total

# Calculate the pooled proportion
pooled_prop = (google_no_copy + deepl_no_copy) / (google_total + deepl_total)

# Calculate the standard error
se = np.sqrt(pooled_prop * (1 - pooled_prop) * ((1 / google_total) + (1 / deepl_total)))

# Calculate the z-score and p-value
z_score = (deepl_prop - google_prop) / se
p_value = 2 * (1 - stats.norm.cdf(abs(z_score)))

# Print the results
print("z-score:", z_score)
print("p-value:", p_value)



import numpy as np
from scipy import stats

# Set the values for the number of successes and trials for each group (RD)
google_no_copy = 23
google_total = 67
deepl_no_copy = 29
deepl_total = 67

# Calculate the sample proportions for each group
google_prop = google_no_copy / google_total
deepl_prop = deepl_no_copy / deepl_total

# Calculate the pooled proportion
pooled_prop = (google_no_copy + deepl_no_copy) / (google_total + deepl_total)

# Calculate the standard error
se = np.sqrt(pooled_prop * (1 - pooled_prop) * ((1 / google_total) + (1 / deepl_total)))

# Calculate the z-score and p-value
z_score = (deepl_prop - google_prop) / se
p_value = 2 * (1 - stats.norm.cdf(abs(z_score)))

# Print the results
print("z-score:", z_score)
print("p-value:", p_value)
