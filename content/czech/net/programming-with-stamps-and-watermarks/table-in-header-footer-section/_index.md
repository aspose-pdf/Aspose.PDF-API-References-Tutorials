---
title: Tabulka V části Záhlaví Zápatí
linktitle: Tabulka V části Záhlaví Zápatí
second_title: Aspose.PDF pro .NET API Reference
description: Naučte se, jak přidat tabulku do sekce záhlaví/zápatí dokumentu PDF pomocí Aspose.PDF pro .NET.
type: docs
weight: 170
url: /cs/net/programming-with-stamps-and-watermarks/table-in-header-footer-section/
---
## Zavedení

Přistihli jste se někdy, že zíráte na obyčejný dokument PDF a přejete si, aby měl ten zvláštní šmrnc? Tak to máš štěstí! Aspose.PDF for .NET vám umožňuje vytvářet a manipulovat se soubory PDF jako profesionál. Dnes se ponoříme do praktické funkce, která vám umožní přidat tabulku do záhlaví vašeho dokumentu PDF. Nejen, že se naučíte, jak na to, ale provedu vás krok za krokem, takže celý proces bude hladký jako máslo. 🎉

## Předpoklady

Než přejdeme k samotné části kódování, ujistěte se, že máte vše, co potřebujete, abyste mohli začít. Zde je to, co budete potřebovat:

1.  Visual Studio: Ujistěte se, že máte v počítači nainstalované Visual Studio. Pokud ne, můžete si jej stáhnout z[stránky společnosti Microsoft](https://visualstudio.microsoft.com/).
2.  Knihovna Aspose.PDF: Musíte mít knihovnu Aspose.PDF pro .NET. K získání můžete použít následující odkaz[Aspose.PDF pro balíček .NET](https://releases.aspose.com/pdf/net/).
3. Základní znalost C#: Měli byste mít alespoň základní znalosti C#. Nedělejte si starosti, pokud se stále učíte; Udělám to co nejjednodušší!

## Importujte balíčky

Dobře, je čas si vyhrnout rukávy a pustit se do kódování! Nejprve však musíme nastavit naše prostředí importem potřebných balíčků. Postup je následující:

###  Otevřete svůj projekt
Otevřete projekt sady Visual Studio, kde budete pracovat na vytváření PDF. 

###  Přidejte odkaz do Aspose.PDF
1. Správce balíčků NuGet: Klikněte pravým tlačítkem na svůj projekt v Průzkumníku řešení a vyberte „Spravovat balíčky NuGet“.
2. Vyhledat Aspose.PDF: Do vyhledávacího řádku napište „Apose.PDF“ a nainstalujte balíček.

Na konci tohoto kroku byste měli mít vše nastaveno a připraveno začít kódovat!

Teď si ušpiníme ruce nějakým kódem! Chcete-li vytvořit tabulku v záhlaví vašeho PDF, postupujte takto:

## Krok 1: Nastavte cestu k adresáři vašeho dokumentu

Než začneme vytvářet naše PDF, musíme definovat, kde bude náš dokument uložen. Postup je následující:

```csharp
// Cesta k adresáři dokumentů.
string dataDir = "YOUR DOCUMENT DIRECTORY"; // Změňte to na svůj skutečný adresář
```

 Nahradit`YOUR DOCUMENT DIRECTORY` cestou, kam chcete soubor PDF uložit. To může být kdekoli ve vašem systému – jen se ujistěte, že je přístupný!

## Krok 2: Vytvořte instanci dokumentu

Dále vytvoříme nový dokument PDF.

```csharp
// Vytvořte instanci dokumentu voláním prázdného konstruktoru
Aspose.Pdf.Document pdfDocument = new Aspose.Pdf.Document();
```

To, co zde děláme, je vytvoření prázdného dokumentu PDF, kam přidáme všechny naše vychytávky.

## Krok 3: Vytvořte novou stránku

Pojďme do našeho dokumentu přidat novou stránku. 

```csharp
// Vytvořte stránku v dokumentu pdf
Aspose.Pdf.Page page = pdfDocument.Pages.Add();
```

Představte si tuto stránku jako prázdné plátno, kde namalujeme naše mistrovské dílo!

## Krok 4: Vytvořte sekci záhlaví

Nyní vytvoříme záhlaví pro naše PDF.

```csharp
// Vytvořte sekci záhlaví souboru PDF
Aspose.Pdf.HeaderFooter header = new Aspose.Pdf.HeaderFooter();
```

Tato hlavička bude držet náš stůl. 

## Krok 5: Přiřaďte záhlaví stránce

Dále se chceme ujistit, že se na stránce zobrazí naše záhlaví.

```csharp
// Nastavte liché záhlaví pro soubor PDF
page.Header = header;
```

## Krok 6: Nastavte horní okraj

Abychom se ujistili, že naše záhlaví má nahoře nějaký prostor pro dýchání, upravíme okraj.

```csharp
//Nastavte horní okraj pro sekci záhlaví
header.Margin.Top = 20;
```

Nastavení okraje je jako dát vašemu textu nějaký osobní prostor – nikdo nemá rád stísněnost!

## Krok 7: Vytvořte tabulku

Nyní je čas vytvořit tabulku, která půjde do naší hlavičky.

```csharp
// Vytvořte instanci objektu tabulky
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();
```

## Krok 8: Přidejte tabulku do záhlaví

Naši nově vytvořenou tabulku přidáme do kolekce odstavců záhlaví.

```csharp
// Přidejte tabulku do kolekce odstavců požadované sekce
header.Paragraphs.Add(tab1);
```

## Krok 9: Nastavte ohraničení buněk

Dejme naší tabulce nějakou strukturu tím, že definujeme výchozí ohraničení buňky.

```csharp
// Nastavte výchozí ohraničení buňky pomocí objektu BorderInfo
tab1.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.1F);
```

## Krok 10: Definujte šířky sloupců

Můžete určit, jak široký by měl být každý sloupec tabulky.

```csharp
// Nastavte šířku sloupců tabulky
tab1.ColumnWidths = "60 300";
```

Hodnoty představují šířku každého sloupce v bodech. Neváhejte je upravit tak, aby vyhovovaly vašim potřebám!

## Krok 11: Vytvořte řádky a přidejte buňky

Je čas hodit nějaké řádky a buňky! 

```csharp
//Vytvořte řádky v tabulce a poté buňky v řádcích
Aspose.Pdf.Row row1 = tab1.Rows.Add();
row1.Cells.Add("Table in Header Section");
row1.BackgroundColor = Color.Gray;
```

Tím se vytvoří první řádek s buňkou obsahující text a barva pozadí se nastaví na šedou.

## Krok 12: Nastavte rozsah řádků a styl textu

Chcete, aby váš řádek zahrnoval více sloupců? Zde je postup:

```csharp
// Nastavte hodnotu rozsahu řádku pro první řádek na 2
tab1.Rows[0].Cells[0].ColSpan = 2;
tab1.Rows[0].Cells[0].DefaultCellTextState.ForegroundColor = Color.Cyan;
tab1.Rows[0].Cells[0].DefaultCellTextState.Font = FontRepository.FindFont("Helvetica");
```

Tento krok nejen nastaví rozsah řádků, ale také změní barvu textu a písmo.

## Krok 13: Přidejte druhou řadu

Přidáme další řádek do naší tabulky, ano?

```csharp
// Vytvořte další řádek v tabulce
Aspose.Pdf.Row row2 = tab1.Rows.Add();

// Nastavte barvu pozadí pro řádek 2
row2.BackgroundColor = Color.White;
```

## Krok 14: Přidejte obrázek do druhého řádku

Nyní přidáme logo, aby náš stůl vypadal elegantně!

```csharp
// Přidejte buňku, která obsahuje obrázek
Aspose.Pdf.Image img = new Aspose.Pdf.Image();
img.File = dataDir + "aspose-logo.jpg"; // Ujistěte se, že jste obrázek umístili do svého adresáře
```

 Nezapomeňte vyměnit`"aspose-logo.jpg"` se skutečným názvem vašeho obrázku!

## Krok 15: Upravte šířku obrázku

Nastavte šířku obrázku, abyste zajistili, že bude v buňce vypadat přesně.

```csharp
// Nastavte šířku obrázku na 60
img.FixWidth = 60;

//Přidejte obrázek do buňky tabulky
Aspose.Pdf.Cell cell2 = row2.Cells.Add();
cell2.Paragraphs.Add(img);
```

## Krok 16: Přidejte text do druhé buňky

Je čas přidat malý text vedle našeho loga!

```csharp
row2.Cells.Add("Logo is looking fine !");
row2.Cells[1].DefaultCellTextState.Font = FontRepository.FindFont("Helvetica");
```

## Krok 17: Zarovnejte text svisle a vodorovně

Ujistěte se, že vše vypadá uklizené. Zarovnejte text!

```csharp
// Nastavte svislé zarovnání textu na střed
row2.Cells[1].VerticalAlignment = Aspose.Pdf.VerticalAlignment.Center;
row2.Cells[1].Alignment = Aspose.Pdf.HorizontalAlignment.Center;
```

## Krok 18: Uložte dokument PDF

V neposlední řadě zachraňme náš výtvor!

```csharp
// Uložte soubor Pdf
pdfDocument.Save(dataDir + "TableInHeaderFooterSection_out.pdf");
```

Et voilà! Vytvořili jste úžasné PDF s tabulkou v záhlaví!

## Závěr

A tady to máte! Úspěšně jste přidali tabulku do záhlaví vašeho dokumentu PDF pomocí Aspose.PDF pro .NET. Je úžasné, jak jen pár řádků kódu dokáže přeměnit jednoduché PDF na profesionálně vypadající dokument. Ať už připravujete zprávy, faktury nebo prezentace, přidání nádechu kreativity může znamenat velký rozdíl. 

## FAQ

### Co je Aspose.PDF pro .NET?
Aspose.PDF for .NET je výkonná knihovna, která umožňuje vývojářům programově vytvářet a manipulovat s dokumenty PDF.

### Potřebuji licenci k používání Aspose.PDF?
 I když můžete knihovnu během zkušebního období používat zdarma, pro prodloužené používání je vyžadována licence. Můžete získat a[dočasná licence](https://purchase.aspose.com/temporary-license/) pro hodnocení.

### Kde najdu dokumentaci?
Kompletní dokumentaci a příklady naleznete na[Dokumentační stránka Aspose.PDF](https://reference.aspose.com/pdf/net/).

### Jak mohu kontaktovat podporu v případě technických problémů?
 Můžete se obrátit na podporu prostřednictvím[Aspose fórum](https://forum.aspose.com/c/pdf/10).

### Mohu vytvářet tabulky v jiných částech PDF?
Absolutně! Tabulky můžete vytvářet také v zápatích a částech těla; prostě postupujte podle podobných kroků.