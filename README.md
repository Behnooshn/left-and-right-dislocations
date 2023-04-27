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



import numpy as np
from statsmodels.stats.proportion import proportions_ztest

# Sample sizes
n1 = n2 = 67

# Number of successes for DeepL
successes1 = 51
successes2 = 29

# Proportions
p1 = successes1 / n1
p2 = successes2 / n2

# Null hypothesis: p1 = p2
# Alternative hypothesis: p1 != p2
# Significance level: 0.05 (default)
z_score, p_value = proportions_ztest([successes1, successes2], [n1, n2], alternative='two-sided')

print(f"Z-score: {z_score:.2f}")
print(f"P-value: {p_value:.2f}")



import numpy as np
from scipy.stats import norm


# Number of successes for Google Translate 
ld_success_rate = 46/69
rd_success_rate = 23/69

p_hat = (46 + 23) / (69 + 69)
se = np.sqrt(p_hat * (1 - p_hat) * (1/69 + 1/69))
z = (ld_success_rate - rd_success_rate) / se
p = 2 * (1 - norm.cdf(np.abs(z)))

print("Z-score: {:.2f}".format(z))
print("P-value: {:.2f}".format(p))

