# Adobe Hackathon 25 - Document Intelligence System

[![Python](https://img.shields.io/badge/Python-3.8+-blue.svg)](https://python.org)
[![License](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)
[![Hackathon](https://img.shields.io/badge/Event-Adobe%20Hackathon%202025-red.svg)](https://github.com/Bhoomi1921/Adobe-Hackathon-25)

An intelligent document processing system that extracts, analyzes, and prioritizes content from PDF collections using advanced NLP techniques and semantic understanding. Built for the Adobe Hackathon 2025 challenge.

## 🌟 Key Features

- **🎯 Content Classification**: Intelligent categorization of document sections based on content type
- **📄 Advanced PDF Processing**: Robust extraction of text, structure, and metadata from PDF documents  
- **🔍 Semantic Analysis**: Deep understanding of document content using transformer models
- **📊 Hierarchical Organization**: Automatic building of document hierarchies and relationships
- **🤖 Machine Learning Pipeline**: End-to-end ML workflow for document intelligence
- **⚡ High Performance**: Optimized processing for large document collections
- **🐳 Containerized Deployment**: Docker support for easy deployment and scaling

## 🏗️ System Architecture

```
┌─────────────────┐    ┌──────────────────┐    ┌─────────────────┐
│   PDF Input     │───▶│  Document Parser │───▶│ Content         │
│   Collection    │    │  & Extractor     │    │ Classifier      │
└─────────────────┘    └──────────────────┘    └─────────────────┘
                                │                        │
                                ▼                        ▼
                       ┌──────────────────┐    ┌─────────────────┐
                       │ Text Processing  │    │ Section         │
                       │ & Cleaning       │    │ Categorization  │
                       └──────────────────┘    └─────────────────┘
                                │                        │
                                ▼                        ▼
                       ┌──────────────────┐    ┌─────────────────┐
                       │ Semantic         │───▶│ Hierarchy       │
                       │ Analyzer         │    │ Builder         │
                       └──────────────────┘    └─────────────────┘
                                                        │
                                                        ▼
                                               ┌─────────────────┐
                                               │ Structured      │
                                               │ Output          │
                                               └─────────────────┘
```

## 🛠️ Technology Stack

- **Core**: Python 3.8+, NumPy, Pandas
- **PDF Processing**: PyPDF2, pdfplumber, pymupdf
- **Machine Learning**: scikit-learn, transformers, sentence-transformers
- **NLP**: NLTK, spaCy, tokenizers
- **Deployment**: Docker, containerized architecture
- **Data Processing**: JSON/CSV output formats

## 📁 Project Structure

```
Adobe-Hackathon-25/
├── adobe-1a/                     # Main document intelligence system
│   ├── __pycache__/              # Python cache files
│   ├── documents/                # Input document storage
│   ├── model/                    # ML models and weights
│   ├── results/                  # Processing output files
│   ├── content_classifier.py     # Document content classification
│   ├── document_parser.py        # PDF parsing and text extraction
│   ├── hierarchy_builder.py      # Document structure analysis
│   ├── main.py                   # Main application entry point
│   ├── semantic_analyzer.py      # Semantic content analysis
│   ├── requirements.txt          # Python dependencies
│   └── README.md                 # Component documentation
├── adobe1b/                      # Alternative implementation
│   ├── input/                    # Input data directory
│   ├── models/                   # Model storage
│   ├── output/                   # Generated outputs
│   ├── sample_data/              # Test datasets
│   ├── src/                      # Source code modules
│   ├── main.py                   # Application entry point
│   ├── run.py                    # Execution script
│   ├── setup_models.py           # Model initialization
│   ├── test_*.py                 # Testing suite
│   └── requirements.txt          # Dependencies
└── README.md                     # This file
```

## 🚀 Quick Start

### Prerequisites

- Python 3.8 or higher
- 4GB RAM (8GB recommended for large documents)
- 2GB free disk space
- Internet connection for initial model download

### Installation

1. **Clone the Repository**
```bash
git clone https://github.com/Bhoomi1921/Adobe-Hackathon-25.git
cd Adobe-Hackathon-25
```

2. **Choose Your Implementation**

For **adobe-1a** (Main System):
```bash
cd adobe-1a
python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate
pip install -r requirements.txt
```

For **adobe1b** (Alternative System):
```bash
cd adobe1b
python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate
pip install -r requirements.txt
python setup_models.py  # Download required models
```

### Basic Usage

**Adobe-1a System:**
```bash
cd adobe-1a
python main.py --input documents/ --output results/
```

**Adobe1b System:**
```bash
cd adobe1b
python run.py --documents sample_data/ --output output/
```

## 📊 Core Components

### 1. Document Parser (`document_parser.py`)
- Extracts text content from PDF files
- Preserves document structure and formatting
- Handles various PDF types and encodings
- Maintains page-level organization

### 2. Content Classifier (`content_classifier.py`)
- Categorizes document sections by content type
- Uses machine learning for intelligent classification
- Supports multiple document domains
- Provides confidence scores for classifications

### 3. Semantic Analyzer (`semantic_analyzer.py`)
- Performs deep semantic understanding of content
- Uses transformer models for contextual analysis
- Identifies key concepts and relationships
- Enables similarity-based document matching

### 4. Hierarchy Builder (`hierarchy_builder.py`)
- Constructs logical document hierarchies
- Identifies parent-child relationships between sections
- Creates structured document maps
- Enables navigation and content organization

## 🧪 Testing & Validation

### Run System Tests
```bash
# For adobe1b system
cd adobe1b
python test_system.py
python test_with_generated_data.py
python test_my_documents.py
```

### Performance Benchmarks
- **Processing Speed**: 3-10 documents in under 60 seconds
- **Memory Usage**: ~2GB typical, 4GB maximum
- **Accuracy**: 90%+ content classification accuracy
- **Scalability**: Handles collections of 100+ documents

## 🐳 Docker Deployment

### Build and Run
```bash
# Build the container
docker build -t adobe-hackathon .

# Run with mounted directories
docker run -v $(pwd)/input:/app/input \
           -v $(pwd)/output:/app/output \
           adobe-hackathon
```

### Production Deployment
```bash
docker run -d \
  --name adobe-doc-intelligence \
  --restart unless-stopped \
  -v /host/documents:/app/input \
  -v /host/results:/app/output \
  adobe-hackathon
```

## 📈 Performance Optimization

### Resource Management
- **CPU Optimization**: Multi-threaded processing for large document sets
- **Memory Efficiency**: Streaming processing to handle large files
- **Disk Usage**: Temporary file cleanup and efficient storage

### Scaling Considerations
- **Horizontal Scaling**: Stateless design for distributed processing
- **Load Balancing**: Queue-based document processing
- **Monitoring**: Built-in performance metrics and logging

## 🔧 Configuration

### Environment Variables
```bash
export ADOBE_MODEL_PATH="/path/to/models"
export ADOBE_OUTPUT_FORMAT="json"  # or "csv"
export ADOBE_DEBUG_MODE="true"
export ADOBE_MAX_WORKERS="4"
```

### Custom Configuration
Modify processing parameters in `config.py`:
```python
# Processing settings
MAX_DOCUMENT_SIZE = 50 * 1024 * 1024  # 50MB
CLASSIFICATION_THRESHOLD = 0.8
SEMANTIC_SIMILARITY_THRESHOLD = 0.7
```

## 📊 Output Format

The system generates structured output with comprehensive metadata:

```json
{
  "metadata": {
    "processing_timestamp": "2025-07-28T10:30:00Z",
    "total_documents": 5,
    "processing_time_seconds": 45.2,
    "system_version": "1.0.0"
  },
  "documents": [
    {
      "filename": "document.pdf",
      "pages": 10,
      "sections": [
        {
          "title": "Introduction",
          "content": "...",
          "classification": "overview",
          "confidence": 0.92,
          "page_numbers": [1, 2]
        }
      ],
      "hierarchy": {
        "structure": "tree",
        "relationships": [...]
      }
    }
  ],
  "summary": {
    "total_sections": 48,
    "classification_distribution": {
      "methodology": 12,
      "results": 8,
      "introduction": 5
    }
  }
}
```

## 🎯 Use Cases

### Academic Research
- **Literature Reviews**: Extract and organize research findings
- **Paper Analysis**: Identify methodology and results sections
- **Citation Analysis**: Track references and relationships

### Business Intelligence
- **Report Processing**: Extract key metrics and insights
- **Document Summarization**: Generate executive summaries
- **Compliance Analysis**: Identify regulatory requirements

### Legal & Compliance
- **Contract Analysis**: Extract terms and conditions
- **Document Discovery**: Find relevant case materials
- **Regulatory Review**: Ensure compliance requirements

## 🚨 Troubleshooting

### Common Issues

**Memory Errors with Large Documents:**
```bash
# Increase Python memory limit
export PYTHONMAXMEMORY=8G
python main.py --batch-size 1
```

**PDF Processing Errors:**
```bash
# Test PDF integrity
python -c "import PyPDF2; print('PDF processing available')"
```

**Model Download Issues:**
```bash
# Manual model setup
cd adobe1b
python setup_models.py --force-download
```

### Debug Mode
```bash
python main.py --debug --verbose --input documents/
```

## 🤝 Contributing

We welcome contributions to improve the system:

1. **Fork** the repository
2. **Create** a feature branch: `git checkout -b feature-name`
3. **Make** your changes with appropriate tests
4. **Follow** Python PEP 8 coding standards
5. **Submit** a pull request with detailed description

### Development Setup
```bash
# Install development dependencies
pip install -r requirements-dev.txt

# Run code formatting
black src/
flake8 src/

# Run tests
pytest tests/
```

## 🏆 Hackathon Team

- **Team Name**: [Trio]
- **Team Members**: [Bhoomi Gupta, Bhagyashri Nigdikar]
- **Challenge**: Adobe Hackathon 2025
- **Category**: Document Intelligence & Processing

## 🙏 Acknowledgments

- Adobe Hackathon 2025 organizers for the inspiring challenge
- Open-source community for excellent libraries and tools
- Hugging Face for providing state-of-the-art transformer models
- Contributors and testers who helped improve the system
