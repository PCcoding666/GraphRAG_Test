# GraphRAG Test Project

## Introduction

This project is a test implementation of the GraphRAG system, using Ollama as a local LLM and embedding model. GraphRAG is a powerful tool for indexing text data and answering questions based on the indexed data.

## Features

- Uses Ollama as a local LLM and embedding model
- Supports text indexing and querying
- Configurable indexing and querying parameters
- Supports both local and global search

## Quick Start

### Prerequisites

- Python 3.10-3.12
- Ollama installed and running locally (http://127.0.0.1:11434)

### Installation

1. Clone the repository:
   ```
   git clone https://github.com/PCcoding666/GraphRAG_Test.git
   cd GraphRAG_Test
   ```

2. Install dependencies:
   ```
   pip install graphrag
   ```

### Configuration

The project uses a `settings.yaml` file for configuration. Key configurations include:

- LLM settings: Using Ollama's qwen2:7b model
- Embedding settings: Also using Ollama's qwen2:7b model
- Indexing and querying parameters

### Running the Indexer

1. Prepare input data:
   ```
   mkdir -p ./ragtest/input
   curl https://www.gutenberg.org/cache/epub/24022/pg24022.txt > ./ragtest/input/book.txt
   ```

2. Run the indexer:
   ```
   python -m graphrag.index --root ./ragtest
   ```

### Using the Query Engine

1. Global search example:
   ```
   python -m graphrag.query --root ./ragtest --method global "What are the top themes in this story?"
   ```

2. Local search example:
   ```
   python -m graphrag.query --root ./ragtest --method local "Who is Scrooge, and what are his main relationships?"
   ```

## Project Structure

- `ragtest/`: Main project directory
  - `input/`: Input text files
  - `output/`: Indexing outputs and reports
  - `settings.yaml`: Configuration file

## Contributing

Issues and pull requests are welcome to improve the project.

## License

[Add license information here]

## Acknowledgements

- GraphRAG project
- Ollama project