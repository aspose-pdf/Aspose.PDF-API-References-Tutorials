---
title: Neviditelná anotace v souboru PDF
linktitle: Neviditelná anotace v souboru PDF
second_title: Aspose.PDF pro .NET API Reference
description: Naučte se, jak vytvořit neviditelnou anotaci v souboru PDF pomocí zdrojového kódu C# s Aspose.PDF pro .NET. Průvodce krok za krokem.
type: docs
weight: 100
url: /cs/net/annotations/invisibleannotation/
---
Anotace v souboru PDF jsou výkonnou funkcí, která vám umožňuje přidávat do dokumentu další informace nebo poznámky, aniž byste měnili skutečný obsah. Lze je použít ke zvýraznění textu, upozornit na konkrétní oblasti dokumentu nebo přidat komentáře či zpětnou vazbu.

Existuje mnoho různých typů anotací, které můžete použít v dokumentech PDF, včetně:

- Textové anotace
- Anotace odkazů
- Razítko Anotace
- Zvukové poznámky
- Anotace příloh souboru
- a mnoho dalších

## Krok 1: Vytvoření neviditelné anotace v dokumentu PDF pomocí Aspose.PDF pro .NET

 Chcete-li vytvořit neviditelnou anotaci v dokumentu PDF pomocí Aspose.PDF pro .NET, musíme nejprve vytvořit`FreeTextAnnotation` objekt a zadejte umístění a velikost anotace.

```csharp
// Cesta k adresáři dokumentů.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Otevřete dokument
Document doc = new Document(dataDir + "input.pdf");

FreeTextAnnotation annotation = new FreeTextAnnotation(doc.Pages[1], new Aspose.Pdf.Rectangle(50, 600, 250, 650), new DefaultAppearance("Helvetica", 16, System.Drawing.Color.Red));
```

 Ve výše uvedeném kódu vytvoříme a`FreeTextAnnotation`objekt a určete umístění anotace na stránce 2 dokumentu PDF. Určujeme také typ písma, velikost a barvu textu, který se zobrazí v anotaci.

## Krok 2: Přidání charakteristik do neviditelné anotace

Dále můžeme do poznámky přidat některé vlastnosti, jako je barva ohraničení, barva pozadí nebo neprůhlednost.

```csharp
annotation.Characteristics.Border = System.Drawing.Color.Red;
```

Ve výše uvedeném kódu jsme nastavili barvu ohraničení anotace na červenou.

## Krok 3: Nastavení příznaků anotace

Poté, co jsme vytvořili anotaci a nastavili její charakteristiky, můžeme určit příznaky anotace. V tomto tutoriálu chceme, aby byla anotace tisknutelná, ale ne viditelná.

```csharp
annotation.Flags = AnnotationFlags.Print | AnnotationFlags.NoView;
doc.Pages[1].Annotations.Add(annotation);
```

## Krok 4: Uložení upraveného dokumentu PDF

Nakonec můžeme upravený PDF dokument uložit s novou neviditelnou anotací.

```csharp
dataDir = dataDir + "InvisibleAnnotation_out.pdf";
doc.Save(dataDir);
```

## Příklad zdrojového kódu pro How to Invisible Annotation pomocí Aspose.PDF for .NET

```csharp
// Cesta k adresáři dokumentů.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Otevřete dokument
Document doc = new Document(dataDir + "input.pdf");

FreeTextAnnotation annotation = new FreeTextAnnotation(doc.Pages[1], new Aspose.Pdf.Rectangle(50, 600, 250, 650), new DefaultAppearance("Helvetica", 16, System.Drawing.Color.Red));
annotation.Contents = "ABCDEFG";
annotation.Characteristics.Border = System.Drawing.Color.Red;
annotation.Flags = AnnotationFlags.Print | AnnotationFlags.NoView;
doc.Pages[1].Annotations.Add(annotation);

dataDir = dataDir + "InvisibleAnnotation_out.pdf";
// Uložit výstupní soubor
doc.Save(dataDir);
// ExEnd:InvisibleAnnotation
Console.WriteLine("\nAnnotation nvisible successfully.\nFile saved at " + dataDir);
```

## Závěr

tomto tutoriálu jsme se naučili, jak vytvořit neviditelnou anotaci v dokumentu PDF pomocí Aspose.PDF pro .NET. Neviditelné anotace jsou užitečnou funkcí, když chcete do dokumentu přidat další informace nebo poznámky, aniž byste je zobrazili čtenáři. Podle podrobného průvodce a pomocí poskytnutého zdrojového kódu C# mohou vývojáři snadno vytvářet a přizpůsobovat neviditelné anotace ve svých dokumentech PDF. Aspose.PDF for .NET poskytuje komplexní sadu nástrojů pro práci s anotacemi, což vám umožní zlepšit interaktivitu a použitelnost vašich souborů PDF.

### FAQ

#### Otázka: Co je to neviditelná anotace v dokumentu PDF?

Odpověď: Neviditelná anotace v dokumentu PDF je anotace, která není na stránce viditelná, ale obsahuje další informace nebo poznámky. Umožňuje vám přidávat komentáře nebo zpětnou vazbu, aniž byste je zobrazili čtenáři.

#### Otázka: Jaké typy charakteristik lze přidat do neviditelné anotace?

Odpověď: K neviditelné anotaci lze přidat různé charakteristiky, jako je barva ohraničení, barva pozadí, neprůhlednost, typ písma, velikost a barva textu, který bude zobrazen.

#### Otázka: Mohu nastavit různé příznaky anotace pro neviditelnou anotaci?

Odpověď: Ano, můžete nastavit různé příznaky anotace pro neviditelnou anotaci, v závislosti na vašich požadavcích. Můžete například nastavit, aby se anotace dala vytisknout, ale ne zobrazitelná.

#### Otázka: Jak mohu přidat neviditelnou anotaci na konkrétní stránku dokumentu PDF?

 A: Chcete-li přidat neviditelnou anotaci na konkrétní stránku dokumentu PDF, musíte vytvořit a`FreeTextAnnotation` objekt a zadejte umístění a velikost anotace na této stránce.

#### Otázka: Mohu upravit vlastnosti existující neviditelné anotace v souboru PDF?

Odpověď: Ano, můžete upravit vlastnosti existující neviditelné anotace v souboru PDF pomocí Aspose.PDF for .NET. Můžete změnit typ písma, velikost, barvu, barvu ohraničení, barvu pozadí, krytí a další vlastnosti poznámky.