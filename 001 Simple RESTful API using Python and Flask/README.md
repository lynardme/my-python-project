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
To update a task
```
curl -i -H "Content-Type: application/json" -X PUT -d '{"done":true}' http://localhost:5000/todo/api/v1.0/tasks/2
```
To delete a task
```
curl -i -X DELETE http://localhost:5000/todo/api/v1.0/tasks/2
```
To get public version of uri
```python
from flask import url_for

def make_public_task(task):
    new_task = {}
    for field in task:
        if field == 'id':
            new_task['uri'] = url_for('get_task', task_id=task['id'], _external=True)
        else:
            new_task[field] = task[field]
    return new_task
```
```python
@app.route('/todo/api/v1.0/tasks', methods=['GET'])
def get_tasks():
    return jsonify({'tasks': [make_public_task(task) for task in tasks]})
```
## Postman
![post method](https://github.com/lynardme/my-python-project/blob/master/img/001-post.png)
