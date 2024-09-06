---
title: Získejte cíle hypertextového odkazu v souboru PDF
linktitle: Získejte cíle hypertextového odkazu v souboru PDF
second_title: Aspose.PDF pro .NET API Reference
description: Naučte se extrahovat cíle hypertextových odkazů do souboru PDF pomocí Aspose.PDF for .NET.
type: docs
weight: 60
url: /cs/net/programming-with-links-and-actions/get-hyperlink-destinations/
---
Aspose.PDF for .NET je výkonná knihovna pro manipulaci a extrahování informací v souboru PDF pomocí programovacího jazyka C#. V tomto tutoriálu se zaměříme na extrahování cílů hypertextových odkazů ze souboru PDF pomocí Aspose.PDF for .NET.

## Předpoklady

Než začnete, ujistěte se, že máte následující:

- Integrované vývojové prostředí (IDE), jako je Visual Studio.
- Knihovna Aspose.PDF pro .NET nainstalovaná na vašem počítači.

## Krok 1: Nastavení vývojového prostředí

Než začnete psát kód, musíte nastavit vývojové prostředí vytvořením nového projektu C# ve vašem oblíbeném IDE.

## Krok 2: Importujte reference Aspose.PDF

Chcete-li použít Aspose.PDF pro .NET, musíte do svého projektu přidat příslušné odkazy. Chcete-li importovat potřebné reference, postupujte podle následujících kroků:

1. Ve svém projektu klikněte pravým tlačítkem na "Reference" a vyberte "Přidat referenci".
2. V okně "Add Reference" vyhledejte a vyberte soubory DLL Aspose.PDF for .NET.
3. Kliknutím na "OK" importujte reference do svého projektu.

## Krok 3: Načtení souboru PDF

Než budete moci extrahovat cíle hypertextových odkazů, musíte načíst soubor PDF do aplikace. K načtení souboru PDF použijte následující kód:

```csharp
// Cesta k adresáři dokumentů.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
// Načtěte soubor PDF
Document document = new Document(dataDir + "input.pdf");
```

Ujistěte se, že jste zadali správnou cestu k adresáři vašeho dokumentu a souboru PDF, který chcete zpracovat.

## Krok 4: Procházení stránek dokumentu

Nyní, když je soubor PDF načten, musíte projít všechny stránky dokumentu. To vám umožní získat

ir anotace hypertextového odkazu na každé stránce. K iteraci stránek dokumentu použijte následující kód:

```csharp
foreach(Aspose.Pdf.Page page in document.Pages)
{
     // Získejte anotace odkazů na konkrétní stránku
     AnnotationSelector selector = new AnnotationSelector(new Aspose.Pdf.Annotations.LinkAnnotation(page, Aspose.Pdf.Rectangle.Trivial));
     page. Accept(selector);
     // Vytvořte seznam pro uložení všech odkazů
     IList<Annotation> list = selector. Selected;
     // Procházejte každou položku v seznamu
     foreach(LinkAnnotation a in list)
     {
         // Vytisknout cílovou adresu URL
         Console.WriteLine("\nDestination: " + (a.Action as Aspose.Pdf.Annotations.GoToURIAction).URI + "\n");
     }
}
```

Tento kód prochází každou stránku dokumentu a vybírá anotace hypertextového odkazu na každé stránce. Poté tyto anotace uloží do seznamu a pro každý odkaz vytiskne cílovou adresu URL.

## Krok 5: Získání cílů hypertextového odkazu

Posledním krokem je extrahování cílů hypertextového odkazu z anotací hypertextového odkazu. Následující kód ukazuje, jak to udělat:

```csharp
foreach(Aspose.Pdf.Page page in document.Pages)
{
     AnnotationSelector selector = new AnnotationSelector(new Aspose.Pdf.Annotations.LinkAnnotation(page, Aspose.Pdf.Rectangle.Trivial));
     page. Accept(selector);
     IList<Annotation> list = selector. Selected;
     foreach(LinkAnnotation a in list)
     {
         string destination = (a.Action as Aspose.Pdf.Annotations.GoToURIAction).URI;
         // Použijte cíl, jak chcete
     }
}
```

V tomto kódu získáme každý cíl hypertextového odkazu z anotací odkazu a uložíme cíl do proměnné. Tuto destinaci pak můžete ve své aplikaci použít libovolně.

### Ukázkový zdrojový kód pro Get Hyperlink Destinations pomocí Aspose.PDF for .NET 
```csharp
try
{
	// Cesta k adresáři dokumentů.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// Načtěte soubor PDF
	Document document = new Document(dataDir + "input.pdf");
	// Procházejte celou stránku PDF
	foreach (Aspose.Pdf.Page page in document.Pages)
	{
		// Získejte anotace odkazu z konkrétní stránky
		AnnotationSelector selector = new AnnotationSelector(new Aspose.Pdf.Annotations.LinkAnnotation(page, Aspose.Pdf.Rectangle.Trivial));
		page.Accept(selector);
		// Vytvořte seznam obsahující všechny odkazy
		IList<Annotation> list = selector.Selected;
		// Iterujte skrz invidiaul položku uvnitř seznamu
		foreach (LinkAnnotation a in list)
		{
			// Vytiskněte cílovou adresu URL
			Console.WriteLine("\nDestination: " + (a.Action as Aspose.Pdf.Annotations.GoToURIAction).URI + "\n");
		}
	}
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

### Časté dotazy pro získání cílů hypertextového odkazu v souboru PDF

#### Otázka: Co je cíl hypertextového odkazu v souboru PDF?

Odpověď: Cíl hypertextového odkazu v souboru PDF je konkrétní umístění nebo cíl, na který odkazuje hypertextový odkaz. Může to být adresa URL, stránka ve stejném dokumentu nebo externí dokument.

#### Otázka: Jak může extrahování cílů hypertextových odkazů prospět mé analýze dokumentů PDF?

Odpověď: Extrahování cílů hypertextových odkazů vám umožňuje identifikovat a katalogizovat všechny cíle, na které odkazují hypertextové odkazy v dokumentu PDF. Tyto informace mohou být užitečné pro ověřování obsahu, ověřování odkazů a analýzu dat.

#### Otázka: Jak Aspose.PDF for .NET pomáhá při extrahování cílů hypertextových odkazů?

Odpověď: Aspose.PDF pro .NET poskytuje výkonná rozhraní API pro snadné extrahování cílů hypertextových odkazů. Tento kurz ukazuje krok za krokem, jak extrahovat cíle hypertextových odkazů pomocí C#.

#### Otázka: Mohu selektivně extrahovat cíle hypertextových odkazů na základě určitých kritérií?

Odpověď: Ano, cíle hypertextových odkazů můžete selektivně extrahovat procházením stránek dokumentu PDF a filtrováním požadovaných anotací hypertextových odkazů na základě vašich kritérií.

#### Otázka: Je možné extrahovat cíle hypertextových odkazů z dokumentů PDF chráněných heslem?

Odpověď: Aspose.PDF for .NET může extrahovat cíle hypertextových odkazů z dokumentů PDF chráněných heslem, pokud při otevírání dokumentu poskytnete potřebné ověřovací údaje.

#### Otázka: Jak mohu využít extrahované cíle hypertextových odkazů ve své aplikaci?

Odpověď: Jakmile extrahujete cíle hypertextových odkazů, můžete je použít k provádění různých akcí, jako je ověřování adres URL odkazů, vytváření sestav nebo implementace vlastní navigace.

#### Otázka: Existují nějaká omezení při extrahování cílů hypertextových odkazů?

Odpověď: I když je extrakce cíle hypertextového odkazu výkonná, je nezbytné vzít v úvahu strukturu dokumentu PDF. Hypertextové odkazy vložené do složité grafiky nebo multimediálního obsahu mohou vyžadovat další manipulaci.

#### Otázka: Mohu extrahovat další atributy hypertextových odkazů, jako jsou typy odkazů nebo souřadnice?

Odpověď: Výukový program se zaměřuje na extrahování cílů hypertextových odkazů. Můžete se však podívat na oficiální dokumentaci Aspose.PDF a prozkoumat pokročilé funkce, včetně extrahování typů odkazů a souřadnic.