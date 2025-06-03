# 📦 **action-repo** ..

This is a **dummy GitHub repository** used to simulate real GitHub events such as:
- `push`
- `pull_request`
- `merge`

These actions trigger a **GitHub webhook**, which sends event data to a webhook listener (`webhook-repo`), where the event is stored and displayed in a live UI.

---

## 🛠️ Before You Begin

> 📌 IMPORTANT: Before doing any Git actions (push, PR, merge), make sure you have **added the webhook URL** to this repo’s settings.

### 🔗 Add GitHub Webhook

1. Go to this repository → **Settings → Webhooks → Add Webhook**
2. Use the following details:

| Field            | Value                                      |
|------------------|--------------------------------------------|
| **Payload URL**  | `https://<your-ngrok-or-deployment-url>/webhook` |
| **Content type** | `application/json`                         |
| **Secret**       | *(leave empty)*                            |
| **Events**       | `Just the push event` or select all        |
| **Active**       | ✅                                           |

3. Click **"Add webhook"**

> You can use [ngrok](https://ngrok.com/) to expose your local Flask server:
```bash
ngrok http 5000
```

## 🚀 How to Use
Once your webhook is connected, you can simulate GitHub events:

## ✅ 1. PUSH Event

### 🔨 Steps to Trigger:
1. Clone your action-repo locally:
```bash
git clone https://github.com/yourusername/action-repo.git
cd action-repo
```

2. Make a change in any file (e.g., README.md) and save it.

3. Push it:

```bash
git add .
git commit -m "Test push webhook"
git push origin main
```

## ✅ 2. PULL REQUEST

### 🧪 Steps to Trigger:

1. Create a new branch:
```bash
git checkout -b feature-branch
```

2. Make a change in a file.

3. Commit and push the branch:

```bash
git add .
git commit -m "Add feature"
git push origin feature-branch
```

4. Go to your GitHub repository in the browser. GitHub will prompt:

“Compare & pull request”
Click it and create a new pull request from feature-branch to main.

✅ This will trigger the pull_request webhook event with action = opened.


## ✅ 3. MERGE Event

### 🧪 Steps to Trigger:
1. From the previous step, you now have an open pull request.

2. On GitHub, click “Merge pull request”, then confirm.
