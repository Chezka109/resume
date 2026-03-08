# Chezka Quinola's Resume

My personal resume built using LaTeX. This template is forked from [Sourabh Bajaj's resume template](https://github.com/sb2nov/resume) with additional enhancements including QR code generation.

## Features

- Clean, ATS-friendly single/two-page format
- Embedded QR code linking to the resume PDF
- Python-based QR code generator
- Custom sections optimized for software engineering roles

## Building the Resume

### Using TinyTeX (macOS)

```sh
export PATH="$HOME/Library/TinyTeX/bin/universal-darwin:$PATH"
pdflatex -interaction=nonstopmode chezka_quinola_resume.tex
```

### Using Docker

```sh
docker build -t latex .
docker run --rm -i -v "$PWD":/data latex pdflatex chezka_quinola_resume.tex
```

### Generating QR Code

The QR code is generated using Python:

```sh
python3 -c "import qrcode; qr = qrcode.QRCode(version=1, box_size=8, border=1); qr.add_data('YOUR_URL_HERE'); qr.make(fit=True); img = qr.make_image(fill_color='black', back_color='white'); img.save('qrcode.png')"
```

## Credits

This resume is based on [Sourabh Bajaj's LaTeX resume template](https://github.com/sb2nov/resume) (MIT License).
