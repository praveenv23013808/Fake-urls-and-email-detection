## Fake Urls And Spam E-mail Detection Using Python

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
## Python Program (Exe file)
```
import re
# Function to detect fake URLs
def is_fake_url(url):
    suspicious_tlds = ['.tk', '.ml', '.ga', '.cf', '.gq']
    suspicious_keywords = ['free', 'login', 'verify', 'bank', 'secure', 'update', 'confirm']

    # Pattern for valid URLs
    regex = re.compile(r'^(http|https)://[a-zA-Z0-9.-]+\.[a-zA-Z]{2,}(/[a-zA-Z0-9#._/?=&-]*)?$')

    if not regex.match(url):
        return True  # Invalid format

    if re.match(r'^(http|https)://\d{1,3}(\.\d{1,3}){3}', url):
        return True  # IP-based URL

    if any(url.endswith(tld) for tld in suspicious_tlds):
        return True

    if any(keyword in url.lower() for keyword in suspicious_keywords):
        return True

    return False

# Function to detect fake emails
def is_fake_email(email):
    disposable_domains = ['tempmail.com', '10minutemail.com', 'mailinator.com']
    regex = re.compile(r'^[a-zA-Z0-9_.+-]+@[a-zA-Z0-9-]+\.[a-zA-Z0-9-.]+$')

    if not regex.match(email):
        return True

    domain = email.split('@')[-1]
    if domain.lower() in disposable_domains:
        return True

    return False


def main():
    while True:
        print("\nChoose an option:")
        print("1. Check URL")
        print("2. Check Email")
        print("3. Exit")

        choice = input("Enter your choice: ")

        if choice == "1":
            url = input("Enter the URL: ")
            print("Result:", "Fake URL ❌" if is_fake_url(url) else "Legit URL ✅")

        elif choice == "2":
            email = input("Enter the Email: ")
            print("Result:", "Fake Email ❌" if is_fake_email(email) else "Legit Email ✅")

        elif choice == "3":
            print("Exiting...")
            break
        else:
            print("Invalid choice. Try again.")

if __name__ == "__main__":
    main()

```
## RESULT:
Two computers were successfully connected in a peer-to-peer network, allowing both to act as client and server by sharing files and sending data without using a centralized server.
