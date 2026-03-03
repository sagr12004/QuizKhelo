\# 🚀 DevQuiz — Web Developer Quiz App



A fully functional, beautifully animated web developer quiz app built with vanilla HTML, CSS and JavaScript.



!\[DevQuiz Banner](https://img.shields.io/badge/DevQuiz-2026-00ffe0?style=for-the-badge\&logo=javascript)

!\[License](https://img.shields.io/badge/License-MIT-ff2d78?style=for-the-badge)

!\[Status](https://img.shields.io/badge/Status-Live-00ff88?style=for-the-badge)



---



\## ✨ Features



\- 🎯 8 Web Dev topics — HTML, CSS, JavaScript, React, APIs, Git, TypeScript, Node.js

\- ⚡ 10 questions per quiz with 30 second timer per question

\- 📊 Live score tracking with animated dots

\- 📧 Result email sent automatically to user's Gmail via EmailJS

\- 📋 Full answer review sheet on results page

\- 🎉 Confetti animation for good scores

\- 📱 Fully responsive on mobile

\- 🌐 Questions fetched from Open Trivia DB API (free, no key needed)

\- 💾 Local fallback questions if API is offline

\- 📊 Google Sheets integration to track all quiz attempts



---



\## 📁 Project Structure

```

webdev-quiz/

│

├── index.html          → Landing page (name + gmail form)

├── README.md           → This file

│

└── pages/

&nbsp;   ├── topics.html     → Topic selection (8 animated cards)

&nbsp;   ├── quiz.html       → Quiz with timer + live feedback

&nbsp;   └── result.html     → Score ring + email + answer review

```



---



\## 🛠️ Tech Stack



| Technology | Purpose |

|------------|---------|

| HTML5 + CSS3 | Structure and styling |

| Vanilla JavaScript | Logic and interactivity |

| Open Trivia DB API | Free quiz questions |

| EmailJS | Send result emails (free) |

| Google Apps Script | Save data to Google Sheets |

| Google Fonts | Syne + Space Mono typography |



---



\## ⚙️ Setup \& Configuration



\### 1. Clone the repo

```bash

git clone https://github.com/YOUR\_USERNAME/webdev-quiz.git

cd webdev-quiz

```



\### 2. Run locally

```bash

\# Using Python

python -m http.server 3000



\# Then open

http://localhost:3000

```



\### 3. Configure EmailJS

1\. Sign up free at \[emailjs.com](https://emailjs.com)

2\. Create a Gmail service

3\. Create an email template with these variables:

&nbsp;  - `{{to\_name}}` `{{to\_email}}` `{{topic}}` `{{score}}`

&nbsp;  - `{{percentage}}` `{{time\_taken}}` `{{verdict}}` `{{answer\_sheet}}`

4\. Open `pages/result.html` and replace:

```javascript

const EMAILJS\_PUBLIC\_KEY  = 'your\_public\_key';

const EMAILJS\_SERVICE\_ID  = 'your\_service\_id';

const EMAILJS\_TEMPLATE\_ID = 'your\_template\_id';

```



\### 4. Configure Google Sheets

1\. Create a new Google Sheet

2\. Go to Extensions → Apps Script

3\. Paste this code:

```javascript

function doPost(e) {

&nbsp; var sheet = SpreadsheetApp.getActiveSpreadsheet().getActiveSheet();

&nbsp; var data = JSON.parse(e.postData.contents);

&nbsp; sheet.appendRow(\[data.name, data.email, data.topic, data.score, data.percentage, data.time, data.date, data.answers]);

&nbsp; return ContentService.createTextOutput('ok');

}

```

4\. Deploy as Web App → copy URL → paste in `pages/quiz.html`



---



\## 🌐 Live Demo



👉 \[View Live Demo]( https://sagr12004.github.io/QuizKhelo/)



---



\## 📧 Email Features



\- Result email sent automatically after quiz

\- Contains: name, topic, score, accuracy, time, verdict, full answer sheet

\- Powered by EmailJS free tier (200 emails/month)

\- Resets every month automatically



---



\## 📊 Google Sheets Tracking



Every quiz attempt saves:

\- Name, Gmail, Topic selected

\- Score and percentage

\- Time taken and date

\- Full answer sheet



---



\## 🎨 Design



\- Dark theme with animated grid background

\- Floating color orbs

\- Glassmorphism cards

\- Syne + Space Mono fonts

\- Smooth CSS animations throughout

\- Confetti on good scores



---



\## 👨‍💻 Built By



\*\*Sagar\*\* — DevQuiz 2026



\- Questions: \[Open Trivia DB](https://opentdb.com)

\- Email: \[EmailJS](https://emailjs.com)

\- Deploy: \[GitHub Pages](https://pages.github.com)



---



\## 📄 License



MIT License — free to use, modify and share.

