---
title: Text A Obrázek Jako Odstavec V Souboru PDF
linktitle: Text A Obrázek Jako Odstavec V Souboru PDF
second_title: Aspose.PDF pro .NET API Reference
description: Naučte se, jak přidat text a obrázek jako vložené odstavce do souboru PDF pomocí Aspose.PDF pro .NET.
type: docs
weight: 530
url: /cs/net/programming-with-text/text-and-image-as-paragraph/
---
Tento tutoriál vysvětluje, jak přidat text a obrázek jako vložené odstavce do souboru PDF pomocí Aspose.PDF pro .NET. Poskytnutý zdrojový kód C# demonstruje proces krok za krokem.

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
using Aspose.Pdf.Drawing;
```

## Krok 3: Nastavte cestu k adresáři dokumentů

 Nastavte cestu k adresáři dokumentů pomocí`dataDir` proměnná:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Nahradit`"YOUR DOCUMENT DIRECTORY"` se skutečnou cestou k vašemu adresáři dokumentů.

## Krok 4: Vytvořte nový dokument a stránku

 Vytvoř nový`Document` objekt a přidejte stránku do kolekce stránek:

```csharp
Document doc = new Document();
Page page = doc.Pages.Add();
```

## Krok 5: Vytvořte TextFragment a přidejte jej jako odstavec

 Vytvořit`TextFragment` objekt a přidejte jej do kolekce odstavců na stránce:

```csharp
TextFragment text = new TextFragment("Hello World.. ");
page.Paragraphs.Add(text);
```

## Krok 6: Přidejte obrázek jako vložený odstavec

 Vytvořit`Aspose.Pdf.Image` objekt a nastavte jej jako vložený odstavec tak, aby se objevil hned za předchozím odstavcem:

```csharp
Aspose.Pdf.Image image = new Aspose.Pdf.Image();
image.IsInLineParagraph = true;
image.File = dataDir + "aspose-logo.jpg";
image.FixHeight = 30; // Volitelné: Nastavte výšku obrázku
image.FixWidth = 100; // Volitelné: Nastavte šířku obrázku
page.Paragraphs.Add(image);
```

 Nahradit`"aspose-logo.jpg"` se skutečným názvem souboru obrázku a podle potřeby upravte volitelnou výšku a šířku obrázku.

## Krok 7: Přidejte další TextFragment jako vložený odstavec

 Znovu inicializujte`TextFragment` objekt s různým obsahem a přidejte jej jako vložený odstavec:

```csharp
text = new TextFragment(" Hello Again..");
text.IsInLineParagraph = true;
page.Paragraphs.Add(text);
```

## Krok 8: Uložte dokument PDF

Uložte upravený dokument PDF:

```csharp
dataDir = dataDir + "TextAndImageAsParagraph_out.pdf";
doc.Save(dataDir);
```

 Nezapomeňte vyměnit`"TextAndImageAsParagraph_out.pdf"` s požadovaným názvem výstupního souboru.

### Ukázkový zdrojový kód pro text a obrázek jako odstavec pomocí Aspose.PDF pro .NET 
```csharp
// Cesta k adresáři dokumentů.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Instancia dokumentu instance
Document doc = new Document();
// Přidejte stránku do kolekce stránek instance dokumentu
Page page = doc.Pages.Add();
// Vytvořte TextFragmnet
TextFragment text = new TextFragment("Hello World.. ");
// Přidejte fragment textu do kolekce odstavců objektu Page
page.Paragraphs.Add(text);
// Vytvořte instanci obrázku
Aspose.Pdf.Image image = new Aspose.Pdf.Image();
// Nastavte obrázek jako vložený odstavec tak, aby se objevil hned za ním
// Předchozí objekt odstavce (TextFragment)
image.IsInLineParagraph = true;
// Zadejte cestu k souboru obrázku
image.File = dataDir + "aspose-logo.jpg";
// Nastavit výšku obrázku (volitelné)
image.FixHeight = 30;
// Nastavit šířku obrázku (volitelné)
image.FixWidth = 100;
// Přidejte obrázek do kolekce odstavců objektu stránky
page.Paragraphs.Add(image);
// Znovu inicializujte objekt TextFragment s jiným obsahem
text = new TextFragment(" Hello Again..");
// Nastavte TextFragment jako vložený odstavec
text.IsInLineParagraph = true;
// Přidejte nově vytvořený TextFragment do kolekce odstavců stránky
page.Paragraphs.Add(text);
dataDir = dataDir + "TextAndImageAsParagraph_out.pdf";
doc.Save(dataDir);
Console.WriteLine("\nText and image added successfully as an inline paragraphs.\nFile saved at " + dataDir);
```

## Závěr

Gratulujeme! Úspěšně jste se naučili, jak přidat text a obrázek jako vložené odstavce do dokumentu PDF pomocí Aspose.PDF for .NET. Tento výukový program poskytuje podrobného průvodce, od nastavení projektu až po uložení upraveného dokumentu. Nyní můžete tento kód začlenit do svých vlastních projektů C# a přizpůsobit tak rozvržení textu a obrázků v souborech PDF.

### FAQ

#### Otázka: Jaký je účel výukového programu "Text a obrázek jako odstavec v souboru PDF"?

Odpověď: Výukový program „Text a obrázek jako odstavec v souboru PDF“ si klade za cíl vést uživatele, jak přidat text i obrázky jako vložené odstavce do dokumentu PDF pomocí Aspose.PDF for .NET. Výukový program poskytuje podrobné pokyny a ukázky kódu C#, které demonstrují proces.

#### Otázka: Jak tento kurz pomáhá při přidávání textu a obrázků jako vkládaných odstavců?

Odpověď: Tento tutoriál pomáhá uživatelům pochopit, jak používat Aspose.PDF pro .NET k začlenění textu i obrázků jako vkládaných odstavců do dokumentu PDF. Podle poskytnutých kroků a příkladů kódu mohou uživatelé vytvářet soubory PDF s vlastním rozvržením, které kombinuje text a obrázky.

#### Otázka: Jaké předpoklady jsou vyžadovány pro sledování tohoto kurzu?

Odpověď: Než začnete s výukovým programem, měli byste mít základní znalosti programovacího jazyka C#. Navíc musíte mít nainstalovanou knihovnu Aspose.PDF for .NET. Můžete jej získat z webu Aspose nebo jej nainstalovat do svého projektu pomocí NuGet.

#### Otázka: Jak nastavím svůj projekt, aby následoval tento tutoriál?

Odpověď: Pro začátek vytvořte nový projekt C# ve vašem preferovaném integrovaném vývojovém prostředí (IDE) a přidejte odkaz na knihovnu Aspose.PDF for .NET. To vám umožní využívat funkce knihovny pro práci s dokumenty PDF, fragmenty textu a obrázky.

#### Otázka: Mohu použít tento tutoriál k přidání více odstavců textu a obrázků do PDF?

Odpověď: Ano, dodané ukázky kódu můžete použít k přidání více instancí odstavců textu i obrázků do stejného dokumentu PDF. Tento výukový program ukazuje, jak vytvářet vložené odstavce, což usnadňuje vkládání různých kombinací textu a obrázků.

#### Otázka: Jak určím obsah a vzhled odstavců textu a obrázků?

 Odpověď: Tutoriál ukazuje, jak vytvořit`TextFragment`objekty reprezentující odstavce textu a`Aspose.Pdf.Image` objekty reprezentující obrazy. Pomocí poskytnutých ukázek kódu můžete přizpůsobit obsah, rozměry a vzhled textu i obrázků.

#### Otázka: Mohu upravit rozložení vložených odstavců?

 Odpověď: Ano, můžete upravit rozvržení vkládaných odstavců řízením jejich umístění, rozměrů a pořadí na stránce. Tutoriál ukazuje, jak nastavit vložené atributy, jako např`IsInLineParagraph`, k ovládání rozvržení odstavců textu a obrázků.

#### Otázka: Jak uložím upravený dokument PDF?

 A: Chcete-li uložit upravený dokument PDF, můžete použít`Save` metoda`Document` objekt. Výukový program poskytuje ukázky kódu, které demonstrují, jak uložit výsledný dokument PDF.