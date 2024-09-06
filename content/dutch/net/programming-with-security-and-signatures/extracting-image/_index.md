---
title: Afbeelding extraheren
linktitle: Afbeelding extraheren
second_title: Aspose.PDF voor .NET API-referentie
description: Haal eenvoudig afbeeldingen uit PDF-documenten met Aspose.PDF voor .NET.
type: docs
weight: 70
url: /nl/net/programming-with-security-and-signatures/extracting-image/
---
Het extraheren van afbeeldingen uit een PDF-document kan in veel gevallen nuttig zijn. Met Aspose.PDF voor .NET kunt u eenvoudig afbeeldingen extraheren met behulp van de volgende broncode:

## Stap 1: Importeer de vereiste bibliotheken

Voordat u begint, moet u de benodigde bibliotheken voor uw C#-project importeren. Dit zijn de benodigde importrichtlijnen:

```csharp
using Aspose.Pdf;
using System.Drawing;
using System.Drawing.Imaging;
```

## Stap 2: Stel het pad naar de documentenmap in

 In deze stap moet u het pad opgeven naar de map met het PDF-bestand waaruit u de afbeelding wilt extraheren. Vervangen`"YOUR DOCUMENTS DIRECTORY"` in de volgende code met het daadwerkelijke pad naar uw documentenmap:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
string input = dataDir + @"ExtractingImage.pdf";
```

## Stap 3: Afbeelding uit PDF-document extraheren

Nu gaan we de afbeelding uit het PDF-document halen met behulp van de volgende code:

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

Gefeliciteerd! Nu hebt u een stapsgewijze handleiding om afbeeldingen uit een PDF-document te halen met Aspose.PDF voor .NET. U kunt deze code integreren in uw eigen projecten om afbeeldingen te halen en ze te gebruiken zoals nodig.

Raadpleeg de officiële Aspose.PDF-documentatie voor meer informatie over geavanceerde functies voor het extraheren van afbeeldingen en het bewerken van PDF-documenten.


### Veelgestelde vragen

#### V: Is Aspose.PDF voor .NET geschikt voor beginners?

A: Hoewel enige kennis van C#-programmering nuttig is, is onze tutorial zo ontworpen dat deze geschikt is voor beginners en u door elke stap wordt geleid.

#### V: Kan ik meerdere afbeeldingen tegelijk extraheren?

A: Absoluut! Door loops te implementeren en de meegeleverde code aan te passen, kunt u meerdere afbeeldingen uit één PDF-document halen.

#### V: Is Aspose.PDF voor .NET de enige oplossing voor het extraheren van afbeeldingen?

A: Hoewel er andere tools beschikbaar zijn, staat Aspose.PDF voor .NET bekend om zijn efficiëntie en uitgebreide functies.

#### V: Mag ik de geëxtraheerde afbeeldingen voor commerciële doeleinden gebruiken?

A: Ja, zodra u de afbeeldingen hebt geëxtraheerd, kunt u ze naar wens gebruiken, ook voor commerciële projecten.

#### V: Waar kan ik meer informatie vinden over PDF-manipulatie met Aspose.PDF?

A: Bezoek onze officiële documentatie voor een schat aan bronnen en inzichten over geavanceerde PDF-manipulatie met Aspose.PDF voor .NET.