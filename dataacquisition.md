ky="AIzaSyB6pVZzXOUv0aD1JdFX89keGAoGjyNRkGw"
#api key
from apiclient.discovery import build
#Google APIs Discovery Service allows you to do all of the above by exposing machine readable metadata
src=build("customsearch",'v1',developerKey=ky).cse()
storage=[]
for i in range(1,100,10):
 res=src.list(q='storage cabinets', cx='e1f68663ba64e4835',searchType='image', start=i).execute()
 storage += res['items']
 for item in storage:
 print(item['title'],item['link'])
 prom=[]
 for i in range(1,100,10):
 res=src.list(q='totes', cx='e1f68663ba64e4835',searchType='image', start=i).execute()
 prom += res['items']
 for item in storage:
 print(item['title'],item['link'])
