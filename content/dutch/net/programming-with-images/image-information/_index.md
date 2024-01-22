---
title: Afbeeldingsinformatie in PDF-bestand
linktitle: Afbeeldingsinformatie in PDF-bestand
second_title: Aspose.PDF voor .NET API-referentie
description: Extraheer afbeeldingsinformatie in een PDF-bestand met Aspose.PDF voor .NET.
type: docs
weight: 160
url: /nl/net/programming-with-images/image-information/
---
In deze handleiding wordt stap voor stap uitgelegd hoe u informatie over afbeeldingen in een PDF-bestand kunt extraheren met Aspose.PDF voor .NET. Zorg ervoor dat u uw omgeving al heeft ingesteld en volg de onderstaande stappen:

## Stap 1: Definieer de documentmap

 Zorg ervoor dat u de juiste documentmap instelt. Vervangen`"YOUR DOCUMENT DIRECTORY"` in de code met het pad naar de map waar uw PDF-document zich bevindt.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Stap 2: Laad het bron-PDF-bestand

 In deze stap laden we het bron-PDF-bestand met behulp van de`Document` klasse van Aspose.PDF. Gebruik de`Document` constructor en geef het pad door naar het PDF-document.

```csharp
Document doc = new Document(dataDir + "ImageInformation.pdf");
```

## Stap 3: Stel de standaardresolutie in

In deze stap stellen we de standaardresolutie voor afbeeldingen in. In het voorbeeld is de standaardresolutie ingesteld op 72.

```csharp
int defaultResolution = 72;
```

## Stap 4: Initialiseer objecten en tellers

In deze stap initialiseren we de objecten en tellers die nodig zijn om de afbeeldingsinformatie op te halen.

```csharp
System.Collections.Stack graphicsState = new System.Collections.Stack();
System.Collections.ArrayList imageNames = new System.Collections.ArrayList(doc.Pages[1].Resources.Images.Names);
```

## Stap 5: Blader door de operators op de eerste pagina van het document

In deze stap lopen we door de operators op de eerste pagina van het document om beeldgerelateerde bewerkingen te identificeren.

```csharp
foreach(Operator op in doc.Pages[1].Contents)
{
```

## Stap 6: Beheer operators en extraheer afbeeldingsinformatie

In deze stap beheren we de verschillende soorten operators en extraheren we de informatie over de afbeeldingen.

```csharp
Aspose.Pdf.Operators.GSave opSaveState = op as Aspose.Pdf.Operators.GSave;
Aspose.Pdf.Operators.GRestore opRestoreState = op as Aspose.Pdf.Operators.GRestore;
Aspose.Pdf.Operators.ConcatenateMatrix opCtm = op as Aspose.Pdf.Operators.ConcatenateMatrix;
Aspose.Pdf.Operators.Do opDo = op as Aspose.Pdf.Operators.Do;

//Voer GSave- en GRestore-bewerkingen uit voor transformaties
if (opSaveState != null)
{
     graphicsState.Push(((System.Drawing.Drawing2D.Matrix)graphicsState.Peek()).Clone());
}
else if (opRestoreState != null)
{
     graphicsState. Pop();
}
// Verwerk de ConcatenateMatrix-bewerking voor transformaties
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
// Voer de Do-bewerking uit voor afbeeldingen
else if (opDo != null)
{
     if (imageNames.Contains(opDo.Name))
     {
         // Haal de afbeelding op
         XImage image = doc.Pages[1].Resources.Images[opDo.Name];
         // Haal de afmetingen van de afbeelding op
         double scaledWidth = Math.Sqrt(Math.Pow(lastCTM.Elements[0], 2) + Math.Pow(lastCTM.Elements[1], 2));
         double scaledHeight = Math.Sqrt(Math.Pow(lastCTM.Elements[2], 2) + Math.Pow(lastCTM.Elements[3], 2));
         // Bereken de resolutie op basis van de bovenstaande informatie
         double resHorizontal = originalWidth * defaultResolution / scaledWidth;
         double resVertical = originalHeight * defaultResolution / scaledHeight;
         // Geef afbeeldingsinformatie weer
         Console.Out.WriteLine(
                 string.Format(dataDir + "image {0} ({1:.##}:{2:.##}): res {3:.##} x {4:.##}",
								 opDo.Name, scaledWidth, scaledHeight, resHorizontal,
								 resVertical));
     }
}
```

### Voorbeeldbroncode voor afbeeldingsinformatie met Aspose.PDF voor .NET 
```csharp
// Het pad naar de documentenmap.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Laad het bron-PDF-bestand
Document doc = new Document(dataDir+ "ImageInformation.pdf");
// Definieer de standaardresolutie voor de afbeelding
int defaultResolution = 72;
System.Collections.Stack graphicsState = new System.Collections.Stack();
// Definieer een arraylijstobject dat afbeeldingsnamen bevat
System.Collections.ArrayList imageNames = new System.Collections.ArrayList(doc.Pages[1].Resources.Images.Names);
// Plaats een object om te stapelen
graphicsState.Push(new System.Drawing.Drawing2D.Matrix(1, 0, 0, 1, 0, 0));
// Zet alle operators op de eerste pagina van het document
foreach (Operator op in doc.Pages[1].Contents)
{
	// Gebruik GSave/GRestore-operatoren om de transformaties terug te zetten naar de eerder ingestelde waarden
	Aspose.Pdf.Operators.GSave opSaveState = op as Aspose.Pdf.Operators.GSave;
	Aspose.Pdf.Operators.GRestore opRestoreState = op as Aspose.Pdf.Operators.GRestore;
	// Instantieer het ConcatenateMatrix-object zoals het de huidige transformatiematrix definieert.
	Aspose.Pdf.Operators.ConcatenateMatrix opCtm = op as Aspose.Pdf.Operators.ConcatenateMatrix;
	// Create Do-operator die objecten uit bronnen haalt. Het tekent vormobjecten en afbeeldingsobjecten
	Aspose.Pdf.Operators.Do opDo = op as Aspose.Pdf.Operators.Do;
	if (opSaveState != null)
	{
		//Bewaar de vorige status en duw de huidige status naar de top van de stapel
		graphicsState.Push(((System.Drawing.Drawing2D.Matrix)graphicsState.Peek()).Clone());
	}
	else if (opRestoreState != null)
	{
		// Gooi de huidige status weg en herstel de vorige
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
		// In het geval dat dit een operator voor het tekenen van afbeeldingen is
		if (imageNames.Contains(opDo.Name))
		{
			System.Drawing.Drawing2D.Matrix lastCTM = (System.Drawing.Drawing2D.Matrix)graphicsState.Peek();
			// Maak een XImage-object om afbeeldingen van de eerste pdf-pagina vast te houden
			XImage image = doc.Pages[1].Resources.Images[opDo.Name];
			// Afmetingen van afbeeldingen ophalen
			double scaledWidth = Math.Sqrt(Math.Pow(lastCTM.Elements[0], 2) + Math.Pow(lastCTM.Elements[1], 2));
			double scaledHeight = Math.Sqrt(Math.Pow(lastCTM.Elements[2], 2) + Math.Pow(lastCTM.Elements[3], 2));
			// Krijg hoogte- en breedte-informatie van de afbeelding
			double originalWidth = image.Width;
			double originalHeight = image.Height;
			// Bereken de resolutie op basis van bovenstaande informatie
			double resHorizontal = originalWidth * defaultResolution / scaledWidth;
			double resVertical = originalHeight * defaultResolution / scaledHeight;
			// Geef informatie over afmetingen en resolutie van elke afbeelding weer
			Console.Out.WriteLine(
					string.Format(dataDir + "image {0} ({1:.##}:{2:.##}): res {3:.##} x {4:.##}",
								 opDo.Name, scaledWidth, scaledHeight, resHorizontal,
								 resVertical));
		}
	}
}
```

## Conclusie

Gefeliciteerd! U hebt nu geleerd hoe u afbeeldingsinformatie uit een PDF-bestand kunt extraheren met Aspose.PDF voor .NET. U kunt deze informatie gebruiken voor verschillende beeldverwerkingstaken in uw toepassingen.

### Veelgestelde vragen over afbeeldingsinformatie in PDF-bestand

#### Vraag: Wat is het doel van het extraheren van afbeeldingsinformatie uit een PDF-document met Aspose.PDF voor .NET?

A: Het extraheren van afbeeldingsinformatie uit een PDF-document geeft inzicht in de afmetingen, resolutie en andere kenmerken van afbeeldingen in het document. Deze informatie kan worden gebruikt voor beeldverwerking, analyse of optimalisatietaken.

#### Vraag: Hoe helpt Aspose.PDF voor .NET bij het extraheren van afbeeldingsinformatie uit een PDF-document?

A: Aspose.PDF voor .NET biedt hulpmiddelen voor toegang tot en analyse van de inhoud van een PDF-document, inclusief de afbeeldingen. De meegeleverde code laat zien hoe u afbeeldingsinformatie kunt extraheren en weergeven met behulp van verschillende operators.

#### Vraag: Welk soort afbeeldingsinformatie kan met deze methode worden geëxtraheerd?

A: Met deze methode kunt u informatie extraheren en weergeven, zoals geschaalde afmetingen, resolutie en afbeeldingsnamen voor afbeeldingen in een PDF-document.

#### Vraag: Hoe identificeert en verwerkt de code afbeeldingsgerelateerde operators in een PDF-document?

A: De code herhaalt de operatoren op een opgegeven pagina van het PDF-document. Het identificeert en verwerkt operators die verband houden met beeldbewerkingen, transformaties en weergave.

#### Vraag: Wat is de betekenis van standaardresolutie en hoe wordt deze in de code gebruikt?

A: De standaardresolutie wordt gebruikt als referentiepunt om de werkelijke resolutie van afbeeldingen te berekenen. De code berekent de resolutie van elke afbeelding op basis van de afmetingen en de standaardresolutie-instelling.

#### Vraag: Hoe kan de geëxtraheerde beeldinformatie worden gebruikt in scenario's in de echte wereld?

A: De geëxtraheerde beeldinformatie kan worden gebruikt voor taken zoals beoordeling van de beeldkwaliteit, beeldoptimalisatie, het genereren van miniatuurafbeeldingen en het faciliteren van beeldgerelateerde besluitvormingsprocessen.

#### Vraag: Kan ik de code wijzigen om aanvullende afbeeldingsgerelateerde kenmerken te extraheren?

A: Ja, u kunt de code aanpassen om aanvullende kenmerken van afbeeldingen te extraheren, zoals kleurruimte, pixeldiepte of afbeeldingstype.

#### Vraag: Is het extractieproces van afbeeldingsinformatie arbeidsintensief of tijdrovend?

A: Het extractieproces voor beeldinformatie is efficiënt en geoptimaliseerd voor prestaties, waardoor een minimale impact op het gebruik van bronnen en verwerkingstijd wordt gegarandeerd.

#### Vraag: Hoe kunnen ontwikkelaars profiteren van het identificeren en extraheren van afbeeldingsinformatie uit PDF-documenten?

A: Ontwikkelaars kunnen inzicht krijgen in de kenmerken van afbeeldingen in PDF-documenten, waardoor ze weloverwogen beslissingen kunnen nemen met betrekking tot beeldmanipulatie, -verwerking en -optimalisatie.

#### Vraag: Kan deze methode worden gebruikt voor batchverwerking van PDF-documenten met afbeeldingen?

A: Ja, deze methode kan worden uitgebreid voor batchverwerking door meerdere pagina's of documenten te doorlopen, afbeeldingsinformatie te extraheren en afbeeldingsgerelateerde taken uit te voeren.