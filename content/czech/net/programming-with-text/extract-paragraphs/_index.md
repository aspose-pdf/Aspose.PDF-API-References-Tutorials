---
title: Extrahujte odstavce do souboru PDF
linktitle: Extrahujte odstavce do souboru PDF
second_title: Aspose.PDF pro .NET API Reference
description: Naučte se extrahovat odstavce do souboru PDF pomocí Aspose.PDF pro .NET.
type: docs
weight: 160
url: /cs/net/programming-with-text/extract-paragraphs/
---
Tento tutoriál vás provede procesem extrahování odstavců v souboru PDF pomocí Aspose.PDF pro .NET. Poskytnutý zdrojový kód C# ukazuje potřebné kroky.

## Požadavky
Než začnete, ujistěte se, že máte následující:

- Visual Studio nebo jakýkoli jiný kompilátor C# nainstalovaný na vašem počítači.
- Aspose.PDF pro knihovnu .NET. Můžete si jej stáhnout z oficiálního webu Aspose nebo jej nainstalovat pomocí správce balíčků, jako je NuGet.

## Krok 1: Nastavte projekt
1. Vytvořte nový projekt C# ve vámi preferovaném vývojovém prostředí.
2. Přidejte odkaz na knihovnu Aspose.PDF for .NET.

## Krok 2: Importujte požadované jmenné prostory
Do souboru kódu, kam chcete extrahovat odstavce, přidejte následující pomocí direktiv v horní části souboru:

```csharp
using Aspose.Pdf;
using System;
using System.Text;
```

## Krok 3: Nastavte adresář dokumentů
 V kódu vyhledejte řádek, který říká`string dataDir = "YOUR DOCUMENT DIRECTORY";` a nahradit`"YOUR DOCUMENT DIRECTORY"` s cestou k adresáři, kde jsou uloženy vaše dokumenty.

## Krok 4: Otevřete dokument PDF
 Otevřete existující dokument PDF pomocí`Document`konstruktoru a předání cesty ke vstupnímu souboru PDF.

```csharp
Document doc = new Document(dataDir + "input.pdf");
```

## Krok 5: Extrahujte odstavce
 Vytvořte instanci`ParagraphAbsorber` třídy a používat její`Visit` metoda extrahování odstavců z dokumentu.

```csharp
ParagraphAbsorber absorb = new ParagraphAbsorber();
absorb.Visit(doc);
```

## Krok 6: Iterujte odstavce
Procházením extrahovaných odstavců získáte přístup k obsahu textu. Použijte vnořené smyčky k procházení sekcemi a řádky v každém odstavci.

```csharp
foreach(PageMarkup markup in absorber.PageMarkups)
{
     int i = 1;
     foreach(MarkupSection section in markup.Sections)
     {
         int j = 1;
         foreach(MarkupParagraph paragraph in section.Paragraphs)
         {
             StringBuilder paragraphText = new StringBuilder();
             foreach(List<TextFragment> line in paragraph.Lines)
             {
                 foreach(TextFragment fragment in line)
                 {
                     paragraphText.Append(fragment.Text);
                 }
                 paragraphText. Append("\r\n");
             }
             paragraphText. Append("\r\n");
             Console.WriteLine("Paragraph {0} of section {1} on page {2}:", j, i, markup.Number);
             Console.WriteLine(paragraphText.ToString());
             j++;
         }
         i++;
     }
}
```

### Ukázkový zdrojový kód pro extrahování odstavců pomocí Aspose.PDF pro .NET 
```csharp
// Cesta k adresáři dokumentů.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Otevřete existující soubor PDF
Document doc = new Document(dataDir + "input.pdf");
// Okamžitý odstavecAbsorber
ParagraphAbsorber absorber = new ParagraphAbsorber();
absorber.Visit(doc);
foreach (PageMarkup markup in absorber.PageMarkups)
{
	int i = 1;
	foreach (MarkupSection section in markup.Sections)
	{
		int j = 1;
		foreach (MarkupParagraph paragraph in section.Paragraphs)
		{
			StringBuilder paragraphText = new StringBuilder();
			foreach (List<TextFragment> line in paragraph.Lines)
			{
				foreach (TextFragment fragment in line)
				{
					paragraphText.Append(fragment.Text);
				}
				paragraphText.Append("\r\n");
			}
			paragraphText.Append("\r\n");
			Console.WriteLine("Paragraph {0} of section {1} on page {2}:", j, i, markup.Number);
			Console.WriteLine(paragraphText.ToString());
			j++;
		}
		i++;
	}
}
```

## Závěr
Úspěšně jste extrahovali odstavce z dokumentu PDF pomocí Aspose.PDF pro .NET. Extrahované odstavce byly zobrazeny v okně konzoly.

### FAQ

#### Otázka: Jaký je účel tohoto tutoriálu?

Odpověď: Tento tutoriál vás provede procesem extrahování odstavců ze souboru PDF pomocí Aspose.PDF pro .NET. Doprovodný zdrojový kód C# poskytuje praktické kroky k dosažení tohoto úkolu.

#### Otázka: Jaké jmenné prostory mám importovat?

Odpověď: Do souboru kódu, ze kterého chcete extrahovat odstavce, zahrňte na začátek souboru následující pomocí direktiv:

```csharp
using Aspose.Pdf;
using System;
using System.Text;
```

#### Otázka: Jak určím adresář dokumentů?

 A: Najděte linku`string dataDir = "YOUR DOCUMENT DIRECTORY";` v kódu a nahradit`"YOUR DOCUMENT DIRECTORY"` se skutečnou cestou k vašemu adresáři dokumentů.

#### Otázka: Jak otevřu existující dokument PDF?

 Odpověď: V kroku 4 otevřete existující dokument PDF pomocí`Document` konstruktoru a poskytnutí cesty ke vstupnímu souboru PDF.

#### Otázka: Jak extrahuji odstavce z dokumentu?

 Odpověď: Krok 5 zahrnuje vytvoření instance souboru`ParagraphAbsorber` třídy a její používání`Visit` metoda pro extrakci odstavců z dokumentu PDF.

#### Otázka: Jak mohu iterovat extrahované odstavce?

Odpověď: Krok 6 vás provede procházením extrahovaných odstavců. Vnořené smyčky se používají k procházení sekcí a řádků v každém odstavci a nakonec k přístupu a zobrazení obsahu textu.

#### Otázka: Jaký je hlavní přínos tohoto tutoriálu?

Odpověď: Podle tohoto návodu jste se naučili, jak extrahovat odstavce z dokumentu PDF pomocí Aspose.PDF pro .NET. Extrahované odstavce byly zobrazeny v okně konzoly, což vám poskytuje cenný náhled do struktury obsahu dokumentu.