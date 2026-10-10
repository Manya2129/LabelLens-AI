# LabelLens AI

LabelLens AI is a Streamlit app that helps users understand packaged food and product labels by analyzing uploaded label photos or text input. It uses Google Gemini to identify ingredients, nutrition details, allergens, additives, and general product concerns in simple language.

The app also supports sending a summarized product analysis to a user's WhatsApp number using Twilio.

## Features

- Upload a product label image in JPG or PNG format
- Analyze product information using Google Gemini AI
- Identify:
  - product name
  - ingredients
  - nutrition information
  - allergens
  - additives and preservatives
  - ingredients users should be aware of
  - overall product assessment
- Chat-based interaction for additional label questions
- Send a short WhatsApp summary to the user

## Tech Stack

- Python
- Streamlit
- Google GenAI SDK
- Twilio API

## Project Structure

- `app.py` – main Streamlit application entry point
- `prompts.py` – system prompts and user-facing message templates
- `requirements.txt` – Python dependencies
- `.streamlit/secrets.toml` – local API credentials and Twilio config

## Setup

1. Clone the repository:

   ```bash
   git clone https://github.com/Manya2129/LabelLens-AI.git
   cd LabelLens-AI
   ```

2. Create and activate a virtual environment:

   ```bash
   python -m venv venv
   ```

   On Windows:

   ```bash
   .\venv\Scripts\activate
   ```

   On macOS/Linux:

   ```bash
   source venv/bin/activate
   ```

3. Install dependencies:

   ```bash
   pip install -r requirements.txt
   ```

4. Add your secrets file:

   Create a file named `.streamlit/secrets.toml` in the project root with the following structure:

   ```toml
   GEMINI_API_KEY = "your_google_gemini_api_key"
   TWILIO_ACCOUNT_SID = "your_twilio_account_sid"
   TWILIO_AUTH_TOKEN = "your_twilio_auth_token"
   TWILIO_WHATSAPP_FROM = "whatsapp:+1234567890"
   TWILIO_CONTENT_SID = "your_twilio_content_template_sid"
   ```

   Replace the example values with your actual API credentials.

## Run the App

Start the Streamlit app:

```bash
streamlit run app.py
```

Then open the local URL shown in the terminal, usually:

```text
http://localhost:8501
```

## How It Works

1. The user enters their name and WhatsApp number during onboarding.
2. They upload a photo of a product label or type a question about it.
3. The app sends the image/text to Google Gemini for analysis.
4. The model returns a clear explanation in beginner-friendly language.
5. The user can optionally send a concise summary to WhatsApp.

## Notes

- The app is designed for understanding packaged food and retail product labels.
- It does not provide medical diagnoses or treatment advice.
- If image text is unclear or unreadable, the app is designed to say so rather than guess.

## License

This project does not currently include a license file. If you plan to distribute or reuse it publicly, add an appropriate open-source license.
