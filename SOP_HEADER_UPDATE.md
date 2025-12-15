# SOP Header Redesign & Customization Update

## ✨ What's New

### 1️⃣ Custom Material & Manufacturer
- **Material:** Changed from dropdown to **text input** (name it whatever you want)
- **Manufacturer:** New **text input field** (e.g., "LuxCreo", "3D Systems")
- Both appear prominently in the SOP document as a **big heading**

### 2️⃣ Product Images
- **Bottle/Product Image:** Upload image of the material bottle or product
- **Application Image:** Upload image of the application (e.g., aligner on teeth, crown, etc.)
- Images appear on the **right side** of the material/manufacturer/application heading
- Max size per image: 180x180px (automatically sized)

### 3️⃣ New SOP Document Layout

```
┌─────────────────────────────────────────────────────────┐
│                                                           │
│  BIG HEADING TEXT              [Image] [Image]           │
│  Material Name                                            │
│  Manufacturer Name                                        │
│  Application Type                                         │
│                                                           │
├─────────────────────────────────────────────────────────┤
│ Equipment: iLuxPro Dental          Resin Tank: LEAP C+  │
├─────────────────────────────────────────────────────────┤
│ LuxFlow: V1.4.3  |  Printer Firmware: V5.5.8  | ...    │
├─────────────────────────────────────────────────────────┤
│                                                           │
│  LUXFLOW: ONE-CLICK GENERATION                           │
│  [Steps and substeps...]                                │
│                                                           │
│  POST-PROCESSING                                         │
│  [Steps and substeps...]                                │
│                                                           │
│  FINISHING                                               │
│  [Steps and substeps...]                                │
│                                                           │
└─────────────────────────────────────────────────────────┘
```

---

## 📋 Form Changes (Creator Page)

### Material & Equipment Selection Section

**Material Name** (TEXT INPUT)
```
Previously: Dropdown with predefined options (DMR III, DCA, etc.)
Now: Type anything you want!
Example: "DMR III", "DCA Plus White", "Custom Material XYZ"
```

**Manufacturer** (NEW TEXT INPUT)
```
Label: Manufacturer
Example: "LuxCreo", "3D Systems", "FormLabs"
```

**Application** (TEXT INPUT - unchanged)
```
Example: "Aligner/Retainer", "Crown", "Bridge", etc.
```

### Product Images Section (NEW)

**Bottle/Product Image** (FILE UPLOAD)
- Upload image of the material bottle or product
- Shows 100x100px preview while editing
- Accepts: PNG, JPG, GIF, etc.
- Automatically converted to base64 (embedded in JSON)

**Application Image** (FILE UPLOAD)
- Upload image showing the application
- Example: Aligner in mouth, Crown on model, etc.
- Shows 100x100px preview while editing
- Same format as bottle image

### Printer & Equipment Section (REORGANIZED)

Separated from material section (was combined before)
- Printer/Equipment (dropdown unchanged)
- Resin Tank (dropdown unchanged)

---

## 🎨 Visual Typography Hierarchy

### In the Document Header

**Material Name (BIG HEADING)**
- Font size: 3em (300%)
- Font weight: 900 (extra bold)
- Color: White (on orange gradient background)
- Example: "DMR III" appears huge and prominent

**Manufacturer (SUB-HEADING)**
- Font size: 1.3em (130%)
- Font weight: 600 (semi-bold)
- Color: White, slight transparency (95%)
- Example: "LuxCreo"

**Application (SUB-HEADING)**
- Font size: 1.2em (120%)
- Font weight: 500 (medium)
- Color: White, slight transparency (90%)
- Example: "Aligner / Retainer"

---

### Equipment Subheading (SMALLER)
```
Equipment: iLuxPro Dental          Resin Tank: LEAP C+ (Digital Polishing)
```
- Font size: 0.95em (smaller than body text)
- Displayed in light gray box with orange left border
- Two columns: Equipment and Resin Tank

---

### Software/Firmware Versions (SMALL SUBTEXT)
```
LuxFlow: V1.4.3  |  Printer Firmware: V5.5.8.t14 or above  |  Wash Box: V2.1.0  |  ...
```
- Font size: 0.85em (small, condensed)
- Only shows versions that are filled in
- Light gray background for subtle appearance
- Displayed inline (wraps on mobile)

---

## 💾 JSON Structure

When you save/export a SOP, it now includes:

```json
{
  "id": 1702684800000,
  "name": "4D Aligner Manufacturing",
  "material": "DMR III",
  "manufacturer": "LuxCreo",
  "application": "Aligner / Retainer",
  "bottleImage": "data:image/png;base64,iVBORw0KGgoAAAANS...",
  "applicationImage": "data:image/png;base64,iVBORw0KGgoAAAANS...",
  "equipment": "iLuxPro Dental",
  "resinTank": "LEAP C+ (Digital Polishing)",
  "luxflowVersion": "V1.4.3",
  "printerFirmware": "V5.5.8.t14 or above",
  "washBoxFirmware": "V2.1.0.250509L/F",
  "cureBoxFirmware": "V1.0.1.250415 or above",
  "luxdesignEnabled": true,
  "luxdesignVersion": "V2.3.2+",
  "luxflow": [...],
  "postprocess": [...],
  "finishing": [...]
}
```

**New fields:**
- `manufacturer` - Manufacturer name text
- `bottleImage` - Base64 encoded image
- `applicationImage` - Base64 encoded image

---

## 📱 Responsive Design

### Desktop View (Wide Screens)
- Material/Manufacturer/Application text on LEFT
- Bottle and Application images on RIGHT (side-by-side)
- Equipment and Resin Tank in one row (2 columns)
- Software versions displayed inline with gaps

### Tablet & Mobile (< 768px)
- Material/Manufacturer/Application text STACKED
- Images BELOW text (centered)
- Equipment and Resin Tank STACKED (2 rows)
- Software versions STACKED (one per line)
- Material font size reduced to 2em

---

## 🔄 Workflow

### Creating a New SOP

```
1. Fill in "Material Name" (type custom name)
   Example: "DMR III"

2. Fill in "Manufacturer"
   Example: "LuxCreo"

3. Fill in "Application"
   Example: "Aligner / Retainer"

4. Upload "Bottle/Product Image"
   - Click file input
   - Select image from computer
   - See preview (100x100px)

5. Upload "Application Image"
   - Click file input
   - Select image from computer
   - See preview (100x100px)

6. Fill in Equipment and Resin Tank (dropdowns)

7. Fill in Software/Firmware Versions (optional)

8. Add Production Steps (LuxFlow, Post-Processing, Finishing)

9. Click "Save SOP" or "Export as JSON"
```

---

## ✅ What's Preserved

Everything from before still works:
- ✅ LuxFlow steps (Section 1)
- ✅ Post-Processing steps (Section 2)
- ✅ Finishing steps (optional Section 3)
- ✅ Image upload for substeps
- ✅ Cropper tool for editing images
- ✅ Tags for substeps (Critical, Warning, etc.)
- ✅ Save/Export functionality
- ✅ Import functionality
- ✅ Storage in window.storage or localStorage
- ✅ GitHub Pages compatibility

---

## 🎯 Use Cases

### 1. Custom Materials
```
Material: "DMR III Ultra"
Manufacturer: "LuxCreo Advanced Division"
App: "High-Precision Aligners"
→ Creates SOP for custom material variant
```

### 2. Different Manufacturers
```
Material: "HD Cast Resin"
Manufacturer: "FormLabs"
App: "Dental Models"
→ Track different source materials
```

### 3. Visual Reference
```
Material: "DCA Plus White"
Manufacturer: "LuxCreo"
Images: [Bottle photo] [Before/After casting example]
→ Visual reference for team on what to expect
```

---

## 🐛 Troubleshooting

### Image not showing in preview
- Check file size (should be under 5 MB)
- Try different image format (JPG, PNG)
- Refresh page and try again

### Images not saving in SOP
- Ensure images fully loaded before clicking Save
- Check browser console for errors (F12)
- Try exporting instead of saving

### File too large after export
- Images are base64 encoded (adds ~33% overhead)
- If total > 25 MB, consider splitting into multiple SOPs
- Or reduce image resolution before uploading

### Images don't appear on GitHub
- This is expected! Images are embedded in JSON
- They're stored as base64 text (not separate files)
- Images display when you import the JSON in the web app
- GitHub shows the raw JSON (not decoded images)

---

## 📊 File Size Reference

### Typical SOP Sizes (with images)

| Configuration | File Size | Notes |
|---------------|-----------|-------|
| 3 steps, no images | 15 KB | Tiny! |
| 3 steps, 2 product images | 1-2 MB | Great for sharing |
| 10 steps, 8 images | 4-6 MB | Good size |
| 20 steps, 15 images | 8-12 MB | Starting to get large |
| 30+ steps, 20+ images | 15-25 MB | Consider splitting |

---

## 🚀 Best Practices

### For Bottle Images
- Show the actual bottle/container
- Clear label visible if possible
- Straight-on or 45° angle
- Recommended size: 400x400px before upload
- Crop to bottle only (remove background)

### For Application Images
- Show the final product or application
- Example: Aligner on teeth, crown on model
- Clear, well-lit photo
- Recommended size: 400x400px before upload
- Include scale reference if helpful

### For Custom Materials
- Be specific in naming
- Include variant/version if applicable
- Example: "DMR III v2.1" vs just "DMR III"

### File Organization
- Use descriptive SOP names
- Follow pattern: "[Material] - [Application]"
- Example: "DMR III - Aligner Manufacturing"
- Makes it easy to find on GitHub

---

## 📚 Updated Files

### Modified
- **sop_generator.html** - Complete redesign with new sections and styling

### What Changed
1. Material field: Dropdown → Text input
2. Added manufacturer field
3. Added bottle image upload
4. Added application image upload
5. Reorganized form sections
6. New SOP header layout in viewer
7. New CSS styles for typography hierarchy
8. Responsive design for mobile
9. Image data stored in JSON

### Backward Compatible?
- Old SOPs without images still display fine
- Images optional (leave blank if not needed)
- Material/Manufacturer can be blank if needed
- No breaking changes to existing functionality

---

## 🎓 For Your Team

### Tell Them
"When creating SOPs, you can now:"
1. ✅ Name the material whatever you want (not limited to dropdown)
2. ✅ Add manufacturer info
3. ✅ Upload photos of the bottle/product
4. ✅ Upload photos of the application
5. ✅ See a beautiful header with all this info at the top

### Show Them
"Here's what it looks like:"
```
[Big "DMR III" text]
[Smaller "LuxCreo" text]
[Smaller "Aligner / Retainer" text]
[Photos of bottle and aligner on right]

Equipment: iLuxPro Dental | Resin Tank: LEAP C+

LuxFlow: V1.4.3 | Printer Firmware: V5.5.8 | etc.

[Rest of SOP steps...]
```

---

## 💡 Pro Tips

1. **Crop images tight** - Remove background, just the product
2. **Use high-contrast images** - Better visibility in PDF exports
3. **Keep material names consistent** - Makes searching easier
4. **Include version numbers** - "DMR III v2.0" is better than "DMR III"
5. **Test on mobile** - Images and text should look good on all sizes
6. **Export as JSON regularly** - Backup your work!

---

## 🔄 Version History

| Version | Changes |
|---------|---------|
| 1.0 | Initial SOP Generator with basic fields |
| 1.1 | Added custom application field |
| 1.2 | Added firmware version fields |
| **2.0** | **Custom material, Manufacturer, Product images, New header layout** |

---

## ❓ FAQ

**Q: Can I change material/manufacturer after saving?**
A: Yes! Load the SOP, edit the fields, save again (overwrites).

**Q: What image formats are supported?**
A: JPG, PNG, GIF, WebP - anything your browser supports.

**Q: Do images export correctly to GitHub?**
A: Yes, as base64 in the JSON file. Import the JSON to see the images.

**Q: Can I use the same image for multiple SOPs?**
A: Yes, upload it each time or copy/paste the JSON data.

**Q: What if I don't have product images?**
A: Leave blank - the fields are optional!

**Q: How do I remove an image after uploading?**
A: Click the file input and don't select anything, or clear it before saving.

**Q: Are images secure in the JSON file?**
A: Base64 is just encoding, not encryption. Same security as JSON files.

---

## 📞 Support

If images don't display:
1. Check file size (< 5 MB each)
2. Try JPG instead of PNG
3. Clear browser cache and refresh
4. Test export → import workflow
5. Check browser console for errors (F12)

All functionality working? Great! You're ready to create beautiful SOPs! 🚀
