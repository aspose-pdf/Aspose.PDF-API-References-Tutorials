---
title: Řádek tabulky stylu
linktitle: Řádek tabulky stylu
second_title: Aspose.PDF pro .NET API Reference
description: Naučte se, jak stylovat řádky tabulky v PDF pomocí Aspose.PDF for .NET, s podrobným průvodcem, jak snadno vylepšit formátování dokumentu.
type: docs
weight: 180
url: /cs/net/programming-with-tagged-pdf/style-table-row/
---
## Zavedení

Pokud jde o vytváření dobře strukturovaných a krásně formátovaných dokumentů PDF, Aspose.PDF for .NET je řešením, na které se můžete obrátit. Ať už automatizujete sestavy, faktury nebo vytváříte dynamické tabulky, formátování tabulek s různými styly je klíčem k vyleštěnému dokumentu. V tomto tutoriálu se ponoříme hluboko do stylování řádku tabulky pomocí Aspose.PDF pro .NET. A nebojte se, provedu vás krok za krokem, stejně jako dobrý rozhovor u kávy!

## Předpoklady

Než se pustíme do toho natvrdlého, ujistíme se, že máte všechny kachny v řadě. Budete potřebovat:

1. Aspose.PDF pro knihovnu .NET  
    Pokud ho ještě nemáte, můžete si ho stáhnout[zde](https://releases.aspose.com/pdf/net/) . Můžete také získat a[zkušební verze zdarma](https://releases.aspose.com/) začít.
2. Vývojové prostředí  
   Nastavte Visual Studio nebo libovolné C# IDE dle vašeho výběru. Budete také potřebovat nainstalovaný .NET, ale předpokládám, že to už znáte.
3. Základní znalost C# a .NET  
   Díky dobré znalosti C# bude tento tutoriál hračkou. Ale nebojte se, každý krok vám podrobně vysvětlím!

## Importujte balíčky

Než začneme pracovat s Aspose.PDF, musíme naimportovat potřebné jmenné prostory. Ve svém projektu C# se ujistěte, že zahrnujete následující:

```csharp
using Aspose.Pdf.LogicalStructure;
using Aspose.Pdf.Tagged;
using Aspose.Pdf.Text;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

Ty jsou nezbytné pro vytvoření a stylování tabulky a samozřejmě pro práci s označeným obsahem pro zajištění souladu.

Nyní si rozeberme úkol krok za krokem, abyste mohli stylovat řádky tabulky jako profesionál!

## Krok 1: Vytvořte nový dokument PDF

Nejdříve: pojďme vytvořit zbrusu nový dokument PDF. Tento dokument bude obsahovat všechny stylizované řádky tabulky.

```csharp
// Cesta k adresáři dokumentů.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Vytvořte dokument
Document document = new Document();
```

 Zde jednoduše inicializujeme nový`Document` objekt, který bude reprezentovat náš soubor PDF. Ujistěte se, že jste nastavili cestu k adresáři, kam budete ukládat výstupní soubory.

## Krok 2: Práce s označeným obsahem

Abychom zajistili přístupnost vašeho PDF, budeme pracovat s tagovaným obsahem. To pomáhá při vytváření strukturovaných prvků, jako jsou tabulky, a zajišťuje, že jsou v souladu se standardy přístupnosti, jako je PDF/UA.

```csharp
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Example table row style");
taggedContent.SetLanguage("en-US");
```

Zde nastavujeme název a jazyk pro tagovaný obsah PDF. Je to jako dát svému PDF jméno a říct mu, jakým jazykem má mluvit!

## Krok 3: Definujte strukturu tabulky

Dále definujeme strukturu tabulky, kterou se chystáme vytvořit. Každá tabulka potřebuje záhlaví, tělo a zápatí – podobně jako dobře uspořádaný blogový příspěvek!

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

To, co zde děláme, je vytvoření tabulky se záhlavím (`THead`), tělo (`TBody`) a zápatí (`TFoot`). Tyto prvky budou držet naše řady.

## Krok 4: Přidejte řádek záhlaví tabulky

Tabulky bez záhlaví jsou jako knihy bez názvu. Nejprve vytvoříme řádek záhlaví, abychom poskytli kontext pro data.

```csharp
TableTRElement headTrElement = tableTHeadElement.CreateTR();
headTrElement.AlternativeText = "Head Row";
for (int colIndex = 0; colIndex < 3; colIndex++)
{
    TableTHElement thElement = headTrElement.CreateTH();
    thElement.SetText(String.Format("Head {0}", colIndex));
}
```

Zde projdeme a přidáme tři buňky záhlaví (`TableTHElement`), přičemž každý z nich má popisný text. Jednoduché, že?

## Krok 5: Přidejte stylizované řady těla

Nyní přichází ta zábavná část – styling řad! Vytvořme sedm řádků s vlastními styly. Nastavíme barvy pozadí, okraje, odsazení a zarovnání textu.

```csharp
for (int rowIndex = 0; rowIndex < 7; rowIndex++)
{
    TableTRElement trElement = tableTBodyElement.CreateTR();
    trElement.AlternativeText = String.Format("Row {0}", rowIndex);
    trElement.BackgroundColor = Color.LightGoldenrodYellow;
    trElement.Border = new BorderInfo(BorderSide.All, 0.75F, Color.DarkGray);
    trElement.DefaultCellBorder = new BorderInfo(BorderSide.All, 0.50F, Color.Blue);
    trElement.MinRowHeight = 100.0;
    trElement.FixedRowHeight = 120.0;
    trElement.IsInNewPage = (rowIndex % 3 == 1);
    trElement.IsRowBroken = true;

    for (int colIndex = 0; colIndex < 3; colIndex++)
    {
        TableTDElement tdElement = trElement.CreateTD();
        tdElement.SetText(String.Format("Cell [{0}, {1}]", rowIndex, colIndex));
    }
}
```

- Barva pozadí: Použili jsme světle zlatou žlutou pro profesionální, ale teplý dotek.
- Ohraničení: Každý řádek má tmavě šedé vnější ohraničení a modré ohraničení buněk pro ostrý vzhled.
- Výška a odsazení: Výšky řádků jsou nastaveny a pro čistý vzhled je přidáno odsazení.
- Konce stránek: Aby byla tabulka čitelnější, každý druhý řádek začíná na nové stránce.

## Krok 6: Přidejte řádek zápatí

Stejně jako záhlaví, zápatí ukotvuje tabulku. Pojďme si jeden vytvořit.

```csharp
TableTRElement footTrElement = tableTFootElement.CreateTR();
footTrElement.AlternativeText = "Foot Row";
for (int colIndex = 0; colIndex < 3; colIndex++)
{
    TableTDElement tdElement = footTrElement.CreateTD();
    tdElement.SetText(String.Format("Foot {0}", colIndex));
}
```

Jednoduše projdeme třemi buňkami zápatí a přidáme trochu textu. Alternativní text pro zápatí je „Foot Row“, aby byl přístupný.

## Krok 7: Uložte dokument PDF

Nyní, když je stůl připraven, je čas uložit své mistrovské dílo!

```csharp
document.Save(dataDir + "StyleTableRow.pdf");
```

Stejně tak se váš PDF uloží se všemi krásnými řádky tabulky, které jsme právě nastylovali.

## Krok 8: Ověřte soulad s PDF/UA

Abychom zajistili, že naše PDF vyhovuje standardům přístupnosti, ověříme, zda je v souladu s PDF/UA.

```csharp
document = new Document(dataDir + "StyleTableRow.pdf");
bool isPdfUaCompliance = document.Validate(dataDir + "StyleTableRow.xml", PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA compliance: {0}", isPdfUaCompliance));
```

Tím je zajištěno, že vaše PDF splňuje standard PDF/UA, takže je přístupné všem. Přístupnost je název hry!

## Závěr

A tady to máte! Pomocí několika řádků kódu jste vytvořili plně stylizovanou tabulku v PDF pomocí Aspose.PDF for .NET. Od záhlaví po zápatí jsme upravili styl každého řádku, přidali prvky usnadnění a dokonce ověřili shodu dokumentu. Ať už pracujete na podnikových zprávách, prezentacích nebo se jen bavíte s PDF, tato příručka vám pomůže. Nyní pokračujte a začněte upravovat své stoly jako profesionál!

## FAQ

### Mohu změnit také styl písma tabulky?  
 Ano! Styl písma můžete upravit pomocí`TextState` objekt pro každou buňku, což umožňuje úplné přizpůsobení.

### Jak do tabulky přidám další sloupce?  
 Stačí upravit`colCount`proměnnou a přidejte další buňky do smyček pro záhlaví, tělo a zápatí.

### Co se stane, když nenastavím výšku řádku?  
Pokud nenastavíte výšku řádku, tabulka se automaticky upraví podle obsahu.

### Mohu to použít pro dynamický počet řádků?  
Absolutně! Můžete načítat data z databáze nebo jakéhokoli jiného zdroje a dynamicky upravovat počty řádků a sloupců.

### Je Aspose.PDF for .NET zdarma k použití?  
 Aspose.PDF for .NET je licencovaný produkt, ale můžete jej vyzkoušet pomocí a[zkušební verze zdarma](https://releases.aspose.com/) nebo získat a[dočasná licence](https://purchase.aspose.com/temporary-license/).