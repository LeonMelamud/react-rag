# React RAG (Retrieval-Augmented Generation) Project

A sophisticated RAG implementation combining React frontend with Python backend, featuring advanced document retrieval and AI-powered question answering capabilities.

## 🚀 Technologies

- **Backend**: Python
- **Frontend**: React
- **Database**: Qdrant
- **Observability**: Langfuse
- **Documentation**: FastAPI (Swagger/ReDoc)
- **Container**: Docker

## 📋 Prerequisites

- Python 3.x
- Node.js and npm
- Docker and Docker Compose
- Qdrant running locally
- Ollama (if using local LLM models)

## 🛠️ Setup and Installation

### 1. Environment Setup

```bash
# Clone the repository
git clone [repository-url]
cd react-rag

# Install Python dependencies
pip install -r requirements.txt

# Configure environment
cp .env.example .env
# Update .env with your Qdrant password in DB_API_KEY
```

### 2. Data Preparation
- Place your PDF documents in the `data/` folder
- Currently supported files:
  - bedrock-api.pdf
  - bedrock-studio-user-guide.pdf
  - mlops.pdf

### 3. Observability Setup

```bash
# Start Langfuse
docker compose -f docker-compose-langfuse.yml up

# Access Langfuse UI
1. Open http://localhost:3000
2. Click on 'signup'
3. Create organization & project
4. Generate public and private API keys
```

## 🚀 Running the Application

### Start the Backend

```bash
# Run the main application
python main.py

# Start the API server
python api_server.py
```

### API Documentation
- Swagger UI: http://localhost:8000/docs
- ReDoc: http://localhost:8000/redoc

### API Usage Example

```bash
curl -X POST http://localhost:8000/api/v1/chat-completion \
-H "Content-Type: application/json" \
-d '{"query": "explain mlops architecture"}'
```

## 📝 API Specification

### Chat Completion Endpoint
- **Method**: POST
- **Endpoint**: http://localhost:8000/api/v1/chat-completion
- **Request Body**:
```json
{
  "query": "explain mlops architecture"
}
```

## 🧪 Evaluation

The project includes RAG evaluation capabilities through `rag_evaluator.py`.

## 🤝 Contributing

1. Fork the repository
2. Create your feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add some amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

## 📄 License

This project is licensed under the MIT License - see the LICENSE file for details.
