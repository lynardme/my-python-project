## Create environment in Anaconda
```
conda create --name flask_api --file flask_api_reqs.txt
```

## Run the flask
```
python app.py
* Running on http://127.0.0.1:5000/
* Restarting with reloader
```
## Invoke from curl
To get all task
```
curl http://localhost:5000/todo/api/v1.0/tasks
```
To get single task
```
curl http://localhost:5000/todo/api/v1.0/tasks/2
```
To insert a new task
```
curl -i -H "Content-Type: application/json" -X POST -d '{"title":"Read a book"}' http://localhost:5000/todo/api/v1.0/tasks
```
To update a task
```
curl -i -H "Content-Type: application/json" -X PUT -d '{"done":true}' http://localhost:5000/todo/api/v1.0/tasks/2
```
To delete a task
```
curl -i -X DELETE http://localhost:5000/todo/api/v1.0/tasks/2
```
To invoke a secure function
```
curl -u lynard:python -i http://localhost:5000/todo/api/v1.0/tasks/secure
```
## Using Postman
![post method](https://github.com/lynardme/my-python-project/blob/master/img/001-post.png)
