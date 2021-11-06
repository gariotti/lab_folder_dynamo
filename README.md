awsstudent:~/environment $ sudo pip install boto3
Collecting boto3
  Downloading https://files.pythonhosted.org/packages/5e/e1/156846b09fca21b9b164c54200011e3bd17f29187cbfc6903a8e0281a304/boto3-1.19.12-py3-none-any.whl (131kB)
    100% |████████████████████████████████| 133kB 4.8MB/s 
Requirement already satisfied: s3transfer<0.6.0,>=0.5.0 in /usr/local/lib/python3.6/site-packages (from boto3)
Collecting botocore<1.23.0,>=1.22.12 (from boto3)
  Downloading https://files.pythonhosted.org/packages/6a/73/552b27e3a1b4f83630907c4958be78e9d4c906e73efd554ebd5e21cb1692/botocore-1.22.12-py3-none-any.whl (8.1MB)
    100% |████████████████████████████████| 8.1MB 166kB/s 
Requirement already satisfied: jmespath<1.0.0,>=0.7.1 in /usr/local/lib/python3.6/site-packages (from boto3)
Requirement already satisfied: urllib3<1.27,>=1.25.4 in /usr/local/lib/python3.6/site-packages (from botocore<1.23.0,>=1.22.12->boto3)
Requirement already satisfied: python-dateutil<3.0.0,>=2.1 in /usr/local/lib/python3.6/site-packages (from botocore<1.23.0,>=1.22.12->boto3)
Requirement already satisfied: six>=1.5 in /usr/local/lib/python3.6/site-packages (from python-dateutil<3.0.0,>=2.1->botocore<1.23.0,>=1.22.12->boto3)
Installing collected packages: botocore, boto3
  Found existing installation: botocore 1.22.7
    Uninstalling botocore-1.22.7:
      Successfully uninstalled botocore-1.22.7
Successfully installed boto3-1.19.12 botocore-1.22.12
You are using pip version 9.0.3, however version 21.3.1 is available.
You should consider upgrading via the 'pip install --upgrade pip' command.
awsstudent:~/environment $ cd lab_folder/
awsstudent:~/environment/lab_folder (main) $ python CheckTableStatus.py movies
Status of table is ACTIVE
Total time: 0.1383075714111328 sec
awsstudent:~/environment/lab_folder (main) $ python MoviesScanYG.py 1980 Comedy
python: can't open file 'MoviesScanYG.py': [Errno 2] No such file or directory
awsstudent:~/environment/lab_folder (main) $ ls
CheckTableStatus.py  DeleteMoviesTable.py  lab_reference_scripts  moviedata.json  MoviesScanYG  PopulateDatabase.py
awsstudent:~/environment/lab_folder (main) $ mv MoviesScanYG MoviesScanYG.py
awsstudent:~/environment/lab_folder (main) $ ls
CheckTableStatus.py  DeleteMoviesTable.py  lab_reference_scripts  moviedata.json  MoviesScanYG.py  PopulateDatabase.py
awsstudent:~/environment/lab_folder (main) $ python MoviesScanYG.py 1980 Comedy
Count is  4
ScannedCount is  44599
Total time: 0.7012522220611572 sec
awsstudent:~/environment/lab_folder (main) $ python MoviesQueryYG.py 1980 Comedy
Count is  4
ScannedCount is  442
Total time: 0.15620136260986328 sec
awsstudent:~/environment/lab_folder (main) $ python DeleteMoviesTable.py
{'TableDescription': {'TableName': 'movies', 'TableStatus': 'DELETING', 'ProvisionedThroughput': {'NumberOfDecreasesToday': 0, 'ReadCapacityUnits': 1000, 'WriteCapacityUnits': 1000}, 'TableSizeBytes': 0, 'ItemCount': 0, 'TableArn': 'arn:aws:dynamodb:us-west-2:741851736632:table/movies', 'TableId': '102b0895-297a-4c6e-8163-15c178a28403'}, 'ResponseMetadata': {'RequestId': 'A04PSDMDJ3D1HKNPE3EHM76C8FVV4KQNSO5AEMVJF66Q9ASUAAJG', 'HTTPStatusCode': 200, 'HTTPHeaders': {'server': 'Server', 'date': 'Sat, 06 Nov 2021 16:09:57 GMT', 'content-type': 'application/x-amz-json-1.0', 'content-length': '320', 'connection': 'keep-alive', 'x-amzn-requestid': 'A04PSDMDJ3D1HKNPE3EHM76C8FVV4KQNSO5AEMVJF66Q9ASUAAJG', 'x-amz-crc32': '562460360'}, 'RetryAttempts': 0}}
awsstudent:~/environment/lab_folder (main) $ python CreateMovieswithGenreLSI.py
Table status: CREATING
awsstudent:~/environment/lab_folder (main) $ python CheckTableStatus.py movies
Status of table is ACTIVE
Total time: 0.11398530006408691 sec
awsstudent:~/environment/lab_folder (main) $ python PopulateDatabase.py moviedata.json
Total time: 94.17501449584961 sec
awsstudent:~/environment/lab_folder (main) $ python MoviesScanYG.py 1980 Comedy
Count is  4
ScannedCount is  44599
Total time: 0.8079128265380859 sec
awsstudent:~/environment/lab_folder (main) $ python MoviesScanYG.py 1980 Comedy
Count is  4
ScannedCount is  44599
Total time: 0.7323410511016846 sec
awsstudent:~/environment/lab_folder (main) $ python MoviesScanYG.py 1980 Comedy
Count is  4
ScannedCount is  44599
Total time: 0.8041057586669922 sec
awsstudent:~/environment/lab_folder (main) $ python MoviesQueryWithLSIYG.py 1980 Comedy
Count is  4
ScannedCount is  4
Total time: 0.15010571479797363 sec
awsstudent:~/environment/lab_folder (main) $ python CreateGenreGSI.py
Still creating...
Still creating...
Still creating...
Still creating...
Still creating...
Still creating...
Still creating...
Still creating...
Still creating...
Still creating...
Still creating...
Still creating...
Still creating...
Still creating...
Still creating...
Still creating...
Total time: 160.6349425315857 sec
awsstudent:~/environment/lab_folder (main) $ python QueryByGenre.py Comedy
Count is  729
ScannedCount is  729
Total time: 0.2509133815765381 sec
awsstudent:~/environment/lab_folder (main) $ python ScanByGenre.py Comedy
Count is  729
ScannedCount is  44599
Total time: 0.837371826171875 sec
awsstudent:~/environment/lab_folder (main) $ ls
CheckTableStatus.py    CreateGenreGSI.py            DeleteGSI.py          lab_reference_scripts  MoviesQueryWithLSIYG.py  MoviesScanYG.py      QueryByGenreAddRatingRange.py  ScanByGenre.py
CreateAttributeGSI.py  CreateMovieswithGenreLSI.py  DeleteMoviesTable.py  moviedata.json         MoviesQueryYG.py         PopulateDatabase.py  QueryByGenre.py
awsstudent:~/environment/lab_folder (main) $ 
