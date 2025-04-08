To use Git with the repository at [this link](https://github.com/OussamaTabDev/GL-Project-), follow these steps:

### **1. Clone the Repository**

If you want to download the project to your local machine, open a terminal and run:

```bash
git clone https://github.com/OussamaTabDev/GL-Project-.git
```

This will create a folder named `GL-Project-` in your current directory.

### **2. Navigate to the Project Folder**

Move into the newly cloned directory:

```bash
cd GL-Project-
```

### **3. Check the Remote Repository**

Ensure that the remote repository is correctly linked:

```bash
git remote -v
```

You should see:

```
origin  https://github.com/OussamaTabDev/GL-Project-.git (fetch)
origin  https://github.com/OussamaTabDev/GL-Project-.git (push)
```

### **4. Create a New Branch (Optional)**

If you want to work on a separate branch before merging changes:

```bash
git checkout -b my-feature-branch
```

### **5. Make Changes and Commit**

Edit files as needed, then add them to the staging area:

```bash
git add .
```

Commit the changes with a message:

```bash
git commit -m "Added a new feature"
```

### **6. Push Changes to GitHub**

If you are working on the `main` branch, push your changes:

```bash
git push origin main
```

Or if you created a new branch:

```bash
git push origin my-feature-branch
```

### **7. Pull the Latest Changes**

If you want to update your local repository with the latest changes from GitHub:

```bash
git pull origin main
```

### **8. Create a Pull Request (If Contributing)***

If you forked the repository or are working on a different branch, go to GitHub and create a pull request to merge your changes.

Let me know if you need help with anything else! 🚀


hello world
this new