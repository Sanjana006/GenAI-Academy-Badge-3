# 🧠 Badge 3: Building GenAI Apps with Gemini, Streamlit, and Cloud Run

After earning **Badge 2**, I wasn’t just excited — I was **hooked** 🤩. **Badge 3** felt like unlocking the next level in my GenAI journey 🎮. But this time, it wasn’t just about experimenting with prompts — it was about building **real AI apps** that do something.

With tools like **Streamlit** 🖼️, **Cloud Run** 🚀, and Google’s powerful **Gemini API** 💡, I dove into the backend-to-frontend world of GenAI. From writing `cURL` commands to deploying live apps, each course challenged me in new ways — and honestly, I had a blast 💥.

---

## 📚 Course Highlights

### 🌐 Course 1: Getting Started with the Gemini API in Vertex AI with cURL
- Explored how RESTful APIs work with Gemini
- Learned to:
  - Authenticate using an access token
  - Formulate a request body with a prompt
  - Send POST requests to the Gemini endpoint using `cURL`

💡 **Key Insight**: Understanding what’s happening under the hood — before jumping into SDKs — gave me much better control and appreciation of how AI models respond.

---

### 🔍 Course 2: Introduction to Function Calling with Gemini
- Implemented **function calling** to allow AI to respond with structured actions.
- Defined a function like this:
```json
{
  "name": "get_flight_info",
  "parameters": {
    "type": "object",
    "properties": {
      "destination": {"type": "string"},
      "departure_date": {"type": "string"}
    }
  }
}
```
- Gemini inferred **when to call** the function based on user prompts.

🧠 Felt like teaching AI how to think structurally — perfect for building booking systems or intelligent support bots.

---

### ⚙️ Course 3: Getting Started with Google Generative AI Using the Gen AI SDK
- Used the **Gen AI SDK** to simplify integration and experimentation.

```python
from vertexai.preview.generative_models import GenerativeModel

model = GenerativeModel("gemini-pro")
response = model.generate_content("Explain the difference between AI and ML.")
print(response.text)
```

💡 SDK made everything cleaner and faster. More building, less setup.

---

### 🖼️ Course 4: Utilize Streamlit with Cloud Run and the Gemini API
This was the fun part — I built and deployed a full **Streamlit app** powered by Gemini!

#### ✅ What I Learned:
- Build a minimal Streamlit UI
- Connect it to Gemini using Vertex AI SDK
- Create a Docker image
- Push to Artifact Registry
- Deploy to Cloud Run

#### 🛠️ Streamlit Code (`app.py`):
```python
import streamlit as st
from vertexai.preview.generative_models import GenerativeModel

model = GenerativeModel("gemini-pro")

st.title("Gemini Chatbot")
user_prompt = st.text_input("Ask me anything:")
if st.button("Send"):
    response = model.generate_content(user_prompt)
    st.write(response.text)
```

#### 📦 Dockerfile:
```Dockerfile
FROM python:3.10
WORKDIR /app
COPY . .
RUN pip install -r requirements.txt
EXPOSE 8501
CMD ["streamlit", "run", "app.py", "--server.port=8501", "--server.address=0.0.0.0"]
```

#### 🚀 Deploy Commands:
```bash
gcloud builds submit --tag <region>-docker.pkg.dev/<project>/gemini-streamlit/gemini-app
gcloud run deploy gemini-app --image <above_image> --platform managed --region <region> --allow-unauthenticated
```

🖥️ **Live Gemini App**: Deployed successfully to Cloud Run with interactive Streamlit UI.

---

### 🎯 Course 5: Develop GenAI Apps — Challenge Lab
No instructions — just me and my skills. I rebuilt the Streamlit app, added UX polish, rebuilt the Docker image, and deployed everything again from scratch.

#### ✅ Added Features:
- Loading spinner
- Error handling
- Better UI with Markdown and styling

🧠 The final challenge showed how far I’ve come. I’m now comfortable going from concept to cloud-deployed app!

---

## 🥳 Final Thoughts
Wow, what a journey **Badge 3** has been! 🎉

Each badge marks a new chapter in growth, and I’m so excited to have you along for the ride 🎢

- 🔗 [Badge 1: Prompt Design in Vertex AI](https://github.com/Sanjana006/GenAI-Academy-Badge-1)
- 🔗 [Badge 2: Building Real-World AI Applications with Gemini & Imagen](https://github.com/Sanjana006/GenAI-Academy-Badge-2)

Let’s connect and collaborate:
📎 [LinkedIn](https://www.linkedin.com/in/sanjana-nathani-26a42727b/) *(Replace with your actual profile)*

---

## 🙌 Thank You!
Thanks to **Google Cloud** and **Hack2Skill** for making this journey possible.

> Keep learning. Keep experimenting. Most importantly — **keep having fun**! 💡🔥

---

### 🏷️ Tags
`#GenAIExchange` `#GenAIAcademy` `#GeminiAPI` `#VertexAI` `#Streamlit` `#CloudRun` `#Docker` `#AIJourney`
