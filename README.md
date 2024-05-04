# Quantisation
Model weights.
•	The larger the weight the greater the accuracy but increased required resources.

•	Normally floating point

•	Quantisation rescales weights and/or activations.
•	Quantisation often uses INT8, INT4
•	Mapping function
o	Map high precision to lower precision.
o	Per layer
o	Q(r) = round((r/S)+Z)
	S = scaling factor
	Z = bias value to map a zero
o	Map the actual range of values from the larger range not the possible range.
	Sensitive to outliers
	Different values could be mapped to the same value.
	Use percentiles instead.
	Use a calibration dataset – Kullback-Leibler divergence.
•	Post train quantisation.
o	Dynamic
	Convert weights ahead of time.
	Resale activations on the fly
o	Static
	Convert weights ahead of time.
	Use a calibration dataset to convert activations ahead of time
•	Quantisation aware training
o	Resource expensive on large LLM’s
•	Dequantization process performed at inference time
