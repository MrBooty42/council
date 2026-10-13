# Council

Ask one question and two AIs work it out. Claude and Gemini each answer on their own with web search, check each other's work, fix only what matters, then merge into one final answer that lists where they still disagree and how confident they are.

**Open the app:** https://mrbooty42.github.io/council/

## How it works
1. **Opening:** both models answer independently.
2. **Review:** each one checks the other's answer, agrees with what's right, and flags only problems that matter (including weak sources).
3. **Revise:** each takes the good points and improves its answer. Skipped when neither review finds a real problem. Quick runs at most one round, Standard two, Deep three, and it stops as soon as they agree on the substance.
4. **Verdict:** one model merges the best of both into a single answer. It favors a few strong primary sources over many weak ones, and the source list shows only what the answer actually cites.

## Create mode
Switch the toggle from **Ask** to **Create** to make something instead of asking a question: a study guide, a paper outline, a business plan, a pitch.
1. **Ideas:** both models pitch a short outline.
2. **Plan:** one plan takes the better idea for each part and gives each part one writer.
3. **Write:** each model writes only its own parts, at the same time, so the work is paid for once.
4. **Check:** each checks the other's parts and fixes only real problems. Quick skips this; Deep adds more research per part.

Pick **Make: Document or Slides** and **Then: Open in Google / Download Word/PowerPoint / Just show it**. With Open in Google, a tab opens when you click Create and turns into the finished Google Doc or Slides deck when it's done. No copying and pasting.

## Finding your own files
Optional, in Settings: let the council search your whole Google Drive (read-only) and/or one folder on your Mac. When your own notes, syllabus, prices or drafts would help, a cheap model searches by keyword, picks up to 3 files and attaches them; the answer shows which files it opened. Turn it off per question with the **My files** switch. It can read, never change or delete. Searching all of Drive needs wider Google permission than the Drive button, so Google shows an "unverified app" warning and may ask you to sign in again weekly.

**Power:** Auto (default) has a tiny model read each question and pick Economy (Claude Sonnet 5.5 + Gemini 3.8 Flash) for everyday questions or Max (Claude Opus 5.5 + Gemini 4 Argon) for hard or high-stakes ones. You can also force Economy or Max.

Also: PDF, Word, PowerPoint and photo uploads; attach from Google Drive (Docs, Slides, Sheets, any file); save results to Google Docs or Google Slides; Create mode can make a slide deck and download it as PowerPoint; solo mode (one model, much cheaper); a monthly spend tracker; Download for Word; history backup.

## Google Drive setup
One-time, about 10 minutes. It lets the **Drive** button attach files from your Google Drive and lets **Save to Google Docs / Slides** put results there. The app only asks for Google's narrowest Drive permission: it can see files you pick and files it creates, nothing else.

Use your personal Google account. A school account (like Mizzou's) may block apps its admins haven't approved.

1. Go to [console.cloud.google.com](https://console.cloud.google.com). In the project picker at the top, click **New project**, name it `Council`, click **Create**, then select it.
2. Turn on two APIs. Open [Google Drive API](https://console.cloud.google.com/apis/library/drive.googleapis.com) and click **Enable**. Then open [Google Picker API](https://console.cloud.google.com/apis/library/picker.googleapis.com) and click **Enable**.
3. Open [Google Auth Platform](https://console.cloud.google.com/auth/overview) and click **Get started**. Enter App name `Council` and your email. For Audience, pick **External**. Enter your email again as the contact, agree, and click **Create**.
4. Go to [Audience](https://console.cloud.google.com/auth/audience). Under **Test users**, click **Add users**, add your own Gmail address, and save.
5. Go to [Clients](https://console.cloud.google.com/auth/clients) and click **Create client**. Pick **Web application** and name it `Council`. Under **Authorized JavaScript origins**, click **Add URI** and enter `https://mrbooty42.github.io`. Click **Create**, then copy the **Client ID** (it ends in `.apps.googleusercontent.com`).
6. Go to [Credentials](https://console.cloud.google.com/apis/credentials) and click **Create credentials** → **API key**. Copy the key. Optional but tidy: click **Edit API key**, choose **Restrict key**, tick **Google Picker API**, and save.
7. In Council, open **Settings**, paste the Client ID and the API key into the Google fields, and click **Save**. Click **Drive**. The first time, Google asks you to sign in and allow access. If it says the app isn't verified, click **Continue**: it's your own app.

## Privacy
The app is one HTML file that runs in your browser. Your API keys and history are stored only in that browser. Questions go straight from your browser to Anthropic and Google. No other server is involved, and nothing private is stored in this repository.
