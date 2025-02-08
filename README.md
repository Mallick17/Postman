# Postman API Documentation

## 1. What is Postman?
Postman is a widely-used tool for API testing, enabling developers to create, test, share, and document APIs efficiently. Postman is a collaboration platform for API development. It allows you to:
- **Build, test, and modify APIs** without writing HTTP client network code.
- **Create test suites** called collections.
- **Make various HTTP requests** such as GET, POST, PUT, PATCH.
- **Convert APIs to code** in languages like JavaScript and Python.
- 
### Key Terminologies
- **API (Application Programming Interface):** Software that enables two applications to communicate.
- **HTTP (Hypertext Transfer Protocol):** Rules for transmitting data on the web, including text, images, and multimedia.

### Why Use Postman?
Postman is favored for its user-friendly tools and convenience. Here are some key reasons to use Postman:

1. **Accessibility:** Use Postman anywhere by logging into your account after installation.
2. **Collections:** Organize API calls into collections with multiple requests and subfolders.
3. **Test Development:** Add checkpoints to verify successful HTTP responses.
4. **Automation Testing:** Use Collection Runner or Newman for repeated tests, saving time.
5. **Creating Environments:** Design multiple environments to reduce test replication.
6. **Debugging:** Utilize the Postman console to track retrieved data.
7. **Collaboration:** Share files by importing/exporting collections and environments.
8. **Continuous Integration:** Supports continuous integration processes.

## Postman Navigation
![postman-ui-v11 26](https://github.com/user-attachments/assets/c7e81d08-bbcd-4661-8df3-f5af9bc63a7d)


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

## 6. Saving Requests to Collections
To save and organize requests:
1. Click the **Save** button after creating a request.
2. Add the request to a **Collection** (a group of related requests).
3. Name the collection (e.g., `Postman Jobs API`).
4. Provide a name for the request (e.g., `Get Jobs in San Francisco`).

### Benefits of Collections:
- Group related requests for easier access.
- Share collections with team members.
- Use collections for automated testing.

## 7. Organizing Collections with Folders
For better organization:
1. Right-click on a collection and select **Add Folder**.
2. Name the folder (e.g., `Jobs by Location`).
3. Drag and drop requests into the folder.
4. Create multiple levels of folders as needed.

