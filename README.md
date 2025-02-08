# **REST API Architectural Constraints**

REST (Representational State Transfer) is a set of rules for building web services. APIs that follow these rules are called RESTful APIs. They allow clients (like apps or websites) to interact with servers using HTTP protocols. Below is a breakdown of the **6 key constraints** that make an API RESTful:

### **1. Uniform Interface**
- **What it means**: There should be a consistent way to interact with the server, no matter the device or app type.
- **Key Principles**:
  1. **Resource-Based**: Resources (like users, products) are identified in URLs (e.g., `/api/users`).
  2. **Manipulation Through Representations**: Clients use representations (like JSON) to modify or delete resources (e.g., using a user ID to update a user).
  3. **Self-descriptive Messages**: Each request contains enough information for the server to understand and process it.
  4. **HATEOAS (Hypermedia as the Engine of Application State)**: Responses include links to related resources, helping clients navigate the API.

### **2. Stateless**
- **What it means**: The server doesn’t store any client session data. Each request from the client must contain all the information needed to process it.
- **Why it’s good**: Improves scalability and reliability since the server doesn’t need to manage client state.
- **Drawback**: Clients may need to send more data in each request, increasing bandwidth usage.

### **3. Cacheable**
- **What it means**: Responses should indicate whether they can be cached (stored) by the client and for how long.
- **Why it’s good**: Caching reduces repeated requests to the server, improving performance.
- **Drawback**: Clients might receive stale (outdated) data if caching isn’t managed properly.

### **4. Client-Server**
- **What it means**: The client and server are separate entities. The client handles the user interface, while the server manages data storage and business logic.
- **Why it’s good**: They can evolve independently, making the system more flexible and scalable.

### **5. Layered System**
- **What it means**: The system can have multiple layers (e.g., load balancers, security layers) between the client and server. Each layer only interacts with the immediate next layer.
- **Why it’s good**: Improves scalability, security, and performance (e.g., through load balancing or shared caches).

### **6. Code on Demand (Optional)**
- **What it means**: The server can send executable code (like JavaScript) to the client to extend its functionality.
- **Why it’s optional**: Not all RESTful APIs need this feature, but it can be useful for dynamic client-side behavior.

---

### **Rules for Creating REST APIs**
1. **Use Nouns, Not Verbs**:
   - URLs should represent resources (nouns), not actions (verbs).
   - **Good**: `/api/users`
   - **Bad**: `/api?type=users`

2. **Use HTTP Verbs**:
   - Use standard HTTP methods to perform actions:
     - **GET**: Retrieve data (e.g., `GET /api/users`).
     - **POST**: Create a resource (e.g., `POST /api/users`).
     - **PUT**: Update a resource (e.g., `PUT /api/users/1`).
     - **DELETE**: Remove a resource (e.g., `DELETE /api/users/1`).
     - **PATCH**: Partially update a resource.

3. **Use Plural Nouns**:
   - Keep URLs consistent by using plurals (e.g., `/api/users`, not `/api/user`).

4. **Return Proper HTTP Status Codes**:
   - Indicate success or failure using codes like:
     - `200 OK`: Success.
     - `201 Created`: Resource created.
     - `400 Bad Request`: Invalid input.
     - `404 Not Found`: Resource not found.
     - `500 Internal Server Error`: Server error.

5. **Idempotent Methods**:
   - **GET, PUT, DELETE** are idempotent: Performing the same operation multiple times has the same effect (e.g., deleting a resource twice).


### **Example Endpoints**
| **URI**            | **HTTP Verb** | **Description**                     |
|---------------------|---------------|-------------------------------------|
| `/api/users`        | GET           | Get all users.                     |
| `/api/users`        | POST          | Add a new user.                    |
| `/api/users/1`      | GET           | Get user with ID 1.                |
| `/api/users/1`      | PUT           | Update user with ID 1.             |
| `/api/users/1`      | DELETE        | Delete user with ID 1.             |

---

# Postman API Documentation

## 1. What is Postman?
Postman is a widely-used tool for API testing, enabling developers to create, test, share, and document APIs efficiently. Postman is a collaboration platform for API development. It allows you to:
- **Build, test, and modify APIs** without writing HTTP client network code.
- **Create test suites** called collections.
- **Make various HTTP requests** such as GET, POST, PUT, PATCH.
- **Convert APIs to code** in languages like JavaScript and Python.

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
<br>
### **Sidebar: The Organizer**
- **What:** The sidebar typically houses collections, environments, and history.
- **How:** It allows you to navigate through your saved API requests, organize them into folders, and switch between different environments.
- **Why:** This helps in maintaining a structured and easily accessible repository of your API endpoints and configurations.

### **Header: The Control Center**
- **What:** The header contains the main navigation options like Home, Workspaces, and API Network, along with a search bar.
- **How:** You can use it to switch between different views, search for specific items, and access collaborative workspaces.
- **Why:** It provides quick access to essential features, ensuring smooth navigation and efficient workflow management.

### **Workbench: The Interaction Hub**
- **What:** The central area, or workbench, is where you build and send API requests.
- **How:** You can enter URLs, select HTTP methods, add parameters, headers, and body content, and view responses.
- **Why:** This is the core area for interacting with APIs, allowing you to test and debug endpoints effectively.

### **Footer: The Status Indicator**
- **What:** The footer usually displays status information, such as the response status code, response time, and size.
- **How:** It provides real-time feedback on the API request's outcome.
- **Why:** This immediate feedback is crucial for understanding the performance and success of your API calls.

### **Right Sidebar: The Detailer**
- **What:** The right sidebar often contains additional details and tools, such as documentation, examples, and settings.
- **How:** It can show contextual information related to the selected request or collection, and provide quick access to related resources.
- **Why:** This enhances your understanding and efficiency by offering relevant information and tools at your fingertips.


## 2. Sending Your First Request
Let’s start with a **GET request** to fetch data from a free API.  

### Sending a GET Request
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

