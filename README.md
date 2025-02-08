# Postman API Documentation

## 1. What is Postman?
Postman is an HTTP client that simplifies the process of creating, sending, and testing API requests. Postman is a collaboration platform for API development. It allows you to:
- Send API requests (GET, POST, PUT, DELETE, etc.).
- Test APIs and debug responses.
- Automate workflows and integrate with CI/CD pipelines.
- Collaborate with teams using shared collections.

## 2. Sending Your First Request
Let’s start with a **GET request** to fetch data from a free API.  

### Example: Fetch a Todo
1. Open Postman and click **New Request**.
2. Set the request method to **GET**.
3. Enter the API endpoint URL (e.g., `https://api.postman.com/jobs`).
4. Click **Send** to submit the request. 
Example:
```plaintext
GET https://api.postman.com/jobs
```

## 3. Understanding HTTP Methods
| Method  | Use Case                     | Example URL                          |
|---------|------------------------------|---------------------------------------|
| `GET`   | Retrieve data                | `GET /todos/1`                        |
| `POST`  | Create new data              | `POST /todos`                         |
| `PUT`   | Update existing data         | `PUT /todos/1`                        |
| `DELETE`| Delete data                  | `DELETE /todos/1`                     |

## 4. Working with Query Parameters
Query parameters allow you to filter or customize the data returned by the API. For example:
- **Location**: Filter jobs by location (e.g., `location=San Francisco`).
- **Keyword Search**: Use the `q` parameter to search for specific keywords (e.g., `q=sales`).

### Steps to Add Query Parameters:
1. Go to the **Params** tab in Postman.
2. Add key-value pairs for the parameters (e.g., `location=San Francisco`).
3. Postman automatically appends these parameters to the URL.
4. Click **Send** to submit the request.

Example:
```plaintext
GET https://api.postman.com/jobs?location=San Francisco&q=sales
```

## 5. Inspecting the Response
After sending a request, Postman displays the response in the **Response** section. Key details to inspect:
- **Status Code**: Indicates the success or failure of the request (e.g., `200 OK`).
- **Response Body**: Contains the data returned by the API, typically in **JSON** format.
- **Headers**: Metadata about the response.

Example Response:
```json
{
  "jobs": [
    {
      "id": 1,
      "title": "Software Engineer",
      "location": "San Francisco"
    }
  ]
}
```



