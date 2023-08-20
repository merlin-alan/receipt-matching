# Receipt Matching Data Science Challenge

Our customers want the ability to automatically match receipt images to the associated transaction within the tide app. For this we have used an external supplier to extract data from the receipt images, (for example, the date of the transaction on the receipt, the name of the merchant, the transaction amount). Each of the data items returned from the external supplier was compared against the same data from the tide transaction, and a ‘transaction-receipt’ matching vector was created. The elements of the matching vector will be produced in different ways depending on the underlying data types being matched (for example for strings it may be a fuzzy matching score, for transaction amounts it may be an absolute difference of the amounts on the receipt and the transaction, for dates/times it may be a time delta, some may be discretized measures of confidence).
Since the data extraction from the receipt image is not always perfect (for example the incorrect string is extracted for the merchant name) we want to build a model to learn which matching features are the most successful. The ultimate goal is to match a single receipt to the correct transaction given a number of possible transactions however, given real world considerations, we want to sort the possible transactions for a given receipt in order of likelihood of being the correct transaction. So in the app when the customer takes a picture of a receipt, the app provides a list of transactions likely to match the receipt, with the one we think is correct at the top of the list. ‘Success’ in this context means that the correct transaction for the given receipt is at the top of the list, (note, if the correct matching is not in the data for a given receipt ‘success’ is not possible).


### model_and_report.ipynb 
The jupyter notebook contains 
- data exploration
- data summary
- ML modeling steps
- prediction steps
- model summary

### python modules required

- hyperopt==0.2.7
- imbalanced-learn==0.11.0
- imblearn==0.0
- matplotlib==3.7.2
- matplotlib-inline==0.1.6
- numpy==1.24.3
- pandas==2.0.0
- scikit-learn==1.3.0
- scipy==1.11.2
- seaborn==0.12.2
- sklearn==0.0

