---
title: Vykreslit tabulku v dokumentu PDF
linktitle: Vykreslit tabulku v dokumentu PDF
second_title: Aspose.PDF pro .NET API Reference
description: Vytvářejte snadno profesionální soubory PDF vykreslováním tabulek pomocí Aspose.PDF pro .NET. Postupujte podle našeho podrobného průvodce generováním hlavních dokumentů.
type: docs
weight: 170
url: /cs/net/programming-with-tables/render-table/
---
## Zavedení

Vytváření profesionálně vypadajících PDF pomocí programu se může zdát jako skličující úkol, ale s Aspose.PDF pro .NET se to stane hračkou. Ať už generujete zprávy, faktury nebo jakýkoli jiný typ dokumentu, který vyžaduje tabulková data, Aspose.PDF nabízí nástroje, které potřebujete. V tomto tutoriálu prozkoumáme, jak vykreslit tabulky v dokumentu PDF krok za krokem. Nakonec budete dobře rozumět tomu, jak snadno manipulovat s tabulkami, spravovat vlastnosti stránky a ukládat soubory PDF.

## Předpoklady

Než se ponoříme do kódu, zde je to, co potřebujete:

-  Visual Studio: Ujistěte se, že máte na svém počítači nainstalované Visual Studio. Můžete si jej stáhnout[zde](https://visualstudio.microsoft.com/downloads/).
-  Aspose.PDF pro .NET: Knihovnu Aspose.PDF si můžete snadno stáhnout z[Aspose release page](https://releases.aspose.com/pdf/net/).
- Základní znalost C#: Pochopení základů C# vám pomůže lépe se orientovat.
- .NET Framework: V ideálním případě se ujistěte, že pracujete v kompatibilním prostředí .NET.

Jakmile máte tyto předpoklady nastaveny, můžete začít vytvářet dokumenty PDF!

## Importujte balíčky

Na začátku vašeho souboru C# budete muset importovat potřebné jmenné prostory Aspose.PDF. To vám umožní využívat funkce knihovny v našem projektu.

```csharp
using System;
using System.IO;
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

 Ujistěte se, že jste do svého projektu přidali potřebné odkazy na knihovnu Aspose.PDF. Pokud používáte NuGet, můžete jej snadno přidat vyhledáním`Aspose.PDF`.

Nyní, když máme vše nastaveno, rozdělíme proces na zvládnutelné kroky pro vykreslení tabulky v dokumentu PDF. Nebojte se; Provedu vás každým krokem s jasnými pokyny!

## Krok 1: Nastavte informace o dokumentu a stránce

Nejprve musíme vytvořit nový dokument a nakonfigurovat nastavení jeho stránky. Postup:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
PageInfo pageInfo = doc.PageInfo;
Aspose.Pdf.MarginInfo marginInfo = pageInfo.Margin;

marginInfo.Left = 37;
marginInfo.Right = 37;
marginInfo.Top = 37;
marginInfo.Bottom = 37;

pageInfo.IsLandscape = true;
```

Vysvětlení: 
- Začneme tím, že definujeme, kam bude náš dokument uložen (`dataDir`). 
-  Poté vytvoříme novou instanci`Document` třída. 
- Okraje stránky nakonfigurujeme tak, aby se kolem našeho stolu vytvořil prostor pro dýchání.
- Nakonec dokumentu nastavíme orientaci na šířku, což pomáhá při zobrazování širších tabulek.

## Krok 2: Vytvořte první tabulku

Dále vytvoříme naši první tabulku a naplníme ji ukázkovými daty:

```csharp
Aspose.Pdf.Table table = new Aspose.Pdf.Table();
table.ColumnWidths = "50 100"; // Definujte šířky sloupců
```

 Vysvětlení: Zde vytvoříme instanci`Table` třídy a nastavte šířky sloupců. První sloupec bude mít šířku 50 jednotek a druhý sloupec bude mít šířku 100 jednotek.

## Krok 3: Vyplňte tabulku řádky

Nyní přidáme řádky do naší tabulky ve smyčce:

```csharp
Page curPage = doc.Pages.Add(); // Přidání nové stránky
for (int i = 1; i <= 120; i++)
{
    Aspose.Pdf.Row row = table.Rows.Add();
    row.FixedRowHeight = 15; // Nastavte pevnou výšku řádků
    
    Aspose.Pdf.Cell cell1 = row.Cells.Add();
    cell1.Paragraphs.Add(new TextFragment("Content 1"));
    
    Aspose.Pdf.Cell cell2 = row.Cells.Add();
    cell2.Paragraphs.Add(new TextFragment("HHHHH"));
}
```

Vysvětlení: 
- Zde vytvoříme novou stránku pro přidání naší tabulky.
-  Používáme a`for` smyčka přidat 120 řádků do naší tabulky. Každý řádek má pevnou výšku 15 jednotek.
- Uvnitř každého řádku přidáme dvě buňky a naplníme je textem.

## Krok 4: Přidejte na stránku první tabulku

Jakmile tabulku naplníme, přidáme ji na aktuální stránku:

```csharp
Aspose.Pdf.Paragraphs paragraphs = curPage.Paragraphs;
paragraphs.Add(table);
```

Vysvětlení: Tento krok jednoduše přidá tabulku, kterou jsme vytvořili, do odstavců aktuální stránky, čímž se tabulka zviditelní v dokumentu PDF.

## Krok 5: Vytvořte druhou tabulku

Nyní vytvoříme druhou tabulku s jiným obsahem a přidáme ji na novou stránku:

```csharp
Aspose.Pdf.Table table1 = new Aspose.Pdf.Table();
table1.ColumnWidths = "100 100";
for (int i = 1; i <= 10; i++)
{
    Aspose.Pdf.Row row = table1.Rows.Add();
    Aspose.Pdf.Cell cell1 = row.Cells.Add();
    cell1.Paragraphs.Add(new TextFragment("LAAAAAAA"));
    
    Aspose.Pdf.Cell cell2 = row.Cells.Add();
    cell2.Paragraphs.Add(new TextFragment("LAAGGGGGG"));
}
table1.IsInNewPage = true; // Nastavení druhé tabulky, aby se objevila na nové stránce
paragraphs.Add(table1);
```

Vysvětlení: 
- Tento fragment kódu vytvoří novou tabulku se dvěma sloupci, oba o šířce 100 jednotek.
-  A`for` smyčka přidá 10 řádků s ukázkovým obsahem.
-  Nastavením`table1.IsInNewPage` Aby to bylo pravda, zajišťujeme, aby se tato tabulka objevila na nové stránce, aby byly věci uspořádané a přehledné.

## Krok 6: Uložte dokument

Nyní, když jsou naše tabulky připraveny, uložme náš dokument:

```csharp
dataDir = dataDir + "IsNewPageProperty_Test_out.pdf";
doc.Save(dataDir);
```

 Vysvětlení: Zadáme název souboru a uložíme dokument do definovaného adresáře. Po spuštění tohoto kódu se zobrazí soubor PDF s názvem`IsNewPageProperty_Test_out.pdf` bude vytvořen ve vámi určeném místě.

## Krok 7: Potvrzující zpráva

Nakonec, aby uživatel věděl, že vše fungovalo hladce, můžeme přidat přátelskou konzolovou zprávu:

```csharp
Console.WriteLine("\nTable rendered successfully on a page.\nFile saved at " + dataDir);
```

Vysvětlení: Toto je jednoduchý způsob, jak potvrdit, že operace byla úspěšná a kde uživatel může najít svůj nový soubor PDF.

## Závěr

A tady to máte! Úspěšně jste vykreslili tabulky v dokumentu PDF pomocí Aspose.PDF for .NET. Pomocí několika řádků kódu můžete zpracovávat a prezentovat velké množství dat v organizovaném formátu, díky čemuž budou vaše dokumenty informativní a vizuálně přitažlivé. Ať už pracujete na inventárních seznamech, finančních výkazech nebo vzdělávacích dokumentech, tabulky jsou vynikajícím způsobem, jak sdělit komplexní informace na první pohled.

## FAQ

### Mohu upravit vzhled tabulek v Aspose.PDF?  
Absolutně! Můžete upravit barvy, okraje, styly písma a další vlastnosti, abyste zlepšili vzhled svých tabulek.

### Je Aspose.PDF zdarma k použití?  
 Aspose.PDF nabízí bezplatnou zkušební verzi, ale pro komerční použití je nutný nákup. Můžete zkontrolovat cenu[zde](https://purchase.aspose.com/buy).

### Jak mohu získat podporu pro problémy Aspose.PDF?  
 Pomoc můžete vyhledat na fóru podpory Aspose[zde](https://forum.aspose.com/c/pdf/10).

### Existují nějaká omezení pro bezplatnou zkušební verzi?  
 Ano, zkušební verze může mít určitá omezení, jako je vodoznak na generovaných dokumentech. Pro plnou funkčnost zvažte získání dočasné licence[zde](https://purchase.aspose.com/temporary-license/).

### Kde najdu více informací o funkcích Aspose.PDF?  
 Můžete prozkoumat kompletní dostupnou dokumentaci[zde](https://reference.aspose.com/pdf/net/).