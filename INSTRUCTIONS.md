# Resume Compilation Instructions

## Prerequisites

- TinyTeX or LaTeX distribution
- Python 3 with `qrcode` and `pillow` packages (for QR code generation)
- Docker (optional, for containerized compilation)

## Generating the QR Code

If you need to regenerate the QR code (e.g., if you change your Linktree URL):

```bash
python3 -c "import qrcode; qr = qrcode.QRCode(version=1, box_size=10, border=2); qr.add_data('https://linktr.ee/chezkaquinola'); qr.make(fit=True); img = qr.make_image(fill_color='black', back_color='white'); img.save('qrcode.png')"
```

Or with the virtual environment:

```bash
.venv/bin/python -c "import qrcode; qr = qrcode.QRCode(version=1, box_size=10, border=2); qr.add_data('https://linktr.ee/chezkaquinola'); qr.make(fit=True); img = qr.make_image(fill_color='black', back_color='white'); img.save('qrcode.png')"
```

## Compiling the Resume

### Option 1: Using TinyTeX (macOS)

```bash
export PATH="/Users/chezkaquinola/Library/TinyTeX/bin/universal-darwin:$PATH"
pdflatex chezka_quinola_resume.tex
```

### Option 2: Using Docker

First, start Docker, then run:

```bash
bash build.sh
```

## ATS Optimization Features

This resume template is optimized for Applicant Tracking Systems (ATS):

1. **Clean formatting**: Uses standard LaTeX fonts and clear section headers
2. **Machine-readable text**: `\pdfgentounicode=1` ensures text extraction works properly
3. **Logical structure**: Clear sections with standard names (Education, Experience, Skills, etc.)
4. **No complex graphics**: QR code is the only image, placed separately from main content
5. **Keyword-rich**: Includes relevant technical skills and accomplishments
6. **Standard fonts**: Uses Computer Modern fonts that are universally readable
7. **Hyperlinks**: Email, phone, and website are clickable but also parseable as plain text

## Customization

To update your resume:

1. Edit `chezka_quinola_resume.tex`
2. Update content in each section
3. Regenerate QR code if URL changes
4. Recompile using one of the methods above

## Output

The compiled PDF will be: `chezka_quinola_resume.pdf`
