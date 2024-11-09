# Cold Email Generator 📧

An AI-powered application that automatically generates personalized cold emails for business development by analyzing job postings and matching them with relevant portfolio items. Built with LangChain, Groq LLM, and ChromaDB for efficient RAG (Retrieval Augmented Generation).

## Features

- 🌐 Web scraping of job postings
- 🤖 Automated job requirement extraction
- 🎯 Portfolio matching using vector similarity
- ✍️ Personalized cold email generation
- 💼 Professional business development context
- 🚀 Streamlit web interface

## Architecture

```
├── main.py           # Streamlit application entry point
├── chains.py         # LLM chain definitions and prompt templates
├── portfolio.py      # Portfolio management and vector search
├── utils.py          # Text cleaning utilities
└── resource/
    └── my_portfolio.csv  # Portfolio data
```

## Prerequisites

- Python 3.8+
- Groq API key
- ChromaDB
- Internet connection for web scraping

## Installation

1. Clone the repository:
```bash
git clone https://github.com/abdellatif-belmady/Cold-Mail-Generator.git
cd cold-email-generator
```

2. Install dependencies:
```bash
pip install -r requirements.txt
```

3. Set up environment variables:
Create a `.env` file in the root directory with:
```
GROQ_API_KEY=your_groq_api_key_here
```

4. Prepare portfolio data:
Create a CSV file at `resource/my_portfolio.csv` with columns:
- `Techstack`: Technical skills and capabilities
- `Links`: Relevant portfolio links

## Usage

1. Start the Streamlit application:
```bash
streamlit run main.py
```

2. Enter a job posting URL in the input field, example `https://jobs.nike.com/fr/job/R-43863?from=job%20search%20funnel`
3. Click "Submit" to generate a personalized cold email

## Components

### Main Application (`main.py`)
- Streamlit web interface
- Handles URL input and job data extraction
- Orchestrates the email generation pipeline

### LLM Chains (`chains.py`)
- Implements two main chains:
  - Job extraction chain: Parses job details into structured format
  - Email generation chain: Creates personalized cold emails
- Uses Groq's LLama 3.1 70B model
- Includes custom prompt templates

### Portfolio Management (`portfolio.py`)
- Manages company portfolio data
- Implements RAG using ChromaDB
- Matches job requirements with relevant portfolio items

### Utilities (`utils.py`)
- Text cleaning and preprocessing
- HTML tag removal
- URL filtering
- Whitespace normalization

## Error Handling

The application includes error handling for:
- Invalid URLs
- Failed web scraping
- Large context processing
- LLM API failures
- Portfolio data issues

## Development

To contribute:

1. Fork the repository
2. Create a feature branch
3. Implement changes
4. Add tests
5. Submit a pull request

## Technical Details

### Vector Search
- Uses ChromaDB for efficient similarity search
- Stores portfolio items as embeddings
- Matches job requirements with portfolio examples

### LLM Integration
- Model: LLaMA 3.1 70B (via Groq)
- Temperature: 0 (for consistent outputs)
- Custom prompt engineering for job extraction and email generation

### Data Processing
- Web scraping using LangChain's WebBaseLoader
- Text cleaning and normalization
- Structured JSON output parsing

## License

Open Source.

## Contributing

Contributions are welcome! Please read the contributing guidelines before submitting pull requests.

## Support

For support, please open an issue in the GitHub repository or contact the maintainers.
