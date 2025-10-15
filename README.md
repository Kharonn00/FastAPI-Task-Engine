
readme_content = """# Task Manager API with Search & Sort

A full-featured RESTful CRUD API built with FastAPI for managing tasks, featuring advanced search, filtering, and multiple sorting algorithms. This project demonstrates fundamental data structures, algorithms, and API design patterns used in production backend systems.

## 🚀 Features

### Core CRUD Operations
- ✅ **Create** new tasks with title, description, and completion status
- 📖 **Read** all tasks or retrieve individual tasks by ID
- ✏️ **Update** existing tasks
- 🗑️ **Delete** tasks permanently

### Advanced Features
- 🔍 **Search** - Case-insensitive search by task title (Linear Search algorithm)
- 🎯 **Filter** - Filter tasks by completion status
- 📊 **Sort** - Sort tasks by title, ID, or completion status
- 🔄 **Combined Operations** - Use search, filter, and sort together
- 🧮 **Algorithm Comparison** - Includes both Timsort (O(n log n)) and Bubble Sort (O(n²)) implementations

### Technical Features
- 🔒 Automatic data validation using Pydantic models
- 📚 Interactive API documentation (Swagger UI & ReDoc)
- ⚡ Fast and lightweight using FastAPI
- 🎓 Educational endpoints demonstrating sorting algorithms

## 🛠️ Technologies Used

- **Python 3.x**
- **FastAPI** - Modern, fast web framework for building APIs
- **Pydantic** - Data validation using Python type annotations
- **Uvicorn** - Lightning-fast ASGI server

## 📋 Algorithms Implemented

| Algorithm | Type | Time Complexity | Use Case |
|-----------|------|-----------------|----------|
| **Linear Search** | Searching | O(n) | Text search in task titles |
| **Timsort** | Sorting | O(n log n) | Default Python sorting (production) |
| **Bubble Sort** | Sorting | O(n²) | Educational demonstration |

## 🔧 Installation

### Prerequisites
- Python 3.7 or higher
- pip (Python package manager)

### Setup Instructions

1. **Clone the repository**
   \`\`\`bash
   git clone <your-repo-url>
   cd task-manager-api
   \`\`\`

2. **Create a virtual environment**
   \`\`\`bash
   python -m venv venv
   \`\`\`

3. **Activate the virtual environment**
   - On macOS/Linux:
     \`\`\`bash
     source venv/bin/activate
     \`\`\`
   - On Windows:
     \`\`\`bash
     .\\venv\\Scripts\\activate
     \`\`\`

4. **Install dependencies**
   \`\`\`bash
   pip install -r requirements.txt
   \`\`\`

5. **Run the application**
   \`\`\`bash
   uvicorn main:app --reload
   \`\`\`

6. **Access the API**
   - API Root: http://127.0.0.1:8000
   - Interactive Docs (Swagger UI): http://127.0.0.1:8000/docs
   - Alternative Docs (ReDoc): http://127.0.0.1:8000/redoc

## 📡 API Endpoints

### Basic CRUD Operations

| Method | Endpoint | Description |
|--------|----------|-------------|
| GET | `/` | Welcome message and API info |
| POST | `/tasks/` | Create a new task |
| GET | `/tasks/` | Get all tasks (with optional filters) |
| GET | `/tasks/{task_id}` | Get a specific task by ID |
| PUT | `/tasks/{task_id}` | Update an existing task |
| DELETE | `/tasks/{task_id}` | Delete a task |

### Advanced Endpoints

| Method | Endpoint | Description |
|--------|----------|-------------|
| GET | `/tasks/bubble-sort` | Get tasks sorted using Bubble Sort algorithm |

### Query Parameters for GET /tasks/

| Parameter | Type | Description | Example |
|-----------|------|-------------|---------|
| `search` | string | Search tasks by title (case-insensitive) | `?search=python` |
| `completed` | boolean | Filter by completion status | `?completed=true` |
| `sort_by` | string | Sort by field (title, id, completed) | `?sort_by=title` |
| `order` | string | Sort order (asc or desc) | `?order=desc` |

## 💡 Usage Examples

### Create a Task
\`\`\`bash
POST /tasks/
Content-Type: application/json

{
  "title": "Learn FastAPI",
  "description": "Build a CRUD API with advanced features",
  "completed": false
}
\`\`\`

### Search Tasks
\`\`\`bash
GET /tasks/?search=FastAPI
\`\`\`

### Filter Completed Tasks
\`\`\`bash
GET /tasks/?completed=true
\`\`\`

### Sort Tasks by Title
\`\`\`bash
GET /tasks/?sort_by=title&order=asc
\`\`\`

### Combine Search, Filter, and Sort
\`\`\`bash
GET /tasks/?search=Learn&completed=false&sort_by=title&order=asc
\`\`\`
*Returns incomplete tasks containing "Learn", sorted alphabetically*

### Compare Sorting Algorithms
\`\`\`bash
# Using Timsort (default, O(n log n))
GET /tasks/?sort_by=id

# Using Bubble Sort (educational, O(n²))
GET /tasks/bubble-sort?sort_by=id
\`\`\`

## 📊 Data Model

\`\`\`python
{
  "id": int,              # Auto-generated, unique identifier
  "title": str,           # Required, task name
  "description": str,     # Optional, task details
  "completed": bool       # Default: false, completion status
}
\`\`\`

## 🧠 What I Learned

### Backend Development
- Building RESTful APIs with FastAPI
- Implementing CRUD operations with HTTP methods (POST, GET, PUT, DELETE)
- Using query parameters for filtering and sorting
- Data validation and serialization with Pydantic models
- API documentation with Swagger UI

### Algorithms & Data Structures
- **Linear Search** - O(n) time complexity for text search
- **Sorting Algorithms** - Comparing different approaches:
  - Timsort (Python's default) - O(n log n) - Hybrid of Merge Sort and Insertion Sort
  - Bubble Sort - O(n²) - Simple but inefficient for large datasets
- **Time Complexity Analysis** - Understanding Big O notation
- **Algorithm Trade-offs** - When to use different sorting strategies

### Software Engineering Best Practices
- Type hints for better code quality
- Virtual environments for dependency management
- Git and version control
- Writing professional documentation
- Project structure and organization

## 🎯 Interview Talking Points

This project demonstrates proficiency in:
- **API Design**: RESTful principles, query parameters, response formatting
- **Algorithms**: Search and sort implementations with complexity analysis
- **Data Validation**: Using Pydantic models for input validation
- **Code Quality**: Type hints, clean code, documentation
- **Problem Solving**: Implementing features that require algorithmic thinking

### Example Interview Answer:
> "I built a Task Manager API with FastAPI that implements full CRUD operations plus advanced features like search, filtering, and sorting. For search, I used a linear search algorithm with O(n) time complexity—suitable for our dataset size, but in production with millions of records, I'd implement database indexing or a more efficient search structure. For sorting, I compared Python's Timsort (O(n log n)) with Bubble Sort (O(n²)) to understand the performance differences. The API uses Pydantic for automatic validation and includes full Swagger documentation."

## 🚧 Future Improvements

- [ ] Connect to a persistent database (PostgreSQL/SQLite)
- [ ] Implement pagination for large datasets
- [ ] Add user authentication and authorization (JWT tokens)
- [ ] Binary Search Tree for O(log n) search performance
- [ ] Task priority system with heap data structure
- [ ] Add task dependencies using graph algorithms (topological sort)
- [ ] Implement caching with Redis
- [ ] Add rate limiting to prevent API abuse
- [ ] Deploy to cloud platform (AWS/Heroku/Railway)
- [ ] Add automated testing with pytest
- [ ] Implement CI/CD pipeline

## 📈 Performance Considerations

### Current Implementation
- **Storage**: In-memory list (resets on restart)
- **Search**: O(n) linear search
- **Sort**: O(n log n) using Timsort
- **Best for**: Small to medium datasets (< 10,000 tasks)

### Production Optimizations
- Database indexing for O(1) lookup by ID
- Full-text search engines (Elasticsearch) for complex queries
- Caching frequently accessed data
- Pagination to limit response sizes

## 📝 License

This project is open source and available for educational purposes.

---

Built as part of my journey to becoming a Backend Python Developer 🚀  
*Demonstrating CRUD operations, search algorithms, sorting algorithms, and RESTful API design*
"""
