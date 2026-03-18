# One-Time Push Instructions

Open a terminal (or Git Bash on Windows) and run:

```bash
# 1. Clone your existing repo somewhere temporary
cd ~/Desktop
git clone https://github.com/Lindorn/admaediamonds.git admaediamonds-temp
cd admaediamonds-temp

# 2. Copy all the organized files from the Cowork folder into the repo
# (Adjust the source path if your Cowork folder is elsewhere)
cp -r ~/Desktop/Cowork/admaediamonds-repo/* .

# 3. Check what's being added
git status

# 4. Stage and commit everything
git add -A
git commit -m "Add organized Squarespace code injections with folder structure

- site-global/: Site-wide CSS and footer injection
- pages/blog/: 3 blog post code injections
- pages/services/: 4 service/landing page code injections
- pages/other/: Client portfolio page
- README.md: Repo structure and deployment docs"

# 5. Push
git push origin main
```

After pushing, you can delete the `admaediamonds-temp` folder.

Or if you prefer **GitHub Desktop**: open the repo, drag the `admaediamonds-repo` folder contents into it, and commit + push from the UI.
