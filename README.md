# Postman API Documentation

## 1. What is Postman?
Postman is a collaboration platform for API development. It allows you to:
- Send API requests (GET, POST, PUT, DELETE, etc.).
- Test APIs and debug responses.
- Automate workflows and integrate with CI/CD pipelines.
- Collaborate with teams using shared collections.

## 2. Sending Your First Request
Let’s start with a **GET request** to fetch data from a free API.  

### Example: Fetch a Todo
1. Open Postman and click **New Request**.
2. Set the method to **GET**.
3. Enter the URL: `https://jsonplaceholder.typicode.com/todos/1`.
4. Click **Send**.  

**Response**:
```json
{
  "userId": 1,
  "id": 1,
  "title": "delectus aut autem",
  "completed": false
}
```
*Status Code: `200 OK` (Success!)*

## 3. Understanding HTTP Methods
| Method  | Use Case                     | Example URL                          |
|---------|------------------------------|---------------------------------------|
| `GET`   | Retrieve data                | `GET /todos/1`                        |
| `POST`  | Create new data              | `POST /todos`                         |
| `PUT`   | Update existing data         | `PUT /todos/1`                        |
| `DELETE`| Delete data                  | `DELETE /todos/1`                     |

