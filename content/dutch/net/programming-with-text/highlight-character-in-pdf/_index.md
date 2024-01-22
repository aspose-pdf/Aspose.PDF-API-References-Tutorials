---
title: Markeer karakter in PDF-bestand
linktitle: Markeer karakter in PDF-bestand
second_title: Aspose.PDF voor .NET API-referentie
description: Leer hoe u tekens in een PDF-bestand kunt markeren met Aspose.PDF voor .NET.
type: docs
weight: 240
url: /nl/net/programming-with-text/highlight-character-in-pdf/
---
In deze zelfstudie leggen we uit hoe u tekens in een PDF-bestand kunt markeren met behulp van de Aspose.PDF-bibliotheek voor .NET. We zullen stapsgewijs het proces doorlopen van het markeren van tekens in een PDF met behulp van de meegeleverde C#-broncode.

## Vereisten

Zorg ervoor dat u over het volgende beschikt voordat u begint:

- De Aspose.PDF voor .NET-bibliotheek geïnstalleerd.
- Basiskennis van programmeren in C#.

## Stap 1: Stel de documentmap in

 Eerst moet u het pad instellen naar de map waar uw invoer-PDF-bestand zich bevindt. Vervangen`"YOUR DOCUMENT DIRECTORY"` in de`dataDir` variabele met het pad naar uw PDF-bestand.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Stap 2: Laad het PDF-document

 Vervolgens laden we het invoer-PDF-document met behulp van de`Aspose.Pdf.Document` klas.

```csharp
Aspose.Pdf.Document pdfDocument = new Aspose.Pdf.Document(dataDir + "input.pdf");
```

## Stap 3: Converteer PDF naar afbeelding

 Om tekens te markeren, converteren we het PDF-document naar een afbeelding met behulp van de`PdfConverter` klas. We stellen de resolutie voor de conversie in en halen de afbeelding op als een`Bitmap` voorwerp.

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

 We doorlopen elke pagina van het PDF-document en gebruiken een`TextFragmentAbsorber` object om alle woorden op de pagina te vinden. Vervolgens herhalen we de tekstfragmenten, segmenten en tekens om ze te markeren met behulp van rechthoeken.

```csharp
using (System.Drawing.Graphics gr = System.Drawing.Graphics.FromImage(bmp))
{
     //Schaal instellen en transformeren
     float scale = resolution / 72f;
     gr.Transform = new System.Drawing.Drawing2D.Matrix(scale, 0, 0, -scale, 0, bmp.Height);

     // Blader door pagina's
     for (int i = 0; i < pdfDocument.Pages.Count; i++)
     {
         Page page = pdfDocument.Pages[1];

         // Zoek alle woorden op de pagina
         TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber(@"[\S]+");
         textFragmentAbsorber.TextSearchOptions.IsRegularExpressionUsed = true;
         page. Accept(textFragmentAbsorber);
         TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;

         // Loop door tekstfragmenten
         foreach(TextFragment textFragment in textFragmentCollection)
         {
             if (i == 0)
             {
                 // Markeer karakters
                 gr.DrawRectangle(
                     Think.Yellow,
                     (float)textFragment.Position.XIndent,
                     (float)textFragment.Position.YIndent,
                     (float)textFragment.Rectangle.Width,
                     (float)textFragment.Rectangle.Height);

                 // Loop door segmenten
                 foreach(TextSegment segment in textFragment.Segments)
                 {
                     // Markeer segment
                     gr.DrawRectangle(
                         Think Green,
                         (float)segment.Rectangle.LLX,
                         (float)segment.Rectangle.LLY,
                         (float)segment.Rectangle.Width,
                         (float)segment.Rectangle.Height);

                     // Loop door karakters
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

Ten slotte slaan we de gewijzigde afbeelding met de gemarkeerde tekens op in het opgegeven uitvoerbestand.

```csharp
dataDir = dataDir + "HighlightCharacterInPDF_out.png";
bmp.Save(dataDir, System.Drawing.Imaging.ImageFormat.Png);
```

### Voorbeeldbroncode voor markeerteken in PDF met Aspose.PDF voor .NET 
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

In deze zelfstudie hebt u geleerd hoe u tekens in een PDF-document kunt markeren met behulp van de Aspose.PDF-bibliotheek voor .NET. Door de stapsgewijze handleiding te volgen en de meegeleverde C#-code uit te voeren, kunt u tekens in een PDF markeren en de uitvoer als afbeelding opslaan.

### Veelgestelde vragen

#### Vraag: Wat is het doel van de tutorial "Tekens markeren in PDF-bestand"?

A: In de tutorial "Tekens markeren in PDF-bestand" wordt uitgelegd hoe u de Aspose.PDF-bibliotheek voor .NET kunt gebruiken om tekens in een PDF-document te markeren. De tutorial biedt een stapsgewijze handleiding en C#-broncode om dit te bereiken.

#### Vraag: Waarom zou ik tekens in een PDF-document willen markeren?

A: Het markeren van tekens in een PDF-document kan voor verschillende doeleinden nuttig zijn, zoals het benadrukken van specifieke inhoud of het zichtbaarder en herkenbaarder maken van bepaalde tekst.

#### Vraag: Hoe stel ik de documentmap in?

A: Om de documentmap in te stellen:

1.  Vervangen`"YOUR DOCUMENT DIRECTORY"` in de`dataDir` variabele met het pad naar de map waar uw invoer-PDF-bestand zich bevindt.

#### Vraag: Hoe laad ik het PDF-document en converteer ik het naar een afbeelding?

 A: In de tutorial wordt de`Aspose.Pdf.Document` klasse wordt gebruikt om het invoer-PDF-document te laden. Dan de`PdfConverter` klasse wordt gebruikt om het PDF-document naar een afbeelding te converteren. De resolutie van de afbeelding wordt ingesteld en de afbeelding wordt opgehaald als`Bitmap` voorwerp.

#### Vraag: Hoe markeer ik tekens in de afbeelding van het PDF-document?

A: De tutorial begeleidt u bij het doorlopen van elke pagina van het PDF-document en het vinden van woorden met behulp van a`TextFragmentAbsorber`en door tekstfragmenten, segmenten en tekens lopen om ze met rechthoeken te markeren.

#### Vraag: Kan ik het uiterlijk van de gemarkeerde tekens en segmenten aanpassen?

A: Ja, u kunt het uiterlijk van de gemarkeerde tekens en segmenten aanpassen door de kleuren en stijlen te wijzigen die bij de tekenbewerkingen worden gebruikt.

#### Vraag: Hoe sla ik de gewijzigde afbeelding op met de gemarkeerde tekens?

 A: De tutorial laat zien hoe u de gewijzigde afbeelding met de gemarkeerde tekens kunt opslaan in het opgegeven uitvoerbestand met behulp van de`Save` werkwijze van de`Bitmap` klas.

#### Vraag: Is een geldige Aspose-licentie vereist voor deze zelfstudie?

A: Ja, een geldige Aspose-licentie is vereist om deze tutorial correct te laten werken. U kunt een volledige licentie kopen of een tijdelijke licentie van 30 dagen verkrijgen via de Aspose-website.