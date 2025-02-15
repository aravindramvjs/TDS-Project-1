# Pro-pilot LLM Project
The name of this LLM is Pro-pilot is a shortform of processing pilot. The core of the project is a FastAPI application that exposes endpoints for executing different types of tasks. These tasks are defined as functions and can be dynamically process and executed based on user input.

## Key Features

1. **Dynamic Task Execution**: The system can parse plain-English task descriptions and map them to appropriate function calls using GPT-4.

2. **Function Mapping**: A wide range of functions are available for various tasks, including:
   - File formatting
   - Database querying
   - Text extraction using LLMs
   - Image processing and text extraction from images
   - Embedding-based text similarity
   - Log file processing
   - JSON manipulation
   - Date processing and pattern matching
   - Package installation and script execution

3. **OpenAI Function Schemas**: The project converts Python functions into OpenAI function schemas, allowing for seamless integration with GPT models.

4. **Error Handling**: Comprehensive error handling and logging are implemented throughout the system.

5. **File Path Handling**: The system adapts file paths based on whether it's running in a local environment, Docker, or GitHub Codespaces.

6. **API Endpoints**: 
   - `/run`: Executes tasks based on plain-English descriptions
   - `/read`: Reads and returns the contents of specified files

7. **Extensibility**: The project is designed to be easily extendable with new function tasks.
export 

## Key Components

### Task Functions (`function_tasks.py`)
- Query execution and database interaction
- Text extraction and embedding analysis
- Image processing and OCR
- File management and sorting
- Date processing
- API interaction
- Git operations

### API Server (`main.py`)
- FastAPI endpoints:
  - `/run`: Executes tasks from natural language descriptions
  - `/read`: Retrieves file contents
- Dynamic function mapping
- Task parsing and execution
- Error handling with detailed tracebacks

## Environment Setup

Required environment variables:
```bash
export OPEN_AI_PROXY_TOKEN=<your-token>
export OPEN_AI_PROXY_URL=http://aiproxy.sanand.workers.dev/openai/v1/chat/completions
export OPEN_AI_EMBEDDING_URL=https://aiproxy.sanand.workers.dev/openai/v1/embeddings
```

## Server Setup

1. Clone the repository:
   ```bash
   git clone https://github.com/aravindramvjs/TDS-Project-1.git
   cd /TDS-Project-1
   ```

2. Install uv and uvicorn
    ```bash
    pip3 install uv, uvicorn
    ```

3. Start the server
    ```bash
    uvicorn main:app --host 0.0.0.0 --port 8000
    ```

3. Make requests:
    ```bash
    curl -X POST "http://localhost:8000/run?task=your-task-description"
    curl -X GET "http://localhost:8000/read?path=output-file-path"
    ```

## 🐳 Docker Image

The Docker image for this project is published on **Docker Hub**:

🔗 **[Docker Hub: docaravind21/tds-project-1](https://hub.docker.com/repository/docker/docaravind21/tds-project-1/general)**
## Container Support
- Handles both local and Docker environments
- Path management via `ensure_local_path` function
- Codespaces compatibility




