---
title: Afbeeldingsplaatsingen
linktitle: Afbeeldingsplaatsingen
second_title: Aspose.PDF voor .NET API-referentie
description: Leer hoe u Aspose.PDF voor .NET gebruikt om afbeeldingen in een PDF-document te plaatsen.
type: docs
weight: 170
url: /nl/net/programming-with-images/image-placements/
---
In deze tutorial gebruiken we de Aspose.PDF-bibliotheek voor .NET om met PDF-documenten te werken en bewerkingen op afbeeldingen uit te voeren. We laden een PDF-document, extraheren de plaatsingsinformatie van de afbeelding en halen de afbeeldingen op met hun zichtbare afmetingen.

## Stap 1: De omgeving instellen
Voordat u begint, moet u ervoor zorgen dat uw ontwikkelomgeving is ingesteld met het volgende:
- Aspose.PDF voor .NET op uw computer geïnstalleerd.
- AC#-project klaar voor gebruik.

## Stap 2: Het PDF-document laden
Om te beginnen moeten we het PDF-document laden dat we willen verwerken. Zorg ervoor dat u het juiste pad naar de directory met het PDF-document hebt.

```csharp
// Het pad naar de documentenmap.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
// Laad het bron-PDF-document
Aspose.Pdf.Document doc = new Aspose.Pdf.Document(dataDir + "PlacementImage.pdf");
```

 Zorg ervoor dat u deze vervangt`"YOUR DOCUMENTS DIRECTORY"` met het werkelijke pad naar de documentenmap waarin het PDF-bestand zich bevindt.

## Stap 3: Plaatsingsinformatie uit afbeeldingen halen
 Nu we het PDF-document hebben geladen, kunnen we de plaatsingsinformatie uit de afbeeldingen halen. We zullen`ImagePlacementAbsorber`om de locaties van afbeeldingen van de eerste pagina van het document over te nemen.

```csharp
ImagePlacementAbsorber abs = new ImagePlacementAbsorber();
// Laad de inhoud van de eerste pagina
doc.Pages[1].Accept(abs);
```

We hebben nu de informatie over de plaatsing van de afbeeldingen van de eerste pagina van het document gehaald.

## Stap 4: Afbeeldingen ophalen met zichtbare afmetingen
Nu gaan we de afbeeldingen met hun zichtbare afmetingen ophalen uit de plaatsingsinformatie die we eerder hebben geëxtraheerd.

```csharp
foreach(ImagePlacement imagePlacement in abs.ImagePlacements)
{
     // Eigenschappen van afbeelding ophalen
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

In deze lus halen we de eigenschappen van elke afbeelding op, zoals breedte, hoogte, X- en Y-coördinaten van de linkerbenedenhoek en horizontale en verticale resolutie. Vervolgens halen we elke afbeelding op met zijn zichtbare afmetingen met behulp van de plaatsingsinformatie.

### Voorbeeldbroncode voor afbeeldingsplaatsingen met behulp van Aspose.PDF voor .NET 
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
	// Eigenschappen van afbeelding ophalen
	Console.Out.WriteLine("image width:" + imagePlacement.Rectangle.Width);
	Console.Out.WriteLine("image height:" + imagePlacement.Rectangle.Height);
	Console.Out.WriteLine("image LLX:" + imagePlacement.Rectangle.LLX);
	Console.Out.WriteLine("image LLY:" + imagePlacement.Rectangle.LLY);
	Console.Out.WriteLine("image horizontal resolution:" + imagePlacement.Resolution.X);
	Console.Out.WriteLine("image vertical resolution:" + imagePlacement.Resolution.Y);
	// Afbeelding ophalen met zichtbare afmetingen
	Bitmap scaledImage;
	using (MemoryStream imageStream = new MemoryStream())
	{
		// Afbeelding ophalen uit bronnen
		imagePlacement.Image.Save(imageStream, System.Drawing.Imaging.ImageFormat.Png);
		Bitmap resourceImage = (Bitmap)Bitmap.FromStream(imageStream);
		//Maak een bitmap met werkelijke afmetingen
		scaledImage = new Bitmap(resourceImage, (int)imagePlacement.Rectangle.Width, (int)imagePlacement.Rectangle.Height);
	}
}
```

## Conclusie
Gefeliciteerd! U hebt nu geleerd hoe u Aspose.PDF voor .NET kunt gebruiken om afbeeldingen in een PDF-document te plaatsen. We hebben de meegeleverde C#-broncode uitgelegd, waarmee u een PDF-document kunt laden, de plaatsingsinformatie uit de afbeeldingen kunt halen en de afbeeldingen met zichtbare afmetingen kunt ophalen. Experimenteer gerust verder met Aspose.PDF om de vele andere functies te verkennen.

### Veelgestelde vragen

#### V: Wat is het doel van het extraheren van informatie over de plaatsing van afbeeldingen uit een PDF-document met Aspose.PDF voor .NET?

A: Door informatie over de plaatsing van afbeeldingen te extraheren, kunt u de positionering, afmetingen en resolutie van afbeeldingen in een PDF-document ophalen. Deze informatie is essentieel voor nauwkeurige beeldmanipulatie en -analyse.

#### V: Hoe vergemakkelijkt Aspose.PDF voor .NET het extraheren van informatie over de plaatsing van afbeeldingen uit een PDF-document?

 A: Aspose.PDF voor .NET biedt de`ImagePlacementAbsorber`klasse, die kan worden gebruikt om details over de plaatsing van afbeeldingen uit een PDF-document te absorberen. De meegeleverde code laat zien hoe u deze klasse kunt gebruiken om informatie over de plaatsing van afbeeldingen op te halen.

#### V: Waarvoor kan informatie over de plaatsing van afbeeldingen in realistische situaties worden gebruikt?

A: Informatie over de plaatsing van afbeeldingen is waardevol voor taken zoals het nauwkeurig uitlijnen van afbeeldingen, het berekenen van de afmetingen van afbeeldingen, het controleren van de beeldkwaliteit en het genereren van rapporten over het gebruik van afbeeldingen in een PDF-document.

#### V: Hoe zorgt het codevoorbeeld ervoor dat de informatie over de plaatsing van afbeeldingen nauwkeurig wordt geëxtraheerd?

 A: Het codevoorbeeld maakt gebruik van de`ImagePlacementAbsorber` klasse om de inhoud van een opgegeven pagina te doorlopen, de plaatsing van afbeeldingen te identificeren en hun kenmerken op te halen, zoals breedte, hoogte, coördinaten en resolutie.

#### V: Kan de code worden uitgebreid om afbeeldingen op meerdere pagina's of documenten te verwerken?

A: Ja, de code kan worden uitgebreid door meerdere pagina's of documenten te doorlopen om informatie over de plaatsing van afbeeldingen te extraheren en taken met betrekking tot afbeeldingen uit te voeren.

#### V: Hoe haalt de code afbeeldingen op met hun zichtbare afmetingen op basis van de plaatsingsinformatie?

A: Het codevoorbeeld haalt de afbeeldingsgegevens uit de bronnen, maakt een bitmapafbeelding met de werkelijke afmetingen en geeft eigenschappen zoals breedte, hoogte, coördinaten en resolutie.

#### V: Is deze aanpak efficiënt voor grote PDF-documenten met veel afbeeldingen?

A: Ja, Aspose.PDF voor .NET is geoptimaliseerd voor prestaties en resourcegebruik. Het extraheert efficiënt informatie over de plaatsing van afbeeldingen, zelfs uit grote PDF-documenten.

#### V: Hoe kunnen ontwikkelaars profiteren van het begrijpen en gebruiken van informatie over de plaatsing van afbeeldingen?

A: Ontwikkelaars kunnen nauwkeurige beeldmanipulatie, uitlijning en analyse binnen PDF-documenten garanderen. Deze informatie stelt hen in staat om applicaties te maken voor beeldverwerking, rapportage en kwaliteitsborging.

#### V: Kan de code worden aangepast om extra afbeeldingsgerelateerde kenmerken of metagegevens te extraheren?

A: Absoluut, de code kan worden uitgebreid om extra kenmerken te extraheren, zoals afbeeldingstype, kleurruimte, compressie en meer, door gebruik te maken van de juiste klassen en methoden die worden aangeboden door Aspose.PDF voor .NET.

#### V: Wat is de betekenis van de conclusie in deze tutorial?

A: De conclusie vat de inhoud van de tutorial samen en moedigt aan tot verdere verkenning van Aspose.PDF voor .NET om de mogelijkheden ervan verder te benutten dan alleen het plaatsen van afbeeldingen, waardoor verschillende PDF-gerelateerde taken mogelijk worden.