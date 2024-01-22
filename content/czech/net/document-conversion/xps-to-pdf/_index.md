---
title: XPS do PDF
linktitle: XPS do PDF
second_title: Aspose.PDF pro .NET API Reference
description: Krok za krokem průvodce převodem XPS souboru do PDF pomocí Aspose.PDF pro .NET.
type: docs
weight: 350
url: /cs/net/document-conversion/xps-to-pdf/
---
V tomto tutoriálu vás krok za krokem provedeme, jak převést soubor XPS do PDF pomocí knihovny Aspose.PDF pro .NET. Podrobně popíšeme poskytnutý zdrojový kód C# a ukážeme vám, jak jej implementovat ve vašich vlastních projektech. Na konci tohoto tutoriálu budete schopni snadno převádět soubory XPS na dokumenty PDF.

## Krok 1: Nastavte adresář dokumentů
```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```
 Nahradit`"YOUR DOCUMENTS DIRECTORY"` s cestou, kam jste uložili soubory.

## Krok 2: Vytvořte instanci objektu LoadOptions pomocí možností načtení XPS
```csharp
Aspose.Pdf.LoadOptions options = new XpsLoadOptions();
```
Vytvořte instanci objektu LoadOptions pomocí možností načtení XPS.

## Krok 3: Vytvořte objekt dokumentu
```csharp
Aspose.Pdf.Document document = new Aspose.Pdf.Document(dataDir + "XPSToPDF.xps", options);
```
Vytvořte objekt Document s uvedením vstupního souboru XPS a možností načtení.

## Krok 4: Uložte výsledný dokument PDF
```csharp
document.Save(dataDir + "XPSToPDF_out.pdf");
```
Uložte výsledný dokument PDF do určeného adresáře.

### Příklad zdrojového kódu pro XPS do PDF pomocí Aspose.PDF pro .NET

```csharp
try
{
	
	// Cesta k adresáři dokumentů.
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	//Vytvořte instanci objektu LoadOption pomocí možnosti načtení XPS
	Aspose.Pdf.LoadOptions options = new XpsLoadOptions();

	// Vytvořit objekt dokumentu
	Aspose.Pdf.Document document = new Aspose.Pdf.Document(dataDir + "XPSToPDF.xps", options);

	// Uložte výsledný dokument PDF
	document.Save(dataDir + "XPSToPDF_out.pdf");
	
}
catch(Exception ex)
   
{
	Console.WriteLine(ex.Message);
}
```

## Závěr
V tomto tutoriálu jsme se naučili, jak převést soubor XPS do PDF pomocí knihovny Aspose.PDF pro .NET. Podle uvedených kroků můžete tento převod snadno provést ve svých vlastních aplikacích. Získejte přesné a profesionální výsledky při převodu souborů XPS do PDF.

### FAQ

#### Otázka: Co je XPS a proč bych jej chtěl převést do PDF?

Odpověď: XPS (XML Paper Specification) je formát dokumentu s pevným rozvržením vyvinutý společností Microsoft. Převod XPS do PDF vám umožní učinit dokument dostupnější a široce kompatibilní, protože PDF je univerzálně podporovaný formát na různých platformách a zařízeních.

#### Otázka: Podporuje knihovna Aspose.PDF jiné formáty souborů kromě XPS?

Odpověď: Ano, Aspose.PDF pro .NET podporuje různé další formáty souborů pro převod, jako jsou HTML, EPUB, SVG, XML a další. Umožňuje také programově vytvářet a manipulovat s dokumenty PDF.

#### Otázka: Mohu přizpůsobit proces převodu PDF, jako je nastavení velikosti stránky, okrajů nebo jiných možností?

Odpověď: Ano, proces převodu PDF můžete upravit pomocí Aspose.PDF pro .NET. Knihovna poskytuje širokou škálu možností pro ovládání velikosti stránky, okrajů, komprese obrázků, vkládání písem a dalších nastavení souvisejících s PDF, aby vyhovovala vašim specifickým požadavkům.

#### Otázka: Je k dispozici zkušební verze Aspose.PDF pro .NET pro testování?

Odpověď: Ano, zkušební verzi Aspose.PDF pro .NET si můžete stáhnout a vyzkoušet z oficiálních stránek Aspose. Zkušební verze vám umožňuje prozkoumat funkce knihovny před nákupem.

#### Otázka: Mohu převést více souborů XPS do PDF v dávkovém procesu?

Odpověď: Ano, můžete převést více souborů XPS do PDF v dávkovém procesu implementací smyčky nebo iterací seznamu souborů XPS a převedením každého souboru do PDF pomocí poskytnutého kódu.