# Tag Highlighting Syntax Guide

## New Format: `[TAGNAME "highlighted text"]`

Tags now fully highlight the specified text with color, using a flexible syntax.

---

## How It Works

### Syntax Structure
```
[TAGNAME "displayed text"]
  │       │        │
  │       │        └─ The text that appears highlighted
  │       └─ Opening quote (required)
  └─ Tag name determines color
```

### Example
```
Input:  "Heat to 200°C [CRITICAL "critical step"] for 5 minutes"

Output: Heat to 200°C [critical step] for 5 minutes
                      (red highlight)
```

---

## Visual Examples

### Example 1: Single Word Highlight
```
Input:  "Add safety goggles [SAFETY "required"]"
Output: Add safety goggles required
                    (red highlight)
```

### Example 2: Phrase Highlight
```
Input:  "Heat mixture to 200°C [CRITICAL "exactly 5 minutes"] before adding"
Output: Heat mixture to 200°C exactly 5 minutes before adding
                       (red highlight)
```

### Example 3: Multiple Tags
```
Input:  "First [EQUIPMENT-SPECIFIC "calibrate the unit"], then [TIME-SENSITIVE "wait 30 seconds"]"
Output: First calibrate the unit, then wait 30 seconds
        (purple highlight)         (amber highlight)
```

### Example 4: Longer Text
```
Input:  'Ensure [SAFETY "proper ventilation is maintained throughout process"]'
Output: Ensure proper ventilation is maintained throughout process
        (red highlight)
```

---

## Tag Colors Reference

| Tag Name | Color | Usage |
|----------|-------|-------|
| CRITICAL | Red | Critical steps that cannot be skipped |
| SAFETY | Red | Safety-related instructions |
| WARNING | Amber | Important warnings |
| TIME-SENSITIVE | Amber | Time-critical steps |
| TEMPERATURE | Red | Temperature specifications |
| EQUIPMENT-SPECIFIC | Purple | Equipment-specific procedures |
| QC-CHECK | Blue | Quality control checkpoints |
| OPTIONAL | Green | Optional steps |
| CONTAMINATION-RISK | Red | Contamination risks |

Custom tags also supported (use any tag name, will default to purple #6366f1 until customized).

---

## Real-World Examples

### Manufacturing SOP
```
"1. Place print trays in queue [CRITICAL "max 11 trays per run"]
2. Verify no overlapping [QC-CHECK "scan for conflicts"]  
3. Enable processing [TIME-SENSITIVE "must complete within 1 hour"]
4. Monitor temperature [TEMPERATURE "maintain 45-50°C"]
5. Optional: Use [OPTIONAL "automated templates"] if available"
```

Displays as:
```
1. Place print trays in queue max 11 trays per run
                          (red highlight)
2. Verify no overlapping scan for conflicts
                        (blue highlight)
3. Enable processing must complete within 1 hour
               (amber highlight)
4. Monitor temperature maintain 45-50°C
                     (red highlight)
5. Optional: Use automated templates if available
            (green highlight)
```

### Laboratory SOP
```
"Pre-heat oven to [TEMPERATURE "200°C"] for [TIME-SENSITIVE "15 minutes minimum"]
[SAFETY "Wear heat-resistant gloves"] when handling hot equipment
Check [QC-CHECK "exact temperature with calibrated thermometer"] before use"
```

---

## Important Syntax Rules

✅ **Correct Syntax**
```
[TAGNAME "text"]       - Standard format
[CRITICAL "step"]      - Works
[TIME-SENSITIVE "5 min"] - Works with dash
[QC-CHECK "verify"]    - Works with dash
[CUSTOM "any text"]    - Custom tags work
```

❌ **Incorrect Syntax**
```
[CRITICAL text]        - Missing quotes (won't highlight)
[CRITICAL "text]       - Missing closing quote (won't work)
[CRITICAL text"]       - Missing opening quote (won't work)
[critical "text"]      - Tag name case-sensitive (use uppercase)
```

---

## Tips & Best Practices

### 1. Use Clear Highlight Text
```
❌ Poor:   "Follow [CRITICAL "instructions"]"
✅ Good:  "Follow [CRITICAL "critical safety steps"]"
```

### 2. Keep Highlighted Text Short
```
❌ Too long:  [CRITICAL "make sure you follow all the safety procedures very carefully"]
✅ Better:   [CRITICAL "follow safety procedures"]
```

### 3. Highlight Key Information Only
```
❌ Over-highlighted:  [CRITICAL "Heat to"] 200°C [CRITICAL "exactly"] for 5 minutes [CRITICAL "minimum"]
✅ Strategic:         Heat to 200°C [CRITICAL "exactly 5 minutes"] minimum
```

### 4. Use Consistent Tag Names
```
✅ Consistent:  [CRITICAL "..."] and [CRITICAL "..."]
❌ Inconsistent: [CRITICAL "..."] and [CRITICAL-STEP "..."]
```

---

## Customizing Tag Colors

1. Click **🎨 Tag Colors** in navigation
2. Find your tag in the list (e.g., CRITICAL, SAFETY, etc.)
3. Click the colored circle to pick a new color
4. Or type hex code directly
5. Changes apply to all new/edited SOPs

### Adding Custom Tags
1. Use any tag name: `[MYNEWTAG "text"]`
2. Will use default purple (#6366f1) until customized
3. Go to Tag Colors to set custom color
4. From then on, all [MYNEWTAG] uses that color

---

## Exporting & Importing

### Export Format
- SOPs export as JSON with full `[TAGNAME "text"]` syntax preserved
- All colors and formatting maintained
- Images and data fully included

### Import Format
- Import any exported SOP
- Syntax preserved exactly
- Colors load from your current Tag Colors settings
- Text renders with appropriate highlighting

---

## Troubleshooting

### Text not highlighting?
**Problem**: `[CRITICAL "text"]` doesn't highlight
**Solution**: Check syntax:
- Is tag name in UPPERCASE?
- Are quotes present and correct?
- Is there a space between tag name and quote?

### Wrong color showing?
**Problem**: Text highlights in wrong color
**Solution**: 
- Tag name is case-sensitive: use `[CRITICAL]` not `[critical]`
- Check Tag Colors if it's a custom tag
- Refresh page to reload color settings

### Text disappears?
**Problem**: Highlighted text vanishes
**Solution**: Verify quote placement:
```
✅ Correct: [CRITICAL "visible text"]
❌ Wrong:   [CRITICAL"visible text"]  (no space)
❌ Wrong:   [CRITICAL "visible text]  (mismatched quotes)
```

---

## HTML Output

When rendered, highlighted text generates:
```html
<span class="inline-tag" style="background-color: #dc2626;">critical step</span>
```

The span includes:
- **Class**: `inline-tag` (for CSS styling)
- **Style**: Dynamic background color from tag
- **Text**: Your custom quoted text (fully visible)
- **Color**: White text on colored background (automatic)

---

## Advanced Usage

### Nested-like Highlighting
```
"First [CRITICAL "prepare equipment"], then [SAFETY "put on protection"], finally [TIME-SENSITIVE "start process"]"
```

### Multiple Highlights in One Step
```
"Heat [TEMPERATURE "200°C"] for [TIME-SENSITIVE "exactly 5 minutes"] while [SAFETY "maintaining ventilation"]"
```

### Paragraph-Length Highlights
```
"[CRITICAL "Do not exceed 250°C at any point, as this will cause thermal degradation of the material. Keep temperature constant throughout the entire process to ensure proper curing."]"
```

---

## Migration from Old Format

If you were using the old `[TagName]` syntax:
- **Old**: `Heat to 200°C [CRITICAL]`
- **New**: `Heat to 200°C [CRITICAL "critical step"]`

Simply add the quoted text inside and your SOPs will display beautifully highlighted!

---

## File Location
- **Main**: `/mnt/user-data/outputs/sop_generator.html`

---

**Last Updated**: December 15, 2025
**Syntax**: `[TAGNAME "highlighted text"]`
**Status**: ✅ Full text highlighting with color
