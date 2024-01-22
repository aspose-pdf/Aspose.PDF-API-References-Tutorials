---
title: Extrahujte zvýrazněný text do souboru PDF
linktitle: Extrahujte zvýrazněný text do souboru PDF
second_title: Aspose.PDF pro .NET API Reference
description: Naučte se extrahovat zvýrazněný text do souboru PDF pomocí Aspose.PDF for .NET pomocí tohoto podrobného průvodce.
type: docs
weight: 60
url: /cs/net/annotations/extracthighlightedtext/
---
Chcete-li extrahovat zvýrazněný text v souboru PDF, můžete použít Aspose.PDF for .NET API. Toto rozhraní API poskytuje jednoduchý způsob, jak načíst veškerý text, který byl v dokumentu zvýrazněn.

## Krok 1: Načtěte dokument PDF

 Prvním krokem při extrahování zvýrazněného textu v souboru PDF je načtení dokumentu pomocí rozhraní Aspose.PDF for .NET API. Můžete to udělat vytvořením nové instance souboru`Document` třídy a předání cesty k dokumentu PDF jako parametr. 

```csharp
// Cesta k adresáři dokumentů.
string dataDir ="YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "ExtractHighlightedText.pdf");
```

## Krok 2: Projděte všechny anotace

 Dalším krokem je projít všechny anotace v dokumentu PDF. Můžete to udělat pomocí a`foreach` smyčka, takhle:

```csharp
foreach (Annotation annotation in doc.Pages[1].Annotations)
{
	// Kód jde sem
}
```

## Krok 3: Filtrujte anotace textových značek

 Uvnitř`foreach` smyčky, budete muset odfiltrovat všechny anotace, které nejsou anotacemi textových značek. Můžete to udělat tak, že zkontrolujete, zda je anotace instancí souboru`TextMarkupAnnotation` třída.

```csharp
if (annotation is TextMarkupAnnotation)
{
	// Kód jde sem
}
```

## Krok 4: Načtěte zvýrazněné fragmenty textu

 Jakmile odfiltrujete všechny anotace textových značek, můžete načíst zvýrazněné části textu pro každou anotaci. Můžete to udělat zavoláním na`GetMarkedTextFragments()` metoda na`TextMarkupAnnotation` objekt.

```csharp
TextMarkupAnnotation highlightedAnnotation = annotation as TextMarkupAnnotation;
TextFragmentCollection collection = highlightedAnnotation.GetMarkedTextFragments();
```

## Krok 5: Zobrazte zvýrazněný text

 Nakonec můžete zobrazit zvýrazněný text uživateli. Můžete to provést procházením každého z nich`TextFragment` objekt v`TextFragmentCollection` a volání na`Text` vlastnictví.

```csharp
foreach (TextFragment tf in collection)
{
	Console.WriteLine(tf.Text);
}
```

### Příklad zdrojového kódu pro extrahování zvýrazněného textu pomocí Aspose.PDF pro .NET

```csharp
// Cesta k adresáři dokumentů.
string dataDir ="YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "ExtractHighlightedText.pdf");

foreach (Annotation annotation in doc.Pages[1].Annotations)
{
	if (annotation is TextMarkupAnnotation)
	{
		TextMarkupAnnotation highlightedAnnotation = annotation as TextMarkupAnnotation;
		TextFragmentCollection collection = highlightedAnnotation.GetMarkedTextFragments();
		foreach (TextFragment tf in collection)
		{
			Console.WriteLine(tf.Text);
		}
	}
}
```

## Závěr

V tomto tutoriálu jsme prozkoumali, jak extrahovat zvýrazněný text z dokumentu PDF pomocí Aspose.PDF pro .NET. Podle podrobného průvodce a pomocí poskytnutého zdrojového kódu C# mohou vývojáři snadno extrahovat a spravovat zvýrazněný text ve svých dokumentech PDF.

### Časté dotazy pro extrahování zvýrazněného textu v souboru PDF

#### Otázka: Co jsou anotace textových značek v dokumentu PDF?

Odpověď: Anotace textových značek jsou anotace, které zvýrazňují nebo označují určitý text v dokumentu PDF. Příklady textových anotací zahrnují zvýraznění, podtržení a přeškrtnutí.

#### Otázka: Mohu extrahovat text z jiných typů anotací pomocí Aspose.PDF pro .NET?

Odpověď: Ano, Aspose.PDF pro .NET poskytuje různé metody pro extrahování textu z různých typů anotací, včetně textových anotací, volných textových anotací a dalších.

#### Otázka: Podporuje Aspose.PDF for .NET extrahování textu ze souborů PDF chráněných heslem?

 Odpověď: Ano, Aspose.PDF for .NET podporuje extrahování textu ze souborů PDF chráněných heslem. Při načítání dokumentu PDF pomocí aplikace musíte zadat správné heslo`Document` třída.

#### Otázka: Mohu filtrovat zvýrazněný text na základě jiných kritérií, jako je barva nebo autor?

Odpověď: Ano, zvýrazněný text můžete filtrovat na základě jiných kritérií, jako je barva, autor nebo datum vytvoření. Aspose.PDF for .NET poskytuje metody pro přístup a filtrování anotací na základě jejich vlastností.

#### Otázka: Je možné uložit extrahovaný zvýrazněný text do samostatného souboru?

Odpověď: Ano, extrahovaný zvýrazněný text můžete uložit do samostatného souboru nebo jej uložit do datové struktury pro další zpracování nebo analýzu.
