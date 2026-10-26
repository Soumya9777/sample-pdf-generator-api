# Sample PDF Generator API

A free starter API that accepts a name and photo and returns a generic PDF marked **SAMPLE DEMO**. It is deliberately not an editable copy of the uploaded ABHA card and does not reproduce official logos, QR codes, numbers, or credential layouts.

## 1. Requirements
- Python 3.10 or newer
- A terminal on your Mac

Check Python:
```bash
python3 --version
```

## 2. Install and run
Open Terminal, move into this folder, then run:

```bash
python3 -m venv .venv
source .venv/bin/activate
python -m pip install --upgrade pip
pip install -r requirements.txt
uvicorn app:app --reload
```

Open this in your browser:
- API home: http://127.0.0.1:8000/
- Interactive API page: http://127.0.0.1:8000/docs

## 3. Generate a PDF in the browser
1. Open `http://127.0.0.1:8000/docs`
2. Expand `POST /generate-pdf`
3. Click **Try it out**
4. Enter a name and select a JPG, PNG, or WEBP photo
5. Click **Execute**
6. Save the PDF response

## 4. Test with curl
```bash
curl -X POST "http://127.0.0.1:8000/generate-pdf" \
  -F "name=Rahul Kumar" \
  -F "photo=@/full/path/to/photo.jpg" \
  --output Rahul_Kumar_sample_demo.pdf
```

Replace `/full/path/to/photo.jpg` with the actual photo path on your computer.

## Endpoint
`POST /generate-pdf`
- `name`: required text, up to 100 characters
- `photo`: required JPG, PNG, or WEBP, maximum 8 MB
- Returns: PDF download

## Notes
- This starter is local-first. Local use is free; online hosting may have free-tier limits and may change.
- Before deploying publicly, add authentication/API keys, rate limits, HTTPS, and a privacy/retention policy. Do not log uploaded images or names.
- Use only images and personal information you have permission to process.
- The supplied ABHA PDF was used only as a layout reference; its official content is not copied into generated output.
