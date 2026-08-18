# Create a complex pipeline


#### Docusaurus প্রজেক্ট তৈরি করা
> Pre-requirement
> - তোমার মেশিনে Node.js ইনস্টল থাকা লাগবে
```bash
mkdir pipeline-tutorial
```
```bash
cd pipeline-tutorial
```
```bash
npm init docusaurus
```
> Note: এটা একটা উইজার্ড চালাবে, সব ডিফল্ট অপশন সিলেক্ট করে যাও (Enter চাপতে থাকো)।
---
> উইজার্ড website/ নামে একটা ফোল্ডারে সাইট বানাবে, কিন্তু আমাদের রুটে চাই:
```bash
mv website/* .
```
```bash
rm -r website
```
---


#### GitLab e project banate hobe ---> http://localhost:8000/dashboard/projects ---> click: New project ---> click: Create blank project ---> Project name: My Pipeline Tutorial Project ---> Project URL, Visibility Level e value set koro and Initialize repository with a README unsign koro ---> click: Create project 

#### project push koro
```bash
git init
git remote add origin http://localhost:8000/<your-group>/my-pipeline-tutorial-project.git
git add .
git commit -m "Add simple generated Docusaurus site"
git branch -M main
git push -u origin main
```
> Note: browser e reload koro ba represh koro http://localhost:8000/wasuit-group/my-pipeline-tutorial-project#  ---> code push hoye jabe
---


#### .gitlab-ci.yml [projecct root e banaw]
```bash
test-job:
  tags:
    - docker
  script:
    - echo "This is my first job!"
    - date
```
---

#### terminal e daw
```bash
git add .gitlab-ci.yml
git commit -m "Add initial CI/CD pipeline config"
git push origin main
```
---

#### click: Build ---> click: pipelines ---> click: id
<img width="1283" height="497" alt="image" src="https://github.com/user-attachments/assets/6d4af51c-f9bc-4b38-bb54-38960515f93f" />

---
