---
title: Verander oriëntatie
linktitle: Verander oriëntatie
second_title: Aspose.PDF voor .NET API-referentie
description: Stapsgewijze handleiding om de pagina-oriëntatie van een PDF te wijzigen met Aspose.PDF voor .NET. Gemakkelijk te volgen en te implementeren in uw projecten.
type: docs
weight: 10
url: /nl/net/programming-with-pdf-pages/change-orientation/
---
## Invoering

Heb je ooit moeite gehad met een PDF-bestand waarvan de pagina-oriëntatie gewoon... niet klopte? Misschien heb je te maken met een document dat verkeerd is gescand of gemaakt, en de pagina's moeten worden gedraaid om logisch te zijn. Gelukkig voor ons biedt Aspose.PDF voor .NET een eenvoudige, krachtige manier om PDF-bestanden op vrijwel elke denkbare manier te manipuleren, inclusief het wijzigen van de oriëntatie van je pagina's. Of je nu wilt overschakelen van staand naar liggend of andersom, deze gids leidt je stap voor stap door het proces.

Dus, als u er klaar voor bent om aan de slag te gaan en die PDF-pagina's eenvoudig te roteren, laten we dan beginnen!

## Vereisten

Voordat we dieper ingaan op het wijzigen van de pagina-oriëntatie in uw PDF, leggen we eerst kort uit wat u hiervoor nodig hebt:

-  Aspose.PDF voor .NET: Zorg ervoor dat u de Aspose.PDF-bibliotheek voor .NET hebt geïnstalleerd. Als u dat niet hebt gedaan, kunt u[download het hier](https://releases.aspose.com/pdf/net/).
- Een .NET-ontwikkelomgeving: u kunt Visual Studio, JetBrains Rider of een andere gewenste IDE gebruiken om met .NET te werken.
- Basiskennis van C#: Hoewel deze gids eenvoudig is, is het met enige basiskennis van C# nog makkelijker te volgen.
- Een PDF-bestand: In het onderstaande voorbeeld wordt ervan uitgegaan dat u een PDF-bestand met meerdere pagina's hebt. Als u er geen bij de hand hebt, kunt u een voorbeeld-PDF maken of downloaden om mee te werken.

 Als u nog maar net begint, kunt u Aspose.PDF ook proberen met een[gratis tijdelijke licentie](https://purchase.aspose.com/temporary-license/) voordat u besluit om[koop de volledige versie](https://purchase.aspose.com/buy).

## Naamruimten importeren

Voordat u de oriëntatie van pagina's in uw PDF kunt manipuleren, moet u de benodigde naamruimten importeren in uw C#-project. Zorg ervoor dat u het volgende hebt:

```csharp
using System.IO;
using Aspose.Pdf;
```

Nu we dit hebben geïmporteerd, kunnen we verder met het hoofdonderdeel van de tutorial.

## Stap 1: Laad het PDF-document

 Het eerste wat we moeten doen is het PDF-bestand laden dat u wilt wijzigen. U kunt de`Document` klasse uit de Aspose.PDF-naamruimte om uw PDF te openen.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "input.pdf");
```

 Deze regel laadt de PDF uit uw opgegeven directory. Zorg ervoor dat u vervangt`"YOUR DOCUMENT DIRECTORY"` met het werkelijke pad naar uw bestand. De`"input.pdf"` is de PDF waarvan u de oriëntatie wilt wijzigen.

## Stap 2: Loop door elke pagina

 Nu we het document hebben geladen, gaan we door elke pagina in de PDF heen. We gebruiken een`foreach` doorloop elke pagina, zodat we de oriëntatiewijziging op alle pagina's kunnen toepassen.

```csharp
foreach (Page page in doc.Pages)
{
    // Manipuleer elke pagina
}
```

Deze lus doorloopt alle pagina's in het document.

## Stap 3: Haal de MediaBox van de pagina op

 Elke pagina in een PDF heeft een`MediaBox` die de grenzen van de pagina definieert. We moeten hier toegang toe hebben om de huidige oriëntatie te bepalen en deze te wijzigen.

```csharp
Aspose.Pdf.Rectangle r = page.MediaBox;
```

 De`MediaBox` geeft ons de afmetingen van de pagina, zoals de breedte, hoogte en positionering.

## Stap 4: Wissel de breedte en hoogte om

Om de pagina-oriëntatie te veranderen van staand naar liggend of van liggend naar staand, wisselen we simpelweg de breedte- en hoogtewaarden om. Deze stap past de afmetingen van de pagina aan.

```csharp
double newHeight = r.Width;
double newWidth = r.Height;
double newLLX = r.LLX;
double newLLY = r.LLY + (r.Height - newHeight);
```

Deze code verwisselt de hoogte en breedte en verplaatst de linkerbenedenhoek (`LLY`) zodat de inhoud na rotatie netjes blijft passen.

## Stap 5: MediaBox en CropBox updaten

Nu we de nieuwe hoogte en breedte hebben, kunnen we de wijzigingen toepassen op de pagina.`MediaBox` En`CropBox` . De`CropBox` is essentieel als het originele document één set had, zodat de hele pagina correct wordt weergegeven.

```csharp
page.MediaBox = new Aspose.Pdf.Rectangle(newLLX, newLLY, newLLX + newWidth, newLLY + newHeight);
page.CropBox = new Aspose.Pdf.Rectangle(newLLX, newLLY, newLLX + newWidth, newLLY + newHeight);
```

Met deze stap wordt de pagina aangepast op basis van de nieuwe afmetingen die we zojuist hebben berekend.

## Stap 6: Draai de pagina

Tot slot stellen we de rotatiehoek van de pagina in. Aspose.PDF maakt dit supersimpel. We kunnen de pagina 90 graden draaien om van portret naar landschap te gaan of andersom.

```csharp
page.Rotate = Rotation.on90;
```

Met deze code wordt de pagina 90 graden gedraaid, waardoor deze in de gewenste stand komt.

## Stap 7: Sla de uitvoer-PDF op

Nadat we de gewijzigde oriëntatie op alle pagina's hebben toegepast, slaan we het gewijzigde document op in een nieuw bestand. 

```csharp
dataDir = dataDir + "ChangeOrientation_out.pdf";
doc.Save(dataDir);
System.Console.WriteLine("\nPage orientation changed successfully.\nFile saved at " + dataDir);
```

 Zorg ervoor dat u een nieuwe bestandsnaam opgeeft (in dit geval`ChangeOrientation_out.pdf`) om de uitvoer op te slaan. Op deze manier overschrijf je je originele bestand niet.

### Conclusie

En daar heb je het! Het wijzigen van de pagina-oriëntatie van een PDF-bestand met Aspose.PDF voor .NET is net zo eenvoudig als het laden van het document, het doorlopen van de pagina's, het aanpassen van de MediaBox en het opslaan van het bijgewerkte bestand. Of je nu te maken hebt met een slecht gescand document of pagina's moet roteren om ze aan te passen aan je opmaakbehoeften, deze stapsgewijze handleiding zou je moeten helpen.

## Veelgestelde vragen

### Kan ik specifieke pagina's roteren in plaats van alle pagina's in de PDF?  
Ja, u kunt de lus aanpassen om specifieke pagina's te targeten met behulp van hun index in plaats van door alle pagina's te lussen.

###  Wat is de`MediaBox`?  
 De`MediaBox` definieert de grootte en vorm van de pagina in een PDF-bestand. Het is waar de inhoud van de pagina wordt geplaatst.

### Werkt Aspose.PDF voor .NET met andere bestandsformaten?  
Ja, Aspose.PDF kan verschillende bestandsformaten verwerken, zoals HTML, XML, XPS en meer.

### Bestaat er een gratis versie van Aspose.PDF voor .NET?  
 Ja, u kunt beginnen met een[gratis proefperiode](https://releases.aspose.com/) of vraag een[tijdelijke licentie](https://purchase.aspose.com/temporary-license/).

### Kan ik de wijzigingen ongedaan maken nadat ik ze heb opgeslagen?  
Zodra u het document opslaat, zijn de wijzigingen permanent. Zorg ervoor dat u aan een kopie werkt of een back-up van het originele bestand bewaart.