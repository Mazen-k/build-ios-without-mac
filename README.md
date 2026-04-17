# ios-build-without-mac

Guide for installing **Flutter** and **React Native** apps on iOS without using a Mac.

---

## What this does

This method lets you build an iOS `.ipa` file using **GitHub Actions**, then install it on an iPhone from a Windows PC.

It can be used for:

* **Flutter apps**
* **React Native apps**

No Mac required.

---

## Requirements

Before starting, install the following tools on your computer:

* **iTunes**
* **[Plume Impactor](https://github.com/CLARATION/Impactor/releases/download/v2.2.3/Impactor-windows-x86_64-setup.exe)**

You will also need:

* A **Flutter** or **React Native** project
* A **GitHub account**
* An **iPhone**
* A **USB cable**

---

## Important Notes

* This method is mainly for **testing / personal use**
* The installed app usually **expires every 7 days**
* You must reinstall it every 7 days
* You may need to trust the developer profile on the iPhone
* You may need to enable Developer Mode
* The GitHub Actions workflow is different for **Flutter** and **React Native**, so make sure you use the correct YAML file for your project

---

# Step 1 — Upload Your Project to GitHub

Create a GitHub repository and upload your Flutter or React Native project.

### Option A — Using Git / Terminal

```bash
git init
git add .
git commit -m "Initial commit"
git branch -M main
git remote add origin YOUR_REPOSITORY_URL
git push -u origin main
```

### Option B — Using GitHub Desktop

1. Install **GitHub Desktop**
2. Open GitHub Desktop
3. Click **Add Existing Repository**
4. Select your project folder
5. Click **Publish Repository**
6. Choose a repository name
7. Upload it to GitHub

GitHub Desktop is easier if you do not want to use terminal commands.

---

# Step 2 — Add the GitHub Actions Workflow

1. Open your GitHub repository
2. Go to **Actions**
3. Click **New workflow**
4. Choose **set up a workflow yourself**
5. Paste the correct YAML file
6. Commit the file

Use:

* the **Flutter workflow** for Flutter projects
* the **React Native workflow** for React Native projects

This workflow will build your iOS app and generate an `.ipa` file.

---

# Step 3 — Run the Workflow

1. Go to the **Actions** tab
2. Select the workflow
3. Click **Run workflow**
4. Wait for it to finish

Once complete, GitHub will upload the `.ipa` file as an artifact.

---

# Step 4 — Download the IPA File

1. Open the completed workflow run
2. Scroll to **Artifacts**
3. Download the artifact
4. Extract it if needed
5. Keep the `.ipa` file ready

---

# Step 5 — Connect Your iPhone

1. Connect your iPhone to your PC using USB
2. Open **iTunes**
3. Confirm the device is detected

Then open **Plume Impactor**.

You should see your device name inside Plume Impactor.

If not:

* Unlock the iPhone
* Press **Trust This Computer**
* Use another cable if needed
* Make sure the device appears in iTunes first

---

# Step 6 — Install the IPA

Inside **Plume Impactor**:

1. Click **Import IPA**
2. Select the downloaded `.ipa`
3. Start installation

Wait until it completes.

---

# Step 7 — Trust Developer on iPhone

If the app does not open:

Go to your iPhone developer / device management settings and **Trust the developer profile** used to install the app.

---

# Step 8 — Enable Developer Mode

You may also need to enable **Developer Mode** on the iPhone.

After enabling it, restart the phone if prompted.

---

# App Expires Every 7 Days

The installation usually expires after **7 days**.

To keep using the app, repeat these steps every 7 days:

1. Connect device
2. Open iTunes
3. Open Plume Impactor
4. Import IPA
5. Install again
6. Trust developer if needed

---

# Full Process Summary

1. Upload Flutter or React Native project to GitHub
2. Add the correct GitHub Actions workflow
3. Run the workflow
4. Download `.ipa` artifact
5. Connect iPhone
6. Open iTunes
7. Open Plume Impactor
8. Import `.ipa`
9. Install app
10. Trust developer
11. Enable Developer Mode

---

# Flutter and React Native Notes

## Flutter

Use the Flutter workflow if your project is a Flutter app.

## React Native

Use the React Native workflow if your project is a React Native app.

For React Native, you may need to adjust:

* app scheme name
* workspace name
* iOS project path

because React Native iOS builds depend on your Xcode project structure.

---

# Disclaimer

This guide is intended for testing and personal installations. Apple policies, signing rules, and sideloading behavior may change over time.
