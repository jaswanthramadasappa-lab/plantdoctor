# 🌱 PlantDoctor

PlantDoctor is a Streamlit vision chatbot inspired by the MacroSnap project
structure.

## Flow

1. User enters their name and WhatsApp number.
2. User chats with Gemini about plants using text or photos.
3. Gemini stays scoped to plant identification and care.
4. The **Send Care Plan** button summarizes the conversation.
5. Twilio sends that care plan to the user's WhatsApp.

## Files

- `app.py` - Streamlit app, Gemini vision chat, and Twilio send action
- `prompts.py` - system prompt, welcome message, and summary prompt
- `requirements.txt` - Python dependencies
- `.streamlit/secrets.toml.example` - secrets template

## Run

```bash
python -m venv venv
```

Windows PowerShell:

```powershell
Set-ExecutionPolicy -Scope Process -ExecutionPolicy Bypass
.\venv\Scripts\Activate.ps1
pip install -r requirements.txt
```

Copy `.streamlit/secrets.toml.example` to
`.streamlit/secrets.toml`, fill in your Gemini and Twilio credentials, then:

```bash
streamlit run app.py
```

## Twilio WhatsApp template

Create an approved WhatsApp text template with two variables:

- `{{1}}` = user's name
- `{{2}}` = plant care plan

Put its Content SID in `TWILIO_CONTENT_SID`.

## Important

PlantDoctor provides visual estimates, not a guaranteed diagnosis.
