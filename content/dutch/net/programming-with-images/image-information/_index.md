---
title: Afbeeldingsinformatie in PDF-bestand
linktitle: Afbeeldingsinformatie in PDF-bestand
second_title: Aspose.PDF voor .NET API-referentie
description: Haal afbeeldingsinformatie uit een PDF-bestand met Aspose.PDF voor .NET.
type: docs
weight: 160
url: /nl/net/programming-with-images/image-information/
---
Deze gids laat u stap voor stap zien hoe u informatie over afbeeldingen in een PDF-bestand kunt extraheren met Aspose.PDF voor .NET. Zorg ervoor dat u uw omgeving al hebt ingesteld en volg de onderstaande stappen:

## Stap 1: Definieer de documentdirectory

 Zorg ervoor dat u de juiste documentdirectory instelt. Vervangen`"YOUR DOCUMENT DIRECTORY"` in de code met het pad naar de map waar uw PDF-document zich bevindt.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Stap 2: Laad het bron-PDF-bestand

 In deze stap laden we het bron-PDF-bestand met behulp van de`Document` klasse van Aspose.PDF. Gebruik de`Document` constructor en geef het pad naar het PDF-document door.

```csharp
Document doc = new Document(dataDir + "ImageInformation.pdf");
```

## Stap 3: Standaardresolutie instellen

In deze stap stellen we de standaardresolutie voor afbeeldingen in. In het voorbeeld is de standaardresolutie ingesteld op 72.

```csharp
int defaultResolution = 72;
```

## Stap 4: Initialiseer objecten en tellers

In deze stap initialiseren we de objecten en tellers die nodig zijn om de beeldinformatie op te halen.

```csharp
System.Collections.Stack graphicsState = new System.Collections.Stack();
System.Collections.ArrayList imageNames = new System.Collections.ArrayList(doc.Pages[1].Resources.Images.Names);
```

## Stap 5: Blader door de operatoren op de eerste pagina van het document

In deze stap doorlopen we de operatoren op de eerste pagina van het document om bewerkingen met betrekking tot afbeeldingen te identificeren.

```csharp
foreach(Operator op in doc.Pages[1].Contents)
{
```

## Stap 6: Beheer operators en extraheer beeldinformatie

In deze stap beheren we de verschillende typen operatoren en extraheren we informatie over de afbeeldingen.

```csharp
Aspose.Pdf.Operators.GSave opSaveState = op as Aspose.Pdf.Operators.GSave;
Aspose.Pdf.Operators.GRestore opRestoreState = op as Aspose.Pdf.Operators.GRestore;
Aspose.Pdf.Operators.ConcatenateMatrix opCtm = op as Aspose.Pdf.Operators.ConcatenateMatrix;
Aspose.Pdf.Operators.Do opDo = op as Aspose.Pdf.Operators.Do;

//GSave- en GRestore-bewerkingen voor transformaties verwerken
if (opSaveState != null)
{
     graphicsState.Push(((System.Drawing.Drawing2D.Matrix)graphicsState.Peek()).Clone());
}
else if (opRestoreState != null)
{
     graphicsState. Pop();
}
// De ConcatenateMatrix-bewerking voor transformaties verwerken
else if (opCtm != null)
{
     // Pas de transformatiematrix toe
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
// De Do-bewerking voor afbeeldingen verwerken
else if (opDo != null)
{
     if (imageNames.Contains(opDo.Name))
     {
         // Haal de afbeelding op
         XImage image = doc.Pages[1].Resources.Images[opDo.Name];
         // De afmetingen van de afbeelding ophalen
         double scaledWidth = Math.Sqrt(Math.Pow(lastCTM.Elements[0], 2) + Math.Pow(lastCTM.Elements[1], 2));
         double scaledHeight = Math.Sqrt(Math.Pow(lastCTM.Elements[2], 2) + Math.Pow(lastCTM.Elements[3], 2));
         // Bereken de resolutie op basis van de bovenstaande informatie
         double resHorizontal = originalWidth * defaultResolution / scaledWidth;
         double resVertical = originalHeight * defaultResolution / scaledHeight;
         // Beeldinformatie weergeven
         Console.Out.WriteLine(
                 string.Format(dataDir + "image {0} ({1:.##}:{2:.##}): res {3:.##} x {4:.##}",
								 opDo.Name, scaledWidth, scaledHeight, resHorizontal,
								 resVertical));
     }
}
```

### Voorbeeldbroncode voor Image Information met behulp van Aspose.PDF voor .NET 
```csharp
// Het pad naar de documentenmap.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Laad het bron-PDF-bestand
Document doc = new Document(dataDir+ "ImageInformation.pdf");
// Definieer de standaardresolutie voor afbeeldingen
int defaultResolution = 72;
System.Collections.Stack graphicsState = new System.Collections.Stack();
// Definieer een arraylijstobject dat afbeeldingsnamen zal bevatten
System.Collections.ArrayList imageNames = new System.Collections.ArrayList(doc.Pages[1].Resources.Images.Names);
// Voeg een object toe om te stapelen
graphicsState.Push(new System.Drawing.Drawing2D.Matrix(1, 0, 0, 1, 0, 0));
// Alle operatoren op de eerste pagina van het document krijgen
foreach (Operator op in doc.Pages[1].Contents)
{
	// Gebruik GSave/GRestore-operatoren om de transformaties terug te zetten naar de eerder ingestelde
	Aspose.Pdf.Operators.GSave opSaveState = op as Aspose.Pdf.Operators.GSave;
	Aspose.Pdf.Operators.GRestore opRestoreState = op as Aspose.Pdf.Operators.GRestore;
	// Instantieer het ConcatenateMatrix-object terwijl het de huidige transformatiematrix definieert.
	Aspose.Pdf.Operators.ConcatenateMatrix opCtm = op as Aspose.Pdf.Operators.ConcatenateMatrix;
	// Create Do operator die objecten uit resources tekent. Het tekent Form-objecten en Image-objecten
	Aspose.Pdf.Operators.Do opDo = op as Aspose.Pdf.Operators.Do;
	if (opSaveState != null)
	{
		//Vorige staat opslaan en huidige staat bovenaan de stapel plaatsen
		graphicsState.Push(((System.Drawing.Drawing2D.Matrix)graphicsState.Peek()).Clone());
	}
	else if (opRestoreState != null)
	{
		// Gooi de huidige staat weg en herstel de vorige
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
		// Vermenigvuldig de huidige matrix met de toestandsmatrix
		((System.Drawing.Drawing2D.Matrix)graphicsState.Peek()).Multiply(cm);
		continue;
	}
	else if (opDo != null)
	{
		// Als dit een operator is voor het tekenen van afbeeldingen
		if (imageNames.Contains(opDo.Name))
		{
			System.Drawing.Drawing2D.Matrix lastCTM = (System.Drawing.Drawing2D.Matrix)graphicsState.Peek();
			// Maak een XImage-object om afbeeldingen van de eerste pdf-pagina vast te houden
			XImage image = doc.Pages[1].Resources.Images[opDo.Name];
			// Afmetingen van de afbeelding ophalen
			double scaledWidth = Math.Sqrt(Math.Pow(lastCTM.Elements[0], 2) + Math.Pow(lastCTM.Elements[1], 2));
			double scaledHeight = Math.Sqrt(Math.Pow(lastCTM.Elements[2], 2) + Math.Pow(lastCTM.Elements[3], 2));
			// Hoogte- en breedte-informatie van afbeelding ophalen
			double originalWidth = image.Width;
			double originalHeight = image.Height;
			// Bereken de resolutie op basis van bovenstaande informatie
			double resHorizontal = originalWidth * defaultResolution / scaledWidth;
			double resVertical = originalHeight * defaultResolution / scaledHeight;
			// Weergave van dimensie- en resolutie-informatie van elke afbeelding
			Console.Out.WriteLine(
					string.Format(dataDir + "image {0} ({1:.##}:{2:.##}): res {3:.##} x {4:.##}",
								 opDo.Name, scaledWidth, scaledHeight, resHorizontal,
								 resVertical));
		}
	}
}
```

## Conclusie

Gefeliciteerd! U hebt nu geleerd hoe u beeldinformatie uit een PDF-bestand kunt extraheren met Aspose.PDF voor .NET. U kunt deze informatie gebruiken voor verschillende beeldverwerkingstaken in uw toepassingen.

### FAQ's voor afbeeldingsinformatie in PDF-bestand

#### V: Wat is het doel van het extraheren van afbeeldingsinformatie uit een PDF-document met Aspose.PDF voor .NET?

A: Het extraheren van beeldinformatie uit een PDF-document biedt inzicht in de afmetingen, resolutie en andere kenmerken van afbeeldingen in het document. Deze informatie kan worden gebruikt voor beeldverwerking, analyse of optimalisatietaken.

#### V: Hoe helpt Aspose.PDF voor .NET bij het extraheren van afbeeldingsinformatie uit een PDF-document?

A: Aspose.PDF voor .NET biedt tools om de inhoud van een PDF-document te openen en analyseren, inclusief de afbeeldingen. De meegeleverde code laat zien hoe u afbeeldingsinformatie kunt extraheren en weergeven met behulp van verschillende operatoren.

#### V: Welke beeldinformatie kan met deze methode worden geëxtraheerd?

A: Met deze methode kunt u informatie zoals geschaalde afmetingen, resolutie en afbeeldingsnamen voor afbeeldingen in een PDF-document extraheren en weergeven.

#### V: Hoe identificeert en verwerkt de code afbeeldinggerelateerde operatoren in een PDF-document?

A: De code itereert door de operatoren op een opgegeven pagina van het PDF-document. Het identificeert en verwerkt operatoren gerelateerd aan afbeeldingsbewerkingen, transformaties en rendering.

#### V: Wat is de betekenis van standaardresolutie en hoe wordt het in de code gebruikt?

A: Standaardresolutie wordt gebruikt als referentiepunt om de werkelijke resolutie van afbeeldingen te berekenen. De code berekent de resolutie van elke afbeelding op basis van de afmetingen en de standaardresolutie-instelling.

#### V: Hoe kan de geëxtraheerde beeldinformatie in realistische situaties worden gebruikt?

A: De geëxtraheerde beeldinformatie kan worden gebruikt voor taken zoals het beoordelen van de beeldkwaliteit, het optimaliseren van beelden, het genereren van miniatuurafbeeldingen en het vergemakkelijken van besluitvormingsprocessen met betrekking tot beelden.

#### V: Kan ik de code aanpassen om extra afbeeldingsgerelateerde kenmerken te extraheren?

A: Ja, u kunt de code aanpassen om extra kenmerken van afbeeldingen te extraheren, zoals kleurruimte, pixeldiepte of afbeeldingstype.

#### V: Is het proces van het extraheren van beeldinformatie arbeidsintensief of tijdrovend?

A: Het proces voor het extraheren van beeldinformatie is efficiënt en geoptimaliseerd voor prestaties, waardoor de impact op het resourcegebruik en de verwerkingstijd minimaal is.

#### V: Hoe kunnen ontwikkelaars profiteren van het identificeren en extraheren van afbeeldingsinformatie uit PDF-documenten?

A: Ontwikkelaars kunnen inzicht krijgen in de kenmerken van afbeeldingen in PDF-documenten, zodat ze weloverwogen beslissingen kunnen nemen over beeldmanipulatie, -verwerking en -optimalisatie.

#### V: Kan deze methode worden gebruikt voor batchverwerking van PDF-documenten met afbeeldingen?

A: Ja, deze methode kan worden uitgebreid voor batchverwerking door meerdere pagina's of documenten te doorlopen, beeldinformatie te extraheren en beeldgerelateerde taken uit te voeren.