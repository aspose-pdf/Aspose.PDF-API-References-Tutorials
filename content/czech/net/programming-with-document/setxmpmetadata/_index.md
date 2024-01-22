---
title: Nastavit XMPMetadata v souboru PDF
linktitle: Nastavit XMPMetadata v souboru PDF
second_title: Aspose.PDF pro .NET API Reference
description: Naučte se, jak nastavit XMPMetadata v souboru PDF pomocí Aspose.PDF pro .NET. Postupujte podle tohoto podrobného průvodce.
type: docs
weight: 330
url: /cs/net/programming-with-document/setxmpmetadata/
---
V tomto článku poskytneme podrobný návod, jak používat Aspose.PDF pro .NET k nastavení metadat XMP v souboru PDF. Na konci článku poskytneme úplný příklad zdrojového kódu.

## Krok 1: Nastavte cestu k adresáři dokumentů

Než začneme, musíme nastavit cestu k adresáři, kde se nachází náš PDF dokument. Tuto cestu uložíme do proměnné s názvem „dataDir“.

```csharp
// Cesta k adresáři dokumentů.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Nezapomeňte vyměnit`YOUR DOCUMENT DIRECTORY` se skutečnou cestou k vašemu souboru PDF.

## Krok 2: Otevřete soubor PDF

 Prvním krokem je otevření souboru PDF, pro který chcete nastavit metadata XMP. Chcete-li to provést, musíte vytvořit nový`Document` objekt a předejte cestu k vašemu souboru PDF.

```csharp
// Cesta k adresáři dokumentů.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Otevřete dokument
Document pdfDocument = new Document(dataDir + "SetXMPMetadata.pdf");
```

## Krok 3: Nastavte vlastnosti metadat XMP

Nyní, když máte otevřený soubor PDF, můžete začít nastavovat vlastnosti metadat XMP. Vlastnosti, které nastavíte, budou záviset na vašich konkrétních potřebách, ale zde jsou některé běžné vlastnosti, které byste mohli chtít nastavit:

- `xmp:CreateDate`: Datum vytvoření souboru PDF.
- `xmp:Nickname`: Přezdívka nebo alias pro soubor PDF.
- `xmp:CustomProperty`: Vlastní vlastnost s hodnotou, kterou určíte.

 Chcete-li nastavit tyto vlastnosti, můžete použít`Metadata` vlastnictvím`Document` objekt. Zde je příklad:

```csharp
// Nastavit vlastnosti
pdfDocument.Metadata["xmp:CreateDate"] = DateTime.Now;
pdfDocument.Metadata["xmp:Nickname"] = "Nickname";
pdfDocument.Metadata["xmp:CustomProperty"] = "Custom Value";
```

tomto tutoriálu nastavujeme datum vytvoření na aktuální datum a čas, přezdívku na „Přezdívku“ a uživatelskou vlastnost na „Vlastní hodnotu“. Tyto hodnoty můžete nahradit vlastními.

## Krok 4: Uložte soubor PDF

 Po nastavení vlastností metadat XMP je třeba uložit soubor PDF. Chcete-li to provést, můžete použít`Save` metoda`Document` objekt a předejte cestu k místu, kam chcete uložit aktualizovaný soubor PDF.

```csharp
dataDir = dataDir + "SetXMPMetadata_out.pdf";
// Uložit dokument
pdfDocument.Save(dataDir);
```

### Příklad zdrojového kódu pro sadu XMPMetadata pomocí Aspose.PDF pro .NET

Zde je kompletní ukázkový zdrojový kód pro nastavení XMPMetadata pomocí Aspose.PDF pro .NET:

```csharp
// Cesta k adresáři dokumentů.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Otevřete dokument
Document pdfDocument = new Document(dataDir + "SetXMPMetadata.pdf");

// Nastavit vlastnosti
pdfDocument.Metadata["xmp:CreateDate"] = DateTime.Now;
pdfDocument.Metadata["xmp:Nickname"] = "Nickname";
pdfDocument.Metadata["xmp:CustomProperty"] = "Custom Value";

dataDir = dataDir + "SetXMPMetadata_out.pdf";
// Uložit dokument
pdfDocument.Save(dataDir);

Console.WriteLine("\nXMP metadata in a pdf file setup successfully.\nFile saved at " + dataDir);
```

## Závěr

Aspose.PDF for .NET nabízí přímočarý způsob, jak nastavit metadata XMP v souborech PDF, což vám umožňuje přidávat do dokumentů popisné informace a vlastnosti. Výše uvedený podrobný průvodce vám ukáže, jak nastavit různé vlastnosti metadat XMP pomocí zdrojového kódu C#. Navíc můžete upravit metadata XMP tak, aby odpovídala vašim specifickým potřebám a obchodním požadavkům. S Aspose.PDF for .NET se správa metadat PDF stává efektivní a umožňuje lepší organizaci a možnosti vyhledávání vašich dokumentů PDF.

### Nejčastější dotazy pro Set XMPMetadata v souboru PDF

#### Otázka: Co jsou metadata XMP v souboru PDF a proč jsou důležitá?

Odpověď: XMP (Extensible Metadata Platform) je standard pro vkládání metadat do různých formátů souborů, včetně PDF. Metadata XMP v souboru PDF umožňují přidat k dokumentu popisné informace a vlastnosti, jako je datum vytvoření, autor, název, klíčová slova a uživatelské vlastnosti. Je to nezbytné pro lepší organizaci, vyhledávání a archivaci dokumentů PDF.

#### Otázka: Mohu nastavit jiné vlastnosti metadat XMP kromě těch, které jsou uvedeny v příkladu?

 Odpověď: Ano, můžete nastavit širokou škálu vlastností metadat XMP v závislosti na vašich konkrétních požadavcích. Některé běžné vlastnosti zahrnují`dc:title` (název dokumentu),`dc:creator` (tvůrce dokumentů),`dc:description` (popis dokumentu),`pdf:Keywords` (klíčová slova dokumentu) a další. Specifikace XMP nabízí různé standardní jmenné prostory a vlastní jmenné prostory pro nastavení různých typů metadat.

#### Otázka: Je možné načíst a přečíst metadata XMP z existujícího souboru PDF?

 Odpověď: Ano, Aspose.PDF for .NET poskytuje možnost číst a získávat metadata XMP z existujícího souboru PDF. Můžete použít`Metadata` vlastnictvím`Document` třídy pro přístup k metadatům XMP a načtení hodnot konkrétních vlastností.