---
title: Odebrat hypertextové odkazy po převodu z HTML
linktitle: Odebrat hypertextové odkazy po převodu z HTML
second_title: Aspose.PDF pro .NET API Reference
description: Průvodce krok za krokem k odstranění hypertextových odkazů po převodu HTML do PDF pomocí Aspose.PDF pro .NET.
type: docs
weight: 250
url: /cs/net/document-conversion/remove-hyperlinks-after-converting-from-html/
---
V tomto tutoriálu vás provedeme procesem odstranění hypertextových odkazů ze souboru PDF vygenerovaného ze souboru HTML pomocí Aspose.PDF for .NET. Hypertextové odkazy jsou klikací odkazy, které mohou přesměrovat na jiné stránky nebo webové stránky. Pomocí následujících kroků budete moci odstranit hypertextové odkazy z výsledného souboru PDF.

## Předpoklady
Než začnete, ujistěte se, že splňujete následující předpoklady:

- Základní znalost programovacího jazyka C#.
- Knihovna Aspose.PDF pro .NET nainstalovaná ve vašem systému.
- Vývojové prostředí, jako je Visual Studio.

## Krok 1: Načtení souboru HTML a odstranění hypertextových odkazů
tomto kroku načteme soubor HTML a odstraníme hypertextové odkazy z výsledného dokumentu PDF. Použijte následující kód:

```csharp
// Cesta k adresáři dokumentů.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Načtěte soubor HTML pomocí možností načítání HTML
Document doc = new Document(dataDir + "SampleHtmlFile.html", new HtmlLoadOptions());

// Procházejte anotace na první stránce dokumentu
foreach(Annotation a in doc.Pages[1].Annotations)
{
     // Zkontrolujte, zda je anotace odkazem
     if (a.AnnotationType == AnnotationType.Link)
     {
         LinkAnnotation the = (LinkAnnotation)a;
        
         // Zkontrolujte, zda je akce typu GoTOURIAction
         if (the.Action is GoToURIAction)
         {
             GoToURIAction gta = (GoToURIAction)the.Action;
             gta.URI = "";
            
             // Použijte absorbér textových fragmentů k nalezení odpovídajících textových fragmentů
             TextFragmentAbsorber tfa = new TextFragmentAbsorber();
             tfa.TextSearchOptions = new TextSearchOptions(a.Rect);
             doc.Pages[a.PageIndex].Accept(tfa);
            
             // Procházejte odpovídající fragmenty textu a odstraňte atributy z hypertextových odkazů
             foreach(TextFragment tf in tfa.TextFragments)
             {
                 tf.TextState.Underline = false;
                 tf.TextState.ForegroundColor = Color.Black;
             }
         }
        
         // Odeberte anotaci ze stránky
         doc.Pages[a.PageIndex].Annotations.Delete(a);
     }
}
```

 Nezapomeňte vyměnit`"YOUR DOCUMENTS DIRECTORY"` se skutečným adresářem, kde se nachází váš soubor HTML.

## Krok 2: Uložení výsledného souboru PDF
Nakonec výsledný soubor PDF uložíme bez hypertextových odkazů. Použijte následující kód:

```csharp
// Uložte výsledný soubor PDF
doc.Save(dataDir + "RemoveHyperlinksFromText_out.pdf");
```

 Výše uvedený kód uloží výsledný soubor PDF s názvem souboru`"RemoveHyperlinksFromText_out.pdf"`.

### Příklad zdrojového kódu pro Remove Hyperlinks After Converting From Html pomocí Aspose.PDF for .NET

```csharp
// Cesta k adresáři dokumentů.
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "SampleHtmlFile.html", new HtmlLoadOptions());
doc.Save(new MemoryStream());
foreach (Annotation a in doc.Pages[1].Annotations)
{
	if (a.AnnotationType == AnnotationType.Link)
	{
		LinkAnnotation la = (LinkAnnotation)a;
		if (la.Action is GoToURIAction)
		{
			GoToURIAction gta = (GoToURIAction)la.Action;
			gta.URI = "";
			TextFragmentAbsorber tfa = new TextFragmentAbsorber();
			tfa.TextSearchOptions = new TextSearchOptions(a.Rect);
			doc.Pages[a.PageIndex].Accept(tfa);
			foreach (TextFragment tf in tfa.TextFragments)
			{
				tf.TextState.Underline = false;
				tf.TextState.ForegroundColor = Color.Black;
			}
		}
		doc.Pages[a.PageIndex].Annotations.Delete(a);
	}
}
doc.Save(dataDir + "RemoveHyperlinksFromText_out.pdf");
```

## Závěr
V tomto tutoriálu jsme se zabývali podrobným procesem odstraňování hypertextových odkazů ze souboru PDF generovaného ze souboru HTML pomocí Aspose.PDF for .NET. Podle výše popsaných pokynů budete moci úspěšně odstranit hypertextové odkazy z výsledného souboru PDF.

### FAQ

#### Otázka: Co je Aspose.PDF pro .NET?

A: Aspose.PDF for .NET je výkonná knihovna, která umožňuje vývojářům pracovat s dokumenty PDF v aplikacích C#. Nabízí širokou škálu funkcí, včetně schopnosti převádět HTML soubory do PDF a manipulovat s obsahem PDF.

#### Otázka: Proč bych měl chtít odstranit hypertextové odkazy ze souboru PDF?

Odpověď: Existují různé důvody pro odstranění hypertextových odkazů ze souboru PDF. Můžete například chtít odstranit externí odkazy pro účely tisku nebo archivace nebo zajistit, aby obsah PDF nebylo možné procházet pomocí hypertextových odkazů.

#### Otázka: Jak mohu načíst soubor HTML a odstranit hypertextové odkazy pomocí Aspose.PDF pro .NET?

 A: Chcete-li načíst soubor HTML a odstranit hypertextové odkazy, můžete použít Aspose.PDF pro .NET`HtmlLoadOptions` třída. Procházejte anotacemi stránek PDF, abyste našli anotace odkazů a upravili jejich atributy.

#### Otázka: Mohu upravit výstupní název souboru pro výsledné PDF?

Odpověď: Ano, můžete upravit výstupní název souboru pro výsledný soubor PDF úpravou kódu, který uloží dokument PDF. Jednoduše změňte požadovaný název souboru v`doc.Save()` metoda.

#### Otázka: Je možné selektivně odstranit hypertextové odkazy na základě určitých kritérií?

Odpověď: Ano, můžete selektivně odstranit hypertextové odkazy na základě specifických kritérií. Můžete se například rozhodnout odstranit pouze externí odkazy nebo odkazy směřující na konkrétní adresy URL.