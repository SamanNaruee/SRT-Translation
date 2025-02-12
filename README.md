# Word Translator & Vocabulary Analyzer  

## 📌 Overview  
This project is a **Django REST Framework (DRF) API** that:  
- Translates words using definitions from top global organizations (e.g., Oxford, Merriam-Webster).  
- Provides example sentences and their **contextual meanings** (e.g., metaphors, proverbs).  
- Translates the examples into **Persian (Farsi)** using Persian equivalents.  
- Supports **SRT file uploads** to extract words, rank their difficulty using **CEFR levels (A1-C2)**, and generate a **PDF report** with charts.  

## 🚀 Features  
✅ **Word Translation & Contextual Meaning**  
✅ **Persian Equivalent Translation**  
✅ **SRT File Parsing & Word Extraction**  
✅ **CEFR Vocabulary Level Detection (A1-C2)**  
✅ **PDF Report Generation with Charts**  

---

## 🏗 Project Structure  
wordtranslator/                     # Root project directory
├── api/                            # Main Django app
│   ├── migrations/                 # Database migrations
│   ├── models.py                   # Word storage model
│   ├── views.py                    # API views
│   ├── urls.py                     # API routes
│   ├── serializers.py              # DRF serializers
│   ├── utils/                      # Helper functions
│   │   ├── srt_parser.py           # Extracts text from SRT files
│   │   ├── vocabulary_levels.py    # Determines CEFR difficulty
│   │   └── pdf_generator.py        # Generates PDF reports
│   └── media/                      # Directory for uploaded SRT files
├── static/                         # Static files (if needed)
├── templates/                      # HTML templates (if needed for admin UI)
├── requirements.txt                # Required Python packages
├── manage.py                       # Django management script
└── README.md                       # Project documentation

---
## 🔧 Installation  

### 1️⃣ Clone the Repository  

git clone https://github.com/SamanNaruee/SRT-Translation.git
cd wordtranslator


### 2️⃣ Create a Virtual Environment

python -m venv venv
source venv/bin/activate  # On Windows use: venv\Scripts\activate


### 3️⃣ Install Dependencies

pip install -r requirements.txt


### 4️⃣ Set Up Environment Variables
Create a `.env` file and add API keys:


OXFORD_APP_ID=your_app_id
OXFORD_API_KEY=your_api_key
GOOGLE_TRANSLATE_API_KEY=your_api_key


### 5️⃣ Apply Database Migrations

python manage.py migrate


### 6️⃣ Run the Server

python manage.py runserver


## 🔥 Usage

### 1️⃣ Translate a Word
**Endpoint:** GET `/api/translate/{word}/`

Example Response:

{
    "word": "journey",
    "definition": "An act of traveling from one place to another.",
    "example": "The journey was long and tiring.",
    "persian_translation": "سفر طولانی و خسته‌کننده بود."
}


### 2️⃣ Upload SRT File for Word Analysis
**Endpoint:** POST `/api/upload-srt/`
- Request: Upload .srt file
- Response: JSON with words, difficulty levels

### 3️⃣ Generate Vocabulary Level Report (PDF)
**Endpoint:** GET `/api/generate-pdf/`
- Response: PDF file with charts

## 📊 CEFR Vocabulary Levels
The project categorizes words into six Common European Framework of Reference (CEFR) levels:

| Level | Description |
|-------|-------------|
| A1    | Beginner |
| A2    | Elementary |
| B1    | Intermediate |
| B2    | Upper Intermediate |
| C1    | Advanced |
| C2    | Proficiency |

## 🛠 Technologies Used
- Python 3.x
- Django REST Framework (DRF)
- Requests (for API calls)
- NLTK / SpaCy (for text processing)
- Matplotlib (for charts)
- FPDF / ReportLab (for PDF generation)

## 🤝 Contributing
1. Fork the repository
2. Create a new branch: `git checkout -b feature-name`
3. Commit your changes: `git commit -m "Added new feature"`
4. Push to the branch: `git push origin feature-name`
5. Create a Pull Request

## 📜 License
This project is open-source under the MIT License.

## 📧 Contact
For any issues or contributions, feel free to open a GitHub issue or contact the developer.

Email: samannaruee@gmail.com, narueesaman@gmail.com