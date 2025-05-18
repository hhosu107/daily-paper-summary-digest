# Daily Paper Summary Digest

Search arXiv with given query, fetch recent papers, summarize it, and send it to your email.

---

### Prompt

Edit `prompt.txt` file.

### Quering & Mail To

Edit `config.yaml` file.

```yaml
- topic: RecSys
  query: (cat:cs.CV OR cat:cs.LG OR cat:cs.AI OR cat:cs.IR) AND ("recommendation" OR "recommender")
  num_papers: 5
  receivers:
    - test@test.com
```

* `topic` is just a verbose title
* `query` will be applied to arXiv API.

---

### Environment Setting

Create a new `.env` file containing:

```
GEMINI_MODEL=models/gemini-2.5-flash-preview-04-17
GEMINI_API_KEY=gemini_api_key
EMAIL_ADDRESS=sender_email@email.com
EMAIL_PASSWORD=gmail_app_password
SMTP_SERVER=smtp.gmail.com
SMTP_PORT=587
PAGE_LIMIT=8
MAX_CONTENT_LENGTH=120000
EVERYDAY_AT=08:00
TIMEZONE=Asia/Seoul
```

### Gmail App Password

See [gmail apppasswords](https://myaccount.google.com/apppasswords).

Remove blanks (16-characters).

### OpenAI API Key

See [API Keys](https://platform.openai.com/api-keys).

---

### Run:

```bash
uv sync
source .venv/bin/activate
nohup python -u entry.py >> output.log 2>&1 &
```

To see logs:

```bash
tail -f output.log
```
