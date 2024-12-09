import requests
import json

url = "https://cdn.ituring.ir/ex/users.json"

class Fetcher:
    def __init__(self,r,s):
        super().__init__()
        req = requests.get(url)
        
    
    def nerds(self,r,s):
        self.r=r
        self.s=s

        r:list = requests.get(url).json()
        r = filter(lambda r: r['score'] >=18.5,r)
        r=list(r)
        r.sort(key=lambda r: r['score'])
        r=map(lambda r: ({'name':r['name']+" "+r['last_name'],'score':r['score']}),r)
        r=list(r)
        s = json.dumps(r,indent=2)
        ###
        x=0
        for i in r:
            print(r[x]["name"] , r[x]['score'])
            x+=1
    def sultans(self,r,s):
        r:list = requests.get(url).json()
        r = filter(lambda r: r['score'] >=18.5,r)
        r=list(r)
        r.sort(key=lambda r: r['score'])
        r=map(lambda r: ({'name':r['name']+" "+r['last_name'],'score':r['score']}),r)
        r=list(r)
        s = json.dumps(r,indent=2)
        ##
        s_tuple=tuple(r)
        print(s_tuple)
    
    def mean(self,r,s):
        r:list = requests.get(url).json()
        r = filter(lambda r: r['score'] >=18.5,r)
        r=list(r)
        r.sort(key=lambda r: r['score'])
        r=map(lambda r: ({'name':r['name']+" "+r['last_name'],'score':r['score']}),r)
        r=list(r)
        s = json.dumps(r,indent=2)
        ###
        x=0
        sum_avg=0
        for i in r:
            sum_avg+=r[x]['score']
            x+=1
        avg = sum_avg/len(r)
        print(f"{avg}")
        print(f"-------{len(r)}")
    
    def __get_students(self,r,s):
        r:list = requests.get(url).json()
        r = filter(lambda r: r['name']+r['last_name'],r)
        r=list(r)
        r.sort(key=lambda r: r['score'])
        r=map(lambda r: ({'name':r['name']+" "+r['last_name'],'score':r['score']}),r)
        r=list(r)
        s = json.dumps(r,indent=2)
        ###
        x=0
        for i in r:
            print(r[x]['name'])
            x+=1
