# ETL - Financial Data Clean-Up Script

This is an ETL script which reads data from three financial tables: clients, transfers and counties. Set size: over 1 million transfers.

Following checks, validations and corrections are made, in order to prepare data for either financial analysis or machine learning processing:

- check if all IDs are unique
- investigate duplicates
- remove duplicates
- check for missing values in 'account_id'
- homogeneity check as a rationale to delete rows with missing values
- check if combination of 'transfer_id' and 'account_id' is unique
- check if any client has more than one account and if any account belongs to more than one person
- check if all values in 'gender' columns are either 'f' or 'm'
- convert 'date' column to pandas' `datetime` format
- check for birthdate outliers
- check if all values in 'set_split' column are either 'test' or 'train'
- check for nulls in the 'loan' column
- convert 'NaN's to zeros
- convert 'loan' data type from `float` to `int`
- remove any unneded columns
- check if there are any transfers with zero value
- check if there are any transfers with negative value
- check for outliers in transfers 'amount' and transfers 'balance'

INTERESTING PROBLEMS

The most interesting problems which arose in this set were:
- 5000 missing 'account_id' values in 'transfers' table
- 180000 missing tags in 'OPERATION' column of the 'transfers' table

These problems were solves using homogenuity test and applying domain knowledge about credit/debit convention in financial transfers data. Details of these solutions can be found in the following paragraphs of the jupiter notebook:
- 'CHECK FOR MISSING VALUES IN ACCOUNT_ID'
- 'CHECK IF THERE ARE ANY 'NaN' VALUES IN ANY OTHER COLUMN'

HOW USE THIS REPO?

In order to use this repo on your own machine, you will need:
- `jupiter notebooks`
- `numpy`
- `pandas`