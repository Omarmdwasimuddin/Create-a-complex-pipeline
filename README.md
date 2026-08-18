# Create a complex pipeline (Docusaurus Project দিয়ে)

## ধাপ ১: Docusaurus Project তৈরি করা

### পূর্বশর্ত (Pre-requirement)

- মেশিনে Node.js ইনস্টল থাকতে হবে

### Project তৈরির Command

```bash
mkdir pipeline-tutorial
```

```bash
cd pipeline-tutorial
```

```bash
npm init docusaurus
```

> **Note:** এটা একটা wizard চালাবে, সব default option সিলেক্ট করে যেতে হবে (Enter চাপতে থাকো)।

### ফোল্ডার Structure ঠিক করা

Wizard `website/` নামে একটা ফোল্ডারে সাইট বানাবে, কিন্তু root-এ চাই। তাই:

```bash
mv website/* .
```

```bash
rm -r website
```

---

## ধাপ ২: GitLab-এ নতুন Project তৈরি করা

নিচের ধাপগুলো অনুসরণ করতে হবে:

1. Visit করুন: `http://localhost:8000/dashboard/projects`
2. **New project** এ ক্লিক করুন
3. **Create blank project** এ ক্লিক করুন
4. Project name দিন: `My Pipeline Tutorial Project`
5. Project URL এবং Visibility Level এ value সেট করুন
6. **Initialize repository with a README** — এই অপশনটি unselect (uncheck) করুন
7. **Create project** এ ক্লিক করুন

---

## ধাপ ৩: Project Push করা

Terminal-এ নিচের command গুলো চালাতে হবে:

```bash
git init
git remote add origin http://localhost:8000/<your-group>/my-pipeline-tutorial-project.git
git add .
git commit -m "Add simple generated Docusaurus site"
git branch -M main
git push -u origin main
```

> **Note:** পুশ করার পর browser-এ project page টি reload/refresh করলে code push হয়ে যাওয়া দেখা যাবে —
> `http://localhost:8000/wasuit-group/my-pipeline-tutorial-project`

---

## ধাপ ৪: `.gitlab-ci.yml` ফাইল তৈরি করা

Project root-এ `.gitlab-ci.yml` ফাইল বানিয়ে নিচের code দিতে হবে:

```yaml
test-job:
  tags:
    - docker
  script:
    - echo "This is my first job!"
    - date
```

---

## ধাপ ৫: CI/CD Config Push করা

Terminal-এ নিচের command গুলো চালাতে হবে:

```bash
git add .gitlab-ci.yml
git commit -m "Add initial CI/CD pipeline config"
git push origin main
```

---

## ধাপ ৬: Pipeline Verify করা

নিচের ধাপ অনুসরণ করে pipeline চেক করতে হবে:

1. **Build** এ ক্লিক করুন
2. **Pipelines** এ ক্লিক করুন
3. Pipeline-এর **id** তে ক্লিক করুন

<img width="1283" height="497" alt="Pipeline id view" src="https://github.com/user-attachments/assets/6d4af51c-f9bc-4b38-bb54-38960515f93f" />

---

## সংক্ষেপে Flow

```
Docusaurus site তৈরি ও ফোল্ডার ঠিক করা
        ↓
GitLab-এ project তৈরি করা
        ↓
Code push করা
        ↓
.gitlab-ci.yml তৈরি ও push করা
        ↓
Pipeline verify করা
```
