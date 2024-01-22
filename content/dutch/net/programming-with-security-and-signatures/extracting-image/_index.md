---
title: Afbeelding extraheren
linktitle: Afbeelding extraheren
second_title: Aspose.PDF voor .NET API-referentie
description: Extraheer eenvoudig afbeeldingen uit PDF-documenten met Aspose.PDF voor .NET.
type: docs
weight: 70
url: /nl/net/programming-with-security-and-signatures/extracting-image/
---
Het extraheren van afbeeldingen uit een PDF-document kan in veel gevallen nuttig zijn. Met Aspose.PDF voor .NET kunt u eenvoudig afbeeldingen extraheren met behulp van de volgende broncode:

## Stap 1: Importeer de vereiste bibliotheken

Voordat u begint, moet u de benodigde bibliotheken voor uw C#-project importeren. Hier zijn de noodzakelijke importrichtlijnen:

```csharp
using Aspose.Pdf;
using System.Drawing;
using System.Drawing.Imaging;
```

## Stap 2: Stel het pad naar de documentenmap in

 In deze stap moet u het pad opgeven naar de map met het PDF-bestand waaruit u de afbeelding wilt extraheren. Vervangen`"YOUR DOCUMENTS DIRECTORY"`in de volgende code met het daadwerkelijke pad naar uw documentenmap:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
string input = dataDir + @"ExtractingImage.pdf";
```

## Stap 3: Afbeelding uit PDF-document extraheren

Nu extraheren we de afbeelding uit het PDF-document met behulp van de volgende code:

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

In dit voorbeeld doorlopen we elk veld van het formulier in het PDF-document. Als er een handtekeningveld wordt gevonden, extraheren we de bijbehorende afbeelding en slaan deze op in een JPEG-bestand.

### Voorbeeldbroncode voor het extraheren van afbeeldingen met Aspose.PDF voor .NET 
```csharp
// Het pad naar de documentenmap.
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

## Conclusie

Gefeliciteerd! Nu hebt u een stapsgewijze handleiding om afbeeldingen uit een PDF-document te extraheren met Aspose.PDF voor .NET. U kunt deze code in uw eigen projecten integreren om afbeeldingen te extraheren en deze indien nodig te gebruiken.

Zorg ervoor dat u de officiële Aspose.PDF-documentatie raadpleegt voor meer informatie over geavanceerde functies voor het extraheren van afbeeldingen en het manipuleren van PDF-documenten.


### Veelgestelde vragen

#### Vraag: Is Aspose.PDF voor .NET geschikt voor beginners?

A: Hoewel enige bekendheid met programmeren in C# handig is, is onze tutorial bedoeld om beginnersvriendelijk te zijn en u door elke stap te leiden.

#### Vraag: Kan ik meerdere afbeeldingen tegelijk extraheren?

EEN: Absoluut! Door loops te implementeren en de meegeleverde code aan te passen, kunt u meerdere afbeeldingen uit één PDF-document extraheren.

#### Vraag: Is Aspose.PDF voor .NET de enige oplossing voor het extraheren van afbeeldingen?

A: Hoewel er andere tools beschikbaar zijn, staat Aspose.PDF voor .NET bekend om zijn efficiëntie en uitgebreide functies.

#### Vraag: Kan ik de geëxtraheerde afbeeldingen gebruiken voor commerciële doeleinden?

A: Ja, zodra u de afbeeldingen hebt uitgepakt, kunt u deze indien nodig gebruiken, ook voor commerciële projecten.

#### Vraag: Waar kan ik meer bronnen vinden over PDF-manipulatie met Aspose.PDF?

A: Bezoek onze officiële documentatie voor een schat aan bronnen en inzichten over geavanceerde PDF-manipulatie met Aspose.PDF voor .NET.