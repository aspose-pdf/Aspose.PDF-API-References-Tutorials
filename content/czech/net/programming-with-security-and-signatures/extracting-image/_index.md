---
title: Extrahování obrázku
linktitle: Extrahování obrázku
second_title: Aspose.PDF pro .NET API Reference
description: Snadno extrahujte obrázky z dokumentů PDF pomocí Aspose.PDF pro .NET.
type: docs
weight: 70
url: /cs/net/programming-with-security-and-signatures/extracting-image/
---
Extrahování obrázků z dokumentu PDF může být užitečné v mnoha případech. S Aspose.PDF pro .NET můžete snadno extrahovat obrázky pomocí následujícího zdrojového kódu:

## Krok 1: Importujte požadované knihovny

Než začnete, musíte importovat potřebné knihovny pro váš projekt C#. Zde jsou nezbytné importní směrnice:

```csharp
using Aspose.Pdf;
using System.Drawing;
using System.Drawing.Imaging;
```

## Krok 2: Nastavte cestu ke složce dokumentů

 V tomto kroku musíte zadat cestu ke složce obsahující soubor PDF, ze kterého chcete obrázek extrahovat. Nahradit`"YOUR DOCUMENTS DIRECTORY"` následujícím kódu se skutečnou cestou ke složce dokumentů:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
string input = dataDir + @"ExtractingImage.pdf";
```

## Krok 3: Extrahujte obrázek z dokumentu PDF

Nyní extrahujeme obrázek z dokumentu PDF pomocí následujícího kódu:

```csharp
using (Document pdfDocument = new Document(input))
{
foreach(Field field in pdfDocument.Form)
{
SignatureField sf = field as SignatureField;
if (sf != null)
{
string outFile = dataDir + @"output_out.jpg";
using (Stream imageStream = sf.ExtractImage())
{
if (imageStream != null)
{
using (Image image = Bitmap.FromStream(imageStream))
{
image.Save(outFile, ImageFormat.Jpeg);
}
}
}
}
}
}
```

V tomto příkladu procházíme každé pole formuláře v dokumentu PDF. Pokud je pole podpisu nalezeno, extrahujeme přidružený obrázek a uložíme jej do souboru JPEG.

### Ukázka zdrojového kódu pro extrahování obrázku pomocí Aspose.PDF pro .NET 
```csharp
// Cesta k adresáři dokumentů.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
string input = dataDir+ @"ExtractingImage.pdf";
using (Document pdfDocument = new Document(input))
{
	foreach (Field field in pdfDocument.Form)
	{
		SignatureField sf = field as SignatureField;
		if (sf != null)
		{
			string outFile = dataDir+ @"output_out.jpg";
			using (Stream imageStream = sf.ExtractImage())
			{
				if (imageStream != null)
				{
					using (System.Drawing.Image image = Bitmap.FromStream(imageStream))
					{
						image.Save(outFile, System.Drawing.Imaging.ImageFormat.Jpeg);
					}
				}
			}
		}
	}
}
```

## Závěr

gratuluji! Nyní máte krok za krokem průvodce extrahováním obrázků z dokumentu PDF pomocí Aspose.PDF pro .NET. Tento kód můžete integrovat do svých vlastních projektů a extrahovat obrázky a používat je podle potřeby.

Nezapomeňte se podívat na oficiální dokumentaci Aspose.PDF, kde najdete další informace o pokročilé extrakci obrázků a funkcích manipulace s dokumenty PDF.


### FAQ

#### Otázka: Je Aspose.PDF pro .NET vhodný pro začátečníky?

Odpověď: I když je určitá znalost programování v C# užitečná, náš tutoriál je navržen tak, aby byl přátelský pro začátečníky a provedl vás každým krokem.

#### Otázka: Mohu extrahovat více obrázků najednou?

A: Rozhodně! Implementací smyček a přizpůsobením poskytnutého kódu můžete extrahovat více obrázků z jednoho dokumentu PDF.

#### Otázka: Je Aspose.PDF pro .NET jediným řešením pro extrakci obrázků?

Odpověď: I když jsou k dispozici další nástroje, Aspose.PDF pro .NET je proslulý svou účinností a komplexními funkcemi.

#### Otázka: Mohu použít extrahované obrázky pro komerční účely?

Odpověď: Ano, po extrahování jsou obrázky vaše a můžete je použít podle potřeby, včetně komerčních projektů.

#### Otázka: Kde najdu další zdroje o manipulaci s PDF pomocí Aspose.PDF?

Odpověď: Navštivte naši oficiální dokumentaci, kde najdete množství zdrojů a postřehů o pokročilé manipulaci s PDF pomocí Aspose.PDF pro .NET.