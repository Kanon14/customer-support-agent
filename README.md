# customer-support-agent
This project is a **Multi-Agent Customer Support System** powered by LangFlow, integrated with OpenAI and Astra DB. The system uses three agents to handle customer queries related to FAQs, order lookups, and product information.

## Project Overview
This project provides a **user-friendly customer** support interface that can:
- Answer frequently asked questions (FAQs).
- Provide real-time order status and transactional details.
- Retrieve detailed product information.

The system routes customer queries to specialized agents to ensure accurate and efficient responses.
![langflow workflow](components/langflow.jpg)

## Features
- **Multi-Agent System**: Separate agents handle FAQs, orders, and product lookups.
- **Integrated Data Sources**:
    - **FAQs**: Static document-based retrieval.
    - **Orders and Products**: Real-time lookup from `.csv` files.
- **OpenAI API Integration**: Agents use `gpt-4.0-mini` for natural language understanding.
- **Scalable and Modular**: Easily extendable with additional agents and data sources.

## Architecture
**Agent Overview**:

- **FAQ Agent**: Answers common customer questions using predefined FAQs.
- **Order Lookup Agent**: Fetches order details based on `orderNumber`.
- **Product Lookup Agent**: Retrieves product specifications based on `productId`.

The system workflow ensures:
1. Queries are routed to the correct agent. 
2. Each agent fetches relevant data and formats the response. 

## Project Setup
### Prerequisites
- Python 3.12+
- Anaconda or Miniconda installed on your machine
- API keys for OpenAI and Astra DB

### Installation
1. Clone the repository:
```bash
git clone https://github.com/Kanon14/customer-support-agent.git
cd customer-support-agent
```
2. Create and activate a Conda environment:
```bash
conda create -n agent python=3.12 -y
conda activate agent
```
3. Install the required dependencies:
```bash
pip install -r requirements.txt
```

### Environment Variables
Create a `.env` file:
```bash
APP_TOKEN=your_astra_db_app_token
OPENAI_API_KEY=your_openai_api_key
```

### How to Run
1. Execute the project:
```bash
streamlit run main.py
```
2. Then, access the application via your web browser:
```bash
open http://localhost:<port>
```

## Future Enhancements
1. **Enhancing Agent Prompts**: Improve the prompt templates to provide more context-specific and structured responses.
2. **Conversation History**: Add support to display past interactions.
3. **Enhanced Data Sources**: Integrate a live database for real-time updates.