---
title: Afbeeldingsplaatsingen
linktitle: Afbeeldingsplaatsingen
second_title: Aspose.PDF voor .NET API-referentie
description: Leer hoe u afbeeldingsplaatsingen in PDF-documenten kunt extraheren en manipuleren met Aspose.PDF voor .NET. Stapsgewijze handleiding met voorbeelden en codefragmenten.
type: docs
weight: 170
url: /nl/net/programming-with-images/image-placements/
---
## Invoering

Werken met afbeeldingen in PDF-bestanden kan lastig zijn, maar met Aspose.PDF voor .NET kunt u eenvoudig afbeeldingseigenschappen manipuleren en extraheren zonder dat u zich in het zweet hoeft te werken. Of u nu de afmetingen van afbeeldingen wilt ophalen, ze wilt extraheren of andere eigenschappen wilt ophalen, zoals resolutie, Aspose.PDF heeft de tools die u nodig hebt. Deze tutorial leidt u door een stapsgewijze handleiding over het extraheren van afbeeldingsplaatsingen in een PDF-document met Aspose.PDF voor .NET. We behandelen alles, van het importeren van pakketten tot het ophalen van afbeeldingseigenschappen, zoals breedte, hoogte en resolutie.

## Vereisten

Voordat we beginnen met de tutorial, zijn er een paar dingen die je op orde moet hebben. Hier is een snelle checklist:

1.  Aspose.PDF voor .NET: Zorg ervoor dat u de Aspose.PDF voor .NET-bibliotheek hebt geïnstalleerd. U kunt deze downloaden[hier](https://releases.aspose.com/pdf/net/).
2. Ontwikkelomgeving: Visual Studio of een andere .NET-ondersteunde IDE moet op uw computer geïnstalleerd zijn.
3. Een PDF-document: Zorg dat u een voorbeeld-PDF-document bij de hand hebt dat afbeeldingen bevat. Voor dit voorbeeld gebruiken we een bestand met de naam`ImagePlacement.pdf`.
4. Basiskennis van C#: Hoewel deze gids geschikt is voor beginners, kunt u met basiskennis van C# de codefragmenten beter begrijpen.

## Pakketten importeren

Voordat we in de details van de code duiken, moet u eerst de benodigde namespaces importeren. Deze pakketten zijn cruciaal voor het werken met PDF-documenten en beeldmanipulatie in Aspose.PDF voor .NET.

```csharp
using System.IO;
using Aspose.Pdf;
using System;
using System.Drawing;
```

Met deze pakketten kunt u met PDF's werken (`Aspose.Pdf`), afbeeldingsplaatsingen manipuleren (`Aspose.Pdf.ImagePlacement`), en verwerken beeldstromen en afbeeldingen (`System.Drawing` En`System.IO`).

Nu we de vereisten en pakketten op orde hebben, kunnen we elk onderdeel van de tutorial opsplitsen in een eenvoudige, gemakkelijk te volgen handleiding.

## Stap 1: Laad het PDF-document

De eerste stap is het laden van het PDF-document in uw project. Dit is de basis voor het werken met afbeeldingen in het PDF-bestand.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY"; 
Aspose.Pdf.Document doc = new Aspose.Pdf.Document(dataDir + "ImagePlacement.pdf");
```

 In deze stap definiëren we het bestandspad van het PDF-document met behulp van`dataDir`en vervolgens een nieuw exemplaar van de`Aspose.Pdf.Document` klasse. Hiermee kunnen we het PDF-bestand in ons programma laden. Simpel, toch? Net als bij het openen van een boek om te beginnen met lezen, zijn we nu klaar om de inhoud ervan te verkennen.

## Stap 2: Initialiseer de Image Placement Absorber

Om de afbeeldingen te extraheren, hebben we iets nodig dat een 'Image Placement Absorber' heet. Je kunt het zien als een hulpmiddel dat alle beeldinformatie op een bepaalde pagina absorbeert.

```csharp
ImagePlacementAbsorber abs = new ImagePlacementAbsorber();
```

 Hier maken we een instantie van`ImagePlacementAbsorber`. Dit object verzamelt en slaat informatie op over alle afbeeldingsplaatsingen op een specifieke PDF-pagina. Stel je voor dat je een pagina scant met een vergrootglas en alle afbeeldingen erop identificeert!

## Stap 3: Accepteer de Absorber op de eerste pagina

Vervolgens moeten we de absorber vertellen welke pagina van de PDF gescand moet worden. Voor dit voorbeeld richten we ons op de eerste pagina.

```csharp
doc.Pages[1].Accept(abs);
```

 De`Accept` methode scant de eerste pagina van het PDF-document op afbeeldingen en slaat de resultaten op in de`ImagePlacementAbsorber`Het is alsof je het vergrootglas vertelt waar het naar afbeeldingen moet zoeken.

## Stap 4: Loop door elke afbeeldingsplaatsing

Nu we de pagina hebben gescand, moeten we alle afbeeldingen op de pagina doorlopen en de eigenschappen ervan ophalen.

```csharp
foreach (ImagePlacement imagePlacement in abs.ImagePlacements)
{
    Console.Out.WriteLine("image width:" + imagePlacement.Rectangle.Width);
    Console.Out.WriteLine("image height:" + imagePlacement.Rectangle.Height);
    Console.Out.WriteLine("image LLX:" + imagePlacement.Rectangle.LLX);
    Console.Out.WriteLine("image LLY:" + imagePlacement.Rectangle.LLY);
    Console.Out.WriteLine("image horizontal resolution:" + imagePlacement.Resolution.X);
    Console.Out.WriteLine("image vertical resolution:" + imagePlacement.Resolution.Y);
}
```

Deze lus gaat door elke afbeelding op de pagina. We printen de breedte, hoogte, linkerbenedenhoek x (LLX), linkerbenedenhoek y (LLY) en de resolutie van de afbeelding (zowel horizontaal als verticaal). Deze details helpen u de grootte en positionering van elke afbeelding in de PDF te begrijpen.

## Stap 5: Extraheer de afbeelding met zichtbare afmetingen

Nadat u informatie over de afbeeldingen hebt verzameld, wilt u misschien de daadwerkelijke afbeelding met zijn afmetingen extraheren. Hier leest u hoe u dat kunt doen.

```csharp
Bitmap scaledImage;
using (MemoryStream imageStream = new MemoryStream())
{
    imagePlacement.Image.Save(imageStream, System.Drawing.Imaging.ImageFormat.Png);
    Bitmap resourceImage = (Bitmap)Bitmap.FromStream(imageStream);
    scaledImage = new Bitmap(resourceImage, (int)imagePlacement.Rectangle.Width, (int)imagePlacement.Rectangle.Height);
}
```

 Dit codefragment haalt de afbeelding op uit de PDF en schaalt deze naar de werkelijke afmetingen zoals gedefinieerd in de`ImagePlacement` object. Door de afbeelding op te slaan in een geheugenstroom en deze te schalen, zorgt u ervoor dat de afbeelding die u extraheert, exact dezelfde grootte behoudt als waarop deze in de PDF werd weergegeven.

## Conclusie

Het extraheren van afbeeldingsplaatsingen uit een PDF-document met Aspose.PDF voor .NET is vrij eenvoudig als u het stap voor stap uitlegt. We hebben alles behandeld, van het laden van een PDF tot het ophalen van afbeeldingseigenschappen en het extraheren van afbeeldingen met hun werkelijke afmetingen. Aspose.PDF maakt het werken met PDF's en het manipuleren van inhoud ongelooflijk eenvoudig, zodat u efficiënt kunt werken met afbeeldingen, tekst en nog veel meer.

## Veelgestelde vragen

### Kan ik afbeeldingen van een specifieke pagina uit de PDF halen?  
 Ja, door het opgeven van het paginanummer bij gebruik van de`Accept` Met deze methode kunt u zich op een specifieke pagina concentreren.

### Welke afbeeldingsformaten worden ondersteund voor extractie?  
Aspose.PDF ondersteunt verschillende formaten, waaronder PNG, JPEG, BMP en meer.

### Is het mogelijk om de geëxtraheerde afbeelding te manipuleren?  
 Absoluut! Zodra het is geëxtraheerd, kunt u de`System.Drawing` naamruimte om de afbeelding te manipuleren.

### Kan ik afbeeldingen uit wachtwoordbeveiligde PDF's halen?  
Ja, dat kan, maar u moet de PDF wel ontgrendelen met de juiste inloggegevens voordat u de afbeeldingen kunt extraheren.

### Werkt Aspose.PDF voor .NET op alle .NET-frameworks?  
Ja, het ondersteunt .NET Framework, .NET Core en .NET 5 en hoger.