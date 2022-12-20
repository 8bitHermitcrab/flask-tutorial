# flask-tutorial
[Flask 공식 문서 tutorial](https://flask.palletsprojects.com/en/2.2.x/tutorial/) 파일 모음

---

# Production 배포


## 빌드

`Build`
소스 코드 파일을 독립 소프트웨어 가공물(standalone)로 변환.

```
pip install wheel
```

```
python setup.py bdist_wheel
```

```
pip install flaskr-1.0.0-py3-none-any.whl
```

```
flask --app flaskr init-db
```


## 비밀키 만들기

```
python -c 'import secrets; print(secrets.token_hex())'

> '192b9bdd22ab9ed4d12e236c78afcb9a393ec15f71bbf5dc987d54727823bcbf'
```

`venv/var/flaskr-instance/config.py` 에 다음 비밀키 값 입력.
```
SECRET_KEY = '192b9bdd22ab9ed4d12e236c78afcb9a393ec15f71bbf5dc987d54727823bcbf'
```

## 배포 서버에 올리기

```
pip install waitress
```

```
waitress-serve --call 'flaskr:create_app'

> Serving on http://0.0.0.0:8080
```