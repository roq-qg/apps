
# Datasets

There are three synthetic datasets that were generated with different criteria. The difference between the datasets are the levels of noise, and mislabeled data. Dataset1 does not have noise added and does not have any mislabeling. Dataset2 has noise added. Dataset3 has noise added and mislabeling. 

ds1: No Noise

ds2: Noise

ds3: Noise + Mislabeling

### Interpreting the Data


```python
Each patient has a mutation count associated with the gene, location and type of mutation in the lefthand columns. If a cell contains a number such as '103' and the left-hand column contains Gene:2, Location 200, Type: SNP, then this means that there were 103 SNP mutations found at Gene 2, genomic location 200. 
There are also data files containining clinical and lab data with information about the patient and details about the extraction as well as whether the patient is diagnosed as a cancer or control

```
