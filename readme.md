## Project Sparkify 2th
The project about what people listen in an app called Sparkify continues with data modeling using Apache Cassandra and Pyhon. The purpose of the project is to see the songs which have the biggest interest.

## Requirements

1. Give me the artist, song title and song's length in the music app history that was heard during sessionId = 338, and itemInSession = 4
2. Give me only the following: name of artist, song (sorted by itemInSession) and user (first and last name) for userid = 10, sessionid = 182
3. Give me every user name (first and last) in my music app history who listened to the song 'All Hands Against His Own'

## DataBase

Apache Cassandra is a non-relational distributed database and the data will be prelucrated as csv file using Python.
It's a good system to store big data
Using a good representation of clusters, from 6821 rows can return only few rows or only 1 without joins.
Only one user listened 'All Hands Against His Own'"

```
select first_name, last_name from users where song_title = 'All Hands Against His Own'
```
Result Sara Johnson 

## Python
```python
import pandas as pd
import cassandra
import re
import os
import glob
import numpy as np
import json
import csv
```

## Datasets

event_data contains the csv data partitioned by date about 6821 rows
```python 
#number of rows in csv file 
with open('event_datafile_new.csv', 'r', encoding = 'utf8') as f:
    print(sum(1 for line in f))    
```     

Features in project:
->artist
->firstName of user
->gender of user
->item number in session
->last name of user
->length of the song
->level (paid or free song)
->location of the user
->sessionId
->song title
->userId

## Tables

songs:
artist| song_title | length | level | session_id | item_in_session
song_session:
artist | song_title | first_name_user | last_name_user | user_id | session_id | item_in_session
users:
first_name | last_name | song_title 

## Solutions 
1) 1 solution
2) 4 solutions 
3) 1 solution
