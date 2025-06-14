Steps to Run and Deploy News Chatbot App
1. Create Files
Create and organize the following files in your project folder:

📁 news-chatbot/
├── main.py                        # Main Streamlit chatbot app
├── .env                          # Store your OpenAI API key (don't upload to GitHub)
├── requirements.txt              # List of required packages
├── .gitignore                    # Add `.env`, `__pycache__/`, `.ipynb_checkpoints/`
├── notebooks/
│   ├── data_collection.ipynb     # Jupyter Notebook for scraping news
│   ├── preprocessing.ipynb       # Preprocess/split text into chunks
│   ├── vector_db_setup.ipynb     # Create & store vectors in FAISS
│   └── test_queries.ipynb        # Test chatbot logic separately
2. Add OpenAI Key to `.env`
OPENAI_API_KEY=your-openai-api-key-here
3. In `app.py`, load `.env`
from dotenv import load_dotenv
import os

load_dotenv()
api_key = os.getenv("OPENAI_API_KEY")
4. Install All Requirements Locally
pip install -r requirements.txt

Example contents of requirements.txt:
streamlit
openai
langchain
faiss-cpu
beautifulsoup4
requests
python-dotenv
notebook
5. Test Locally
streamlit run app.py

Use Jupyter Notebooks in `notebooks/` for testing individual modules.
6. Push to GitHub
Upload all files except `.env`:
- Add `.env` to `.gitignore`
- Push app.py, notebooks/, requirements.txt, etc.
7. Deploy on Streamlit Cloud
- Go to: https://streamlit.io/cloud
- Log in with GitHub
- Click 'New app'
- Choose your repo and set app.py as the main file
8. Add API Key in Streamlit Cloud
In Advanced Settings > Secrets, add:
OPENAI_API_KEY = your-api-key
9. Click 'Deploy'
Your app will go live at:
https://chatbot-bpt2ywwbvpysh6xuhbpcip.streamlit.app/
