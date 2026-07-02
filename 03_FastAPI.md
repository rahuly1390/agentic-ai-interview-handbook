# ⚡ FastAPI Interview Refresher (High Yield)

> Focus: What you actually need to recall in interviews + production usage

---

# 1. What is FastAPI?

FastAPI is a modern Python web framework for building APIs.

### Why it's used in AI/Agentic systems:
- Fast inference APIs for LLM apps
- RAG backend services
- Agent orchestration APIs
- Tool calling endpoints

---

# 2. Key Idea (Interview One-Liner)

FastAPI = ASGI framework + Pydantic validation + async support

---

# 3. ASGI vs WSGI (VERY IMPORTANT)

| Feature | WSGI (Flask/Django old) | ASGI (FastAPI) |
|--------|------------------------|----------------|
| Concurrency | Sync | Async |
| Performance | Slower | High performance |
| WebSockets | Not supported | Supported |
| AI apps | Not ideal | Ideal |

---

# 4. First API (Must Know)

```python
from fastapi import FastAPI

app = FastAPI()

@app.get("/")
def home():
    return {"message": "Hello World"}
```

---

# 5. Path & Query Params

### Path
```python
@app.get("/user/{user_id}")
def get_user(user_id: int):
    return {"user_id": user_id}
```

### Query
```python
@app.get("/search")
def search(q: str, limit: int = 10):
    return {"q": q, "limit": limit}
```

---

# 6. Request Body (Pydantic)

```python
from pydantic import BaseModel

class User(BaseModel):
    name: str
    age: int

@app.post("/user")
def create_user(user: User):
    return user
```

---

# 7. Dependency Injection (VERY IMPORTANT)

Used in auth, DB sessions, LLM clients.

```python
from fastapi import Depends

def common_dep():
    return {"role": "admin"}

@app.get("/items")
def get_items(dep=Depends(common_dep)):
    return dep
```

---

# 8. Routers (Project Structure)

```python
from fastapi import APIRouter

router = APIRouter()

@router.get("/items")
def items():
    return {"items": []}
```

---

# 9. Middleware

Used for logging, auth, tracing.

```python
@app.middleware("http")
async def log_requests(request, call_next):
    response = await call_next(request)
    return response
```

---

# 10. Async Support (CRITICAL)

```python
@app.get("/async")
async def async_func():
    return {"status": "async"}
```

---

# 11. Background Tasks

Used in email sending, agent execution.

```python
from fastapi import BackgroundTasks

def task():
    print("Running task")

@app.post("/run")
def run(bg: BackgroundTasks):
    bg.add_task(task)
    return {"status": "queued"}
```

---

# 12. Authentication (JWT Concept)

Must know in interviews:
- OAuth2
- Bearer token
- JWT structure

---

# 13. WebSockets (for agents/chatbots)

Used in:
- ChatGPT-like apps
- streaming LLM tokens

```python
@app.websocket("/ws")
async def websocket(ws):
    await ws.accept()
    await ws.send_text("Hello")
```

---

# 14. Exception Handling

```python
from fastapi import HTTPException

@app.get("/item/{id}")
def get_item(id: int):
    if id < 0:
        raise HTTPException(status_code=400, detail="Invalid ID")
```

---

# 15. Performance Tips (INTERVIEW FAVORITE)

- Use async for I/O heavy tasks
- Avoid blocking code
- Use connection pooling
- Use background tasks for heavy work
- Use caching (Redis)
- Use Uvicorn workers

---

# 16. Deployment Stack

```
FastAPI → Uvicorn → Gunicorn → Docker → Cloud
```

---

# 17. Most Asked Interview Questions

### Q1. Why FastAPI over Flask?
- Async support
- Pydantic validation
- Fast performance
- Auto docs (Swagger)

---

### Q2. What is ASGI?
Async server gateway interface enabling async Python apps.

---

### Q3. What is Dependency Injection?
A pattern to inject reusable logic like DB/session/auth.

---

### Q4. FastAPI is sync or async?
Both, but optimized for async.

---

### Q5. Why is FastAPI good for Agentic AI?
- Fast tool execution APIs
- LLM orchestration endpoints
- Streaming responses for agents
- Easy integration with LangChain/LangGraph

---

# 18. Cheat Sheet

- GET → Read
- POST → Create
- PUT → Update
- DELETE → Remove
- Depends → DI
- Pydantic → Validation
- Middleware → Request processing
- BackgroundTasks → async jobs
- WebSockets → streaming

---

# 19. Agentic AI Connection (VERY IMPORTANT)

FastAPI is used in Agentic AI for:

- Tool APIs (calculator, search, DB)
- LLM gateway endpoints
- Multi-agent orchestration APIs
- Streaming token responses
- RAG query endpoints

# 🧠 Pydantic Interview Refresher (High Yield)

---

# 1. What is Pydantic?

Pydantic is a Python library for:
- Data validation
- Serialization
- Type enforcement

Used heavily in:
- FastAPI
- LLM pipelines
- Agent frameworks

---

# 2. Why Pydantic? (Interview Answer)

- Ensures data correctness
- Automatic validation
- Type safety
- Clean API contracts
- Works with FastAPI seamlessly

---

# 3. Basic Model

```python
from pydantic import BaseModel

class User(BaseModel):
    name: str
    age: int
```

---

# 4. Validation in Action

```python
User(name="Alice", age="25")
```

Auto converts `"25"` → `int`

---

# 5. Field Constraints

```python
from pydantic import BaseModel, Field

class User(BaseModel):
    name: str = Field(min_length=3, max_length=50)
    age: int = Field(gt=0, lt=120)
```

---

# 6. Nested Models (VERY IMPORTANT)

```python
class Address(BaseModel):
    city: str
    pin: int

class User(BaseModel):
    name: str
    address: Address
```

---

# 7. Validators

```python
from pydantic import BaseModel, field_validator

class User(BaseModel):
    name: str

    @field_validator("name")
    def check_name(cls, v):
        if len(v) < 3:
            raise ValueError("Name too short")
        return v
```

---

# 8. model_dump (Serialization)

```python
user.model_dump()
```

Converts model → dict

---

# 9. model_validate (New Pydantic v2)

```python
User.model_validate(data)
```

---

# 10. Settings Management

Used in production apps

```python
from pydantic import BaseSettings

class Settings(BaseSettings):
    api_key: str
```

---

# 11. Why Pydantic in FastAPI?

- Request validation
- Response shaping
- Auto schema generation (OpenAPI)

---

# 12. Common Interview Questions

### Q1. Why Pydantic instead of dict?
- Validation
- Type safety
- Error handling

---

### Q2. What happens if validation fails?
FastAPI returns 422 error automatically.

---

### Q3. Pydantic v1 vs v2?
- v2 faster (Rust core)
- `model_dump` replaces `dict()`
- `model_validate` replaces constructor logic

---

### Q4. What is schema generation?
Automatic OpenAPI docs creation from models.

---

# 13. Common Mistakes

- Using wrong types
- Missing validators
- Overcomplicated models
- Not using nested models properly

---

# 14. Cheat Sheet

- BaseModel → schema
- Field → constraints
- field_validator → custom logic
- model_dump → dict
- model_validate → parse input
- Nested models → structured data

---

# 15. Agentic AI Connection

Pydantic is used in:

- Tool input/output validation
- LLM structured outputs
- Agent memory schemas
- API contracts between agents
- RAG query validation
