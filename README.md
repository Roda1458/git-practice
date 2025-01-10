# git-practice

### **🚀 Git Practice: Branching, Merging & Conflict Resolution**  

## **📌 Steps to Follow**  

### **1️⃣ Setting Up the Project**  
#### **🔹 Create a new directory and initialize Git**  
```sh
mkdir git-practice
cd git-practice
git init
```

#### **🔹 Create an `index.html` file**  
Create `index.html` and add the following content:  
```html
<!DOCTYPE html>
<html>
  <head>
    <title>Git Practice</title>
  </head>
  <body>
    <h1>Welcome to Git Practice!</h1>
  </body>
</html>
```

#### **🔹 Check the status and make the first commit**  
```sh
git status
git add index.html
git commit -m "Initial commit with index.html"
```

---

### **2️⃣ Creating a Branch and Making Changes**  
#### **🔹 Create and switch to a new branch**  
```sh
git checkout -b feature-navbar
```

#### **🔹 Modify `index.html` to add a navigation bar**  
Edit `index.html` to include the following **navigation bar**:  
```html
<nav>
  <ul>
    <li><a href="#">Home</a></li>
    <li><a href="#">About</a></li>
    <li><a href="#">Contact</a></li>
  </ul>
</nav>
```

#### **🔹 Stage and commit your changes**  
```sh
git add index.html
git commit -m "Added navigation bar"
```

---

### **3️⃣ Creating a Merge Conflict**
#### **🔹 Switch back to the `main` branch**  
```sh
git checkout main
```

#### **🔹 Modify `index.html` differently in `main` branch**  
Change the `<h1>` heading inside `index.html` to something like:  
```html
<h1>Welcome to Git Learning!</h1>
```

#### **🔹 Stage and commit the changes in `main` branch**  
```sh
git add index.html
git commit -m "Changed heading text in main branch"
```

#### **🔹 Try to merge `feature-navbar` into `main`**  
```sh
git merge feature-navbar
```
If there are conflicting changes, **Git will show a merge conflict**.

---

### **4️⃣ Resolving Merge Conflict**
#### **🔹 Open `index.html` in Notepad to fix the conflict**  
```sh
notepad index.html
```
In `index.html`, Git will show conflict markers like this:  
```html
<<<<<<< HEAD
<h1>Welcome to Git Learning!</h1>
=======
<h1>Welcome to Git Practice!</h1>
<nav>
  <ul>
    <li><a href="#">Home</a></li>
    <li><a href="#">About</a></li>
    <li><a href="#">Contact</a></li>
  </ul>
</nav>
>>>>>>> feature-navbar
```
#### **🔹 Manually edit the file to merge changes properly**  
Remove the conflict markers (`<<<<<<<`, `=======`, `>>>>>>>`) and decide on the final version. For example:  
```html
<h1>Welcome to Git Learning!</h1>
<nav>
  <ul>
    <li><a href="#">Home</a></li>
    <li><a href="#">About</a></li>
    <li><a href="#">Contact</a></li>
  </ul>
</nav>
```
#### **🔹 Stage and commit the resolved file**  
```sh
git add index.html
git commit -m "Resolved merge conflict"
```

---

### **5️⃣ Pushing to GitHub**  
#### **🔹 Add the remote repository (if not added yet)**  
```sh
git remote add origin https://github.com/Roda1458/git-practice.git
git branch -M main
```

#### **🔹 Pull the latest changes before pushing**  
```sh
git pull origin main --rebase
```

#### **🔹 Push the changes to GitHub**  
```sh
git push origin main
```

---

### **🌟 Additional Git Commands**
- **Check the commit history:**  
  ```sh
  git log --oneline --graph --all
  ```
- **View branch list:**  
  ```sh
  git branch
  ```
- **Delete a branch after merging:**  
  ```sh
  git branch -d feature-navbar
  ```


