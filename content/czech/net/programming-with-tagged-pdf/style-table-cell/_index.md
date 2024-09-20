---
title: Buňka tabulky stylu
linktitle: Buňka tabulky stylu
second_title: Aspose.PDF pro .NET API Reference
description: V tomto podrobném kurzu se dozvíte, jak upravit styl buněk tabulky v PDF pomocí Aspose.PDF for .NET. Postupujte podle pokynů a vytvořte a naformátujte krásné tabulky PDF.
type: docs
weight: 160
url: /cs/net/programming-with-tagged-pdf/style-table-cell/
---
## Zavedení

Vytváření profesionálně vypadajících tabulek PDF může být složité, ale s Aspose.PDF pro .NET je to překvapivě jednoduché! Ať už upravujete záhlaví, zápatí nebo konkrétní buňky tabulky, tato výkonná knihovna vám poskytuje všechny nástroje, které potřebujete k vytváření krásně formátovaných dokumentů PDF. V tomto tutoriálu si projdeme, jak stylovat buňky tabulky v dokumentu PDF pomocí Aspose.PDF for .NET. Nebojte se – vše rozdělíme do snadno pochopitelných kroků.

## Předpoklady

Než se ponoříte do kódu, ujistěte se, že máte následující předpoklady:

1. Aspose.PDF pro .NET: Stáhněte si a nainstalujte nejnovější verzi Aspose.PDF z[zde](https://releases.aspose.com/pdf/net/).
2. IDE (jako Visual Studio): Nastavte vývojové prostředí .NET.
3. Základní znalost programování v C#: Vyžaduje se trochu znalosti C#.
4.  Licence Aspose.PDF: Získejte dočasnou nebo plnou licenci k odemknutí všech funkcí knihovny. Můžete získat bezplatnou zkušební verzi[zde](https://purchase.aspose.com/temporary-license/).

## Importujte balíčky

Než začnete, nezapomeňte importovat potřebné jmenné prostory. Ve svém projektu budete potřebovat následující:

```csharp
using Aspose.Pdf.LogicalStructure;
using Aspose.Pdf.Tagged;
using Aspose.Pdf.Text;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

Nyní, když je vše nastaveno, pojďme se vrhnout na průvodce krok za krokem!

Vytvoříme tabulku v dokumentu PDF a upravíme styl jejích buněk. Každý krok podrobně vysvětlí proces.

## Krok 1: Vytvořte nový dokument PDF

 Prvním krokem je vytvoření nového dokumentu PDF. V Aspose.PDF můžete inicializovat nový`Document` objekt, který představuje váš soubor PDF.

```csharp
// Cesta k adresáři dokumentů.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Vytvořte nový dokument PDF
Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Example table cell style");
taggedContent.SetLanguage("en-US");
```

Zde inicializujeme dokument PDF a nastavíme jeho název a jazyk. To dává vašemu dokumentu správnou strukturu, která je nezbytná pro shodu s PDF/UA.

## Krok 2: Nastavte strukturu tabulky

Tabulky v PDF jsou definovány v prvcích struktury. Pojďme vytvořit tabulku a definovat řádky a sloupce tabulky.

```csharp
// Získejte prvek kořenové struktury
StructureElement rootElement = taggedContent.RootElement;

// Vytvořte prvek struktury tabulky
TableElement tableElement = taggedContent.CreateTableElement();
rootElement.AppendChild(tableElement);
TableTHeadElement tableTHeadElement = tableElement.CreateTHead();
TableTBodyElement tableTBodyElement = tableElement.CreateTBody();
TableTFootElement tableTFootElement = tableElement.CreateTFoot();
```

Nyní jsme definovali hlavu tabulky (`TableTHeadElement`), tělo (`TableTBodyElement`), a noha (`TableTFootElement`) oddíly. Můžete si je představit jako kostru vašeho stolu.

## Krok 3: Upravte styl buněk záhlaví

Styling buněk záhlaví je zvýrazní. Zde použijeme barvy pozadí, ohraničení a zarovnání textu.

```csharp
int colCount = 4;
TableTRElement headTrElement = tableTHeadElement.CreateTR();
headTrElement.AlternativeText = "Head Row";

for (int colIndex = 0; colIndex < colCount; colIndex++)
{
    TableTHElement thElement = headTrElement.CreateTH();
    thElement.SetText($"Head {colIndex}");
    thElement.BackgroundColor = Color.GreenYellow;
    thElement.Border = new BorderInfo(BorderSide.All, 4.0F, Color.Gray);
    thElement.IsNoBorder = true;
    thElement.Margin = new MarginInfo(16.0, 2.0, 8.0, 2.0);
    thElement.Alignment = HorizontalAlignment.Right;
}
```

V tomto kroku procházíme každou buňku záhlaví a dáváme jí zeleno-žluté pozadí, šedý okraj a text zarovnaný doprava. Tyto vlastnosti můžete upravit tak, aby odpovídaly vašemu požadovanému designu.

## Krok 4: Vyplňte a upravte styl těla tabulky

Tělo tabulky obsahuje aktuální data. Zde je návod, jak můžete upravit styl každé buňky pomocí specifických okrajů, ohraničení a nastavení textu.

```csharp
int rowCount = 4;

for (int rowIndex = 0; rowIndex < rowCount; rowIndex++)
{
    TableTRElement trElement = tableTBodyElement.CreateTR();
    trElement.AlternativeText = $"Row {rowIndex}";

    for (int colIndex = 0; colIndex < colCount; colIndex++)
    {
        TableTDElement tdElement = trElement.CreateTD();
        tdElement.SetText($"Cell [{rowIndex}, {colIndex}]");
        tdElement.BackgroundColor = Color.Yellow;
        tdElement.Border = new BorderInfo(BorderSide.All, 4.0F, Color.Gray);
        tdElement.Margin = new MarginInfo(8.0, 2.0, 8.0, 2.0);
        tdElement.Alignment = HorizontalAlignment.Center;
        
        TextState cellTextState = new TextState();
        cellTextState.ForegroundColor = Color.DarkBlue;
        cellTextState.FontSize = 7.5F;
        cellTextState.FontStyle = FontStyles.Bold;
        cellTextState.Font = FontRepository.FindFont("Arial");
        tdElement.DefaultCellTextState = cellTextState;
    }
}
```

 V tomto kroku vyplníme tělo tabulky čtyřmi řádky a nastylujeme každou buňku žlutým pozadím a vycentrovaným, tučným modrým textem. Používáme také`MarginInfo`třídy k definování výplně kolem textu.

## Krok 5: Upravte styl zápatí

Aby tabulka získala úplnou strukturu, přidáme a nastylujeme buňky zápatí, stejně jako jsme to udělali se záhlavím.

```csharp
TableTRElement footTrElement = tableTFootElement.CreateTR();
footTrElement.AlternativeText = "Foot Row";

for (int colIndex = 0; colIndex < colCount; colIndex++)
{
    TableTDElement tdElement = footTrElement.CreateTD();
    tdElement.SetText($"Foot {colIndex}");
}
```

Zápatí je stylizováno podobně jako záhlaví, takže čtenáři mohou snadno sledovat strukturu tabulky.

## Krok 6: Uložte a ověřte dokument PDF

Nakonec dokument PDF uložíme a zkontrolujeme, zda je kompatibilní s PDF/UA.

```csharp
// Uložte tagovaný dokument PDF
document.Save(dataDir + "StyleTableCell.pdf");

// Kontrola shody s PDF/UA
document = new Document(dataDir + "StyleTableCell.pdf");
bool isPdfUaCompliance = document.Validate(dataDir + "StyleTableCell.xml", PdfFormat.PDF_UA_1);
Console.WriteLine($"PDF/UA compliance: {isPdfUaCompliance}");
```

 Uložíme PDF a použijeme`Validate` způsob, jak zajistit, že splňuje standardy přístupnosti (shoda PDF/UA).

## Závěr

Stylování tabulek v PDF pomocí Aspose.PDF pro .NET je výkonné a flexibilní. Pomocí několika řádků kódu můžete vytvořit vlastní návrhy tabulek, díky kterým budou vaše dokumenty PDF vynikat. Aspose.PDF usnadňuje vytváření leštěných souborů PDF, od přizpůsobení ohraničení buněk a pozadí až po zajištění shody s přístupností.

## FAQ

### Mohu na jednotlivé buňky tabulky použít různé styly?  
Ano, můžete upravit jednotlivé buňky přizpůsobením`TableTDElement` vlastnosti.

### Jak mohu sloučit buňky tabulky?  
 Můžete použít`ColSpan` a`RowSpan` vlastnosti pro sloučení buněk v tabulce.

### Je možné vytvořit tabulku kompatibilní s PDF/UA?  
 Ano, jak je ukázáno v této příručce, shodu s PDF/UA můžete zajistit ověřením dokumentu pomocí`Validate` metoda.

### Mohu v buňkách tabulky použít různá písma?  
 Absolutně! Můžete zadat různá písma pomocí`TextState` objekt pro každou buňku.

### Jak si stáhnu Aspose.PDF pro .NET?  
 Můžete si jej stáhnout z[stránka vydání](https://releases.aspose.com/pdf/net/).