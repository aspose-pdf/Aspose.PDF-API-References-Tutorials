---
title: Informace o obrázku v souboru PDF
linktitle: Informace o obrázku v souboru PDF
second_title: Aspose.PDF pro .NET API Reference
description: Extrahujte informace o obrázku do souboru PDF pomocí Aspose.PDF pro .NET.
type: docs
weight: 160
url: /cs/net/programming-with-images/image-information/
---
Tato příručka vás krok za krokem provede extrahováním informací o obrázcích v souboru PDF pomocí Aspose.PDF pro .NET. Ujistěte se, že jste již nastavili své prostředí a postupujte podle následujících kroků:

## Krok 1: Definujte adresář dokumentů

 Ujistěte se, že jste nastavili správný adresář dokumentů. Nahradit`"YOUR DOCUMENT DIRECTORY"` v kódu s cestou k adresáři, kde se nachází váš dokument PDF.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Krok 2: Načtěte zdrojový soubor PDF

 V tomto kroku načteme zdrojový soubor PDF pomocí`Document` třída Aspose.PDF. Použijte`Document` konstruktoru a předejte cestu k dokumentu PDF.

```csharp
Document doc = new Document(dataDir + "ImageInformation.pdf");
```

## Krok 3: Nastavte výchozí rozlišení

V tomto kroku nastavíme výchozí rozlišení obrázků. V příkladu je výchozí rozlišení nastaveno na 72.

```csharp
int defaultResolution = 72;
```

## Krok 4: Inicializujte objekty a čítače

V tomto kroku inicializujeme objekty a čítače potřebné k načtení obrazových informací.

```csharp
System.Collections.Stack graphicsState = new System.Collections.Stack();
System.Collections.ArrayList imageNames = new System.Collections.ArrayList(doc.Pages[1].Resources.Images.Names);
```

## Krok 5: Procházejte operátory na první stránce dokumentu

V tomto kroku projdeme operátory na první stránce dokumentu, abychom identifikovali operace související s obrázky.

```csharp
foreach(Operator op in doc.Pages[1].Contents)
{
```

## Krok 6: Správa operátorů a extrahování informací o obrázku

V tomto kroku budeme spravovat různé typy operátorů a extrahovat informace o obrázcích.

```csharp
Aspose.Pdf.Operators.GSave opSaveState = op as Aspose.Pdf.Operators.GSave;
Aspose.Pdf.Operators.GRestore opRestoreState = op as Aspose.Pdf.Operators.GRestore;
Aspose.Pdf.Operators.ConcatenateMatrix opCtm = op as Aspose.Pdf.Operators.ConcatenateMatrix;
Aspose.Pdf.Operators.Do opDo = op as Aspose.Pdf.Operators.Do;

//Zvládněte operace GSave a GRestore pro transformace
if (opSaveState != null)
{
     graphicsState.Push(((System.Drawing.Drawing2D.Matrix)graphicsState.Peek()).Clone());
}
else if (opRestoreState != null)
{
     graphicsState. Pop();
}
// Pro transformace zpracujte operaci ConcatenateMatrix
else if (opCtm != null)
{
     // Použijte transformační matici
     System.Drawing.Drawing2D.Matrix cm = new System.Drawing.Drawing2D.Matrix(
        (float)opCtm.Matrix.A,
        (float)opCtm.Matrix.B,
        (float)opCtm.Matrix.C,
        (float)opCtm.Matrix.D,
        (float)opCtm.Matrix.E,
        (float)opCtm.Matrix.F);


     ((System.Drawing.Drawing2D.Matrix)graphicsState.Peek()).Multiply(cm);
     keep on going;
}
// Proveďte operaci Do pro obrázky
else if (opDo != null)
{
     if (imageNames.Contains(opDo.Name))
     {
         // Načtěte obrázek
         XImage image = doc.Pages[1].Resources.Images[opDo.Name];
         // Načtěte rozměry obrázku
         double scaledWidth = Math.Sqrt(Math.Pow(lastCTM.Elements[0], 2) + Math.Pow(lastCTM.Elements[1], 2));
         double scaledHeight = Math.Sqrt(Math.Pow(lastCTM.Elements[2], 2) + Math.Pow(lastCTM.Elements[3], 2));
         // Vypočítejte rozlišení na základě výše uvedených informací
         double resHorizontal = originalWidth * defaultResolution / scaledWidth;
         double resVertical = originalHeight * defaultResolution / scaledHeight;
         // Zobrazení informací o obrázku
         Console.Out.WriteLine(
                 string.Format(dataDir + "image {0} ({1:.##}:{2:.##}): res {3:.##} x {4:.##}",
								 opDo.Name, scaledWidth, scaledHeight, resHorizontal,
								 resVertical));
     }
}
```

### Ukázkový zdrojový kód pro Image Information pomocí Aspose.PDF pro .NET 
```csharp
// Cesta k adresáři dokumentů.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Načtěte zdrojový soubor PDF
Document doc = new Document(dataDir+ "ImageInformation.pdf");
// Definujte výchozí rozlišení obrázku
int defaultResolution = 72;
System.Collections.Stack graphicsState = new System.Collections.Stack();
// Definujte objekt seznamu polí, který bude obsahovat názvy obrázků
System.Collections.ArrayList imageNames = new System.Collections.ArrayList(doc.Pages[1].Resources.Images.Names);
// Vložte objekt, který chcete naskládat
graphicsState.Push(new System.Drawing.Drawing2D.Matrix(1, 0, 0, 1, 0, 0));
// Získejte všechny operátory na první stránce dokumentu
foreach (Operator op in doc.Pages[1].Contents)
{
	// Pomocí operátorů GSave/GRestore vrátíte transformace zpět na dříve nastavené
	Aspose.Pdf.Operators.GSave opSaveState = op as Aspose.Pdf.Operators.GSave;
	Aspose.Pdf.Operators.GRestore opRestoreState = op as Aspose.Pdf.Operators.GRestore;
	// Vytvořte instanci objektu ConcatenateMatrix, protože definuje aktuální transformační matici.
	Aspose.Pdf.Operators.ConcatenateMatrix opCtm = op as Aspose.Pdf.Operators.ConcatenateMatrix;
	// Operátor Create Do, který čerpá objekty ze zdrojů. Kreslí objekty Form a Image objekty
	Aspose.Pdf.Operators.Do opDo = op as Aspose.Pdf.Operators.Do;
	if (opSaveState != null)
	{
		//Uložte předchozí stav a přesuňte aktuální stav na vrchol zásobníku
		graphicsState.Push(((System.Drawing.Drawing2D.Matrix)graphicsState.Peek()).Clone());
	}
	else if (opRestoreState != null)
	{
		// Zahodit současný stav a obnovit předchozí
		graphicsState.Pop();
	}
	else if (opCtm != null)
	{
		System.Drawing.Drawing2D.Matrix cm = new System.Drawing.Drawing2D.Matrix(
		   (float)opCtm.Matrix.A,
		   (float)opCtm.Matrix.B,
		   (float)opCtm.Matrix.C,
		   (float)opCtm.Matrix.D,
		   (float)opCtm.Matrix.E,
		   (float)opCtm.Matrix.F);
		// Vynásobte aktuální matici stavovou maticí
		((System.Drawing.Drawing2D.Matrix)graphicsState.Peek()).Multiply(cm);
		continue;
	}
	else if (opDo != null)
	{
		// V případě, že se jedná o operátor kreslení obrázků
		if (imageNames.Contains(opDo.Name))
		{
			System.Drawing.Drawing2D.Matrix lastCTM = (System.Drawing.Drawing2D.Matrix)graphicsState.Peek();
			// Vytvořte objekt XImage pro uložení obrázků první stránky PDF
			XImage image = doc.Pages[1].Resources.Images[opDo.Name];
			// Získejte rozměry obrázku
			double scaledWidth = Math.Sqrt(Math.Pow(lastCTM.Elements[0], 2) + Math.Pow(lastCTM.Elements[1], 2));
			double scaledHeight = Math.Sqrt(Math.Pow(lastCTM.Elements[2], 2) + Math.Pow(lastCTM.Elements[3], 2));
			// Získejte informace o výšce a šířce obrázku
			double originalWidth = image.Width;
			double originalHeight = image.Height;
			// Vypočítejte rozlišení na základě výše uvedených informací
			double resHorizontal = originalWidth * defaultResolution / scaledWidth;
			double resVertical = originalHeight * defaultResolution / scaledHeight;
			// Zobrazení informací o rozměrech a rozlišení každého obrázku
			Console.Out.WriteLine(
					string.Format(dataDir + "image {0} ({1:.##}:{2:.##}): res {3:.##} x {4:.##}",
								 opDo.Name, scaledWidth, scaledHeight, resHorizontal,
								 resVertical));
		}
	}
}
```

## Závěr

gratuluji! Nyní jste se naučili, jak extrahovat informace o obrázku do souboru PDF pomocí Aspose.PDF pro .NET. Tyto informace můžete použít pro různé úlohy zpracování obrazu ve vašich aplikacích.

### Časté dotazy pro informace o obrázku v souboru PDF

#### Otázka: Jaký je účel extrahování obrazových informací z dokumentu PDF pomocí Aspose.PDF pro .NET?

Odpověď: Extrahování obrazových informací z dokumentu PDF poskytuje náhled na rozměry, rozlišení a další atributy obrazů v dokumentu. Tyto informace lze použít pro zpracování obrazu, analýzu nebo optimalizační úlohy.

#### Otázka: Jak Aspose.PDF for .NET pomáhá při extrahování obrazových informací z dokumentu PDF?

Odpověď: Aspose.PDF for .NET poskytuje nástroje pro přístup a analýzu obsahu dokumentu PDF, včetně jeho obrázků. Poskytnutý kód ukazuje, jak extrahovat a zobrazovat informace o obrázku pomocí různých operátorů.

#### Otázka: Jaký druh obrazových informací lze pomocí této metody extrahovat?

Odpověď: Tato metoda umožňuje extrahovat a zobrazovat informace, jako jsou zmenšené rozměry, rozlišení a názvy obrázků pro obrázky v dokumentu PDF.

#### Otázka: Jak kód identifikuje a zpracovává operátory související s obrázky v dokumentu PDF?

Odpověď: Kód iteruje operátory na zadané stránce dokumentu PDF. Identifikuje a zpracovává operátory související s operacemi s obrázky, transformacemi a vykreslováním.

#### Otázka: Jaký je význam výchozího rozlišení a jak se používá v kódu?

A: Výchozí rozlišení se používá jako referenční bod pro výpočet skutečného rozlišení obrázků. Kód vypočítá rozlišení každého obrázku na základě jeho rozměrů a výchozího nastavení rozlišení.

#### Otázka: Jak lze extrahované obrazové informace využít ve scénářích reálného světa?

Odpověď: Extrahované obrazové informace lze použít pro úkoly, jako je hodnocení kvality obrazu, optimalizace obrazu, generování miniatur snímků a usnadnění rozhodovacích procesů souvisejících s obrazem.

#### Otázka: Mohu upravit kód a extrahovat další atributy související s obrázkem?

Odpověď: Ano, kód můžete přizpůsobit tak, aby extrahoval další atributy obrázků, jako je barevný prostor, hloubka pixelů nebo typ obrázku.

#### Otázka: Je proces extrakce obrazových informací náročný na zdroje nebo časově?

Odpověď: Proces extrakce obrazových informací je efektivní a optimalizovaný pro výkon a zajišťuje minimální dopad na využití zdrojů a dobu zpracování.

#### Otázka: Jak mohou vývojáři těžit z identifikace a extrahování obrazových informací z dokumentů PDF?

Odpověď: Vývojáři mohou získat přehled o vlastnostech obrázků v dokumentech PDF, což jim umožní činit informovaná rozhodnutí týkající se manipulace s obrázky, zpracování a optimalizace.

#### Otázka: Lze tuto metodu použít pro dávkové zpracování dokumentů PDF obsahujících obrázky?

Odpověď: Ano, tuto metodu lze rozšířit pro dávkové zpracování iterací přes více stránek nebo dokumentů, extrahováním obrazových informací a prováděním úloh souvisejících s obrazem.