---
title: Zarovnání textu pro obsah plovoucího rámečku v souboru PDF
linktitle: Zarovnání textu pro obsah plovoucího rámečku v souboru PDF
second_title: Aspose.PDF pro .NET API Reference
description: Naučte se zarovnávat text v plovoucích rámečcích v souboru PDF pomocí Aspose.PDF for .NET.
type: docs
weight: 520
url: /cs/net/programming-with-text/text-alignment-for-floating-box-contents/
---
Tento tutoriál vysvětluje, jak zarovnat text v plovoucích rámečcích v souboru PDF pomocí Aspose.PDF pro .NET. Poskytnutý zdrojový kód C# demonstruje proces krok za krokem.

## Předpoklady

Než budete pokračovat ve výukovém programu, ujistěte se, že máte následující:

- Základní znalost programovacího jazyka C#.
- Nainstalovaná knihovna Aspose.PDF pro .NET. Můžete jej získat z webu Aspose nebo jej pomocí NuGet nainstalovat do svého projektu.

## Krok 1: Nastavte projekt

Začněte vytvořením nového projektu C# ve vašem preferovaném integrovaném vývojovém prostředí (IDE) a přidejte odkaz na knihovnu Aspose.PDF for .NET.

## Krok 2: Importujte potřebné jmenné prostory

Chcete-li importovat požadované jmenné prostory, přidejte následující pomocí direktiv na začátek souboru C#:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

## Krok 3: Nastavte cestu k adresáři dokumentů

 Nastavte cestu k adresáři dokumentů pomocí`dataDir` proměnná:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Nahradit`"YOUR DOCUMENT DIRECTORY"` se skutečnou cestou k vašemu adresáři dokumentů.

## Krok 4: Vytvořte nový dokument

 Vytvořte nový`Document` objekt:

```csharp
Aspose.Pdf.Document doc = new Document();
doc.Pages.Add();
```

## Krok 5: Vytvořte plovoucí rámečky s textovými fragmenty

 Vytvořte více`FloatingBox` objekty s různým vertikálním zarovnáním a horizontálním zarovnáním:

```csharp
Aspose.Pdf.FloatingBox floatBox = new Aspose.Pdf.FloatingBox(100, 100);
floatBox.VerticalAlignment = VerticalAlignment.Bottom;
floatBox.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Right;
floatBox.Paragraphs.Add(new TextFragment("FloatingBox_bottom"));
floatBox.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, Aspose.Pdf.Color.Blue);
doc.Pages[1].Paragraphs.Add(floatBox);

Aspose.Pdf.FloatingBox floatBox1 = new Aspose.Pdf.FloatingBox(100, 100);
floatBox1.VerticalAlignment = VerticalAlignment.Center;
floatBox1.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Right;
floatBox1.Paragraphs.Add(new TextFragment("FloatingBox_center"));
floatBox1.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, Aspose.Pdf.Color.Blue);
doc.Pages[1].Paragraphs.Add(floatBox1);

Aspose.Pdf.FloatingBox floatBox2 = new Aspose.Pdf.FloatingBox(100, 100);
floatBox2.VerticalAlignment = VerticalAlignment.Top;
floatBox2.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Right;
floatBox2.Paragraphs.Add(new TextFragment("FloatingBox_top"));
floatBox2.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, Aspose.Pdf.Color.Blue);
doc.Pages[1].Paragraphs.Add(floatBox2);
```

 Upravte text a styl souboru`TextFragment` předměty dle přání.

## Krok 6: Uložte dokument PDF

Uložte upravený dokument PDF:

```csharp
doc.Save(dataDir + "FloatingBox_alignment_review_out.pdf");
```

 Nezapomeňte vyměnit`"FloatingBox_alignment_review_out.pdf"` s požadovaným názvem výstupního souboru.

### Ukázkový zdrojový kód pro zarovnání textu pro obsah plovoucího rámečku pomocí Aspose.PDF pro .NET 
```csharp
// Cesta k adresáři dokumentů.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Aspose.Pdf.Document doc = new Document();
doc.Pages.Add();
Aspose.Pdf.FloatingBox floatBox = new Aspose.Pdf.FloatingBox(100, 100);
floatBox.VerticalAlignment = VerticalAlignment.Bottom;
floatBox.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Right;
floatBox.Paragraphs.Add(new TextFragment("FloatingBox_bottom"));
floatBox.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, Aspose.Pdf.Color.Blue);
doc.Pages[1].Paragraphs.Add(floatBox);
Aspose.Pdf.FloatingBox floatBox1 = new Aspose.Pdf.FloatingBox(100, 100);
floatBox1.VerticalAlignment = VerticalAlignment.Center;
floatBox1.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Right;
floatBox1.Paragraphs.Add(new TextFragment("FloatingBox_center"));
floatBox1.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, Aspose.Pdf.Color.Blue);
doc.Pages[1].Paragraphs.Add(floatBox1);
Aspose.Pdf.FloatingBox floatBox2 = new Aspose.Pdf.FloatingBox(100, 100);
floatBox2.VerticalAlignment = VerticalAlignment.Top;
floatBox2.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Right;
floatBox2.Paragraphs.Add(new TextFragment("FloatingBox_top"));
floatBox2.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, Aspose.Pdf.Color.Blue);
doc.Pages[1].Paragraphs.Add(floatBox2);
doc.Save(dataDir + "FloatingBox_alignment_review_out.pdf");
```

## Závěr

Gratuluji! Úspěšně jste se naučili, jak zarovnat text v plovoucích rámečcích v dokumentu PDF pomocí Aspose.PDF pro .NET. Tento výukový program poskytuje podrobného průvodce, od nastavení projektu až po uložení upraveného dokumentu. Nyní můžete tento kód začlenit do svých vlastních projektů C# a přizpůsobit zarovnání textu v plovoucích rámečcích v souborech PDF.

### FAQ

#### Otázka: Jaký je účel výukového programu "Zarovnání textu pro obsah plovoucího rámečku v souboru PDF"?

Odpověď: Výukový program "Zarovnání textu pro obsah plovoucích rámečků v souboru PDF" má za cíl uživatele vést, jak zarovnat text v plovoucích rámečcích v dokumentu PDF pomocí Aspose.PDF for .NET. Výukový program poskytuje podrobné pokyny a ukázky kódu C#, které demonstrují proces.

#### Otázka: Jak tento kurz pomáhá při zarovnávání textu v plovoucích rámečcích?

Odpověď: Tento tutoriál pomáhá uživatelům pochopit, jak využít Aspose.PDF for .NET k zarovnání textu v plovoucích rámečcích v dokumentu PDF. Podle poskytnutých kroků a příkladů kódu mohou uživatelé přizpůsobit vertikální a horizontální zarovnání textu v plovoucích rámečcích.

#### Otázka: Jaké předpoklady jsou vyžadovány pro sledování tohoto kurzu?

Odpověď: Než začnete s výukovým programem, měli byste mít základní znalosti programovacího jazyka C#. Navíc musíte mít nainstalovanou knihovnu Aspose.PDF for .NET. Můžete jej získat z webu Aspose nebo jej nainstalovat do svého projektu pomocí NuGet.

#### Otázka: Jak nastavím svůj projekt, aby následoval tento tutoriál?

A: Chcete-li začít, vytvořte nový projekt C# ve vašem preferovaném integrovaném vývojovém prostředí (IDE) a přidejte odkaz na knihovnu Aspose.PDF for .NET. To vám umožní využít funkce knihovny pro práci s dokumenty PDF a zarovnání textu v plovoucích rámečcích.

#### Otázka: Mohu použít tento tutoriál k zarovnání textu v jakémkoli typu plovoucího rámečku?

Odpověď: Ano, tento tutoriál poskytuje pokyny, jak zarovnat text v plovoucích rámečcích v dokumentu PDF pomocí Aspose.PDF pro .NET. Dodané ukázky kódu můžete použít k přizpůsobení svislého a vodorovného zarovnání textu v plovoucích rámečcích.

#### Otázka: Jak určím zarovnání textu v plovoucím rámečku?

 Odpověď: Tutoriál ukazuje, jak vytvořit`FloatingBox`objekty a nastavte je`VerticalAlignment` a`HorizontalAlignment` vlastnosti pro ovládání zarovnání obsaženého textu. Tyto vlastnosti si můžete upravit podle svých požadavků.

#### Otázka: Jak mohu přizpůsobit vzhled plovoucích krabic?

 Odpověď: Vzhled plovoucích rámečků můžete upravit úpravou vlastností, jako je ohraničení, velikost a obsah textu. Výukový program poskytuje ukázky kódu, které demonstrují, jak vytvořit a upravit styl`FloatingBox` objektů.

#### Otázka: Mohu do stejného dokumentu PDF přidat více plovoucích rámečků s různým zarovnáním?

 Odpověď: Ano, tutoriál ukazuje, jak vytvořit více`FloatingBox` objekty s různým vertikálním a horizontálním zarovnáním a přidejte je do stejného dokumentu PDF. To vám umožní vidět účinky různých zarovnání v rámci stejného dokumentu.

#### Otázka: Jak uložím upravený dokument PDF?

 A: Chcete-li uložit upravený dokument PDF, můžete použít`Save` metoda`Document` objekt. Výukový program poskytuje ukázky kódu, které demonstrují, jak uložit výsledný dokument PDF.