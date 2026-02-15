# AI Assistant - Multi-Model Chat Application

A modern Flask web application that allows users to interact with multiple AI models (Llama, Granite, and Mistral) through IBM Watsonx AI. Compare responses from different models in a clean, intuitive chat interface.

> **Note**: This project was developed as part of the IBM course **"Develop Generative AI Applications: Get Started"** on Coursera. The course provides hands-on experience with IBM Watsonx AI and building generative AI applications.

## 🚀 Features

- **Multi-Model Support**: Switch between three powerful AI models:
  - **Llama 3.2** (11B Vision Instruct)
  - **Granite 3.3** (8B Instruct)
  - **Mistral Small 3.1** (24B Instruct)
- **Modern UI**: Clean, responsive design with real-time chat interface
- **Response Analysis**: Get structured responses with sentiment analysis and summaries
- **Performance Metrics**: View response times for each model
- **Real-time Chat**: Interactive chat experience with loading indicators

## 📋 Prerequisites

- Python 3.8 or higher
- IBM Watsonx AI account with API credentials
- pip (Python package manager)

## 🛠️ Installation

1. **Clone the repository**
   ```bash
   git clone https://github.com/abdelrhmanidk/genai_flask_app.git
   cd genai_flask_app
   ```

2. **Create a virtual environment**
   ```bash
   python3 -m venv venv
   source venv/bin/activate  # On Windows: venv\Scripts\activate
   ```

3. **Install dependencies**
   ```bash
   pip install -r requirements.txt
   ```

4. **Set up environment variables**
   
   Copy the example environment file:
   ```bash
   cp .env.example .env
   ```
   
   Edit `.env` and add your IBM Watsonx AI credentials:
   ```env
   WATSONX_API_KEY=your_api_key_here
   WATSONX_URL=https://eu-de.ml.cloud.ibm.com
   WATSONX_PROJECT_ID=your_project_id_here
   ```

## 🎯 Usage

1. **Start the Flask application**
   ```bash
   python app.py
   ```

2. **Open your browser**
   
   Navigate to `http://localhost:5000`

3. **Start chatting**
   - Select a model from the dropdown
   - Type your message in the input field
   - Press Enter or click the send button
   - View responses with sentiment analysis and performance metrics

## 📁 Project Structure

```
genai_flask_app/
├── app.py                 # Main Flask application
├── model.py               # AI model integration and response handling
├── config.py              # Model configuration and parameters
├── requirements.txt       # Python dependencies
├── .env.example          # Environment variables template
├── .gitignore            # Git ignore rules
├── README.md             # This file
├── static/
│   ├── styles.css        # Application styles
│   └── script.js         # Frontend JavaScript
├── templates/
│   └── index.html        # Main HTML template
└── tests/
    ├── capital.py        # Test scripts
    └── llm_test.py      # Model testing utilities
```

## 🔧 Configuration

### Model Parameters

Edit `config.py` to customize model behavior:

```python
PARAMETERS = {
    GenParams.DECODING_METHOD: "greedy",
    GenParams.MAX_NEW_TOKENS: 256,
}
```

### Available Models

The application supports three models defined in `config.py`:
- `LLAMA_MODEL_ID`: Meta Llama 3.2 11B Vision Instruct
- `GRANITE_MODEL_ID`: IBM Granite 3.3 8B Instruct
- `MISTRAL_MODEL_ID`: Mistral Small 3.1 24B Instruct

## 🔒 Security

- **Never commit your `.env` file** - it contains sensitive API keys
- The `.gitignore` file is configured to exclude sensitive files
- Always use environment variables for credentials

## 🧪 Testing

Test scripts are available in the `tests/` directory:

```bash
python tests/llm_test.py
```

## 📝 API Endpoints

### `GET /`
Returns the main chat interface.

### `POST /generate`
Generates AI responses based on user input.

**Request Body:**
```json
{
  "message": "Your question here",
  "model": "llama" | "granite" | "mistral"
}
```

**Response:**
```json
{
  "summary": "Summary of the message",
  "sentiment": 85,
  "response": "AI generated response",
  "duration": 1.23
}
```

## 🛠️ Technologies Used

- **Flask**: Web framework
- **LangChain**: LLM integration framework
- **IBM Watsonx AI**: AI model hosting
- **Pydantic**: Data validation
- **Python-dotenv**: Environment variable management

## 📄 License

This project is open source and available under the MIT License.

## 🤝 Contributing

Contributions, issues, and feature requests are welcome! Feel free to check the issues page.

## 👤 Author

**Abdelrahman Elsharkawi**
- GitHub: [@abdelrhmanidk](https://github.com/abdelrhmanidk)

## 🙏 Acknowledgments

- **IBM** for the excellent course "Develop Generative AI Applications: Get Started" on Coursera
- **IBM Watsonx AI** for providing the AI models and platform
- **LangChain** for the excellent LLM integration framework
- **Flask** community for the robust web framework

---

⭐ If you find this project helpful, please consider giving it a star!
