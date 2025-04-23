# 📘 AL-Bank Umbraco Site – Setup Guide

Dette dokument beskriver, hvordan man opsætter et **Umbraco 13.8.0** projekt med **Tailwind CSS**. Guiden dækker opsætning af backend og frontend, samt ekstra features og tips til en moderne brugeroplevelse.

---

## ✅ Teknologier og versioner

| Teknologi         | Version       |
|-------------------|---------------|
| .NET SDK          | `8.0.408`     |
| Umbraco CMS       | `13.8.0`      |
| Tailwind CSS      | Seneste       |
| PostCSS           | Seneste       |
| Autoprefixer      | Seneste       |
| npm (Node.js)     | Seneste       |

---

## 🛠️ Opsætning trin-for-trin

### 1. Installation Umbraco templates

```bash
dotnet new install Umbraco.Templates::13.8.0 --force

- Opretter en ny Visual Studio løsning med navnet "Al project case".
    dotnet new sln --name "Al project case" 

- Opretter en ny Visual Studio løsning med navnet "Al project case".
    dotnet new umbraco --force -n "AL-Bank Umbraco Site" --friendly-name "Nemo" --email "nemo.spaske@live.com" --password "Nemos003s!" --development-database-type SQLite 

- Opret et nyt Umbraco projekt
    dotnet new umbraco --force -n "AL-Bank Umbraco Site" --friendly-name "Nemo" --email "nemo.spaske@live.com" --password "Nemos003s!" --development-database-type SQLite

- Tilføj projektet til løsningen
    dotnet sln add "AL-Bank Umbraco Site"

- Start projektet
    dotnet run --project "AL-Bank Umbraco Site" 

    
### 2. Umbraco Setup

#### Document Types Created:

- `Produkt`
  - `Produktnavn` (Text)
  - `Beskrivelse` (Rich Text Editor)
  - `ProduktBeskrivelse` (Rich Text – shown only in modal)
  - `Pris` (Decimal)
  - `Produktbillede` (Media Picker)
  - `Produktbillede1` (Optional second Media Picker)

- `Produktside`
  - `Sidetitel` (Text)
  - Uses **child nodes of type `Produkt`** to dynamically list products

- `KontaktSide`
  - `Sidetitel`, `Beskrivelse`, `Email`, `Telefonnummer`, `Adresse`, `Kort` (Google Maps iframe)

- `HomePage`
  - `Title`, `Beskrivelse`

---

### 2. Frontend Setup – Tailwind CSS

    npm init -y
    npm install -D tailwindcss postcss autoprefixer
    npx tailwindcss init -p

- Responsive **grid layout** using Tailwind: `grid-cols-2`, `grid-cols-3`, `auto-fit`, `minmax(...)`
- Product cards designed as **Partial Views** with image, name, price, and short description
- Modal built with **Alpine.js** for interactive preview with image thumbnails, zoom, and transitions
- **Hover effects**, **mobile-first layout**, and clean design

---

### 3. Extra Features

- Modal supports multiple images with click-to-zoom preview
- Embedded Google Maps iframe on contact page
- Sticky footer and responsive navigation
- Fallbacks and validation for missing fields/images
- Fully styled contact page with SVG icons and Tailwind

---
