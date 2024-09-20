---
title: Přidat opakující se sloupec do dokumentu PDF
linktitle: Přidat opakující se sloupec do dokumentu PDF
second_title: Aspose.PDF pro .NET API Reference
description: Naučte se přidávat opakující se sloupce do dokumentů PDF pomocí Aspose.PDF pro .NET. Průvodce krok za krokem s příklady a kódem. Ideální pro vývojáře.
type: docs
weight: 20
url: /cs/net/programming-with-tables/add-repeating-column/
---
## Zavedení

Pokud pracujete s dokumenty PDF a potřebujete přidat opakující se sloupce, jste na správném místě! Pomocí Aspose.PDF for .NET můžete snadno spravovat tabulky a obsah v PDF. Ať už vytváříte dynamické sestavy, faktury nebo jakýkoli jiný strukturovaný dokument, opakující se sloupce mohou změnit hru v organizaci dat. Pojďme se ponořit do podrobného průvodce, jak do dokumentu PDF přidat opakující se sloupce.

## Předpoklady

Než se pustíme do kódu, ujistěte se, že máte vše nastaveno:

- Aspose.PDF for .NET: Ve svém projektu musíte mít nainstalovanou knihovnu Aspose.PDF for .NET.
- [Stáhněte si Aspose.PDF pro .NET](https://releases.aspose.com/pdf/net/)
- [Bezplatná zkušební verze](https://releases.aspose.com/)
- Vývojové prostředí: Ujistěte se, že máte nainstalované IDE kompatibilní s .NET, jako je Visual Studio.
- Základní porozumění C#: I když vše rozebereme, základní znalost C# vám pomůže hladce pokračovat.
  
 Pokud ještě nemáte Aspose.PDF pro .NET, můžete získat a[dočasná licence](https://purchase.aspose.com/temporary-license/) začít zkoumat jeho vlastnosti.

## Importujte balíčky

Chcete-li začít, musíte importovat potřebné jmenné prostory z Aspose.PDF pro .NET. Postup je následující:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

Tyto balíčky poskytují základní třídy a metody potřebné pro práci s dokumenty PDF a manipulaci s tabulkami.

Nyní si tento proces rozdělíme do několika kroků, abychom do dokumentu PDF přidali opakující se sloupce. Sledujte nás!

## Krok 1: Nastavte cestu k adresáři vašich dokumentů

Než vytvoříme nebo s jakýmikoli soubory budeme manipulovat, musíme definovat cestu, kam se vygenerované PDF uloží. Ve svém projektu C# nastavte cestu k adresáři, kde budou umístěny vaše soubory:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
string outFile = dataDir + "AddRepeatingColumn_out.pdf";
```

 Tato cesta ukazuje do adresáře, kam se uloží výstupní PDF. Nahradit`"YOUR DOCUMENT DIRECTORY"` se skutečnou cestou na vašem počítači.

## Krok 2: Vytvořte nový dokument PDF

 Chcete-li začít, vytvořte instanci nového`Document` objekt. To bude sloužit jako kontejner pro všechny stránky a obsah v PDF.

```csharp
Document doc = new Document();
Aspose.Pdf.Page page = doc.Pages.Add();
```

 Zde jsme vytvořili nový dokument PDF a přidali do něj prázdnou stránku. The`doc.Pages.Add()` metoda vloží do dokumentu novou stránku.

## Krok 3: Vytvořte instanci vnějšího stolu

Dále vytvoříme vnější tabulku. Tato tabulka bude pokrývat celou šířku stránky a bude sloužit jako kontejner pro další tabulky, včetně té, která bude obsahovat opakující se sloupce.

```csharp
Aspose.Pdf.Table outerTable = new Aspose.Pdf.Table();
outerTable.ColumnWidths = "100%";
outerTable.HorizontalAlignment = HorizontalAlignment.Left;
```

 Nastavili jsme`ColumnWidths` vlastnost na "100%", což znamená, že tabulka se roztáhne přes celou šířku stránky.

## Krok 4: Vytvořte vnitřní tabulku

 Nyní vytvoříme vnitřní tabulku, která bude mít opakující se sloupce. Zde jsou klíčové vlastnosti`Broken` , což umožňuje, aby tabulka pokračovala přes stejnou stránku, a`ColumnAdjustment`, který automaticky upraví šířku sloupců tak, aby odpovídala obsahu.

```csharp
Aspose.Pdf.Table mytable = new Aspose.Pdf.Table();
mytable.Broken = TableBroken.VerticalInSamePage;
mytable.ColumnAdjustment = ColumnAdjustment.AutoFitToContent;
```

Tato vnitřní tabulka bude vnořena do vnější tabulky.

## Krok 5: Přidejte tabulky na stránku

Nyní, když máme připravené vnější i vnitřní tabulky, přidáme je na stránku. Tento krok zajistí, že tabulky budou zahrnuty do struktury dokumentu.

```csharp
page.Paragraphs.Add(outerTable);
var bodyRow = outerTable.Rows.Add();
var bodyCell = bodyRow.Cells.Add();
bodyCell.Paragraphs.Add(mytable);
mytable.RepeatingColumnsCount = 5;
```

 Zde jsme přidali`outerTable` na stránku a pak do vnější tabulky jsme vnořili`mytable` . Navíc jsme nastavili`RepeatingColumnsCount`až 5, určující, kolik sloupců se má při přidání dat opakovat.

## Krok 6: Přidejte řádek záhlaví

Nyní je čas přidat záhlaví do tabulky. Řádek záhlaví poskytuje kontext datům a pomáhá strukturovat sloupce. 

```csharp
Aspose.Pdf.Row row = mytable.Rows.Add();
row.Cells.Add("header 1");
row.Cells.Add("header 2");
row.Cells.Add("header 3");
row.Cells.Add("header 4");
row.Cells.Add("header 5");
row.Cells.Add("header 6");
row.Cells.Add("header 7");
row.Cells.Add("header 11");
row.Cells.Add("header 12");
row.Cells.Add("header 13");
row.Cells.Add("header 14");
row.Cells.Add("header 15");
row.Cells.Add("header 16");
row.Cells.Add("header 17");
```

Tento fragment kódu přidá první řádek (který použijeme jako záhlaví) a naplní jej buňkami obsahujícími text jako „záhlaví 1“, „záhlaví 2“ a tak dále.

## Krok 7: Přidejte datové řádky

Nakonec můžeme do tabulky přidat nějaká data. Tato smyčka dynamicky vytváří řádky a naplňuje buňky obsahem:

```csharp
for (int RowCounter = 0; RowCounter <= 5; RowCounter++)
{
    Aspose.Pdf.Row row1 = mytable.Rows.Add();
    row1.Cells.Add("col " + RowCounter.ToString() + ", 1");
    row1.Cells.Add("col " + RowCounter.ToString() + ", 2");
    row1.Cells.Add("col " + RowCounter.ToString() + ", 3");
    row1.Cells.Add("col " + RowCounter.ToString() + ", 4");
    row1.Cells.Add("col " + RowCounter.ToString() + ", 5");
    row1.Cells.Add("col " + RowCounter.ToString() + ", 6");
    row1.Cells.Add("col " + RowCounter.ToString() + ", 7");
    row1.Cells.Add("col " + RowCounter.ToString() + ", 11");
    row1.Cells.Add("col " + RowCounter.ToString() + ", 12");
    row1.Cells.Add("col " + RowCounter.ToString() + ", 13");
    row1.Cells.Add("col " + RowCounter.ToString() + ", 14");
    row1.Cells.Add("col " + RowCounter.ToString() + ", 15");
    row1.Cells.Add("col " + RowCounter.ToString() + ", 16");
    row1.Cells.Add("col " + RowCounter.ToString() + ", 17");
}
```

Cyklus se šestkrát iteruje, přidá řádky a naplní každou buňku odpovídajícími daty sloupce (např. „sloupec 1, 1“, „sloupec 2, 2“ atd.).

## Krok 8: Uložte dokument

Po přidání všech řádků a sloupců je posledním krokem uložení dokumentu do zadané cesty k souboru.

```csharp
doc.Save(outFile);
```

Váš dokument je nyní uložen s opakujícími se sloupci!

## Závěr

Tady to máš! Pomocí těchto jednoduchých kroků můžete pomocí Aspose.PDF for .NET vytvořit dokument PDF s opakujícími se sloupci. Využitím flexibility vnořených tabulek můžete dosáhnout složitých rozvržení, díky kterým budou vaše PDF vypadat profesionálně a uspořádaně. Vyzkoušejte to pro svůj další projekt a prozkoumejte plný potenciál Aspose.PDF ke zvládnutí vašich potřeb v oblasti generování PDF.

## FAQ

### Co je Aspose.PDF pro .NET?
Aspose.PDF for .NET je výkonná knihovna, která umožňuje vývojářům vytvářet, upravovat a spravovat dokumenty PDF programově.

### Mohu dynamicky upravit počet opakujících se sloupců?
 Ano, počet opakujících se sloupců můžete změnit úpravou`RepeatingColumnsCount` vlastnictví.

### Jak mohu použít licenci na Aspose.PDF pro .NET?
 Licenci ze souboru nebo streamu můžete použít následujícím způsobem[dokumentace](https://reference.aspose.com/pdf/net/).

### Je možné přidat obrázky do buněk tabulky?
Ano, Aspose.PDF for .NET podporuje přidávání různých typů obsahu, včetně obrázků, do buněk tabulky.

### Mohu si rozložení tabulky dále přizpůsobit?
Absolutně! Aspose.PDF poskytuje rozsáhlé funkce pro přizpůsobení stylů tabulek, včetně ohraničení, odsazení, zarovnání a dalších.