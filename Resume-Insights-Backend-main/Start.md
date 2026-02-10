# 🚀 Resume Insights Backend - Quick Start Guide

यह guide आपको शुरुआत से लेकर server run करने तक की सभी commands देगा।

---

## 📋 Requirements (जरूरी चीजें)

- Python 3.7 या उससे ऊपर
- pip (Python package installer)
- Internet connection (dependencies download करने के लिए)

---

## 🛠️ Installation & Setup (कदम-दर-कदम)

### Step 1: Python Version Check करें
```bash
python3 --version
```
या
```bash
python --version
```

**Expected Output:** `Python 3.x.x` (x कोई भी version हो सकती है 7 या अधिक)

---

### Step 2: Project Directory में जाएं

Terminal खोलें और project folder में navigate करें:

```bash
cd /Users/jitendrayadav/Downloads/Resume-Insights-Backend-main
```

**Note:** अपने computer पर correct path use करें।

---

### Step 3: Dependencies Install करें

```bash
pip install -r requirements.txt
```

या अगर `pip3` use करना पड़े:

```bash
pip3 install -r requirements.txt
```

**यह step में क्या होगा:**
- FastAPI और Uvicorn install होंगे
- PDF/DOCX processing के लिए libraries install होंगी
- Machine learning models download होंगी
- सभी dependencies automatically install होंगी

**Time:** लगभग 3-5 मिनट (internet speed पर depend करता है)

**Important:** अगर कोई error आए, तो उसे note कर लें और आगे बताएं।

---

### Step 4: Server Start करें

Dependencies install हो जाने के बाद, server चलाएं:

```bash
uvicorn main:app --host 127.0.0.1 --port 8000 --reload
```

**Command का मतलब:**
- `uvicorn` - Server runner
- `main:app` - main.py file में app instance
- `--host 127.0.0.1` - Local host पर run करें
- `--port 8000` - Port number 8000 use करें
- `--reload` - Auto-reload enabled (code change पर automatically restart)

---

### Step 5: Server Start होने का Verification

Server start होने पर आपको यह message दिखना चाहिए:

```
INFO:     Will watch for changes in these directories: ['/path/to/project']
INFO:     Uvicorn running on http://127.0.0.1:8000 (Press CTRL+C to quit)
INFO:     Started reloader process [XXXX] using WatchFiles
INFO:     Started server process [XXXX]
INFO:     Waiting for application startup.
INFO:     Application startup complete.
```

यह message दिखने पर server successfully start हो गया है! 🎉

---

## 🌐 Server Access करें

### API Documentation (Interactive):
```
http://127.0.0.1:8000/docs
```

### Alternative Documentation:
```
http://127.0.0.1:8000/redoc
```

### OpenAPI Schema:
```
http://127.0.0.1:8000/openapi.json
```

**Browser में जाकर:** यह URLs copy करके browser में paste करें और Enter दबाएं।

---

## 📡 Available API Endpoints

### 1. Upload Resume
- **Method:** POST
- **URL:** `http://127.0.0.1:8000/upload-resume`
- **Purpose:** Resume file (PDF/DOCX) upload करना
- **Response:** Extracted text और session ID

### 2. Submit Job Description
- **Method:** POST
- **URL:** `http://127.0.0.1:8000/submit-job`
- **Purpose:** Job description submit करना
- **Response:** Success message और session ID

### 3. Generate Detailed Report
- **Method:** POST
- **URL:** `http://127.0.0.1:8000/detailed-report`
- **Purpose:** Resume और job description का detailed matching report generate करना
- **Response:** Complete ATS match report with scores और recommendations

---

## 🧪 Testing the API

आप browser में `http://127.0.0.1:8000/docs` खोलकर interactive API testing कर सकते हैं।

**Swagger UI में:**
1. कोई भी endpoint पर click करें (POST /upload-resume जैसे)
2. "Try it out" button click करें
3. Required information fill करें
4. "Execute" button press करें
5. Response देखें

---

## 🛑 Server को Stop करना

Server को बंद करने के लिए terminal में:

```
CTRL + C
```

या Cmd key press करके C दबाएं (Mac पर)।

---

## ❌ Common Issues और Solutions

### Issue 1: `python3: command not found`
**Solution:** Python install नहीं है। Python 3.7+ install करें।
```bash
# Check करें
which python3
```

### Issue 2: `pip: command not found`
**Solution:** pip install नहीं है।
```bash
# Try करें
python -m pip install -r requirements.txt
```

### Issue 3: Port 8000 already in use
**Error:** `Address already in use`

**Solution 1:** Different port use करें:
```bash
uvicorn main:app --host 127.0.0.1 --port 8001 --reload
```

**Solution 2:** पहले से running process kill करें:
```bash
# Mac/Linux पर
lsof -ti:8000 | xargs kill -9

# फिर दोबारा server start करें
uvicorn main:app --host 127.0.0.1 --port 8000 --reload
```

### Issue 4: `spaCy model 'en_core_web_sm' not found`
**Solution:** Model manually download करें:
```bash
python -m spacy download en_core_web_sm
```

### Issue 5: Permission denied errors
**Solution:** sudo use करें (Mac/Linux पर):
```bash
sudo pip3 install -r requirements.txt
```

---

## 📝 Quick Command Summary

**पूरी process एक साथ:**

```bash
# 1. Navigate to project
cd /Users/jitendrayadav/Downloads/Resume-Insights-Backend-main

# 2. Install dependencies
pip install -r requirements.txt

# 3. Start server
uvicorn main:app --host 127.0.0.1 --port 8000 --reload
```

**Server access:**
- Docs: http://127.0.0.1:8000/docs
- Redoc: http://127.0.0.1:8000/redoc

---

## 🔄 Next Time Use (अगली बार use करने के लिए)

अगली बार जब project use करना हो, तो सिर्फ यह command run करें:

```bash
cd /Users/jitendrayadav/Downloads/Resume-Insights-Backend-main
uvicorn main:app --host 127.0.0.1 --port 8000 --reload
```

**Note:** Dependencies पहले ही install हैं, तो सिर्फ Step 2 (server start) करना है।

---

## 📚 Additional Resources

- **FastAPI Documentation:** https://fastapi.tiangolo.com/
- **Uvicorn Documentation:** https://www.uvicorn.org/
- **spaCy Documentation:** https://spacy.io/usage

---

## ✨ Features

- ✅ Resume और Job Description matching
- ✅ ATS (Applicant Tracking System) compatible
- ✅ Detailed matching scores और recommendations
- ✅ PDF और DOCX file support
- ✅ Real-time processing
- ✅ Interactive API documentation

---

## 🆘 Need Help?

अगर कोई problem आए या कुछ समझ न आए, तो:
1. Error message को properly copy करें
2. Terminal output screenshot लें
3. विस्तार से describe करें कि क्या हो रहा है

---

## 📄 License

MIT License - See LICENSE.txt for details

---

**Happy Coding! 🎉**

Last Updated: January 2025

