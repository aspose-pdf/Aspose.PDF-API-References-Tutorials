---
title: Text do PDF
linktitle: Text do PDF
second_title: Aspose.PDF pro .NET API Reference
description: Jednoduchý a efektivní převod textových souborů do PDF pomocí Aspose.PDF pro .NET.
type: docs
weight: 300
url: /cs/net/document-conversion/text-to-pdf/
---
Tento tutoriál vás provede kroky převodu textového souboru na soubor PDF pomocí Aspose.PDF for .NET. Aspose.PDF nabízí jednoduché a efektivní řešení pro převod prostého textu do PDF při zachování formátování a prezentace textu. Chcete-li provést tento převod, postupujte podle následujících kroků.

## Předpoklady
Než začnete, ujistěte se, že splňujete následující předpoklady:

- Základní znalost programovacího jazyka C#.
- Knihovna Aspose.PDF pro .NET nainstalovaná ve vašem systému.
- Vývojové prostředí, jako je Visual Studio.

## Krok 1: Čtení textového souboru
 Prvním krokem je načtení obsahu textového souboru pomocí`StreamReader` třída. Použijte následující kód:

```csharp
// Cesta k adresáři dokumentů.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Přečtěte si textový soubor
TextReader tr = new StreamReader(dataDir + "log.txt");
```

 Nezapomeňte vyměnit`"YOUR DOCUMENTS DIRECTORY"`se skutečným adresářem, kde se nachází váš textový soubor.

## Krok 2: Vytvoření dokumentu PDF
 Druhým krokem je vytvoření a`Document` objekt, který bude reprezentovat konečný dokument PDF. Použijte následující kód:

```csharp
// Vytvořte objekt dokumentu
Document doc = new Document();
```

## Krok 3: Přidejte text do dokumentu
Třetím krokem je přidání přečteného textu na stránku dokumentu PDF. Použijte následující kód:

```csharp
//Přidejte do dokumentu novou stránku
Page page = doc.Pages.Add();

// Vytvořte objekt TextFragment a předejte přečtený text jako argument
TextFragment text = new TextFragment(tr.ReadToEnd());

// Přidejte odstavec textu na stránku
page.Paragraphs.Add(text);
```

## Krok 4: Uložení souboru PDF
Nakonec uložte výsledný soubor PDF zadáním požadované cesty a názvu souboru. Použijte následující kód:

```csharp
// Uložte výsledný soubor PDF
doc.Save(dataDir + "TexttoPDF_out.pdf");
```

Nezapomeňte zadat požadovanou cestu a název souboru pro výsledný soubor PDF.

### Příklad zdrojového kódu pro Text to PDF pomocí Aspose.PDF pro .NET

```csharp
try
{
	
	// Cesta k adresáři dokumentů.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// Přečtěte si zdrojový textový soubor
	TextReader tr = new StreamReader(dataDir + "log.txt");

	// Vytvořte instanci objektu Document voláním jeho prázdného konstruktoru
	Document doc = new Document();

	// Přidejte novou stránku do kolekce Stránky dokumentu
	Page page = doc.Pages.Add();

	// Vytvořte instanci TextFragmet a předejte text z objektu čtečky jeho konstruktoru jako argument
	TextFragment text = new TextFragment(tr.ReadToEnd());
	//Text.TextState.Font = FontRepository.FindFont("Arial Unicode MS");

	// Přidejte nový textový odstavec do kolekce odstavců a předejte objekt TextFragment
	page.Paragraphs.Add(text);

	// Uložte výsledný soubor PDF
	doc.Save(dataDir + "TexttoPDF_out.pdf"); 
	
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## Závěr
V tomto tutoriálu jsme se naučili, jak převést textový soubor na soubor PDF pomocí Aspose.PDF pro .NET. Podle výše uvedených kroků můžete tento převod snadno provést. Použijte tuto metodu k převodu textových souborů do PDF a vychutnejte si flexibilitu a kvalitu Aspose.PDF.

### FAQ

#### Otázka: Co je Aspose.PDF pro .NET?

A: Aspose.PDF for .NET je výkonná knihovna, která umožňuje vývojářům pracovat s dokumenty PDF v aplikacích C#. Nabízí různé funkce, včetně převodu prostého textu do PDF.

#### Otázka: Proč bych měl chtít převést textový soubor do PDF?

Odpověď: Převod textových souborů do formátu PDF umožňuje lepší správu, sdílení a distribuci dokumentů. Soubory PDF nabízejí konzistentní formátování napříč různými zařízeními a operačními systémy.

#### Otázka: Jak mohu načíst textový soubor a převést jej do PDF pomocí Aspose.PDF pro .NET?

A: Chcete-li načíst textový soubor, můžete použít`StreamReader` třídy pro čtení obsahu souboru. Poté vytvořte a`Document` objekt reprezentující dokument PDF. Přidejte novou stránku a`TextFragment` obsahující text z textového souboru. Nakonec výsledné PDF uložte pomocí`Save` metoda`Document` objekt.

#### Otázka: Mohu upravit vzhled textu v PDF?

Odpověď: Ano, Aspose.PDF for .NET poskytuje různé možnosti přizpůsobení vzhledu textu ve výsledném PDF, jako je styl písma, velikost, barva a zarovnání.

#### Otázka: Je ve výsledném PDF zachováno formátování textu?

Odpověď: Ano, Aspose.PDF for .NET zachovává formátování textu a rozvržení během převodu textu do PDF, čímž zajišťuje přesnou reprezentaci původního obsahu.