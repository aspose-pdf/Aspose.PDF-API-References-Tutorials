---
title: Nastavit informace o souboru v souboru PDF
linktitle: Nastavit informace o souboru v souboru PDF
second_title: Aspose.PDF pro .NET API Reference
description: Naučte se, jak používat Aspose.PDF pro .NET k nastavení informací o souboru v souboru PDF pomocí tohoto podrobného průvodce.
type: docs
weight: 310
url: /cs/net/programming-with-document/setfileinfo/
---
Pokud pracujete na projektu, který vyžaduje správu souborů PDF pomocí Aspose.PDF pro .NET, jednou z funkcí, kterou možná budete chtít využít, je možnost nastavit informace o souboru pro dokument PDF. Informace o souboru zahrnují různé podrobnosti, jako je autor, datum vytvoření, klíčová slova, datum úpravy, předmět a název. Tato příručka vás provede procesem nastavení informací o souboru pro dokument PDF pomocí zdrojového kódu C# s Aspose.PDF pro .NET.

## Podrobný průvodce nastavením informací o souboru pomocí Aspose.PDF pro .NET

1. Vytvořte nový projekt C# ve svém IDE sady Visual Studio.
2. Přidejte do projektu odkaz na knihovnu Aspose.PDF for .NET.
3. Vytvořte nový objekt dokumentu PDF zadáním cesty k souboru PDF, pro který chcete upravit informace o souboru.

## Krok 1: Nastavte cestu k adresáři dokumentů.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Krok 2: Otevřete dokument PDF

```csharp
// Otevřete dokument
Document pdfDocument = new Document(dataDir + "SetFileInfo.pdf");
```

## Krok 3: Pomocí objektu DocumentInfo získáte přístup k informacím o souboru dokumentu PDF.

```csharp
DocumentInfo docInfo = new DocumentInfo(pdfDocument);
```

## Krok 4: Nastavte požadované hodnoty informací o souboru pomocí vlastností objektu DocumentInfo.

```csharp
docInfo.Author = "Aspose";
docInfo.CreationDate = DateTime.Now;
docInfo.Keywords = "Aspose.Pdf, DOM, API";
docInfo.ModDate = DateTime.Now;
docInfo.Subject = "PDF Information";
docInfo.Title = "Setting PDF Document Information";
```

## Krok 5: Uložte aktualizovaný dokument PDF do určeného umístění.

```csharp
dataDir = dataDir + "SetFileInfo_out.pdf";
pdfDocument.Save(dataDir);
```

## Krok 6: Ověřte, že informace o souboru byly úspěšně aktualizovány.

```csharp
Console.WriteLine("\nFile informations setup successfully.\nFile saved at " + dataDir);
```

Úspěšně jste nastavili informace o souboru pro dokument PDF pomocí Aspose.PDF for .NET.

### Příklad zdrojového kódu pro Set File Info pomocí Aspose.PDF pro .NET


```csharp
// Cesta k adresáři dokumentů.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Otevřete dokument
Document pdfDocument = new Document(dataDir + "SetFileInfo.pdf");

// Zadejte informace o dokumentu
DocumentInfo docInfo = new DocumentInfo(pdfDocument);

docInfo.Author = "Aspose";
docInfo.CreationDate = DateTime.Now;
docInfo.Keywords = "Aspose.Pdf, DOM, API";
docInfo.ModDate = DateTime.Now;
docInfo.Subject = "PDF Information";
docInfo.Title = "Setting PDF Document Information";

dataDir = dataDir + "SetFileInfo_out.pdf";
// Uložit výstupní dokument
pdfDocument.Save(dataDir);

Console.WriteLine("\nFile informations setup successfully.\nFile saved at " + dataDir);
```

## Závěr

Závěrem lze říci, že Aspose.PDF for .NET poskytuje jednoduchý a efektivní způsob nastavení informací o souborech pro dokumenty PDF. Podle výše uvedených kroků můžete snadno nastavit požadované hodnoty informací o souborech pro vaše dokumenty PDF pomocí zdrojového kódu C#.

### Často kladené otázky pro nastavení informací o souboru v souboru PDF

#### Otázka: Mohu nastavit další vlastnosti informací o souboru, které nejsou uvedeny v příkladu?

 Odpověď: Ano, můžete nastavit další vlastnosti informací o souboru pomocí`DocumentInfo` objekt v Aspose.PDF pro .NET. The`DocumentInfo`class poskytuje různé vlastnosti, které vám umožňují nastavit další informace, jako je výrobce, verze a uživatelské vlastnosti.

#### Otázka: Je možné získat informace o souboru z existujícího dokumentu PDF?

 Odpověď: Ano, informace o souboru můžete získat z existujícího dokumentu PDF pomocí Aspose.PDF pro .NET. Chcete-li to provést, můžete použít`DocumentInfo` objekt pro přístup k vlastnostem informací o souboru a čtení informací uložených v dokumentu PDF.

#### Otázka: Změní nastavení informací o souboru původní dokument PDF?

Odpověď: Ne, nastavení informací o souboru pomocí Aspose.PDF pro .NET nemění původní dokument PDF. Místo toho vytvoří nový dokument PDF s aktualizovanými informacemi o souboru. Původní dokument PDF zůstane nezměněn.