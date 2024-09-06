---
title: Tekststempel toevoegen in PDF-bestand
linktitle: Tekststempel toevoegen in PDF-bestand
second_title: Aspose.PDF voor .NET API-referentie
description: Leer hoe u eenvoudig een tekststempel aan een PDF-bestand kunt toevoegen met Aspose.PDF voor .NET.
type: docs
weight: 50
url: /nl/net/programming-with-stamps-and-watermarks/add-text-stamp/
---
In deze tutorial laten we u stap voor stap zien hoe u een tekststempel toevoegt aan een PDF-bestand met Aspose.PDF voor .NET. We laten u zien hoe u de meegeleverde C#-broncode gebruikt om een aangepaste tekststempel toe te voegen aan een specifieke pagina van het PDF-bestand.

## Stap 1: De omgeving instellen

Voordat u begint, moet u ervoor zorgen dat u het volgende bij de hand hebt:

- Een geïnstalleerde .NET-ontwikkelomgeving.
- De Aspose.PDF-bibliotheek voor .NET is gedownload en wordt in uw project gebruikt.

## Stap 2: Het PDF-document laden

De eerste stap is om het bestaande PDF-document in uw project te laden. Dit doet u als volgt:

```csharp
// Het pad naar de documentenmap.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Open het document
Document pdfDocument = new Document(dataDir + "AddTextStamp.pdf");
```

Zorg ervoor dat u "UW DOCUMENTENMAP" vervangt door het daadwerkelijke pad naar de map waarin uw PDF-document zich bevindt.

## Stap 3: De tekstbuffer maken

Nu u het PDF-document hebt geüpload, kunt u de tekststempel maken die u wilt toevoegen. Dit is hoe u dat doet:

```csharp
// Maak de tekstbuffer
TextStamp textStamp = new TextStamp("Example Stamp");
```

De bovenstaande code maakt een nieuwe tekstbuffer aan die de opgegeven tekst bevat.

## Stap 4: Tekststempeleigenschappen configureren

Voordat u de tekststempel aan het PDF-document toevoegt, kunt u verschillende eigenschappen van de stempel configureren, zoals achtergrond, positie, rotatie, lettertype, grootte, enz. Dit doet u als volgt:

```csharp
// Eigenschappen van tekstbuffer configureren
textStamp. Background = true;
textStamp. XIndent = 100;
textStamp. YIndent = 100;
textStamp.Rotate = Rotate.on90;
textStamp.TextState.Font = FontRepository.FindFont("Arial");
textStamp.TextState.FontSize = 14.0F;
textStamp.TextState.FontStyle = FontStyles.Bold | FontStyles.Italic;
textStamp.TextState.ForegroundColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Aqua);
```

U kunt deze eigenschappen naar wens aanpassen.

## Stap 5: Tekststempel toevoegen aan PDF

Nu de tekststempel klaar is, kunt u deze toevoegen aan een specifieke pagina van het PDF-document. Dit doet u als volgt:

```csharp
//Voeg tekstbuffer toe aan specifieke pagina
pdfDocument.Pages[1].AddStamp(textStamp);
```

De bovenstaande code voegt de tekststempel toe aan de eerste pagina van het PDF-document. U kunt indien nodig een andere pagina opgeven.

## Stap 6: Sla het uitvoerdocument op

Zodra u de tekststempel hebt toegevoegd, kunt u het bewerkte PDF-document opslaan. Dit doet u als volgt:

```csharp
// Sla het uitvoerdocument op
pdfDocument.Save(dataDir);
```

De bovenstaande code slaat het gewijzigde PDF-document op in de opgegeven map.

### Voorbeeldbroncode voor Add Text Stamp met behulp van Aspose.PDF voor .NET 
```csharp

// Het pad naar de documentenmap.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Document openen
Document pdfDocument = new Document(dataDir+ "AddTextStamp.pdf");

// Tekststempel maken
TextStamp textStamp = new TextStamp("Sample Stamp");

// Instellen of stempel achtergrond is
textStamp.Background = true;

// Oorsprong instellen
textStamp.XIndent = 100;
textStamp.YIndent = 100;

// Draai stempel
textStamp.Rotate = Rotation.on90;

// Teksteigenschappen instellen
textStamp.TextState.Font = FontRepository.FindFont("Arial");
textStamp.TextState.FontSize = 14.0F;
textStamp.TextState.FontStyle = FontStyles.Bold;
textStamp.TextState.FontStyle = FontStyles.Italic;
textStamp.TextState.ForegroundColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Aqua);

// Voeg stempel toe aan specifieke pagina
pdfDocument.Pages[1].AddStamp(textStamp);
dataDir = dataDir + "AddTextStamp_out.pdf";

// Uitvoerdocument opslaan
pdfDocument.Save(dataDir);
Console.WriteLine("\nText stamp added successfully.\nFile saved at " + dataDir);            

```

## Conclusie

Gefeliciteerd! U hebt geleerd hoe u een tekststempel kunt toevoegen met Aspose.PDF voor .NET. Nu kunt u deze kennis toepassen op uw eigen projecten om aangepaste tekststempels toe te voegen aan PDF-documenten.

### FAQ's voor het toevoegen van een tekststempel in een PDF-bestand

#### V: Wat is het doel van het toevoegen van een tekststempel aan een PDF-bestand met Aspose.PDF voor .NET?

A: Door een tekststempel toe te voegen, kunt u aangepaste tekst op een specifieke pagina van een PDF-document plaatsen. Deze functie is handig voor het toevoegen van labels, opmerkingen, watermerken of andere tekstuele informatie om de inhoud van het document te verbeteren en extra context te bieden.

#### V: Kan ik het uiterlijk van de tekststempel aanpassen, zoals lettertype, grootte, kleur en rotatie?

 A: Ja, u kunt het uiterlijk van de tekststempel volledig aanpassen. De meegeleverde C#-broncode laat zien hoe u verschillende eigenschappen van de`TextStamp` object, inclusief lettertype, lettergrootte, letterstijl, tekstkleur, achtergrondkleur en rotatie.

#### V: Is het mogelijk om meerdere tekststempels aan verschillende pagina's van hetzelfde PDF-document toe te voegen?

A: Absoluut, u kunt meerdere tekststempels toevoegen aan verschillende pagina's van hetzelfde PDF-document. De code van de tutorial stelt u in staat om de doelpagina te specificeren voor het toevoegen van de tekststempel, waardoor het veelzijdig is voor verschillende pagina's in het document.

#### V: Hoe geef ik de positie van de tekststempel in het PDF-document op?

 A: U kunt de positie van de tekststempel aanpassen door de`XIndent` En`YIndent` eigenschappen van de`TextStamp` object. Deze eigenschappen definiëren de coördinaten van de linkerbovenhoek van de postzegel ten opzichte van de oorsprong van de pagina.

#### V: Kan ik deze methode toepassen op bestaande PDF-documenten om tekststempels toe te voegen?

A: Ja, u kunt deze methode toepassen op bestaande PDF-documenten om tekststempels toe te voegen. De code in de tutorial laat zien hoe u een bestaand PDF-document laadt en een tekststempel toevoegt aan een specifieke pagina.

#### V: Kan ik zowel een achtergrond- als voorgrondkleur aan de tekststempel toevoegen?

 A: Ja, u kunt zowel achtergrond- als voorgrondkleuren toevoegen aan de tekststempel. Door de`Background` eigendom van`true` , kunt u een gekleurde achtergrond voor de tekststempel opgeven. Daarnaast kunt u de`TextState.ForegroundColor` Eigenschap om de kleur van de tekst zelf te specificeren.

#### V: Hoe kan ik ervoor zorgen dat de tekststempel de onderliggende inhoud van het PDF-document niet bedekt?

A: Wanneer u een tekststempel toevoegt, moet u op de plaatsing letten om ervoor te zorgen dat deze geen belangrijke informatie blokkeert of de leesbaarheid van het document negatief beïnvloedt. U kunt de`XIndent` En`YIndent` eigenschappen om de tekststempel op de juiste plaats te zetten.

#### V: Kan ik deze methode gebruiken om andere stempels dan tekst toe te voegen, bijvoorbeeld afbeeldingen of logo's?

A: Deze specifieke tutorial richt zich op het toevoegen van tekststempels, maar u kunt op dezelfde manier andere typen stempels toevoegen, zoals afbeeldingen of logo's, met behulp van Aspose.PDF voor .NET. Het proces omvat het maken van het juiste stempelobject en het configureren van de eigenschappen ervan.

#### V: Hoe kan ik het proces van het toevoegen van tekststempels aan meerdere PDF-documenten automatiseren?

A: U kunt het proces voor het toevoegen van tekststempels aan meerdere PDF-documenten automatiseren door een script of programma te maken dat door een lijst met documenten itereert en hetzelfde tekststempelproces op elk document toepast.