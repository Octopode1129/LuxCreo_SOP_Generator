# LuxCreo SOP Repository 🦷🖨️

**Collaborative Standard Operating Procedures for LuxCreo Dental Manufacturing**

A web-based platform for creating, sharing, and managing dental manufacturing workflows with precision image documentation, step-by-step guidance, and team collaboration.

[![GitHub Pages](https://img.shields.io/badge/Site-Live-brightgreen)](https://yourusername.github.io/luxcreo-sop-repository)
[![License](https://img.shields.io/badge/License-MIT-blue)](#license)
[![Contributions](https://img.shields.io/badge/Contributions-Welcome-brightgreen)](CONTRIBUTING.md)

---

## 🚀 Quick Start

### View SOPs Online
Visit: **https://yourusername.github.io/luxcreo-sop-repository**

### Create or Edit SOPs
1. Click **Create SOP** tab
2. Select material (DMR III, DCA, FPD, DNG, etc.)
3. Add workflow steps with images
4. Click **Save**
5. Export as JSON to share with team

### Share SOPs with Team
```bash
1. Click 📥 Export SOPs
2. Email JSON file to team
3. They click 📤 Import SOPs to load it
```

---

## 📋 What's Inside

### Supported Materials
- **DMR III** - UV-sensitive resin for aligners
- **DCA** - Dental Crown Acrylic
- **DCA Plus White** - Enhanced white acrylic
- **FPD** - Fixed Partial Denture resin
- **DNG** - Night Guard material

### Supported Equipment
- **iLuxPro Dental** - LuxCreo printer
- **FastPrint.io** - Alternative printer
- **iLuxWash Dental** - Wash station
- **LuxOven Pro** - Cure oven
- **iLuxCure Pro** - UV curing

### Documentation Includes
- 🖼️ **Annotated Images** - Precise crop points for critical details
- 📝 **Step-by-Step Instructions** - Each substep numbered and detailed
- ⚠️ **Safety Tags** - Warnings, tips, critical notes
- 🔧 **Firmware Versions** - Material & equipment specific settings
- 📊 **Production Metrics** - Cycle times, quality standards

---

## 📚 SOP Sections

Each SOP documents three workflow phases:

### 1️⃣ **LuxFlow**
Printer setup and execution
- Material loading
- Screen configuration
- Print parameters
- Monitor execution

### 2️⃣ **Post-Processing**
Cleaning and curing
- Wash station cycles
- Oven cure settings
- UV curing parameters
- Cooling procedures

### 3️⃣ **Finishing** (Optional)
Quality control & packaging
- Visual inspection
- Dimension verification
- Packaging standards
- Labeling requirements

---

## 🤝 Contributing

### For Everyone
See **[CONTRIBUTING.md](CONTRIBUTING.md)** for:
- How to submit new SOPs
- SOP quality standards
- Image guidelines
- Testing requirements

### For Developers
Submit improvements via Pull Request:
```bash
git clone https://github.com/yourusername/luxcreo-sop-repository.git
git checkout -b sop/your-sop-name
# Make changes
git commit -m "Add SOP: [Material] - [Application]"
git push origin sop/your-sop-name
```

---

## 📖 How to Use This Repository

### Viewing SOPs
1. Click **View SOPs** tab on live site
2. Filter by material or equipment
3. Click a card to see full details
4. Download images or print instructions

### Creating SOPs
1. Click **Create SOP** tab
2. Fill form with material/equipment/application
3. Add steps with:
   - Detailed descriptions
   - Emphasis tags (Warning, Tip, Critical)
   - Reference images (with cropping)
4. Save and export

### Team Collaboration
**Workflow:**
1. Create SOP in web interface
2. Export as JSON
3. Open GitHub Issue with title: "Review: [SOP Name]"
4. Attach JSON file
5. Team reviews and approves
6. Maintainer merges into main database

---

## 🗂️ Repository Structure

```
luxcreo-sop-repository/
├── index.html                 # Live web application
├── README.md                  # This file
├── CONTRIBUTING.md            # Contribution guidelines
├── data/
│   ├── sample-sops.json       # Example SOPs
│   ├── dmr-iii-aligners.json  # Material-specific collections
│   └── dca-crowns.json        # Production-proven workflows
├── docs/
│   ├── SETUP.md               # Detailed setup guide
│   ├── TROUBLESHOOTING.md     # Common issues & fixes
│   ├── BEST_PRACTICES.md      # Manufacturing tips
│   └── FAQ.md                 # Frequently asked questions
└── .github/
    └── workflows/
        └── validate.json.yml  # Auto-validate SOP data
```

---

## 🔄 Workflow Examples

### Example 1: Adding a New Material SOP
```
1. Team creates DMR III SOP for ortho models
2. Exports JSON from web interface
3. Opens Issue: "Review: DMR III - Ortho Model SOP"
4. Quality team tests procedure
5. Reviews image clarity and step completeness
6. Approves and merges into data/dmr-iii-aligners.json
7. Published and available to all manufacturing team members
```

### Example 2: Updating Existing SOP
```
1. Engineer discovers optimized cure settings
2. Edits existing SOP in web interface
3. Exports updated JSON
4. Comments in original Issue with changes
5. Team verifies improvement
6. Merged with version update
```

---

## 💾 Data Format

All SOPs stored as JSON for version control:

```json
{
  "id": "sop-001",
  "name": "4D Aligner - DMR III",
  "material": "DMR III",
  "application": "Aligner Manufacturing",
  "equipment": "iLuxPro Dental",
  "resinTank": "LEAP C+",
  "createdAt": "2025-12-15",
  "createdBy": "john@company.com",
  "firmwareVersions": {
    "luxflow": "3.2.1",
    "printer": "4.1.0"
  },
  "luxflowSteps": [
    {
      "id": "step-1",
      "name": "Printer Setup",
      "substeps": [
        {
          "id": "sub-1",
          "description": "Verify resin level is above minimum mark",
          "tags": ["Critical"],
          "image": "data:image/png;base64,..."
        }
      ]
    }
  ]
}
```

---

## 🛠️ Technical Details

- **No Backend Required** - Runs entirely in browser
- **Storage Options:**
  - Claude Persistent Storage (team shared)
  - Browser localStorage (personal)
- **Export Format:** JSON (version control friendly)
- **Images:** Embedded as base64 (no external links)
- **Cropping:** Integrated Cropper.js for precision

---

## 📱 Accessibility

- ✅ Mobile responsive
- ✅ Works offline (after first load)
- ✅ Keyboard navigation
- ✅ Dark mode compatible
- ✅ Printable SOP formats

---

## 🔐 Privacy & Sharing

### Public Repository
- Anyone can view published SOPs
- Read-only access by default
- No sign-up required

### Team Editing
- GitHub collaborators can propose changes
- Changes reviewed before publishing
- Full audit trail via Git history

### Data Security
- No personal data transmitted
- All storage local or in Claude workspace
- Git commits track who made what changes

---

## 📞 Support

### Getting Help
- **Questions?** → Check [CONTRIBUTING.md](CONTRIBUTING.md)
- **Found a bug?** → [Open an Issue](../../issues)
- **Have a suggestion?** → Start a [Discussion](../../discussions)
- **Need setup help?** → See [SETUP.md](docs/SETUP.md)

### Common Issues
See [TROUBLESHOOTING.md](docs/TROUBLESHOOTING.md) for:
- Import/Export problems
- Storage issues
- Image cropping help
- Collaborative workflow questions

---

## 👥 Contributors

Thanks to these manufacturing experts who contributed SOPs:

- 👤 **John Smith** - DMR III workflows
- 👤 **Sarah Chen** - DCA Plus specifications
- 👤 **Mike Rodriguez** - Equipment setup guides

Want to be listed here? [See how to contribute](CONTRIBUTING.md)

---

## 📜 License

This project is licensed under the **MIT License** - see [LICENSE](LICENSE) file for details.

**In plain English:** You can use, modify, and share these SOPs freely for manufacturing dental products. Give credit where appropriate.

---

## 🎯 Roadmap

- [x] Web-based SOP creator
- [x] GitHub Pages hosting
- [x] JSON export/import
- [ ] Search functionality
- [ ] Version history/compare
- [ ] Approval workflow automation
- [ ] Slack/Teams integration
- [ ] Mobile app version

---

## 🚀 Getting Started

### For Manufacturers
1. Visit the [live site](https://yourusername.github.io/luxcreo-sop-repository)
2. Browse existing SOPs
3. Follow step-by-step instructions
4. Report any issues or improvements

### For Team Leads
1. [Enable GitHub Pages](GITHUB_SETUP_GUIDE.md)
2. Invite team members as collaborators
3. Review and approve SOP submissions
4. Maintain version history

### For Developers
1. Fork this repository
2. Make improvements
3. Submit pull requests
4. Help maintain documentation

---

## 📊 Stats

- 📋 **SOPs Created:** [Auto-counted from data folder]
- 👥 **Contributors:** [Auto-counted from git history]
- 🔄 **Last Updated:** [Auto from git commits]
- ⭐ **Stars:** Help others find this project!

---

## 🎓 Learn More

- [Setup Instructions](GITHUB_SETUP_GUIDE.md)
- [Contributing Guidelines](CONTRIBUTING.md)
- [Best Practices](docs/BEST_PRACTICES.md)
- [FAQ](docs/FAQ.md)
- [LuxCreo Documentation](https://www.luxcreo.com/docs)

---

<div align="center">

**Made with ❤️ for dental manufacturing teams**

[Visit Live Site](https://yourusername.github.io/luxcreo-sop-repository) • [View Issues](../../issues) • [Start Discussion](../../discussions)

</div>
