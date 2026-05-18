# Google Calendar OAuth Setup — Step by Step

## 1. Create a Google Cloud Project

1. Go to **https://console.cloud.google.com/**
2. At the top, click the project dropdown (it may say "Select a project")
3. Click **"NEW PROJECT"**
4. Give it a name, e.g. `Espanlava Calendar`
5. Click **CREATE**
6. Wait a few seconds, then make sure your new project is selected in the top dropdown

---

## 2. Enable Google Calendar API

1. In the left sidebar, click **"APIs & Services" → "Library"**
2. In the search bar, type: `Google Calendar API`
3. Click on **"Google Calendar API"** in the results
4. Click the blue **"ENABLE"** button
5. Wait for it to finish enabling

---

## 3. Configure OAuth Consent Screen

1. In the left sidebar, click **"APIs & Services" → "OAuth consent screen"**
2. Choose **"External"** (this lets any Google user sign in)
3. Click **"CREATE"**
4. Fill in the required fields:
   - **App name**: `Espanlava Calendar` (or anything you want)
   - **User support email**: pick your Gmail address from the dropdown
   - **Developer contact information**: enter your email address
5. Click **"SAVE AND CONTINUE"**
6. On the **Scopes** page, click **"ADD OR REMOVE SCOPES"**
   - In the filter, search: `calendar.events`
   - Check the box for: `.../auth/calendar.events`
   - Click **"UPDATE"**
   - Click **"SAVE AND CONTINUE"**
7. On the **Test users** page, click **"ADD USERS"**
   - Enter your own Gmail address
   - Click **"ADD"**
   - Click **"SAVE AND CONTINUE"**
8. On the summary page, click **"BACK TO DASHBOARD"**

---

## 4. Create OAuth Client ID

1. In the left sidebar, click **"APIs & Services" → "Credentials"**
2. Click **"+ CREATE CREDENTIALS"** at the top
3. Choose **"OAuth client ID"**
4. For **Application type**, select: **"Web application"**
5. Give it a name, e.g. `Espanlava Calendar Web`
6. Under **"Authorized JavaScript origins"**, click **"+ ADD URI"**
   - Add: `https://espanlava-calendar.vercel.app`
   - (Optional) Also add: `http://localhost` if you want to test locally too
7. Click **"CREATE"**
8. A popup appears with your **Client ID** and **Client Secret**
   - **Copy the Client ID** (looks like: `123456789-abc123def456.apps.googleusercontent.com`)
   - Click **"OK"**

---

## 5. Paste Client ID into your Calendar App

1. Open your live site: **https://espanlava-calendar.vercel.app**
2. In the **"Client ID"** field at the top, paste the Client ID you copied
3. In the **"Kalenteri ID"** field, type: `primary`
4. Click **"🔗 Yhdistä"**
5. Google will ask you to sign in and authorize the app
6. Click **"Allow"**

Done! Now when you save an event, it will also appear in your Google Calendar.
