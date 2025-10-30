<h1 align="center">🧠 README Genie — Automated README Generator</h1>

<p align="center">
  <b>A smart AI-powered README generator built using <a href="https://n8n.io/">n8n</a> that creates beautiful README.md files and commits them automatically into your GitHub repository.</b>
</p>

---

## ✨ Features

- 📝 **Generates Stunning README.md Files** – Clean, structured and aesthetic Markdown with emojis.
- 🤖 **AI Content Generation** – Uses Google Gemini Chat Model to create meaningful descriptions.
- 🔄 **Automated GitHub Commit** – Creates & pushes README.md directly into the repo.
- 📁 **Repository Parsing** – Reads project file structure and uses it inside README.
- 🧩 **Fully Customizable** – Add project name, features, tech stack, etc., dynamically.

---

## ⚙️ Workflow Overview (n8n)

<p align="center">
  <img src="assets/workflow.png" alt="n8n Workflow" width="800"/>
</p>

<p align="center"><i>The workflow gathers repo info → processes via AI → generates README → commits to GitHub.</i></p>

---

## 🖼️ Example Output

```md
🌟 Project Name: Awesome App

🚀 Description:
A modern and scalable project built using cutting-edge technologies.

📂 Project Structure:
- src/
- components/
- README.md (auto-generated)
---
📌 Author

👩‍💻 Developed by Akshitha Reddy
⭐ If you like this project, don’t forget to star the repo!

