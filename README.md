# Petition Signer PDF Generator

A simple browser-based tool to convert CSV exports (from ActionKit or similar platforms) into formatted petition signer PDFs. Handles 5,000+ signers efficiently, automatically paginating as needed.

## 🔒 Privacy First

**Your data never leaves your computer.** All CSV processing and PDF generation happens entirely in your browser. No data is uploaded to any server.

For extra confidence, you can disconnect from the internet after the page loads — the tool will continue to work completely offline.

## Usage

1. Open `index.html` in your browser
2. Drop your CSV file onto the page (or click to browse)
3. Verify the column mapping (auto-detects common column names – see below)
4. Click "Generate PDF"
5. Save the downloaded PDF

## CSV Format

The tool auto-detects common column names from ActionKit and other platforms:

| Field | Recognized columns |
|-------|-------------------|
| First Name | `first_name`, `firstname`, `first`, `fname` |
| Last Name | `last_name`, `lastname`, `last`, `lname`, `surname` |
| City | `city`, `town` |
| State | `state`, `region`, `province` |
| ZIP | `zip`, `postal`, `postal_code`, `zipcode`, `zip_code` |

If your columns have different names, just select the correct mapping from the dropdowns.

## Output Format

The PDF generates a 3-column grid with:
- Name (bold) on the first line
- City, State ZIP on the second line
- Clean, bordered cells

---

## Fully Offline Version

The default `index.html` loads the jsPDF library from a CDN (unpkg.com). If you want a completely offline version with no network requests:

1. Download jsPDF: https://unpkg.com/jspdf@3.0.4/dist/jspdf.umd.min.js
2. Save it as `jspdf.umd.min.js` in the same folder as `index.html`
3. Edit `index.html` and change this line:
   ```html
   <script src="https://unpkg.com/jspdf@3.0.4/dist/jspdf.umd.min.js"></script>
   ```
   to:
   ```html
   <script src="jspdf.umd.min.js"></script>
   ```
   
---

## Credits

Built with [jsPDF](https://github.com/parallax/jsPDF) for PDF generation.
