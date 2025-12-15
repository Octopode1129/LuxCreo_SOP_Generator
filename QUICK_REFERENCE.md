# GitHub SOP Repository - Quick Reference

## 🚀 One-Time Setup (5 minutes)

```bash
1. Go to github.com/new
2. Name: luxcreo-sop-repository
3. Select: Public
4. Click "Add a README file"
5. Create repository

6. Settings → Pages
7. Source: Deploy from a branch
8. Branch: main
9. Folder: / (root)
10. Save
```

**Your live site:** `https://yourusername.github.io/luxcreo-sop-repository`

---

## 📤 Upload Files to GitHub

### Web Upload (Easiest)
```
1. Your repo → Add file → Upload files
2. Drag and drop sop_generator.html
3. Rename to: index.html
4. Create folder: data/
5. Upload sample-sops.json into data/
6. Commit
```

### Command Line
```bash
git clone https://github.com/yourusername/luxcreo-sop-repository.git
cd luxcreo-sop-repository
cp sop_generator.html index.html
mkdir -p data
cp sample-sops.json data/
git add .
git commit -m "Initial SOP generator setup"
git push origin main
```

---

## 📋 Typical SOP Submission Workflow

```
┌─────────────────────────────────────────────────────────┐
│  TEAM MEMBER CREATES SOP                                │
│  1. Visit: https://yourusername.github.io/...           │
│  2. Fill form with material/equipment/application       │
│  3. Add steps with images                               │
│  4. Click "Save SOP"                                    │
└────────────────────┬────────────────────────────────────┘
                     │
┌────────────────────▼────────────────────────────────────┐
│  EXPORT & SHARE                                         │
│  1. Click "📥 Export SOPs" button                       │
│  2. Save JSON file: "dmr3-aligners.json"                │
│  3. Email to: sop-maintainer@company.com                │
└────────────────────┬────────────────────────────────────┘
                     │
┌────────────────────▼────────────────────────────────────┐
│  MAINTAINER REVIEWS                                     │
│  1. Open GitHub Issue: "Review: DMR III Aligners"       │
│  2. Attach exported JSON                                │
│  3. Team tests & provides feedback                      │
│  4. JSON edited & finalized                             │
└────────────────────┬────────────────────────────────────┘
                     │
┌────────────────────▼────────────────────────────────────┐
│  MERGE & PUBLISH                                        │
│  1. Approved JSON added to data/ folder                 │
│  2. Commit: "Add SOP: DMR III - Aligner manufacturing"  │
│  3. Git push origin main                                │
│  4. GitHub Pages auto-updates (1-2 min)                 │
│  5. Live for entire team! 🎉                            │
└─────────────────────────────────────────────────────────┘
```

---

## 🔗 File Structure

```
luxcreo-sop-repository/
├── index.html                    ← SOP Generator App
├── README.md                     ← Project overview
├── CONTRIBUTING.md               ← Contribution guide
├── GITHUB_SETUP_GUIDE.md        ← Detailed setup
│
└── data/
    ├── sample-sops.json         ← Template/example
    ├── dmr-iii-aligners.json    ← Your approved SOPs
    ├── dca-crowns.json          ← More approved SOPs
    └── [material-workflows].json ← More materials
```

---

## 💻 Share Repository Links

**Live Site (View Only):**
```
https://yourusername.github.io/luxcreo-sop-repository
```

**GitHub Repository (For Developers/Contributors):**
```
https://github.com/yourusername/luxcreo-sop-repository
```

**Share with Team:**
- Non-technical: Send them the live site URL
- Technical: Send them the GitHub repo URL
- New contributors: Send [CONTRIBUTING.md](CONTRIBUTING.md)

---

## ✅ Checklist for First Launch

- [ ] GitHub account created
- [ ] Repository created and public
- [ ] GitHub Pages enabled (Settings → Pages)
- [ ] `index.html` uploaded to root
- [ ] `data/sample-sops.json` uploaded
- [ ] `README.md` created
- [ ] `CONTRIBUTING.md` created
- [ ] Team members invited as collaborators (Settings → Collaborators)
- [ ] Tested the live site (loads without errors)
- [ ] Shared links with team

---

## 🔄 Regular Operations

### Creating New SOP (Team Member)
```
1. Open https://yourusername.github.io/luxcreo-sop-repository
2. Click "Create SOP"
3. Fill form
4. Click "Save"
5. Click "📥 Export SOPs"
6. Email JSON to maintainer
```

### Adding SOP to Repository (Maintainer)
```bash
# Receive JSON from team member, test it
git pull origin main
cp received-sop.json data/new-material-sop.json
git add data/new-material-sop.json
git commit -m "Add SOP: [Material] - [Application]"
git push origin main
# Site updates automatically (1-2 min)
```

### Updating Existing SOP
```bash
git pull origin main
# Edit JSON directly in editor or use web app
git add data/file-you-edited.json
git commit -m "Update SOP: [Material] - clarify [step]"
git push origin main
```

---

## 🆘 Troubleshooting

| Problem | Solution |
|---------|----------|
| Changes don't appear | Wait 1-2 min for GitHub Pages deploy. Check Actions tab. Clear browser cache. |
| 404 error on site | Check that `index.html` is in root (not in folder). Disable GitHub Pages/re-enable. |
| Import/Export not working | Check browser console (F12). Ensure JSON is valid. Try different browser. |
| Can't push changes | Run `git pull origin main` first. Resolve conflicts. Then push. |
| Forgot GitHub password | Go to Settings → Change Password. Or click "Forgot password" on login. |

---

## 📊 Team Roles

### Manufacturing Tech
- Creates SOPs in web interface
- Exports as JSON
- Submits for review

### Maintainer
- Reviews submitted SOPs
- Tests in production
- Merges into repository
- Manages versions

### Quality Assurance
- Validates SOP accuracy
- Tests procedures
- Leaves GitHub issue comments
- Approves or requests changes

---

## 🎯 Git Commands You'll Need

```bash
# Pull latest changes from team
git pull origin main

# See what you changed
git status
git diff

# Save your changes
git add .
git commit -m "Add SOP: [Description]"

# Push to GitHub (publish)
git push origin main

# Create new branch for experimental SOP
git checkout -b sop/new-material
# ... make changes ...
git push origin sop/new-material
# Then open Pull Request on GitHub.com
```

---

## 📚 Full Documentation

- **Setup Details:** [GITHUB_SETUP_GUIDE.md](GITHUB_SETUP_GUIDE.md)
- **Contribution Rules:** [CONTRIBUTING.md](CONTRIBUTING.md)
- **Project Overview:** [README.md](README.md)

---

## 🎓 GitHub Learning Resources

- [GitHub Pages (30 min)](https://pages.github.com)
- [Git Basics (1 hour)](https://git-scm.com/docs/gittutorial)
- [Markdown Guide (15 min)](https://guides.github.com/features/mastering-markdown/)
- [Collaborating on GitHub (30 min)](https://docs.github.com/en/pull-requests/collaborating-with-pull-requests)

---

## 💡 Pro Tips

1. **Naming Convention:** Use clear, descriptive names
   - ✅ `dmr-iii-4d-aligners.json`
   - ✅ `dca-crown-high-precision.json`
   - ❌ `sop1.json` or `data.json`

2. **Commit Messages:** Be specific
   - ✅ "Add SOP: DMR III - 4D Aligner manufacturing workflow"
   - ❌ "Updated file" or "Added stuff"

3. **Image Quality:** Keep images clear
   - Use PNG format (better compression)
   - 800x600px minimum resolution
   - Crop to focus on critical details
   - Include annotations if possible

4. **Version Control:** Use semantic versioning
   - v1.0.0 - First approved release
   - v1.1.0 - Minor updates (clarifications)
   - v2.0.0 - Major process changes

5. **Backup:** GitHub IS your backup
   - All history preserved
   - Can revert to any old version
   - No need for manual backups

---

<div align="center">

**Questions? Email: [your-email@company.com]**

**Need help? Check GitHub Issues: https://github.com/yourusername/luxcreo-sop-repository/issues**

</div>
