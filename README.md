# EmotiText — เกมทายอารมณ์จากข้อความ
**NLP Emotion Analysis Demo | HTML + CSS + JavaScript**

---

## 📁 โครงสร้างไฟล์

```
emotitext/
├── index.html    ← หน้าหลัก (เปิดไฟล์นี้ใน Browser)
├── style.css     ← สไตล์ทั้งหมด
├── nlp.js        ← NLP Engine (Tokenizer, Lexicon, Classifier)
├── app.js        ← UI Controller
└── README.md     ← คู่มือนี้
```

---

## 🚀 วิธีรันใน VS Code

### วิธีที่ 1: Live Server (แนะนำ)
1. ติดตั้ง Extension **Live Server** ใน VS Code
2. คลิกขวาที่ `index.html` → **Open with Live Server**
3. เปิด Browser ที่ `http://127.0.0.1:5500`

### วิธีที่ 2: เปิดตรง
- ดับเบิลคลิก `index.html` เพื่อเปิดใน Browser โดยตรง

---

## 🧠 NLP Pipeline (ตามรายงาน)

| ขั้นตอน | รายละเอียด | เครื่องมือจริง |
|---------|-----------|---------------|
| Step 1: Text Preprocessing | Tokenization + Stopword Removal | PyThaiNLP |
| Step 2: Feature Extraction | TF-IDF / Bag of Words weighting | scikit-learn |
| Step 3: Emotion Classification | Naive Bayes / SVM scoring | scikit-learn |

---

## 🎭 อารมณ์ที่จำแนกได้

| อารมณ์ | อีโมจิ | ตัวอย่างคำ |
|--------|-------|----------|
| สุข | 😄 | ดีใจ, สนุก, ผ่าน, happy |
| เศร้า | 😔 | เหนื่อย, ไม่ไหว, เศร้า, sad |
| โกรธ | 😠 | โกรธ, รำคาญ, เกลียด, angry |
| กลัว | 😨 | กลัว, กังวล, วิตก, scared |
| เฉย ๆ | 😐 | เฉย, โอเค, ธรรมดา, fine |

---

## 📚 Language Resources (ตามรายงาน)
- **Emotion Lexicon**: คลังคำศัพท์แสดงอารมณ์ภาษาไทย+อังกฤษ (ใน `nlp.js`)
- **Stopword List**: คำหยุดภาษาไทย+อังกฤษ (ใน `nlp.js`)
- **Ambiguity Patterns**: รูปแบบข้อความกำกวม เช่น คำประชด, การปฏิเสธ
- **Document Clusters**: 5 กลุ่มอารมณ์ตาม Document Clustering

---

## 📎 References
1. [Emotion Detection from Text using NLP and Neural Networks](https://ijisae.org/index.php/IJISAE/article/view/4707)
2. [Text-based Emotion Recognition using Machine Learning](https://www.propulsiontechjournal.com/index.php/journal/article/view/9126)
3. [Text-based Emotion Detection: A Review](https://journal.nielit.edu.in/index.php/01/article/view/101)

---

## ⚙️ Python Implementation (ขยายต่อ)

สำหรับ implementation จริงด้วย Python ให้ติดตั้ง:

```bash
pip install pythainlp scikit-learn nltk
```

```python
from pythainlp.tokenize import word_tokenize
from pythainlp.corpus.common import thai_stopwords
from sklearn.naive_bayes import MultinomialNB
from sklearn.feature_extraction.text import TfidfVectorizer

# 1. Tokenize
text = "วันนี้เหนื่อยมากเลย ไม่ไหวแล้ว"
tokens = word_tokenize(text, engine='newmm')

# 2. Remove stopwords
stop = thai_stopwords()
filtered = [t for t in tokens if t not in stop]

# 3. Feature Extraction + Classification (ต้องใช้ dataset จาก references)
# ... train Naive Bayes / SVM model
```
