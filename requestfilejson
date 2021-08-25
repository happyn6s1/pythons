import requests,json
l=[]
'''
for i in range(47,0,-1):
    url="https://tryhackme.com/api/hacktivities?page="+str(i)+"&free=all&order=newest&difficulty=all&type=all"
    resp=requests.get(url)
    data=resp.json()["rooms"]
    l=l+data
'''
atts=["code",
    "users",
    "userCompleted",
    "image",
    "title",
    "created",
    "difficulty",
    "creator",
    "headerImage",
    "published",
    "upVotes",
    "freeToUse",
    "type",
    "description"]
#with open("rooms.json","w") as rfile:
#    json.dump(l,rfile)
l=[]
with open("rooms.json","r") as rfile:
    l=json.load(rfile)
print(type(l))
with open("rooms.csv","w") as csv:
    for room in l:
        print(room["code"])
        rurl="https://tryhackme.com/room/"+room["code"]
        line=[rurl]
        tags=[]
        for t in room["tags"]:
            tags.append(t)
        line.append(";".join(tags))
        for key in atts:
            if key in room:
                tt=room[key]
                #print(tt,type(tt),type(u""))
                if type(tt)!=type(u""):
                    print(tt)
                    tt=str(tt)

                line.append(tt)
            else:
                line.append("--")
        ll=u",".join(line)+u"\n"
        csv.write(ll.encode("utf8"))
