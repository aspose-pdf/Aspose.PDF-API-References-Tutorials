---
title: Přidat Odebrat Javascript do dokumentu PDF
linktitle: Přidat Remove Javascript To Doc
second_title: Aspose.PDF pro .NET API Reference
description: Naučte se, jak přidat a odebrat JavaScript do dokumentu PDF pomocí Aspose.PDF for .NET. Podrobný průvodce s výukovým programem kódu pro skriptování na úrovni dokumentu.
type: docs
weight: 30
url: /cs/net/programming-with-document/addremovejavascripttodoc/
---
Pro přidání a odebrání JavaScriptu do PDF dokumentu použijeme knihovnu Aspose.PDF for .NET. Tato výkonná knihovna nám umožňuje manipulovat se soubory PDF v aplikacích .NET. Chcete-li přidat a odebrat JavaScript pomocí Aspose.PDF for .NET, postupujte podle níže uvedených podrobných pokynů.

## Krok 1: Vytvořte nový dokument PDF

 Začněte vytvořením nové instance souboru`Document` třídy poskytované Aspose.PDF pro .NET. To bude sloužit jako dokument PDF, kam přidáme JavaScript.

```csharp
// Cesta k adresáři dokumentů.
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
doc.Pages.Add();
```

## Krok 2: Přidejte JavaScript na úrovni dokumentu

 Chcete-li přidat JavaScript na úrovni dokumentu, použijte`JavaScript` vlastnictvím`Document` třída. Přiřaďte funkce JavaScriptu klíčům ve slovníku JavaScript.

```csharp
doc.JavaScript["func1"] = "function func1() { hello(); }";
doc.JavaScript["func2"] = "function func2() { hello(); }";
doc.Save(dataDir + "AddJavascript.pdf");
```

 V tomto tutoriálu jsme přidali dvě funkce JavaScript,`func1` a`func2`, do dokumentu PDF.

## Krok 3: Odeberte JavaScript na úrovni dokumentu

 Chcete-li odstranit JavaScript na úrovni dokumentu, načtěte dokument PDF a otevřete soubor`JavaScript`slovník. Iterujte přes klávesy a odstraňte požadovanou funkci JavaScriptu.

```csharp
Document doc1 = new Document(dataDir + "AddJavascript.pdf");
IList keys = (System.Collections.IList)doc1.JavaScript.Keys;

foreach (string key in keys)
{
    Console.WriteLine(key + " ==> " + doc1.JavaScript[key]);
}

doc1.JavaScript.Remove("func1");
Console.WriteLine("Key 'func1' removed");
```

 V tomto tutoriálu odstraníme`func1` Funkce JavaScript z dokumentu PDF.

## Krok 4: Uložte a ověřte změny

Uložte upravený dokument PDF a ověřte změny.

```csharp
Console.WriteLine("\nJavascript added/removed successfully to a document.");
```

Tento kód uloží upravený dokument PDF a zobrazí zprávu o úspěchu.

### Příklad zdrojového kódu pro Add Remove Javascript from PDF dokumentů pomocí Aspose.PDF for .NET

```csharp
// Cesta k adresáři dokumentů.
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
doc.Pages.Add();
doc.JavaScript["func1"] = "function func1() { hello(); }";
doc.JavaScript["func2"] = "function func2() { hello(); }";
doc.Save(dataDir + "AddJavascript.pdf");

// Odebrat JavaScript na úrovni dokumentu
Document doc1 = new Document(dataDir + "AddJavascript.pdf");
IList keys = (System.Collections.IList)doc1.JavaScript.Keys;
Console.WriteLine("=============================== ");
foreach (string key in keys)
{
	Console.WriteLine(key + " ==> " + doc1.JavaScript[key]);
}

doc1.JavaScript.Remove("func1");
Console.WriteLine("Key 'func1' removed ");
Console.WriteLine("=============================== ");

Console.WriteLine("\nJavascript added/removed successfully to a document.");
```

## Závěr

V tomto článku jsme poskytli podrobného průvodce přidáváním a odstraňováním JavaScriptu z dokumentů PDF pomocí Aspose.PDF for .NET. Podle pokynů a pomocí poskytnutých výukových programů s kódem můžete snadno začlenit JavaScript do svých dokumentů PDF a v případě potřeby jej odstranit. JavaScript umožňuje dynamickou funkcionalitu a interaktivitu ve vašich souborech PDF, čímž zlepšuje uživatelskou zkušenost.


### Časté dotazy pro přidání a odstranění javascriptu do dokumentu PDF

#### Otázka: Co je Aspose.PDF pro .NET?

A: Aspose.PDF for .NET je výkonná knihovna, která umožňuje vývojářům efektivně manipulovat se soubory PDF v aplikacích .NET. Poskytuje rozsáhlé funkce pro programovou práci s dokumenty PDF.

#### Otázka: Jak mohu přidat JavaScript do dokumentu PDF pomocí Aspose.PDF pro .NET?

 Odpověď: JavaScript můžete přidat na úrovni dokumentu pomocí`JavaScript` vlastnictvím`Document` třída. Jednoduše přiřaďte funkce JavaScriptu klávesám ve slovníku JavaScript.

#### Otázka: Mohu odstranit JavaScript z dokumentu PDF pomocí Aspose.PDF for .NET?

 Odpověď: Ano, JavaScript můžete z dokumentu PDF odstranit přístupem k`JavaScript` slovník a odstranění požadované funkce JavaScriptu.

#### Otázka: Je Aspose.PDF pro .NET vhodný pro profesionální projekty?

Odpověď: Aspose.PDF pro .NET je zcela jistě široce používán v profesionálních projektech pro manipulaci a generování PDF. Nabízí vysoký výkon a spolehlivou funkčnost.

#### Otázka: Jaké výhody přináší přidání JavaScriptu do dokumentu PDF?

Odpověď: Přidání JavaScriptu do dokumentu PDF vám umožní vytvářet interaktivní a dynamické soubory PDF. Můžete implementovat ověřování formulářů, provádět výpočty a přidávat různé interaktivní funkce pro zlepšení uživatelské zkušenosti.