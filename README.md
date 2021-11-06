awsstudent:~/environment $ cd lab_folder/
awsstudent:~/environment/lab_folder (main) $ python CheckTableStatus.py movies
Status of table is ACTIVE
Total time: 0.1383075714111328 sec

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

