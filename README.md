# Dental Image Similarity Search and Q&A System

A comprehensive system for dental image analysis that combines computer vision, vector similarity search, and large language models to provide intelligent question-answering capabilities for dental images.

## 🔍 Overview

This project implements an end-to-end pipeline for dental image analysis that:
- Extracts features from dental images using a pre-trained CNN model
- Stores image embeddings in Qdrant vector database for efficient similarity search
- Retrieves similar images based on visual similarity
- Generates intelligent answers to user questions using Claude AI

## 🏗️ Architecture

```
Query Image → CNN Feature Extraction → Vector Search (Qdrant) → Similar Image + Description → Claude AI → Answer
```

## ✨ Features

- **Image Feature Extraction**: Uses a custom-trained CNN model for dental image feature extraction
- **Vector Similarity Search**: Leverages Qdrant database for fast and accurate similarity search
- **Intelligent Q&A**: Integrates Claude 3.5 Sonnet for contextual question answering
- **Dental-Specific**: Optimized for dental image analysis and diagnostics
- **Scalable**: Built with production-ready vector database architecture

## 🚀 Getting Started

### Prerequisites

- Python 3.8+
- TensorFlow 2.x
- Qdrant instance (cloud or local)
- Claude AI API key
- Pre-trained dental CNN model (`Dental_CNN_model_v4.h5`)

### Installation

1. Clone the repository:
```bash
git clone https://github.com/yourusername/dental-image-similarity-search.git
cd dental-image-similarity-search
```

2. Install dependencies:
```bash
pip install -r requirements.txt
```

3. Set up environment variables:
```bash
export QDRANT_URL="your-qdrant-url"
export QDRANT_API_KEY="your-qdrant-api-key"
export CLAUDE_API_KEY="your-claude-api-key"
```

### Configuration

1. **Qdrant Setup**: Configure your Qdrant instance connection in the main script
2. **Model Path**: Update the path to your pre-trained dental CNN model
3. **Collection Setup**: Create or recreate the Qdrant collection for your embeddings

### Usage

1. **Basic Usage**:
```python
from dental_similarity_search import handle_user_request

# Process a query image and question
query_image_path = "path/to/your/dental/image.jpg"
user_question = "What is the main dental issue in this image?"

retrieved_image, description, answer = handle_user_request(query_image_path, user_question)
print(f"Answer: {answer}")
```

2. **Interactive Mode**: Upload images and ask questions directly through the interface

## 📁 Project Structure

```
dental-image-similarity-search/
├── README.md
├── requirements.txt
├── .gitignore
├── notebooks/
│   └── dental_similarity_search.ipynb
├── models/
│   └── README.md (instructions for model placement)
├── data/
│   └── README.md (data organization guidelines)
└── src/
    └── (main application code)
```

## 🔧 Key Components

### 1. CNN Feature Extraction
- Uses a pre-trained dental image classification model
- Extracts 64-dimensional feature vectors from dental images
- Removes the final classification layer for feature extraction

### 2. Vector Database (Qdrant)
- Stores image embeddings with metadata
- Enables fast cosine similarity search
- Maintains image paths and descriptions as payload

### 3. Claude AI Integration
- Processes retrieved image descriptions
- Generates contextual answers to user questions
- Provides detailed dental analysis and recommendations

## 🎯 Use Cases

- **Dental Diagnosis Support**: Assist dentists in identifying similar cases
- **Treatment Planning**: Find similar cases for treatment reference
- **Educational Tool**: Help dental students learn from similar cases
- **Research**: Analyze patterns in dental conditions

## 📊 Performance

- **Search Speed**: Sub-second similarity search across large image databases
- **Accuracy**: High precision in finding visually similar dental images
- **Scalability**: Supports thousands of images with consistent performance

## 🛠️ Technical Details

### CNN Model
- Architecture: Custom dental image classification model
- Input: Preprocessed dental images
- Output: 64-dimensional feature vectors
- Training: Trained on dental image dataset

### Vector Database
- Database: Qdrant
- Distance Metric: Cosine similarity
- Dimension: 64
- Collections: Organized by image type and metadata

### AI Integration
- Model: Claude 3.5 Sonnet
- Max Tokens: 1000
- Use Case: Question answering based on image descriptions

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 🙏 Acknowledgments

- TensorFlow team for the deep learning framework
- Qdrant team for the vector database
- Anthropic for Claude AI capabilities
- Dental imaging research community

## 📧 Contact

For questions or support, please open an issue or contact [your-email@example.com]

## 🔮 Future Enhancements

- [ ] Multi-modal search (text + image queries)
- [ ] Batch processing capabilities
- [ ] Web interface for easy interaction
- [ ] Advanced filtering and search options
- [ ] Integration with DICOM medical imaging standards
- [ ] Real-time processing pipeline
- [ ] Model fine-tuning capabilities
