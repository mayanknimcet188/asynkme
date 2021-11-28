<div align="center">
  <h3>Asynkme</h3>
 
### Features :sparkles:
- Application container
- Lifecycle hooks
- Middlewares
- Routing
- Request/Response helpers

### Overview

To give you a first grasp, here is simple example of app made with `sketch`

`app.py`

```python3
import asyncio

from sketch import Application, Response, run_app

loop = asyncio.get_event_loop()


async def handler(request):
    username = request.match_info["username"]
    return Response(f"Hello, {username}")

app = Application(loop)

app.router.add_route("GET", "/{username}", handler)

if __name__ == "__main__":
    run_app(app, port=8080)

```

```shell
$ python app.py
>> Started server on 127.0.0.1:8080
```

```shell
$ curl http://127.0.0.1:8080/oleh
>> Hello, oleh
```

### License

MIT
