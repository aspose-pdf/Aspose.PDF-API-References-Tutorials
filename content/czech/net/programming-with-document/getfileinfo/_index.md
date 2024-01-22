---
title: Získejte informace o souboru v souboru PDF
linktitle: Získejte informace o souboru v souboru PDF
second_title: Aspose.PDF pro .NET API Reference
description: Naučte se používat funkci GetFileInfo in PDF souboru Aspose.PDF for .NET k načtení informací metadat o dokumentu PDF.
type: docs
weight: 180
url: /cs/net/programming-with-document/getfileinfo/
---
 Aspose.PDF for .NET je oblíbená knihovna pro manipulaci s PDF, která umožňuje vývojářům vytvářet, upravovat a převádět soubory PDF v jejich aplikacích .NET. Jednou z funkcí, které tato knihovna nabízí, je možnost získat informace o metadatech dokumentu PDF. Tento tutoriál vás provede kroky použití`GetFileInfo` funkce Aspose.PDF pro .NET k načtení informací o metadatech dokumentu PDF.

## Krok 1: Nainstalujte Aspose.PDF pro .NET

 Chcete-li používat Aspose.PDF pro .NET ve svých aplikacích .NET, musíte nejprve nainstalovat knihovnu. Nejnovější verzi knihovny si můžete stáhnout z[Stránka ke stažení Aspose.PDF pro .NET](https://releases.aspose.com/pdf/net).

Po stažení knihovny rozbalte obsah souboru ZIP do složky v počítači. Poté budete muset přidat odkaz na Aspose.PDF for .NET DLL ve vašem projektu .NET.

## Krok 2: Načtěte dokument PDF

Jakmile nainstalujete Aspose.PDF pro .NET a přidáte odkaz na knihovnu DLL ve svém projektu .NET, můžete začít používat`GetFileInfo` funkce pro načtení informací o metadatech dokumentu PDF.

Prvním krokem při použití této funkce je načtení dokumentu PDF, o kterém chcete získat informace. Chcete-li to provést, můžete použít následující kód:

```csharp
// Cesta k dokumentu PDF
string dataDir = "YOUR DOCUMENT DIRECTORY";

//Otevřete dokument PDF
Document pdfDocument = new Document(dataDir + "GetFileInfo.pdf");
```

 Ve výše uvedeném kódu nahraďte`"YOUR DOCUMENT DIRECTORY"` s cestou k adresáři, kde se nachází váš dokument PDF. Tento kód načte dokument PDF do a`Document` objekt, který pak můžete použít k načtení informací o metadatech dokumentu.

## Krok 3: Načtěte metadata dokumentu

Chcete-li získat informace o metadatech dokumentu PDF, můžete použít následující kód:

```csharp
// Získejte informace o dokumentu
DocumentInfo docInfo = pdfDocument.Info;

// Zobrazit informace o dokumentu
Console.WriteLine("Author: {0}", docInfo.Author);
Console.WriteLine("Creation Date: {0}", docInfo.CreationDate);
Console.WriteLine("Keywords: {0}", docInfo.Keywords);
Console.WriteLine("Modify Date: {0}", docInfo.ModDate);
Console.WriteLine("Subject: {0}", docInfo.Subject);
Console.WriteLine("Title: {0}", docInfo.Title);
```

Ve výše uvedeném kódu každý řádek načte jinou vlastnost metadat dokumentu PDF a odešle je do konzoly. Tento kód můžete přizpůsobit tak, aby získal pouze vlastnosti, které vás zajímají.

### Příklad zdrojového kódu získat informace o souboru PDF pomocí Aspose.PDF pro .NET

 Zde je úplný zdrojový kód pro načtení metadat dokumentu PDF pomocí`GetFileInfo` funkce Aspose.PDF pro .NET:

```csharp
// Cesta k dokumentu PDF
string dataDir = "YOUR DOCUMENT DIRECTORY";

//Otevřete dokument PDF
Document pdfDocument = new Document(dataDir + "GetFileInfo.pdf");

// Získejte informace o dokumentu
DocumentInfo docInfo = pdfDocument.Info;

// Zobrazit informace o dokumentu
Console.WriteLine("Author: {0}", docInfo.Author);
Console.WriteLine("Creation Date: {0}", docInfo.CreationDate);
Console.WriteLine("Keywords: {0}", docInfo.Keywords);
Console.WriteLine("Modify Date: {0}", docInfo.ModDate);
Console.WriteLine("Subject: {0}", docInfo.Subject);
Console.WriteLine("Title: {0}", docInfo.Title);
```

## Závěr

tomto tutoriálu jsme diskutovali o tom, jak použít Aspose.PDF pro .NET k načtení informací o metadatech dokumentu PDF. Načtením dokumentu PDF a přístupem k jeho vlastnostem metadat můžete získat informace o charakteristikách a vlastnostech dokumentu. Aspose.PDF for .NET poskytuje jednoduché a snadno použitelné rozhraní API pro práci s dokumenty PDF, včetně získávání informací o metadatech, což z něj činí cenný nástroj pro manipulaci s PDF v aplikacích .NET.

### FAQ

#### Otázka: Co jsou metadata v dokumentu PDF?

Odpověď: Metadata v dokumentu PDF odkazují na informace, které popisují vlastnosti a charakteristiky dokumentu. Tyto informace obvykle zahrnují název dokumentu, autora, předmět, klíčová slova, datum vytvoření, datum změny a další.

#### Otázka: Jak mohu nainstalovat Aspose.PDF for .NET do svého projektu .NET?

 A: Chcete-li nainstalovat Aspose.PDF pro .NET, musíte si stáhnout knihovnu z[Stránka ke stažení Aspose.PDF pro .NET](https://releases.aspose.com/pdf/net). Po stažení rozbalte obsah souboru ZIP a přidejte odkaz na Aspose.PDF for .NET DLL ve vašem projektu .NET.

#### Otázka: Mohu přizpůsobit kód tak, aby načítal pouze specifické vlastnosti metadat?

Odpověď: Ano, kód můžete upravit tak, aby získal specifické vlastnosti metadat, a to tak, že zakomentujete řádky, které nepotřebujete. Každý řádek v kódu odpovídá určité vlastnosti metadat, takže můžete vlastnosti zahrnout nebo vyloučit na základě svých požadavků.

#### Otázka: Jaké typy vlastností metadat mohu získat pomocí Aspose.PDF pro .NET?

Odpověď: Pomocí Aspose.PDF for .NET můžete získat různé vlastnosti metadat dokumentu PDF, včetně autora, názvu, předmětu, klíčových slov, data vytvoření a data modifikace.