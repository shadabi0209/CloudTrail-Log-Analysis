# CloudTrail-Log-Analysis
Converts CloudTrail logs stored in S3 buckets from json format to query optimized dataset.

The JSON log files stored in multiple subfolders of S3 have struct data type which are converted into single Apache Parquet file format and stored back on S3 for further analysis and visualization. S3-triggered Lambda functions are used to transform the folder structure and store the files in single folder of a new S3 bucket. Code from fileCollate.py is added to the Lambda function and is used for the transformation.
The transformed files are then converted to parquet format and stored back in S3. Upload fileConvert.py to the S3 and add it to the Glue job for the file conversion.

Prerequisite: Lambda and Glue should have roles and inline policies to access and modify S3 buckets.
