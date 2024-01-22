---
title: Tekststempel toevoegen aan PDF-bestand
linktitle: Tekststempel toevoegen aan PDF-bestand
second_title: Aspose.PDF voor .NET API-referentie
description: Leer hoe u eenvoudig een tekststempel kunt toevoegen aan een PDF-bestand met Aspose.PDF voor .NET.
type: docs
weight: 50
url: /nl/net/programming-with-stamps-and-watermarks/add-text-stamp/
---
In deze tutorial laten we u stap voor stap zien hoe u een tekststempel in een PDF-bestand kunt toevoegen met Aspose.PDF voor .NET. We laten u zien hoe u de meegeleverde C#-broncode kunt gebruiken om een aangepaste tekststempel toe te voegen aan een specifieke pagina van het PDF-bestand.

## Stap 1: De omgeving instellen

Zorg ervoor dat u over het volgende beschikt voordat u begint:

- Een geïnstalleerde .NET-ontwikkelomgeving.
- De Aspose.PDF-bibliotheek voor .NET gedownload en waarnaar wordt verwezen in uw project.

## Stap 2: Het PDF-document laden

De eerste stap is het laden van het bestaande PDF-document in uw project. Hier is hoe:

```csharp
// Het pad naar de documentenmap.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Open het document
Document pdfDocument = new Document(dataDir + "AddTextStamp.pdf");
```

Zorg ervoor dat u "UW DOCUMENTENMAP" vervangt door het daadwerkelijke pad naar de map waar uw PDF-document zich bevindt.

## Stap 3: De tekstbuffer maken

Nu u het PDF-document heeft geüpload, kunt u de tekststempel maken die u wilt toevoegen. Hier leest u hoe u het moet doen:

```csharp
// Maak de tekstbuffer
TextStamp textStamp = new TextStamp("Example Stamp");
```

Met de bovenstaande code wordt een nieuwe tekstbuffer gemaakt die de opgegeven tekst bevat.

## Stap 4: Tekststempeleigenschappen configureren

Voordat u de tekststempel aan het PDF-document toevoegt, kunt u verschillende eigenschappen van de stempel configureren, zoals achtergrond, positie, rotatie, lettertype, grootte, enz. Zo gaat u te werk:

```csharp
// Configureer de eigenschappen van de tekstbuffer
textStamp. Background = true;
textStamp. XIndent = 100;
textStamp. YIndent = 100;
textStamp.Rotate = Rotate.on90;
textStamp.TextState.Font = FontRepository.FindFont("Arial");
textStamp.TextState.FontSize = 14.0F;
textStamp.TextState.FontStyle = FontStyles.Bold | FontStyles.Italic;
textStamp.TextState.ForegroundColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Aqua);
```

U kunt deze eigenschappen aanpassen aan uw behoeften.

## Stap 5: Voeg een tekststempel toe aan PDF

Nu de tekststempel klaar is, kunt u deze toevoegen aan een specifieke pagina van het PDF-document. Hier is hoe:

```csharp
//Voeg tekstbuffer toe aan een specifieke pagina
pdfDocument.Pages[1].AddStamp(textStamp);
```

De bovenstaande code voegt de tekststempel toe aan de eerste pagina van het PDF-document. Indien nodig kunt u een andere pagina opgeven.

## Stap 6: Sla het uitvoerdocument op

Nadat u de tekststempel heeft toegevoegd, kunt u het bewerkte PDF-document opslaan. Hier is hoe:

```csharp
// Sla het uitvoerdocument op
pdfDocument.Save(dataDir);
```

De bovenstaande code slaat het gewijzigde PDF-document op in de opgegeven map.

### Voorbeeldbroncode voor het toevoegen van tekststempel met Aspose.PDF voor .NET 
```csharp

// Het pad naar de documentenmap.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Document openen
Document pdfDocument = new Document(dataDir+ "AddTextStamp.pdf");

// Maak een tekststempel
TextStamp textStamp = new TextStamp("Sample Stamp");

// Stel in of de stempel een achtergrond is
textStamp.Background = true;

// Oorsprong instellen
textStamp.XIndent = 100;
textStamp.YIndent = 100;

// Stempel draaien
textStamp.Rotate = Rotation.on90;

// Teksteigenschappen instellen
textStamp.TextState.Font = FontRepository.FindFont("Arial");
textStamp.TextState.FontSize = 14.0F;
textStamp.TextState.FontStyle = FontStyles.Bold;
textStamp.TextState.FontStyle = FontStyles.Italic;
textStamp.TextState.ForegroundColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Aqua);

// Voeg een stempel toe aan een bepaalde pagina
pdfDocument.Pages[1].AddStamp(textStamp);
dataDir = dataDir + "AddTextStamp_out.pdf";

// Sla het uitvoerdocument op
pdfDocument.Save(dataDir);
Console.WriteLine("\nText stamp added successfully.\nFile saved at " + dataDir);            

```

## Conclusie

Gefeliciteerd! U hebt geleerd hoe u een tekststempel kunt toevoegen met Aspose.PDF voor .NET. Nu kunt u deze kennis toepassen op uw eigen projecten en aangepaste tekststempels toevoegen aan PDF-documenten.

### Veelgestelde vragen over het toevoegen van een tekststempel aan een PDF-bestand

#### Vraag: Wat is het doel van het toevoegen van een tekststempel aan een PDF-bestand met Aspose.PDF voor .NET?

A: Door een tekststempel toe te voegen, kunt u aangepaste tekst op een specifieke pagina van een PDF-document plaatsen. Deze functie is handig voor het toevoegen van labels, opmerkingen, watermerken of andere tekstuele informatie om de inhoud van het document te verbeteren en extra context te bieden.

#### Vraag: Kan ik het uiterlijk van de tekststempel aanpassen, zoals lettertype, grootte, kleur en rotatie?

 A: Ja, u kunt het uiterlijk van de tekststempel volledig aanpassen. De meegeleverde C#-broncode laat zien hoe u verschillende eigenschappen van het`TextStamp` object, inclusief lettertype, lettergrootte, letterstijl, tekstkleur, achtergrondkleur en rotatie.

#### Vraag: Is het mogelijk om meerdere tekststempels toe te voegen aan verschillende pagina's van hetzelfde PDF-document?

A: Absoluut, u kunt meerdere tekststempels toevoegen aan verschillende pagina's van hetzelfde PDF-document. Met de bij de tutorial meegeleverde code kunt u de doelpagina opgeven voor het toevoegen van de tekststempel, waardoor deze veelzijdig is voor verschillende pagina's in het document.

#### Vraag: Hoe geef ik de positie van de tekststempel in het PDF-document op?

 A: U kunt de positie van de tekststempel aanpassen door de`XIndent` En`YIndent` eigenschappen van de`TextStamp` voorwerp. Deze eigenschappen definiëren de coördinaten van de linkerbovenhoek van de stempel ten opzichte van de oorsprong van de pagina.

#### Vraag: Kan ik deze methode toepassen op bestaande PDF-documenten om tekststempels toe te voegen?

A: Ja, u kunt deze methode toepassen op bestaande PDF-documenten om tekststempels toe te voegen. De bij de zelfstudie geleverde code laat zien hoe u een bestaand PDF-document laadt en een tekststempel aan een specifieke pagina toevoegt.

#### Vraag: Kan ik zowel achtergrond- als voorgrondkleuren aan de tekststempel toevoegen?

 A: Ja, u kunt zowel achtergrond- als voorgrondkleuren aan de tekststempel toevoegen. Door het instellen van de`Background` eigendom aan`true` , kunt u een gekleurde achtergrond voor de tekststempel opgeven. Bovendien kunt u de`TextState.ForegroundColor` eigenschap om de kleur van de tekst zelf op te geven.

#### Vraag: Hoe kan ik ervoor zorgen dat de tekststempel de onderliggende inhoud van het PDF-document niet verbergt?

 A: Houd bij het toevoegen van een tekststempel rekening met de plaatsing ervan om ervoor te zorgen dat deze geen kritieke informatie belemmert of de leesbaarheid van het document negatief beïnvloedt. U kunt de`XIndent` En`YIndent` eigenschappen om de tekststempel op de juiste manier te positioneren.

#### Vraag: Kan ik deze methode gebruiken om andere stempels dan tekst toe te voegen, zoals afbeeldingen of logo's?

A: Deze specifieke tutorial richt zich op het toevoegen van tekststempels, maar u kunt op dezelfde manier andere typen stempels toevoegen, zoals afbeeldingen of logo's, met behulp van Aspose.PDF voor .NET. Het proces omvat het maken van het juiste stempelobject en het configureren van de eigenschappen ervan.

#### Vraag: Hoe kan ik het proces van het toevoegen van tekststempels aan meerdere PDF-documenten automatiseren?

A: U kunt het proces van het toevoegen van tekststempels aan meerdere PDF-documenten automatiseren door een script of programma te maken dat een lijst met documenten doorloopt en op elk document hetzelfde tekststempelproces toepast.