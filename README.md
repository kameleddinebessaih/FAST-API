# FAST-API
Why did we choose FAST API over Flask and Django for our RESTFUL Micro-services
According to techempower benchmark Fast API beats every other framework when it comes to performance where Flask and Django are no where near the Top 10.
Development Speed
-Here we are only concerned about a RESTful Micro-service, which would have the following as basic requirements.
-Exposes REST endpoint/s.
-OpenAPI(Swagger) documentation.
-Database connection (Optional).


Creating a REST API endpoint with Fast API and Open API takes less than a 5 minutes.


import uvicorn
from fastapi import FastAPI
from pydantic import BaseModel


class User(BaseModel):
    first_name: str
    last_name: str = None
    age: int


app = FastAPI()


@app.post("/user/", response_model=User)
async def create_user(user: User):
    return user


if __name__ == "__main__":
    uvicorn.run(app, host="0.0.0.0", port=8000)
    
    
    One Last Thing

    
    @app.post("/user/", response_model=User)
async def create_user(user: User):
    return user
