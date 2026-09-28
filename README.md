
# 🎤 Oracle APEX Voice Input / Speech-to-Text

## 📌 Overview

This project demonstrates how to implement **Voice Input / Speech-to-Text functionality in Oracle APEX** using JavaScript and the browser's Web Speech API.

The user can click a Voice button, speak through the microphone, and the browser converts the speech into text. The recognized text is then automatically added to an Oracle APEX Page Item.

This is a simple and practical example of integrating **JavaScript and browser-based speech recognition with Oracle APEX**.

---

## 🎯 Objective

The main objective of this implementation is to allow users to enter text into an Oracle APEX application using their voice instead of typing manually.

### Basic Workflow

```text
User
  │
  ▼
Click Voice Button
  │
  ▼
Browser requests Microphone Access
  │
  ▼
User Speaks
  │
  ▼
Web Speech API
  │
  ▼
Speech converted to Text
  │
  ▼
Text added to APEX Page Item
function startSpeechRecognition() {
    var recognition = new webkitSpeechRecognition();
    recognition.lang = 'en-US';
### Java script code page Level
    recognition.onresult = function(event) {
        var result = event.results[0][0].transcript;
        var existingText = document.getElementById('P5_TEXT').value;
        document.getElementById('P5_TEXT').value = existingText + " " + result;
    };

    recognition.start();
}
