# introduction-to-couchdb-python
a breif instructions on hoe to use couchdb(or any nosql) with a python framework

# Connecting your database
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
          
  # writing to your database
  doc_id, doc_rev = db.save({'key': 'value'})
  
  # retriving document by id
  db.get(doc_id)
  doc = db[doc_id]
  
  # deleting a  doc
  db.delete(doc)
  
  # saving a doc
  db.delete(doc)
  
  # update a doc
the only way to do it is to delete privious doc and add new doc with the updated data with same id
doc=db[id]
doc_updated={new data}
db.delete(doc)
db.save(doc-updated)
db["my_document_id"] = {'key': doc}

