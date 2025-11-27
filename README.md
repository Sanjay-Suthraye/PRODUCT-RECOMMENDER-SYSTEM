# Flipkart Product Recommender Chatbot 🛍️🤖

A RAG-based conversational AI system that helps users explore and understand Flipkart products through natural language conversations. Built with cutting-edge LLM technology and deployed with monitoring capabilities.

## What It Does

Ever wanted to chat naturally about product reviews instead of scrolling through hundreds of them? This chatbot lets you ask questions like "Which earphones have the best bass?" or "Tell me about battery life of these headphones" and get intelligent, context-aware responses based on actual customer reviews.

## Tech Stack

- **LangChain** - RAG pipeline orchestration
- **Groq** - Lightning-fast LLM inference (llama-3.1-8b-instant)
- **AstraDB** - Vector database for storing product embeddings
- **HuggingFace** - Embeddings model (BAAI/bge-base-en-v1.5)
- **Flask** - Web interface
- **Docker** - Containerization
- **Kubernetes** - Orchestration
- **Prometheus + Grafana** - Monitoring stack

## Features

- 💬 Natural conversation with chat history
- 🔍 Context-aware product recommendations
- 📊 Real product reviews from Flipkart dataset
- 🎯 Retrieval Augmented Generation for accurate responses
- 📈 Production-ready monitoring setup

## Quick Start

```bash
# Clone the repository
git clone <repo-url>
cd flipkart-recommender

# Install dependencies
pip install -e .

# Set up environment variables
cp .env.example .env
# Add your API keys (Groq, AstraDB, HuggingFace)

# Run the app
python app.py
```

Visit `http://localhost:5000` and start chatting!

## Project Structure

```
├── flipkart/           # Core RAG components
│   ├── config.py       # Configuration
│   ├── data_converter.py
│   ├── data_ingestion.py
│   └── rag_chain.py    # LangChain RAG pipeline
├── app.py              # Flask application
├── templates/          # Web UI
├── data/               # Product review dataset
└── prometheus/         # Monitoring configs
```

## How It Works

1. **Data Ingestion**: Product reviews are converted to embeddings and stored in AstraDB
2. **Query Processing**: User questions are embedded and used to retrieve relevant reviews
3. **Context Generation**: Retrieved reviews provide context for the LLM
4. **Response**: Groq's Llama model generates natural, helpful responses
5. **Chat Memory**: Conversation history is maintained for contextual follow-ups

## Deployment

The project includes complete Kubernetes manifests for production deployment with monitoring:

```bash
# Deploy the app
kubectl apply -f flask-deployment.yaml

# Deploy monitoring
kubectl apply -f prometheus/
kubectl apply -f grafana/
```

## Monitoring

- **Prometheus**: Scrapes metrics from the Flask app
- **Grafana**: Visualizes request counts, latencies, and system health
- Access Grafana dashboard at NodePort 32000

## Dataset

Uses real Flipkart product reviews covering various categories like:
- Bluetooth headsets
- Wireless earbuds
- Wired headphones
- Neckbands

## Future Enhancements

- [ ] Add product images in responses
- [ ] Implement user feedback loop
- [ ] Multi-language support
- [ ] Product comparison feature
- [ ] Price tracking integration

## Author

Built by **Sanjay** - Exploring the intersection of e-commerce and conversational AI

---

*Note: This is a learning project. Make sure to add your own API keys and never commit them to version control.*
