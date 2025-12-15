# GitHub + GitHub Pages Setup Guide for SOP Generator

## Quick Start (5 minutes)

### 1. Create GitHub Repository

1. Go to [github.com/new](https://github.com/new)
2. Repository name: `luxcreo-sop-repository` (or your preference)
3. Description: "LuxCreo Dental Manufacturing SOP Generator - Collaborative Documentation Repository"
4. Select: **Public** (so others can view)
5. Check: "Add a README file"
6. Click **Create repository**

### 2. Enable GitHub Pages

1. Go to your repository → **Settings** tab
2. Scroll to **Pages** (left sidebar)
3. Under "Source", select: **Deploy from a branch**
4. Select branch: **main**
5. Select folder: **/ (root)**
6. Click **Save**

Your site will be live at: `https://yourusername.github.io/luxcreo-sop-repository`

### 3. Upload Files to GitHub

#### Option A: Web Upload (Easiest)
1. On your repo homepage, click **Add file** → **Upload files**
2. Drag and drop:
   - `sop_generator.html` → rename to `index.html`
   - Create a `data/` folder with `sample-sops.json`
3. Commit with message: "Initial SOP generator setup"

#### Option B: Command Line (Recommended Long-term)
```bash
# Clone the repository
git clone https://github.com/yourusername/luxcreo-sop-repository.git
cd luxcreo-sop-repository

# Copy files
cp sop_generator.html index.html
mkdir -p data
cp sample-sops.json data/

# Commit and push
git add .
git commit -m "Add SOP generator and initial data"
git push origin main
```

---

## Collaborative Workflow

### How Team Members Contribute

#### For Non-Technical Users (Simple):
1. Visit: `https://yourusername.github.io/luxcreo-sop-repository`
2. Create SOPs using the web interface
3. Click **📥 Export SOPs** button
4. Save the JSON file
5. Share via email/Slack with a note: "Updated SOPs - review and merge"

#### For Technical Users (Git Workflow):
1. Fork the repository
2. Clone and make changes
3. Commit: `git commit -m "Add ortho model SOP for DMR III"`
4. Push to fork
5. Create Pull Request (PR)
6. Maintainer reviews and merges

---

## Data Management Strategy

### Structure Your Repo Like This:
```
luxcreo-sop-repository/
├── index.html                 # Your SOP generator
├── README.md                  # Project description
├── CONTRIBUTING.md            # Contribution guidelines
├── data/
│   ├── sample-sops.json       # Example SOPs
│   ├── dmr-iii-workflows.json # Material-specific SOPs
│   └── faq.md                 # Common questions
└── docs/
    ├── SETUP.md
    ├── TROUBLESHOOTING.md
    └── BEST_PRACTICES.md
```

### Version Control Your SOP Data

Create `data/sops-master.json` to track official SOPs:

```json
{
  "version": "1.0.0",
  "lastUpdated": "2025-12-15",
  "sops": [
    {
      "id": "sop-001",
      "name": "4D Aligner - DMR III Standard",
      "material": "DMR III",
      "application": "Aligner Manufacturing",
      "equipment": "iLuxPro Dental",
      "createdBy": "john@company.com",
      "lastModified": "2025-12-15",
      "status": "approved",
      "steps": []
    }
  ]
}
```

---

## Updating & Maintaining

### Weekly Workflow:
1. **Team creates SOPs** in the web interface
2. **Export JSON** from the app
3. **Create a GitHub Issue** titled: "Review: [Material] - [Process]"
4. **Add JSON to issue** for review
5. **Approved?** → Merge into `data/sops-master.json`
6. **Not approved?** → Feedback in comments

### Using GitHub Discussions (Optional)
Enable in repo Settings → Enable Discussions
- Team discusses SOP improvements
- Links to SOPs under review
- Centralized knowledge base

---

## Sharing the Repository

### Share with your team:
```
Direct Link: https://github.com/yourusername/luxcreo-sop-repository
Live Site: https://yourusername.github.io/luxcreo-sop-repository
```

### Getting Team Members Access:

**For Viewing Only (No Setup):**
- Just send them the live site URL
- They can view/copy data, but can't push

**For Contributing:**
1. Add them as **Collaborators** (Settings → Collaborators)
2. Or have them fork and create PRs

---

## Troubleshooting

### "My changes don't appear on the site"
- GitHub Pages takes 1-2 minutes to deploy
- Check Actions tab to see build status
- Clear browser cache (Ctrl+Shift+Delete)

### "Import/Export isn't working"
- Make sure you're on `https://` (not `http://`)
- Check browser console for errors (F12)
- Verify JSON file format is valid

### "How do I handle conflicts?"
- If two people edit same SOP, first to merge wins
- Use GitHub's conflict resolution tool
- Or manually merge in a text editor

---

## Next Steps (Optional Enhancements)

### 1. Add CI/CD Validation
Create `.github/workflows/validate.yml` to auto-check JSON files:
```yaml
name: Validate SOP Data
on: [push, pull_request]
jobs:
  validate:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v3
      - name: Validate JSON
        run: |
          for file in data/*.json; do
            python -m json.tool "$file" > /dev/null
          done
```

### 2. Add GitHub Pages Theme
Edit `.github/workflows/pages.yml` to customize styling

### 3. Create Automated Releases
Tag releases: `v1.0.0`, `v1.1.0` for version tracking

### 4. Add Search Functionality
Integrate Algolia or similar for site-wide SOP search

---

## Resources

- [GitHub Pages Documentation](https://pages.github.com)
- [GitHub Markdown Guide](https://guides.github.com/features/mastering-markdown/)
- [How to Collaborate on GitHub](https://docs.github.com/en/pull-requests/collaborating-with-pull-requests)
- [JSON Schema Validation](https://json-schema.org/)

---

## Questions?

Document issues in your repo's **Issues** tab:
1. Click **New Issue**
2. Title: "Question: [Your question]"
3. Community can help troubleshoot

Good luck with your collaborative SOP repository! 🚀
