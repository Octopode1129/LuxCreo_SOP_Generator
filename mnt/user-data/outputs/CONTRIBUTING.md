# Contributing to LuxCreo SOP Repository

Thank you for helping improve our manufacturing documentation! This guide explains how to contribute.

## Before You Start

- **No coding required** - Use the web interface to create SOPs
- **Be descriptive** - Clear steps help manufacturing teams
- **Include images** - Visual documentation is crucial for dental manufacturing
- **Test your SOPs** - Verify steps work in real production

## How to Contribute

### Option 1: Web Interface (Easiest)

1. Visit: https://yourusername.github.io/luxcreo-sop-repository
2. Click **Create SOP** tab
3. Fill in:
   - **Material** (DMR III, DCA, FPD, etc.)
   - **Application** (what are you manufacturing?)
   - **Equipment** (iLuxPro, FastPrint, etc.)
   - **Firmware versions** (if relevant)
4. Add workflow sections:
   - **LuxFlow Steps** (printer settings)
   - **Post-Processing** (wash, cure, finishing)
   - **Finishing** (optional - packaging, QC, etc.)
5. For each step, add **substeps**:
   - **Description** - What to do (be specific!)
   - **Tags** - Highlight warnings, tips, critical steps
   - **Images** - Crop and add photos of the process
6. Click **Save SOP**
7. Click **📥 Export SOPs** button
8. Email the JSON file to the maintainer with:
   ```
   Subject: New SOP Submission - [Material] [Application]
   
   Created SOP for: [Description]
   Tested: [Yes/No]
   Notes: [Any special considerations]
   ```

### Option 2: GitHub Pull Request (For Developers)

1. Fork this repository
2. Create a branch: `git checkout -b sop/dca-plus-aligners`
3. Add/edit SOP JSON files in `data/` folder
4. Commit with clear message:
   ```bash
   git commit -m "Add DCA Plus White SOP for ortho models"
   ```
5. Push to fork: `git push origin sop/dca-plus-aligners`
6. Open Pull Request (PR) on GitHub with:
   - **Title:** "Add SOP: [Material] - [Application]"
   - **Description:** Why this SOP is needed, testing results
   - **Checklist:**
     - [ ] Tested in production
     - [ ] Images included
     - [ ] JSON validates
     - [ ] No duplicate SOPs

---

## SOP Quality Standards

### Required Fields
- ✅ Material selection (DMR III, DCA, DCA Plus, FPD, DNG)
- ✅ Application (what are you making?)
- ✅ Equipment (what printer/equipment)
- ✅ At least 3 workflow steps
- ✅ Firmware versions (if material-specific)

### Best Practices

#### 1. Step Names Should Be Clear
❌ Bad: "Do the thing"
✅ Good: "Load Resin Tank into iLuxPro Printer"

#### 2. Substeps Need Detail
❌ Bad: "Process it"
✅ Good: 
- "Insert resin tank with blue label facing forward"
- "Tap tank 3 times to settle resin"
- "Close printer door gently"

#### 3. Use Tags Effectively
- **⚠️ Warning** - Safety critical, expensive mistakes
- **💡 Tip** - Optimization, saves time
- **🔴 Critical** - Must follow exactly
- **⏱️ Timing** - Speed-sensitive steps
- **📷 Visual** - Important to see the image

#### 4. Images Matter
- **Show the screen** - Printer settings, screen interfaces
- **Show the part** - What good output looks like
- **Show common mistakes** - What to avoid
- **Resolution:** 800x600px minimum
- **Format:** PNG preferred (cleaner than JPG)

#### 5. Testing Before Submission
Run the SOP with:
- [ ] Fresh technician (can they follow it?)
- [ ] Different printer model (is it universal?)
- [ ] Real production material (does it actually work?)
- [ ] Peak production hours (any surprises?)

---

## SOP Structure Template

```
Material: [DMR III / DCA / DCA Plus White / FPD / DNG]
Application: [What product are you making?]
Equipment: [iLuxPro Dental / FastPrint.io]
Resin Tank: [LEAP C+ / LEAP X]

LuxFlow Steps:
1. Printer Setup
   - Substep 1: Detail...
   - Substep 2: Detail... [with image]
   - Substep 3: Detail...

2. Print Execution
   - Substep 1: Detail...
   - Substep 2: Detail... [with image]

Post-Processing:
1. Wash Station Setup
   - Substep 1: Detail... [with image]

2. Cure Station
   - Substep 1: Detail...
   - Substep 2: Detail... [with image]

Finishing (Optional):
1. Quality Control
   - Substep 1: Detail... [with image]

2. Packaging
   - Substep 1: Detail...
```

---

## Review Process

### What Happens to Your Submission

1. **Submitted** → We receive your SOP export
2. **Under Review** (1-3 days)
   - Manufacturing team tests it
   - Quality team checks format
   - We ask clarifying questions in GitHub Issue
3. **Approved** ✅ → Merged into main SOP library
4. **Needs Changes** → We comment with feedback, you revise
5. **Published** 🎉 → Available to entire team

### Timeline
- Non-urgent SOPs: 1 week turnaround
- Material-critical SOPs: 2-3 day priority review
- Emergency procedures: Reviewed within hours

---

## Reporting Issues

Found an error in an existing SOP?

1. Go to **Issues** tab
2. Click **New Issue**
3. Title: "Fix SOP: [Material] - [Issue]"
4. Description:
   ```
   What's wrong: [Clear description]
   Where: [Step number or section]
   Impact: [Does this cause bad parts? Safety issue?]
   Suggested fix: [How to correct it]
   ```

---

## Questions?

- **How do I...?** → Check existing SOPs for examples
- **This is confusing** → Open an Issue, ask in Discussions
- **I found a bug** → Report in Issues tab
- **Feature request** → Discuss in GitHub Discussions

---

## Recognition

Contributors with 5+ accepted SOPs get:
- 🏆 Listed as "Contributing Author" in README
- 📌 Pinned to repository highlights
- 🎖️ Contributor badge on profile

---

## Code of Conduct

- Be respectful in all comments and discussions
- Assume good intent from reviewers
- Provide constructive feedback
- Celebrate improvements together

Thank you for making our documentation better! 🚀
