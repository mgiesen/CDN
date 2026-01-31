# Beschreibung

Zentrales Asset-Repo für Bilder, PDFs und Docs zum einfachen Verlinken.

## Vorgehen

1. UUID generieren und Datei benennen
1. Datei in Repository hochladen
1. Öffentlichen Link auf Drittplattform teilen/verlinken

## Generierung von UUID

[https://mgiesen.github.io/CDN/](https://mgiesen.github.io/CDN/)

## Öffentliche Verlinkung

https://raw.githubusercontent.com/mgiesen/CDN/main/assets/FILENAME.jpg

## Bildkomprimierung mit WebP

Bilder sollten vor dem Upload komprimiert werden. Das **WebP-Format** bietet eine hervorragende Komprimierung bei hoher Bildqualität.

### Installation

```bash
brew install webp
```

### Einzelne Bilder konvertieren

```bash
cwebp -q 90 input.jpg -o output.webp
```

- `-q 85` setzt die Qualität (0-100)
- Ergebnis: **50-70% Größeneinsparung** im Vergleich zu JPG

### Alle JPEG und PNG Dateien in einem Ordner konvertieren

```bash
for file in *.{jpg,jpeg,png}(N); do
  cwebp -q 85 "$file" -o "${file%.*}.webp";
done
```

> **Hinweis:** Syntax optimiert für **zsh** (macOS Standard).

### Alle JPEG und PNG Dateien in einem Ordner löschen

> ⚠️ **Vorsicht:** Löscht unwiderruflich alle Originale!

```bash
for file in *.{jpg,jpeg,png}(N); do
  rm "$file"
done
```

> **Hinweis:** Syntax optimiert für **zsh** (macOS Standard).
