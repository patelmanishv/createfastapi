## Code to access the API -
```python
import requests

# Base URL of your FastAPI server (adjust if running on a different machine)
BASE_URL = "http://127.0.0.1:8000"
# or live website - https://fastapi-75jc.onrender.com/

# 1. GET the homepage
response = requests.get(f"{BASE_URL}/")
print("Home page:", response.text)

# 2. GET all items
response = requests.get(f"{BASE_URL}/items")
print("All items:", response.json())

# 3. POST a new item
new_item = {
    "name": "Laptop",
    "description": "Gaming laptop",
    "price": 1500,
    "tax": 100
}
response = requests.post(f"{BASE_URL}/items/", json=new_item)
print("Created item:", response.json())

# 4. GET a specific item by ID (e.g., item 0)
response = requests.get(f"{BASE_URL}/items/0")
print("Item 0:", response.json())
```
