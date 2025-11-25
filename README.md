# Custom Chatbot Project: 2023 Fashion Trends RAG System

## Project Overview

This project implements a Retrieval-Augmented Generation (RAG) system that provides expert fashion advice based on 2023 fashion trends. By combining OpenAI's language models with a curated dataset of fashion trends, the chatbot delivers accurate, specific, and contextually relevant fashion recommendations.

## Dataset

**Dataset Used:** 2023 Fashion Trends from Refinery29

The dataset contains 82 detailed entries about fashion trends from 2023, including:
- Color trends (glossy reds, metallics, lime green)
- Clothing styles (cargo pants, sheer clothing, denim reimagined)
- Seasonal trends and runway insights
- Designer recommendations and styling tips

**Why This Dataset?**

Fashion trends change rapidly year-to-year, making this an ideal candidate for demonstrating RAG systems. The 2023-specific information would not be readily available in a base language model's training data, allowing us to clearly show the difference between generic fashion knowledge and specialized, current trend insights.

## How It Works

### RAG Pipeline

1. **Data Preparation**: Fashion trend descriptions are loaded into a pandas DataFrame
2. **Embedding Creation**: Each trend is converted into a vector embedding using OpenAI's `text-embedding-ada-002` model
3. **Query Processing**: User questions are converted to embeddings
4. **Similarity Search**: The system finds the 3 most relevant fashion trends using cosine similarity
5. **Context Enhancement**: Relevant trends are injected into the prompt
6. **Response Generation**: OpenAI's `gpt-3.5-turbo-instruct` generates an informed answer

## Technology Stack

- **Python 3.9**
- **pandas**: Data manipulation and analysis
- **numpy**: Vector calculations and cosine similarity
- **OpenAI API (v0)**: Embeddings and text completion
- **Jupyter Notebook**: Interactive development environment

## Project Structure
```
.
├── project.ipynb           # Main Jupyter notebook
├── data/
│   └── 2023_fashion_trends.csv   # Fashion trends dataset
├── README.md               # This file
└── requirements.txt        # Python dependencies
```

## Setup Instructions

### Prerequisites

1. Python 3.9 or higher
2. OpenAI API key
3. Jupyter Notebook environment

### Installation

1. Clone or download this repository

2. Install required packages:
```bash
pip install -r requirements.txt
```

3. Set up your OpenAI API key in the notebook:
```python
openai.api_key = "YOUR_API_KEY"
```

### Running the Project

1. Open `project.ipynb` in Jupyter Notebook or JupyterLab

2. Run all cells sequentially:
   - Data loading and wrangling
   - Embedding creation
   - RAG function definitions
   - Question demonstrations

## Results
```Actual results are shown in answers.txt file. ```
The project demonstrates clear performance improvements when using custom data: 

### Question 1: "What colors should I wear for 2023 fashion trends?"

- **Basic Completion**: Provides generic color advice
- **Custom Completion**: Specifically mentions glossy reds, metallics, lime green, and other 2023-specific trends from the dataset

### Question 2: "What type of pants are trending in 2023?"

- **Basic Completion**: Generic pants recommendations
- **Custom Completion**: Specifically recommends cargo pants with details about tailored silhouettes, elevated fabrics, and styling beyond traditional khaki

## Key Features

✅ **82 Fashion Trends**: Comprehensive 2023 fashion trend database  
✅ **Semantic Search**: Finds most relevant trends using embeddings  
✅ **Context-Aware**: Responses grounded in actual 2023 runway data  
✅ **Comparative Analysis**: Side-by-side basic vs. custom completions  
✅ **Production-Ready**: Clean, modular code structure  

## Performance Comparison

| Metric | Basic Completion | Custom RAG System |
|--------|-----------------|-------------------|
| Specificity | Generic advice | 2023-specific trends |
| Accuracy | Limited context | Grounded in dataset |
| Relevance | Variable | High (top 3 matches) |
| Designer References | None | Sandy Liang, Tory Burch, etc. |

## Limitations

- Dataset limited to 2023 trends (not current)
- Requires OpenAI API credits
- English language only
- Fashion-specific domain

## Future Enhancements

- [ ] Add interactive chatbot loop for continuous Q&A
- [ ] Expand dataset to include 2024-2025 trends
- [ ] Implement filtering by season, occasion, or style
- [ ] Add image generation for outfit visualization
- [ ] Create web interface using Streamlit or Flask

## Dependencies
```
openai==0.28.1
pandas>=1.5.0
numpy>=1.23.0
jupyter>=1.0.0
```

## License

This project is for educational purposes as part of a course assignment.

## Author

Sage Rimal  
[sagerimal.com](https://sagerimal.com)

## Acknowledgments

- Dataset sourced from Refinery29's 2023 Fashion Trends coverage
- Built for AI/ML course project
- Powered by OpenAI's embedding and completion models

---

**Note**: Remember to replace `"YOUR_API_KEY"` with your actual OpenAI API key before running, and remove it before submitting the project.
