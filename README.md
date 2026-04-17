# flutter-ios-build-without-mac

Guide for installing Flutter apps on iOS without using a Mac.

---

## What this does

This method lets you build an iOS `.ipa` file for a Flutter app using **GitHub Actions**, then install it on an iPhone from a Windows PC.

No Mac required.

---

## Requirements

Before starting, install the following tools on your computer:

* **iTunes**
* **[Plume Impactor](https://github.com/CLARATION/Impactor/releases/download/v2.2.3/Impactor-windows-x86_64-setup.exe)**

You will also need:

* A **Flutter project**
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

---

# Step 1 — Upload Your Flutter Project to GitHub

Create a GitHub repository and upload your Flutter project.

Example:

```bash id="hmn9db"
git init
git add .
git commit -m "Initial commit"
git branch -M main
git remote add origin YOUR_REPOSITORY_URL
git push -u origin main
```

---

# Step 2 — Add GitHub Actions Workflow

1. Open your GitHub repository
2. Go to **Actions**
3. Click **New workflow**
4. Choose **set up a workflow yourself**
5. Paste the provided YAML file
6. Commit the file

This workflow will build your Flutter iOS app and generate an `.ipa` file.

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

If the app will not open:

Go to your iPhone developer/device management settings and **Trust the developer profile** used to install the app.

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

1. Upload Flutter project to GitHub
2. Add GitHub Actions workflow
3. Run workflow
4. Download `.ipa` artifact
5. Connect iPhone
6. Open iTunes
7. Open Plume Impactor
8. Import `.ipa`
9. Install app
10. Trust developer
11. Enable Developer Mode

---

# Disclaimer

This guide is intended for testing and personal installations. Apple policies and sideloading behavior may change over time.
