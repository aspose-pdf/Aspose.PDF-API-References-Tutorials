---
title: Přidat Java Script do souboru PDF
linktitle: Přidat soubor PDF Java Script
second_title: Aspose.PDF pro .NET API Reference
description: Naučte se, jak přidat JavaScript do souboru PDF pomocí Aspose.PDF pro .NET. Podrobný průvodce s výukovým programem kódu pro skriptování na úrovni dokumentu a stránky.
type: docs
weight: 10
url: /cs/net/programming-with-document/addjavascripttopage/
---
Chcete-li přidat JavaScript do souboru PDF, použijeme Aspose.PDF pro .NET. Tato knihovna poskytuje jednoduchý a efektivní způsob práce se soubory PDF v aplikacích .NET. Následující kroky vás provedou procesem přidání JavaScriptu do souboru PDF pomocí Aspose.PDF for .NET.

## Krok 1: Načtěte soubor PDF

 Prvním krokem je načtení souboru PDF, do kterého chcete přidat JavaScript. Můžete to udělat pomocí`Document` třídy poskytované Aspose.PDF pro .NET. The`Document` class poskytuje metody pro načítání, ukládání a manipulaci se soubory PDF.

```csharp
// Cesta k adresáři dokumentů.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Načtěte existující soubory PDF
Document doc = new Document(dataDir + "input.pdf");
```

## Krok 2: Přidejte JavaScript na úrovni dokumentu

Chcete-li přidat JavaScript na úrovni dokumentu, použijeme`JavascriptAction` třídy poskytované Aspose.PDF pro .NET. Tato třída vám umožňuje zadat příkaz JavaScript, který chcete přidat do souboru PDF.

```csharp
// Přidání JavaScriptu na úrovni dokumentu
// Okamžitě aktivujte JavascriptAction s požadovaným příkazem JavaScript
JavascriptAction javaScript = new JavascriptAction("this.print({bUI:true,bSilent:false,bShrinkToFit:true});");

// Přiřaďte objekt JavascriptAction požadované akci dokumentu
doc.OpenAction = javaScript;
```

V tomto tutoriálu přidáváme příkaz JavaScript, který při otevření dokumentu vytiskne soubor PDF se zadanými možnostmi.

## Krok 3: Přidejte JavaScript na úrovni stránky

 Chcete-li přidat JavaScript na úrovni stránky, použijeme`JavascriptAction` třída a`Actions` vlastnost poskytovaná Aspose.PDF pro .NET. Tato vlastnost umožňuje zadat příkazy JavaScriptu, které se provedou při otevření nebo zavření stránky.

```csharp
// Přidání JavaScriptu na úrovni stránky
doc.Pages[2].Actions.OnOpen = new JavascriptAction("app.alert('page 1 opened')");
doc.Pages[2].Actions.OnClose = new JavascriptAction("app.alert('page 1 closed')");
```

V tomto tutoriálu přidáváme příkazy JavaScript, které zobrazí výstražnou zprávu při otevření nebo zavření stránky.

## Krok 4: Uložte soubor PDF

Po přidání JavaScriptu do souboru PDF musíte upravený soubor uložit. Můžete to udělat pomocí`Save` metoda poskytovaná společností`Document` třída.

```csharp
dataDir = dataDir + "JavaScript-Added_out.pdf";
// Uložit dokument PDF
doc.Save(dataDir);

Console.WriteLine("\nJavascript added successfully to a page.\nFile saved at " + dataDir);
```

Tento kód uloží upravený soubor PDF do určeného adresáře.

### Příklad zdrojového kódu pro Add Java Script To Page pomocí Aspose.PDF for .NET

```csharp
            
// Cesta k adresáři dokumentů.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Načtěte existující soubory PDF
Document doc = new Document(dataDir + "input.pdf");

// Přidání JavaScriptu na úrovni dokumentu
// Okamžitá akce JavascriptAction pomocí příkazu Desried JavaScript
JavascriptAction javaScript = new JavascriptAction("this.print({bUI:true,bSilent:false,bShrinkToFit:true});");

// Přiřaďte objekt JavascriptAction požadované akci dokumentu
doc.OpenAction = javaScript;

// Přidání JavaScriptu na úrovni stránky
doc.Pages[2].Actions.OnOpen = new JavascriptAction("app.alert('page 1 opened')");
doc.Pages[2].Actions.OnClose = new JavascriptAction("app.alert('page 1 closed')");

dataDir = dataDir + "JavaScript-Added_out.pdf";
// Uložit dokument PDF
doc.Save(dataDir);

Console.WriteLine("\nJavascript added successfully to a page.\nFile saved at " + dataDir);     
```

## Závěr

V tomto článku jsme vysvětlili, jak přidat JavaScript do souboru PDF na úrovni dokumentu i na úrovni stránky pomocí Aspose.PDF for .NET. Poskytli jsme pokyny krok za krokem a zahrnuli jsme úplný zdrojový kód pro každý příklad. S těmito znalostmi můžete do svých souborů PDF přidat JavaScript a upravit jejich chování podle svých potřeb.


### Časté dotazy pro přidání java skriptu do souboru PDF

#### Otázka: Co je Aspose.PDF pro .NET?

A: Aspose.PDF for .NET je výkonná knihovna, která umožňuje vývojářům pracovat se soubory PDF v aplikacích .NET. Poskytuje širokou škálu funkcí pro vytváření, úpravy a manipulaci s dokumenty PDF.

#### Otázka: Mohu přidat JavaScript do dokumentu PDF pomocí Aspose.PDF pro .NET?

Odpověď: Ano, Aspose.PDF for .NET vám umožňuje přidat JavaScript jak na úroveň dokumentu, tak na úroveň stránky souboru PDF, což vám umožňuje vytvářet dynamické a interaktivní dokumenty PDF.

#### Otázka: Jak načtu existující soubor PDF pomocí Aspose.PDF for .NET?

 Odpověď: Stávající soubor PDF můžete načíst pomocí`Document` třída a její metody, jak je ukázáno v průvodci krok za krokem.

#### Otázka: Jaké typy akcí JavaScriptu mohu přidat do dokumentu PDF?

Odpověď: S Aspose.PDF pro .NET můžete přidat širokou škálu akcí JavaScriptu, jako je tisk, výstražné zprávy, manipulace s poli formuláře a další.

#### Otázka: Je Aspose.PDF for .NET vhodný pro komerční projekty?

Odpověď: Ano, Aspose.PDF for .NET je spolehlivá a robustní knihovna, která se běžně používá v komerčních projektech pro úlohy manipulace a generování PDF.

