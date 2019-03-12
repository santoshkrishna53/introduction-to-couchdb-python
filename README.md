# introduction-to-couchdb-python
a breif instructions on hoe to use couchdb(or any nosql) with a python framework

# accessing your Couch Database
couch = couchdb.Server('http://your_username:password@localhost:5984')

# selecting a database
we can select the database we want to operate as 
db=couch['passenger']
ie, here the database passenger is selected

# selecting views
db.view('_design/pass/_view/new-view')

# user authenticating 
for item in db.view('_design/pass/_view/new-view'):
    if(item.key == username):
          if(item.value['password']==password):
                            print('successfully logined')
           else:
                print("wrong password")
     else:
          print("username does not exists")
          
