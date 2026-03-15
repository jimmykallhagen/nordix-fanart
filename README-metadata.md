# Nordix Fanart - Digital Artist Metadata Guide

---

## 1. - **Install perl-image-exiftool.**

Arch Linux:
```bash
sudo pacman -S perl-image-exiftool
```

---

## 2. - **How to set your license**

Write metadata to a single image:
```bash
exiftool -r \
-XMP-dc:creator="Jimmy Källhagen" \
-XMP-dc:rights="© 2026 Jimmy Källhagen" \
-XMP-xmpRights:Marked=True \
-XMP-xmpRights:UsageTerms="CC-BY-NC-4.0" \
-XMP-cc:License="https://creativecommons.org/licenses/by-nc/4.0/" \

-XMP-dc:description="Nordix fanart Linux wallpaper" \
"/path/to/your/image-folder/image.png"
```

Batch write:
```bash
exiftool -r \
-XMP-dc:creator="Jimmy Källhagen" \
-XMP-dc:rights="© 2026 Jimmy Källhagen" \
-XMP-xmpRights:Marked=True \
-XMP-xmpRights:UsageTerms="CC-BY-NC-4.0" \
-XMP-cc:License="https://creativecommons.org/licenses/by-nc/4.0/" \

-XMP-dc:description="Nordix fanart Linux wallpaper" \
"/path/to/your/image-folder/"
```

**Overwrite existing metadata - without create a backup file**

Write metadata to a single image:
```bash
exiftool -r -overwrite_original \
-XMP-dc:creator="Jimmy Källhagen" \
-XMP-dc:rights="© 2026 Jimmy Källhagen" \
-XMP-xmpRights:Marked=True \
-XMP-xmpRights:UsageTerms="CC-BY-NC-4.0" \
-XMP-cc:License="https://creativecommons.org/licenses/by-nc/4.0/" \

-XMP-dc:description="Nordix fanart Linux wallpaper" \
"/path/to/your/image-folder/image.png"
```

Batch write:
```bash
exiftool -r -overwrite_original \
-XMP-dc:creator="Jimmy Källhagen" \
-XMP-dc:rights="© 2026 Jimmy Källhagen" \
-XMP-xmpRights:Marked=True \
-XMP-xmpRights:UsageTerms="CC-BY-NC-4.0" \
-XMP-cc:License="https://creativecommons.org/licenses/by-nc/4.0/" \

-XMP-dc:description="Nordix fanart Linux wallpaper" \
"/path/to/your/image-folder/"
```

- Change the info to your own.
- pick the license you want to use
- [Example of license](https://creativecommons.org/share-your-work/cclicenses/)

---

## 3. - **Add a LICENSE.md to your fanart repository**
- [**Example**](nordix-fanart/LICENSE.md)

---

## 4. - **The license "CC-BY-NC-4.0"**

This license means that you may **use, share, and modify** the artwork **for non-commercial purposes only**, as long as you give **credit to the creator**.

All commercial rights remain with the creator.  
You may **not** use the artwork commercially, such as:
- selling prints or digital copies  
- including in advertising  
- distributing in commercial products

---

## 5. - **Show metadata**

**IPTC and XMP format**
```bash
exiftool -a -G1 -s "image.png"
```

**Extract XMP as text file**
```bash
exiftool -b -XMP "image.png" > "image.xmp"
```

---
