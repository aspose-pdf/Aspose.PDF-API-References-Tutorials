---
title: Markeer karakter in PDF-bestand
linktitle: Markeer karakter in PDF-bestand
second_title: Aspose.PDF voor .NET API-referentie
description: Leer hoe u tekens in een PDF-bestand kunt markeren met Aspose.PDF voor .NET.
type: docs
weight: 240
url: /nl/net/programming-with-text/highlight-character-in-pdf/
---
In deze tutorial leggen we uit hoe u tekens in een PDF-bestand kunt markeren met behulp van de Aspose.PDF-bibliotheek voor .NET. We doorlopen het stapsgewijze proces van het markeren van tekens in een PDF met behulp van de meegeleverde C#-broncode.

## Vereisten

Voordat u begint, moet u ervoor zorgen dat u over het volgende beschikt:

- De Aspose.PDF voor .NET-bibliotheek is geïnstalleerd.
- Basiskennis van C#-programmering.

## Stap 1: De documentenmap instellen

 Eerst moet u het pad instellen naar de map waar uw invoer-PDF-bestand zich bevindt. Vervangen`"YOUR DOCUMENT DIRECTORY"` in de`dataDir` variabele met het pad naar uw PDF-bestand.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Stap 2: Het PDF-document laden

 Vervolgens laden we het invoer-PDF-document met behulp van de`Aspose.Pdf.Document` klas.

```csharp
Aspose.Pdf.Document pdfDocument = new Aspose.Pdf.Document(dataDir + "input.pdf");
```

## Stap 3: PDF naar afbeelding converteren

 Om tekens te markeren, converteren we het PDF-document naar een afbeelding met behulp van de`PdfConverter` klasse. We stellen de resolutie voor de conversie in en halen de afbeelding op als een`Bitmap` voorwerp.

```csharp
int resolution = 150;
using (MemoryStream ms = new MemoryStream())
{
     PdfConverter conv = new PdfConverter(pdfDocument);
     conv. Resolution = new Resolution(resolution, resolution);
     conv. GetNextImage(ms, System.Drawing.Imaging.ImageFormat.Png);
     Bitmap bmp = (Bitmap)Bitmap.FromStream(ms);
```

## Stap 4: Markeer tekens

 We doorlopen elke pagina van het PDF-document en gebruiken een`TextFragmentAbsorber` object om alle woorden op de pagina te vinden. Vervolgens itereren we over de tekstfragmenten, segmenten en tekens om ze te markeren met rechthoeken.

```csharp
using (System.Drawing.Graphics gr = System.Drawing.Graphics.FromImage(bmp))
{
     // Schaal instellen en transformeren
     float scale = resolution / 72f;
     gr.Transform = new System.Drawing.Drawing2D.Matrix(scale, 0, 0, -scale, 0, bmp.Height);

     // Door pagina's bladeren
     for (int i = 0; i < pdfDocument.Pages.Count; i++)
     {
         Page page = pdfDocument.Pages[1];

         //Vind alle woorden op de pagina
         TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber(@"[\S]+");
         textFragmentAbsorber.TextSearchOptions.IsRegularExpressionUsed = true;
         page. Accept(textFragmentAbsorber);
         TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;

         // Door tekstfragmenten bladeren
         foreach(TextFragment textFragment in textFragmentCollection)
         {
             if (i == 0)
             {
                 // Markeer tekens
                 gr.DrawRectangle(
                     Think.Yellow,
                     (float)textFragment.Position.XIndent,
                     (float)textFragment.Position.YIndent,
                     (float)textFragment.Rectangle.Width,
                     (float)textFragment.Rectangle.Height);

                 // Door segmenten heen lussen
                 foreach(TextSegment segment in textFragment.Segments)
                 {
                     // Markeer segment
                     gr.DrawRectangle(
                         Think Green,
                         (float)segment.Rectangle.LLX,
                         (float)segment.Rectangle.LLY,
                         (float)segment.Rectangle.Width,
                         (float)segment.Rectangle.Height);

                     // Door tekens heen bladeren
                     foreach(CharInfo characterInfo in segment.Characters)
                     {
                         // Markeer karakter
                         gr.DrawRectangle(
                             Think.Black,
                             (float)characterInfo.Rectangle.LLx,
                             (float)characterInfo.Rectangle.LLY,
                             (float)characterInfo.Rectangle.Width,
                             (float)characterInfo.Rectangle.Height);
                     }
                 }
             }
         }
     }
}
```

## Stap 5: Sla de uitvoerafbeelding op

Tot slot slaan we de aangepaste afbeelding met de gemarkeerde tekens op in het opgegeven uitvoerbestand.

```csharp
dataDir = dataDir + "HighlightCharacterInPDF_out.png";
bmp.Save(dataDir, System.Drawing.Imaging.ImageFormat.Png);
```

### Voorbeeldbroncode voor Markeerteken in PDF met behulp van Aspose.PDF voor .NET 
```csharp
try
{
	// Het pad naar de documentenmap.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	int resolution = 150;
	Aspose.Pdf.Document pdfDocument = new Aspose.Pdf.Document(dataDir + "input.pdf");
	using (MemoryStream ms = new MemoryStream())
	{
		PdfConverter conv = new PdfConverter(pdfDocument);
		conv.Resolution = new Resolution(resolution, resolution);
		conv.GetNextImage(ms, System.Drawing.Imaging.ImageFormat.Png);
		Bitmap bmp = (Bitmap)Bitmap.FromStream(ms);
		using (System.Drawing.Graphics gr = System.Drawing.Graphics.FromImage(bmp))
		{
			float scale = resolution / 72f;
			gr.Transform = new System.Drawing.Drawing2D.Matrix(scale, 0, 0, -scale, 0, bmp.Height);
			for (int i = 0; i < pdfDocument.Pages.Count; i++)
			{
				Page page = pdfDocument.Pages[1];
				// Maak een TextAbsorber-object om alle woorden te vinden
				TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber(@"[\S]+");
				textFragmentAbsorber.TextSearchOptions.IsRegularExpressionUsed = true;
				page.Accept(textFragmentAbsorber);
				// Haal de geëxtraheerde tekstfragmenten op
				TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
				// Loop door de fragmenten
				foreach (TextFragment textFragment in textFragmentCollection)
				{
					if (i == 0)
					{
						gr.DrawRectangle(
						Pens.Yellow,
						(float)textFragment.Position.XIndent,
						(float)textFragment.Position.YIndent,
						(float)textFragment.Rectangle.Width,
						(float)textFragment.Rectangle.Height);
						for (int segNum = 1; segNum <= textFragment.Segments.Count; segNum++)
						{
							TextSegment segment = textFragment.Segments[segNum];
							for (int charNum = 1; charNum <= segment.Characters.Count; charNum++)
							{
								CharInfo characterInfo = segment.Characters[charNum];
								Aspose.Pdf.Rectangle rect = page.GetPageRect(true);
								Console.WriteLine("TextFragment = " + textFragment.Text + "    Page URY = " + rect.URY +
												  "   TextFragment URY = " + textFragment.Rectangle.URY);
								gr.DrawRectangle(
								Pens.Black,
								(float)characterInfo.Rectangle.LLX,
								(float)characterInfo.Rectangle.LLY,
								(float)characterInfo.Rectangle.Width,
								(float)characterInfo.Rectangle.Height);
							}
							gr.DrawRectangle(
							Pens.Green,
							(float)segment.Rectangle.LLX,
							(float)segment.Rectangle.LLY,
							(float)segment.Rectangle.Width,
							(float)segment.Rectangle.Height);
						}
					}
				}
			}
		}
		dataDir = dataDir + "HighlightCharacterInPDF_out.png";
		bmp.Save(dataDir, System.Drawing.Imaging.ImageFormat.Png);
	}
	Console.WriteLine("\nCharacters highlighted successfully in pdf document.\nFile saved at " + dataDir);
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message + "\nThis example will only work if you apply a valid Aspose License. You can purchase full license or get 30 day temporary license from http:// Www.aspose.com/purchase/default.aspx.");
}
```

## Conclusie

In deze tutorial hebt u geleerd hoe u tekens in een PDF-document kunt markeren met behulp van de Aspose.PDF-bibliotheek voor .NET. Door de stapsgewijze handleiding te volgen en de meegeleverde C#-code uit te voeren, kunt u tekens in een PDF markeren en de uitvoer opslaan als een afbeelding.

### Veelgestelde vragen

#### V: Wat is het doel van de tutorial 'Teken markeren in PDF-bestand'?

A: De tutorial "Markeer karakter in PDF-bestand" legt uit hoe u de Aspose.PDF-bibliotheek voor .NET kunt gebruiken om karakters in een PDF-document te markeren. De tutorial biedt een stapsgewijze handleiding en C#-broncode om dit te bereiken.

#### V: Waarom zou ik tekens in een PDF-document willen markeren?

A: Het markeren van tekens in een PDF-document kan om verschillende redenen nuttig zijn, bijvoorbeeld om specifieke inhoud te benadrukken of om bepaalde tekst beter zichtbaar en herkenbaar te maken.

#### V: Hoe stel ik de documentenmap in?

A: Om de documentenmap in te stellen:

1.  Vervangen`"YOUR DOCUMENT DIRECTORY"` in de`dataDir` variabele met het pad naar de map waar uw PDF-invoerbestand zich bevindt.

#### V: Hoe laad ik een PDF-document en converteer ik het naar een afbeelding?

 A: In de tutorial wordt de`Aspose.Pdf.Document` klasse wordt gebruikt om het invoer-PDF-document te laden. Vervolgens wordt de`PdfConverter` klasse wordt gebruikt om het PDF-document naar een afbeelding te converteren. De resolutie van de afbeelding wordt ingesteld en de afbeelding wordt opgehaald als een`Bitmap` voorwerp.

#### V: Hoe markeer ik tekens in de afbeelding van een PDF-document?

A: De tutorial begeleidt u door het proces van het doorlopen van elke pagina van het PDF-document, waarbij u woorden vindt met behulp van een`TextFragmentAbsorber`en door tekstfragmenten, segmenten en tekens te itereren om ze te markeren met behulp van rechthoeken.

#### V: Kan ik het uiterlijk van de gemarkeerde karakters en segmenten aanpassen?

A: Ja, u kunt het uiterlijk van de gemarkeerde tekens en segmenten aanpassen door de kleuren en stijlen te wijzigen die worden gebruikt bij de tekenbewerkingen.

#### V: Hoe kan ik de aangepaste afbeelding met de gemarkeerde tekens opslaan?

 A: De tutorial laat zien hoe je de gewijzigde afbeelding met de gemarkeerde tekens kunt opslaan in het opgegeven uitvoerbestand met behulp van de`Save` methode van de`Bitmap` klas.

#### V: Is een geldige Aspose-licentie vereist voor deze tutorial?

A: Ja, een geldige Aspose-licentie is vereist om deze tutorial correct te laten werken. U kunt een volledige licentie kopen of een tijdelijke licentie van 30 dagen verkrijgen via de Aspose-website.