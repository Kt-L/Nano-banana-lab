# Nano Banana Pro | Future Lab Edition 🍌

**A lightweight, single-file interface for the Gemini 3 Pro Image Generation Model.**

**Nano Banana Pro** is a serverless, local-first web application designed for power users who want to experiment with Google's latest Gemini 3 Pro image generation capabilities. It features a "Future Lab" aesthetic and focuses on batch processing, direct local file synchronization, and multimodal inputs.

> **⚠️ Note:** This is a specialized tool that leverages the **File System Access API**. It currently **only works on Chromium-based browsers** (Chrome, Edge, Brave, Opera) on Desktop. Firefox and Safari are not supported.

---

## UI Preview

<p align="center">
  <img src="screenshot.png" alt="Nano Banana Pro UI Interface" width="100%">
</p>

---

## ✨ Key Features

* **⚡ Serverless & Single-File:** The entire app is contained in one `nano.html` file. No Node.js, Python, or Docker required. Just download and run.
* **📂 Direct Disk Sync:** Bypasses the browser's "Download" folder. Connects directly to a local folder on your computer to save generated images and metadata (`.json`) automatically in real-time.
* **🧠 Multimodal Reference Inputs:** Drag and drop reference images to guide the generation (Style Transfer/Composition).
* **🔄 Parallel Execution & Auto-Retry:** Supports batch generation (up to 20 images at once) with built-in exponential backoff and retry logic for API stability.
* **🔐 Bring Your Own Key (BYOK):** Your API keys are stored locally in your browser (LocalStorage) and are used to communicate directly with Google's servers. Keys are never sent to any middleman.
* **🎨 Advanced Workflow:**
* **Key Rotation:** Add multiple API keys; the app cycles through them to manage rate limits.
* **Drag & Drop Sorting:** Organize results visually and manage multiple lists.
* **Lightbox:** High-res zoom and inspection.
* **Auto-Resume:** IndexedDB caching ensures your session is restored if you accidentally refresh.



---

## 🚀 Quick Start

1. **Get an API Key:** You need a Google Gemini API Key with access to the `gemini-3-pro-image-preview` model. Get it here: [Google AI Studio](https://aistudio.google.com/app/apikey).
2. **Download:** Save the `nano.html` file from this repository to your computer.
3. **Run:** Double-click `nano.html` to open it in **Google Chrome** or **Microsoft Edge**.
4. **Authorize:**
* Click **"Select Output Directory"**.
* Choose a folder on your computer where you want images to be saved.
* **Important:** When the browser asks for "Read/Write" permission, click **Allow**.


5. **Generate:** Paste your API key, enter a prompt, and click **Initialize**.

---

## ⚙️ Usage Guide

### 1. Configuration Panel

* **API Key Access:** Paste your Gemini API key. You can add multiple keys; the app will rotate through them automatically for batch jobs.
* **Retry Protocol:** Enable "Auto-Retry" to handle network hiccups or API rate limits automatically.
* **Resolution & Ratio:** Select from standard presets (1K/2K/4K) and aspect ratios (1:1, 16:9, etc.).
* **Batch Count:** Set how many images to generate in parallel (Max 20).

### 2. Reference Input (Multimodal)

* You can influence the generation by providing reference images.
* **Drag & Drop:** Drag images from your desktop into the "Reference Input" zone.
* **Internal Drag:** You can even drag a *generated result* back into the reference zone to iterate on a style.

### 3. Output & Management

* **The Stream:** Generated images appear in the main results panel.
* **Lists:** Create multiple lists (tabs) to organize your generations (e.g., "Architecture", "Character Design").
* **Drag Sorting:** Drag images to reorder them or move them between lists.
* **Import:** Use the "Import Image" button to bring external images into your workspace for organization.

---

## 🛠️ Advanced / Hacking

Since this is a single HTML file, it is extremely easy to modify.

* **Changing the Model:**
The tool is currently hardcoded to use `gemini-3-pro-image-preview`. If Google changes the endpoint name in the future, open `nano.html` in any text editor (Notepad, VS Code), search for `gemini-3-pro-image-preview`, and replace it with the new model name.
* **CSS Customization:**
The `<style>` block at the top of the file contains all the CSS variables (`--primary-grad-start`, etc.). Feel free to tweak the colors to match your preference.

---

## ⚠️ Known Limitations

1. **Browser Compatibility:** Strictly requires a browser that supports the [File System Access API](https://developer.mozilla.org/en-US/docs/Web/API/File_System_Access_API).
* ✅ Chrome, Edge, Opera, Brave (Desktop)
* ❌ Firefox, Safari, Mobile Browsers


2. **Network Requirements:** The tool makes direct `fetch` calls to `generativelanguage.googleapis.com`. Ensure your network environment can access Google services directly.
3. **Permissions:** You must re-confirm directory access every time you completely restart the browser (a security feature of the web platform).

---

## 🔒 Privacy Policy

* **Local Only:** This application runs entirely in your browser.
* **No Analytics:** No tracking scripts or analytics are included.
* **Key Safety:** Your API Keys are stored in `LocalStorage` on your machine. They are sent *only* to Google's official API endpoints.
* **File Access:** The app only has access to the specific folder you explicitly authorize.

---

## ⚖️ Disclaimer

* **Vibe Coding:** This project is a result of vibe coding (developed using AI coding tools) and is provided for reference only.
* **Experimental:** As a "Lab Edition", it is intended for testing and personal use.

---

## 📄 License

This project is open-source and available under the **MIT License**. Feel free to fork, modify, and distribute.