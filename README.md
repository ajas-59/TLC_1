# TLC
**Translating Care Healthcare Project: Multilingual Medical Chatbot via Pivot Translation – work in progress**

> *Selected for development at the 2025 SCAI (Sorbonne Cluster for AI) Franco-Moroccan Research Center Summer School for Sustainable AI for Resource-Constrained Healthcare*
>
> 
> *Referenced by Prof. Wiem Takrouni (dissertation supervisor)*

---

## 📌 Project Summary

**Aim:** Building smarter healthcare assistants for multilingual and underserved communities.

&emsp;This project explores how AI can support multilingual healthcare communication in settings involving low-resource languages like Moroccan Arabic (Darija) and Amazigh. The system uses a **pivot-based approach**: user queries are translated into English, processed using English-language AI models (e.g., QA, triage), and optionally translated back into the original language. This design enables accessibility where native-language models don’t exist.

---

## 💡 Motivation

&emsp;In many multilingual clinical environments, patients speak languages unsupported by AI tools. By routing communication through English, this project enables AI-powered health guidance in low-resource settings.

---

## 🧰 System Architecture

```
User (Darija / Amazigh)
        ↓
Translate → English
        ↓
AI model performs task (e.g., question answering)
        ↓
Translate → Darija (optional)
        ↓
Chatbot response
```

---

## 🧪 Use Case Example

Imagine a patient speaking Moroccan Arabic (Darija) wants to know whether they can take paracetamol with food.

**Input (User question in Darija):**  
> <div dir="rtl">واش نقدر ناخد باراسيتامول مع الماكلة؟</div>  
> *("Can I take paracetamol with food?")*

**Processing:**
1. Translate question to English using MarianMT  
2. Use QA model to analyze medical context  
3. Translate response back to Darija

**Response (Darija):**  
> <div dir="rtl">نعم، باراسيتامول يمكن تناوله مع الطعام.</div>  
> *("Yes, paracetamol can be taken with food.")*

---

## ⚙️ Technologies Used

| Purpose               | Tool / Model                          |
|-----------------------|----------------------------------------|
| Translation           | `Helsinki-NLP/opus-mt-ar-en` + `en-ar` |
| Language Task (QA)    | `deepset/roberta-base-squad2`          |
| Interface             | Gradio                                 |
| Programming Language  | Python                                 |
| Framework             | Hugging Face Transformers              |

---

## 📁 Project Structure

```plaintext
pivot-chatbot/
├── app.py                  # Main Gradio app
├── translate_to_english.py
├── run_qa_english.py
├── translate_to_darija.py
├── requirements.txt
├── README.md
└── data/
    └── sample_context.txt
```

---

## 🚀 Quickstart

```bash
# 1. Install dependencies
pip install -r requirements.txt

# 2. Run the chatbot
python app.py

# 3. Ask questions in Moroccan Arabic
#    → The chatbot processes and returns the answer
```

---

## 📊 Evaluation Strategy

| Component     | Metric     | Notes                              |
|---------------|------------|------------------------------------|
| Translation   | COMET, BERTScore | Human spot-checks included         |
| Task Output   | F1, EM     | Standard QA metrics                |
| Readability   | Human Eval | Measures clarity of final response |

---

<details>
<summary>📎 Additional Information</summary>

### 🧭 Ethical Considerations

- ⚠️ This system is **not a substitute** for professional medical advice.  
- ⚠️ Translation quality may vary; clinical outputs should be reviewed.  
- ⚠️ All assessments are provided for **research and educational use only**.

---

### 🛠 Future Work

- Add summarization and intent classification  
- Improve translation of domain-specific medical terminology  
- Build a multilingual UI with user-selectable language options  
- Add fallback to SQL-based lookup if model output lacks confidence  

---

### 📚 References

<!-- - Hugging Face Transformers-->
<!-- - TICO-19 Dataset-->
<!-- - SQuAD v2 for QA-->
<!-- - Helsinki-NLP MarianMT models-->
</details>

---

## 👩‍💻 About the Author

**Amélie Smith**  
&emsp;MSc student in Computer Science and Linguistics, Sorbonne University  
&emsp;Specialization: Low-Resource Machine Translation & AI for Health  

**Email:** amelie.smith@sorbonne-universite.fr / amelie.laceysmith@gmail.com  
**GitHub:** [github.com/ameliesmith](https://github.com/ameliesmith)  
**LinkedIn:** [Amélie Lacey Smith](https://www.linkedin.com/in/amelie-lacey-smith/)
