

# Dataset

The dataset consists of a large number of samples from https://portal.gdc.cancer.gov/  and each sample consists of a large number of absolute expression values of microRNAs (miRNAs). miRNAs are small non-coding RNA molecules that are involved in the silencing or down-regulation of a variety of genes, including oncogenic and tumor suppressor genes. In general, a high expression of a miRNA indicates a higher concentration and thus a higher regulatory impact. Each sample is also labeled with a clinical diagnosis. In total, there are 5 different cancer entities in the dataset.


### Interpreting the Data


```python
The "miRNA_counts.csv" file contains the data described above. Each patient has a count associated with the expression of miRNA. Each column in the file except for the first represents a feature, "Reads per million miRNA mapped", and each row represents a patient/sample. The data is already normalized. There is also a data file containining clinical information labeled "clinical.csv" about each patient such as details about their cancer type, diagnosis, and tumor. Finally, there is a data dictionary labeled "data_dictionary.csv" which describes all the data in the clinical file. 

```



```python

```
