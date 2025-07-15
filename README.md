## Fake Urls And Spam E-mail Detection

### NAME : PRAVEEN V

### REGISTER NO : 212222233004

## AIM:
A web-based fake URL and email detection tool hosted on Netlify.

## PROBLEM STATEMENT:
To create ATM System software that will meet the needs of the applicant and help them to withdraw money,deposit.
# Fake URL Detector

A web application to detect fake URLs and emails, built with [Bolt](https://boltcss.com) and hosted on [Netlify](https://resplendent-swan-61ccee.netlify.app/).

## Features
- Detects phishing or suspicious links
- Identifies fake email patterns
- Responsive UI for desktop and mobile

## Live Demo
🔗 https://resplendent-swan-61ccee.netlify.app/

## Technologies Used
- HTML/CSS/JavaScript
- Bolt CSS
- Netlify Hosting

## Program(Front End)
```

---

### ✅ `index.html` (basic example, update if you have a custom version)

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Fake URL & Email Detector</title>
  <link rel="stylesheet" href="style.css" />
</head>
<body>
  <h1>Fake URL & Email Detector</h1>
  <input type="text" id="inputField" placeholder="Enter URL or Email" />
  <button onclick="validateInput()">Check</button>
  <p id="result"></p>

  <script src="script.js"></script>
</body>
</html>

```
## Program(Back End)
```
function validateInput() {
  const input = document.getElementById("inputField").value.trim();
  const result = document.getElementById("result");

  const emailRegex = /^[^\s@]+@[^\s@]+\.[^\s@]+$/;
  const urlRegex = /^(https?:\/\/)?([\w\-]+\.)+[a-z]{2,6}(\/[\w\-]*)*\/?$/i;

  if (emailRegex.test(input)) {
    result.textContent = "✅ Valid email address";
    result.style.color = "green";
  } else if (urlRegex.test(input)) {
    result.textContent = "✅ Valid URL";
    result.style.color = "green";
  } else {
    result.textContent = "❌ Invalid or suspicious input";
    result.style.color = "red";
  }
}

```
## RESULT:
Two computers were successfully connected in a peer-to-peer network, allowing both to act as client and server by sharing files and sending data without using a centralized server.
