---
title: Afbeeldingsplaatsingen
linktitle: Afbeeldingsplaatsingen
second_title: Aspose.PDF voor .NET API-referentie
description: Leer hoe u Aspose.PDF voor .NET gebruikt om afbeeldingen in een PDF-document te plaatsen.
type: docs
weight: 170
url: /nl/net/programming-with-images/image-placements/
---
In deze zelfstudie gebruiken we de Aspose.PDF-bibliotheek voor .NET om met PDF-documenten te werken en bewerkingen op afbeeldingen uit te voeren. We laden een PDF-document, extraheren de informatie over de plaatsing van de afbeelding en halen de afbeeldingen op met zichtbare afmetingen.

## Stap 1: De omgeving instellen
Zorg ervoor dat u, voordat u begint, uw ontwikkelomgeving hebt ingesteld met het volgende:
- Aspose.PDF voor .NET geïnstalleerd op uw computer.
- AC#-project klaar voor gebruik.

## Stap 2: Het PDF-document laden
Om te beginnen moeten we het PDF-document laden dat we willen verwerken. Zorg ervoor dat u het juiste pad naar de map met het PDF-document heeft.

```csharp
// Het pad naar de documentenmap.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
// Laad het bron-PDF-document
Aspose.Pdf.Document doc = new Aspose.Pdf.Document(dataDir + "PlacementImage.pdf");
```

 Zeker vervangen`"YOUR DOCUMENTS DIRECTORY"` met het daadwerkelijke pad naar uw documentenmap die het PDF-bestand bevat.

## Stap 3: Haal plaatsingsinformatie uit afbeeldingen
 Nu we het PDF-document hebben geladen, kunnen we de plaatsingsinformatie uit de afbeeldingen halen. We zullen gebruiken`ImagePlacementAbsorber`om afbeeldingslocaties van de eerste pagina van het document te absorberen.

```csharp
ImagePlacementAbsorber abs = new ImagePlacementAbsorber();
// Laad de inhoud van de eerste pagina
doc.Pages[1].Accept(abs);
```

We hebben nu de informatie over de plaatsing van de afbeelding uit de eerste pagina van het document gehaald.

## Stap 4: Afbeeldingen met zichtbare afmetingen ophalen
Nu halen we de afbeeldingen met hun zichtbare afmetingen op uit de plaatsingsinformatie die we eerder hebben geëxtraheerd.

```csharp
foreach(ImagePlacement imagePlacement in abs.ImagePlacements)
{
     // Afbeeldingseigenschappen ophalen
     Console.Out.WriteLine("Image Width: " + imagePlacement.Rectangle.Width);
     Console.Out.WriteLine("Image Height: " + imagePlacement.Rectangle.Height);
     Console.Out.WriteLine("LLX of image: " + imagePlacement.Rectangle.LLX);
     Console.Out.WriteLine("LLY of image: " + imagePlacement.Rectangle.LLY);
     Console.Out.WriteLine("Horizontal resolution of the image

  : " + imagePlacement.Resolution.X);
     Console.Out.WriteLine("Vertical image resolution: " + imagePlacement.Resolution.Y);

     // Haal de afbeelding op met zichtbare afmetingen
     Bitmap scaledImage;
     using (MemoryStream imageStream = new MemoryStream())
     {
         // Haal de afbeelding uit de bronnen
         imagePlacement.Image.Save(imageStream, System.Drawing.Imaging.ImageFormat.Png);
         Bitmap resourceImage = (Bitmap)Bitmap.FromStream(imageStream);

         // Maak een afbeelding met werkelijke afmetingen
         scaledImage = new Bitmap(resourceImage, (int)imagePlacement.Rectangle.Width, (int)imagePlacement.Rectangle.Height);
     }
}
```

In deze lus halen we de eigenschappen van elke afbeelding op, zoals breedte, hoogte, X- en Y-coördinaten van de linkerbenedenhoek en horizontale en verticale resolutie. Vervolgens halen we elke afbeelding met de zichtbare afmetingen op met behulp van de plaatsingsinformatie.

### Voorbeeldbroncode voor afbeeldingsplaatsingen met Aspose.PDF voor .NET 
```csharp
// Het pad naar de documentenmap.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Laad het bron-PDF-document
Aspose.Pdf.Document doc = new Aspose.Pdf.Document(dataDir+ "ImagePlacement.pdf");
ImagePlacementAbsorber abs = new ImagePlacementAbsorber();
// Laad de inhoud van de eerste pagina
doc.Pages[1].Accept(abs);
foreach (ImagePlacement imagePlacement in abs.ImagePlacements)
{
	// Afbeeldingseigenschappen ophalen
	Console.Out.WriteLine("image width:" + imagePlacement.Rectangle.Width);
	Console.Out.WriteLine("image height:" + imagePlacement.Rectangle.Height);
	Console.Out.WriteLine("image LLX:" + imagePlacement.Rectangle.LLX);
	Console.Out.WriteLine("image LLY:" + imagePlacement.Rectangle.LLY);
	Console.Out.WriteLine("image horizontal resolution:" + imagePlacement.Resolution.X);
	Console.Out.WriteLine("image vertical resolution:" + imagePlacement.Resolution.Y);
	// Haal een afbeelding op met zichtbare afmetingen
	Bitmap scaledImage;
	using (MemoryStream imageStream = new MemoryStream())
	{
		// Haal afbeelding op uit bronnen
		imagePlacement.Image.Save(imageStream, System.Drawing.Imaging.ImageFormat.Png);
		Bitmap resourceImage = (Bitmap)Bitmap.FromStream(imageStream);
		//Maak een bitmap met werkelijke afmetingen
		scaledImage = new Bitmap(resourceImage, (int)imagePlacement.Rectangle.Width, (int)imagePlacement.Rectangle.Height);
	}
}
```

## Conclusie
Gefeliciteerd! U hebt nu geleerd hoe u Aspose.PDF voor .NET kunt gebruiken om afbeeldingsplaatsingen in een PDF-document uit te voeren. We hebben de meegeleverde C#-broncode uitgelegd, waarmee u een PDF-document kunt laden, de plaatsingsinformatie uit de afbeeldingen kunt extraheren en de afbeeldingen kunt ophalen met hun zichtbare afmetingen. Voel je vrij om meer te experimenteren met Aspose.PDF om de vele andere functies ervan te ontdekken.

### Veelgestelde vragen

#### Vraag: Wat is het doel van het extraheren van informatie over de plaatsing van afbeeldingen uit een PDF-document met Aspose.PDF voor .NET?

A: Door informatie over de plaatsing van afbeeldingen te extraheren, kunt u de positionering, afmetingen en resolutie van afbeeldingen in een PDF-document ophalen. Deze informatie is essentieel voor nauwkeurige beeldmanipulatie en -analyse.

#### Vraag: Hoe vergemakkelijkt Aspose.PDF voor .NET de extractie van informatie over de plaatsing van afbeeldingen uit een PDF-document?

 A: Aspose.PDF voor .NET biedt de`ImagePlacementAbsorber`klasse, die kan worden gebruikt om details over de plaatsing van afbeeldingen uit een PDF-document te absorberen. De meegeleverde code laat zien hoe u deze klasse kunt gebruiken om informatie over de plaatsing van afbeeldingen op te halen.

#### Vraag: Waarvoor kan informatie over de plaatsing van afbeeldingen worden gebruikt in realistische scenario's?

A: Informatie over de plaatsing van afbeeldingen is waardevol voor taken zoals het zorgen voor een nauwkeurige uitlijning van afbeeldingen, het berekenen van afbeeldingsafmetingen, het verifiëren van de afbeeldingskwaliteit en het genereren van rapporten over afbeeldingsgebruik in een PDF-document.

#### Vraag: Hoe zorgt het codevoorbeeld voor een nauwkeurige extractie van informatie over de plaatsing van afbeeldingen?

 A: Het codevoorbeeld maakt gebruik van de`ImagePlacementAbsorber` class om de inhoud van een opgegeven pagina te doorkruisen, de plaatsing van afbeeldingen te identificeren en hun attributen op te halen, zoals breedte, hoogte, coördinaten en resolutie.

#### Vraag: Kan de code worden uitgebreid om afbeeldingen over meerdere pagina's of documenten te verwerken?

A: Ja, de code kan worden uitgebreid door meerdere pagina's of documenten te doorlopen om informatie over de plaatsing van afbeeldingen te extraheren en afbeeldingsgerelateerde taken uit te voeren.

#### Vraag: Hoe haalt de code afbeeldingen op met hun zichtbare afmetingen op basis van de plaatsingsinformatie?

A: Het codevoorbeeld haalt de afbeeldingsgegevens uit de bronnen, creëert een bitmapafbeelding met de werkelijke afmetingen en biedt eigenschappen zoals breedte, hoogte, coördinaten en resolutie.

#### Vraag: Is deze aanpak efficiënt voor grote PDF-documenten die veel afbeeldingen bevatten?

A: Ja, Aspose.PDF voor .NET is geoptimaliseerd voor prestaties en bronnengebruik. Het haalt op efficiënte wijze informatie over de plaatsing van afbeeldingen op, zelfs uit grote PDF-documenten.

#### Vraag: Hoe kunnen ontwikkelaars profiteren van het begrijpen en gebruiken van informatie over de plaatsing van afbeeldingen?

A: Ontwikkelaars kunnen zorgen voor nauwkeurige beeldmanipulatie, uitlijning en analyse binnen PDF-documenten. Met deze informatie kunnen ze toepassingen maken voor beeldverwerking, rapportage en kwaliteitsborging.

#### Vraag: Kan de code worden aangepast om aanvullende afbeeldingsgerelateerde attributen of metagegevens te extraheren?

A: Absoluut, de code kan worden verbeterd om extra attributen te extraheren, zoals afbeeldingstype, kleurruimte, compressie en meer, door gebruik te maken van de juiste klassen en methoden die worden aangeboden door Aspose.PDF voor .NET.

#### Vraag: Wat is de betekenis van de conclusie in deze tutorial?

A: De conclusie vat de inhoud van de tutorial samen en moedigt verdere verkenning van Aspose.PDF voor .NET aan om de mogelijkheden ervan te benutten die verder gaan dan het plaatsen van afbeeldingen, waardoor deuren worden geopend voor verschillende PDF-gerelateerde taken.