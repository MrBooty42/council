# Council

Ask one question and get one strong answer from two AIs that check each other. Whichever model suits the question leads: Gemini for search-heavy, current, local, photo and long-file questions; Claude for reasoning, writing and advice. The other one fact-checks, or on problems with one right answer, both solve it separately and the answers are compared blind.

**Open the app:** https://mrbooty42.github.io/council/

## How it works
One answer from two AIs. A tiny model picks the power and the lead: Gemini leads search-heavy, current, local, photo and long-file questions; Claude leads reasoning, writing and advice (you can force either in Settings). The other model fact-checks the answer, Gemini always with Google Search, and the lead fixes what's wrong. On math and logic, both solve it separately and the answers are compared blind. Writing and simple questions get one model. Create mode builds docs and slide decks and opens them in Google Docs/Slides or downloads Word/PowerPoint. Reads PDFs, Word, photos and your Google Drive.

Quick is the cheapest: math and logic get one solver thinking harder, and Claude checks without new searches. Standard solves math and logic twice and checks with search. Deep never skips the second model and fact-checks up to two rounds.

**Power:** Auto (default) has a tiny model read each question and pick Economy (Claude Sonnet 5.5) for everyday questions or Max (Claude Opus 5.5) for hard or high-stakes ones. Gemini always runs the model chosen in Settings (Gemini 4 Argon by default), because it costs a fraction of Claude. You can also force Economy or Max.

In Create mode, the plan step sees both models' proposals as A and B in random order, so the best idea wins each part regardless of who wrote it.

Also: PDF, Word, PowerPoint and photo uploads; attach from Google Drive (Docs, Slides, Sheets, any file); save results to Google Docs or Google Slides; Create mode can make a slide deck and download it as PowerPoint; solo mode (one model, much cheaper); a monthly spend tracker; Download for Word; history backup.

## Google Drive setup
One-time, about 10 minutes. It lets the **Drive** button attach files from your Google Drive and lets **Save to Google Docs / Slides** put results there. The app only asks for Google's narrowest Drive permission: it can see files you pick and files it creates, nothing else.

If your files are in a school Google account (like Mizzou's), create the project while signed in to that account and pick **Internal** in step 3; skip step 4. Otherwise use your personal account and **External**.

1. Go to [console.cloud.google.com](https://console.cloud.google.com). In the project picker at the top, click **New project**, name it `Council`, click **Create**, then select it.
2. Turn on two APIs. Open [Google Drive API](https://console.cloud.google.com/apis/library/drive.googleapis.com) and click **Enable**. Then open [Google Picker API](https://console.cloud.google.com/apis/library/picker.googleapis.com) and click **Enable**.
3. Open [Google Auth Platform](https://console.cloud.google.com/auth/overview) and click **Get started**. Enter App name `Council` and your email. For Audience, pick **External**. Enter your email again as the contact, agree, and click **Create**.
4. Go to [Audience](https://console.cloud.google.com/auth/audience). Under **Test users**, click **Add users**, add your own Gmail address, and save.
5. Go to [Clients](https://console.cloud.google.com/auth/clients) and click **Create client**. Pick **Web application** and name it `Council`. Under **Authorized JavaScript origins**, click **Add URI** and enter `https://mrbooty42.github.io`. Click **Create**, then copy the **Client ID** (it ends in `.apps.googleusercontent.com`).
6. Optional: go to [Credentials](https://console.cloud.google.com/apis/credentials), click **Create credentials** → **API key**, and copy it. It turns on Google's own file picker. Schools often block this; without a key, the Drive button shows a simple search list of your Drive instead.
7. In Council, open **Settings**, paste the Client ID (and the API key, if you made one) into the Google fields, and click **Save**. Click **Drive**. The first time, Google asks you to sign in and allow access. If it says the app isn't verified, click **Continue**: it's your own app.

## Privacy
The app is one HTML file that runs in your browser. Your API keys and history are stored only in that browser. Questions go straight from your browser to Anthropic and Google. No other server is involved, and nothing private is stored in this repository.
