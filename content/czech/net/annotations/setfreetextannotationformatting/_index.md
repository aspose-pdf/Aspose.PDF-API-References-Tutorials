---
title: Nastavte volné formátování textové poznámky
linktitle: Nastavte volné formátování textové poznámky
second_title: Aspose.PDF pro .NET API Reference
description: Tento článek poskytuje podrobný návod, jak vytvořit anotaci volného textu a specifikovat její obsah pomocí Aspose.PDF pro .NET
type: docs
weight: 140
url: /cs/net/annotations/setfreetextannotationformatting/
---
Aspose.PDF for .NET je výkonné a snadno použitelné rozhraní API pro manipulaci s dokumenty PDF, které vám umožňuje pracovat se soubory PDF programově ve vašich aplikacích .NET. Jednou z funkcí poskytovaných Aspose.PDF pro .NET je možnost nastavit volné formátování textových poznámek v dokumentech PDF. V tomto článku vás provedeme krok za krokem procesem nastavení volného formátování textových poznámek pomocí Aspose.PDF pro .NET.

## Předpoklady

Než začneme, ujistěte se, že máte následující předpoklady:

- Microsoft Visual Studio 2010 nebo novější
- Aspose.PDF pro .NET
- základní znalost C#



## Krok 1: Vytvořte novou konzolovou aplikaci C#

Nejprve vytvořte novou konzolovou aplikaci C# v Microsoft Visual Studio. Chcete-li vytvořit novou konzolovou aplikaci, vyberte z hlavní nabídky „Soubor“ > „Nový“ > „Projekt“ > „Visual C#“ > „Aplikace konzoly“.

## Krok 2: Přidejte odkaz na Aspose.PDF pro .NET

Dále do projektu přidejte odkaz na Aspose.PDF for .NET. Chcete-li to provést, klepněte pravým tlačítkem myši na svůj projekt v podokně "Solution Explorer", vyberte "Přidat" > "Odkaz" a poté přejděte do umístění, kam jste uložili soubor Aspose.PDF for .NET DLL. Vyberte soubor DLL a kliknutím na tlačítko "OK" přidejte odkaz na svůj projekt.

## Krok 3: Nastavte prostředí

Po přidání odkazu na Aspose.PDF pro .NET je třeba nastavit prostředí. Chcete-li to provést, vytvořte novou řetězcovou proměnnou nazvanou „dataDir“ a nastavte ji na cestu k adresáři, kde se nachází váš dokument PDF. Nahraďte „VÁŠ ADRESÁŘ DOKUMENTŮ“ v níže uvedeném kódu skutečnou cestou vašeho adresáře dokumentů:

```csharp
// Cesta k adresáři dokumentů.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Krok 4: Otevřete dokument PDF

Jakmile nastavíte prostředí, můžete otevřít dokument PDF pomocí následujícího kódu:

```csharp
// Otevřete dokument
Document pdfDocument = new Document(dataDir + "SetFreeTextAnnotationFormatting.pdf");
```

Nahraďte „SetFreeTextAnnotationFormatting.pdf“ skutečným názvem vašeho dokumentu PDF.

## Krok 5: Nastavte výchozí vzhled

Chcete-li nastavit výchozí vzhled anotace volného textu, musíte vytvořit instanci objektu DefaultAppearance s požadovaným písmem, velikostí písma a barvou. V tomto tutoriálu nastavujeme písmo na "Arial", velikost písma na 28 a barvu na červenou.

```csharp
// Vytvořit objekt DefaultAppearance
DefaultAppearance default_appearance = new DefaultAppearance("Arial", 28, System.Drawing.Color.Red);
```

## Krok 6: Vytvořte anotaci volného textu

Nyní, když jste nastavili výchozí vzhled, můžete vytvořit anotaci volného textu pomocí následujícího kódu:

```csharp
// Vytvořte anotaci
FreeTextAnnotation freetext = new FreeTextAnnotation(pdfDocument.Pages[1], new Aspose.Pdf.Rectangle(200, 400, 400, 600), default_appearance);
```

Výše uvedený kód vytvoří novou anotaci volného textu na druhé stránce dokumentu PDF. Anotace bude umístěna na (200, 400) a bude mít šířku 400 a výšku 600.

## Krok 7: Zadejte obsah anotace

Po vytvoření anotace volného textu můžete určit obsah anotace pomocí následujícího kódu:

```csharp
// Zadejte obsah anotace
freetext.Contents = "Free Text
```

### Příklad zdrojového kódu pro Set Free Text Annotation Formatting pomocí Aspose.PDF for .NET
```csharp
// Cesta k adresáři dokumentů.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Otevřete dokument
Document pdfDocument = new Document(dataDir + "SetFreeTextAnnotationFormatting.pdf");

// Vytvořit objekt DefaultAppearance
DefaultAppearance default_appearance = new DefaultAppearance("Arial", 28, System.Drawing.Color.Red);
// Vytvořte anotaci
FreeTextAnnotation freetext = new FreeTextAnnotation(pdfDocument.Pages[1], new Aspose.Pdf.Rectangle(200, 400, 400, 600), default_appearance);
// Zadejte obsah anotace
freetext.Contents = "Free Text";
// Přidejte anotace do kolekce anotací na stránce
pdfDocument.Pages[1].Annotations.Add(freetext);
dataDir = dataDir + "SetFreeTextAnnotationFormatting_out.pdf";
// Uložte aktualizovaný dokument
pdfDocument.Save(dataDir);            
```

## Závěr

tomto tutoriálu jsme se naučili, jak nastavit formátování volné textové poznámky v dokumentu PDF pomocí Aspose.PDF pro .NET. Knihovna poskytuje přímý a efektivní způsob programové práce s dokumenty PDF a umožňuje vývojářům vytvářet a přizpůsobovat různé typy anotací, včetně anotací s volným textem. Podle podrobného průvodce a pomocí dodaného zdrojového kódu C# můžete snadno nastavit prostředí, otevřít dokument PDF a vytvořit anotaci volného textu s vlastním formátováním. Aspose.PDF for .NET je robustní a spolehlivé API, které zjednodušuje úlohy manipulace s dokumenty PDF, což z něj činí cenný nástroj pro vývojáře .NET pracující se soubory PDF.

### FAQ

#### Otázka: Co je to volná textová anotace v dokumentu PDF?

Odpověď: Anotace s volným textem v dokumentu PDF je typ anotace, která vám umožňuje přidat text do dokumentu, aniž by byla vázána na určité místo nebo strukturu. Běžně se používá k poskytování komentářů, poznámek nebo jiných doplňujících informací v dokumentu.

#### Otázka: Mohu upravit vzhled volné textové anotace pomocí Aspose.PDF pro .NET?

Odpověď: Ano, můžete přizpůsobit různé vlastnosti volné textové anotace, jako je písmo, velikost písma, barva, poloha a další.

#### Otázka: Jak určím obsah anotace volného textu?

 A: Chcete-li určit obsah anotace volného textu, můžete nastavit`Contents` vlastnictvím`FreeTextAnnotation` objekt k požadovanému textu.

#### Otázka: Mohu do dokumentu PDF pomocí Aspose.PDF pro .NET přidat více volných textových anotací?

 Odpověď: Ano, v dokumentu PDF můžete vytvořit více anotací s volným textem vytvořením více instancí souboru`FreeTextAnnotation`objekt a přidat je na různé stránky nebo umístění v dokumentu.