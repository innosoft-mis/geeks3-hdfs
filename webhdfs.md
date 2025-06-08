```python
# List a Directory 

url = "http://localhost:9870/webhdfs/v1/user/student?op=LISTSTATUS&user.name=student"
r = requests.get(url)
obj = json.loads(r.content)
print(json.dumps(obj, indent=2))
```

```python
# Make a Directory

url = "http://localhost:9870/webhdfs/v1/user/student/ncd_screen?op=MKDIRS&user.name=student"
r = requests.put(url)
r.status_code
```

```python
# CREATE A FILE

url = "http://localhost:9870/webhdfs/v1/user/student/ncd_screen/data.csv?op=CREATE&user.name=student&overwrite=true"
r = requests.put(url, data=open('ncd_screen_001.csv', 'r').read())
r.status_code
```

```python
# FILE STATUS

url = "http://localhost:9870/webhdfs/v1/user/student/ncd_screen/data.csv?op=GETFILESTATUS&user.name=student"
r = requests.get(url)
obj = json.loads(r.content)
print(json.dumps(obj, indent=2))
```

```python
# APPEND FILE

url = "http://localhost:9870/webhdfs/v1/user/student/ncd_screen/data.csv?op=APPEND&user.name=student"
r = requests.post(url, data=open("ncd_screen_002.csv","r").read())
r.status_code
```
