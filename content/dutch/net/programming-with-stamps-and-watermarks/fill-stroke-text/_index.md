---
title: Vul lijntekst in PDF-bestand
linktitle: Vul lijntekst in PDF-bestand
second_title: Aspose.PDF voor .NET API-referentie
description: Leer hoe u eenvoudig tekst in een PDF-bestand kunt invullen en schetsen met Aspose.PDF voor .NET.
type: docs
weight: 90
url: /nl/net/programming-with-stamps-and-watermarks/fill-stroke-text/
---
In deze zelfstudie laten we u stap voor stap zien hoe u tekst in een PDF-bestand kunt invullen en schetsen met Aspose.PDF voor .NET. We laten u zien hoe u de meegeleverde C#-broncode kunt gebruiken om opvul- en omtrekkleuren toe te passen op tekst in het PDF-bestand.

## Stap 1: De omgeving instellen

Zorg ervoor dat u over het volgende beschikt voordat u begint:

- Een geïnstalleerde .NET-ontwikkelomgeving.
- De Aspose.PDF-bibliotheek voor .NET gedownload en waarnaar wordt verwezen in uw project.

## Stap 2: Het TextState-object maken

De eerste stap is het maken van een TextState-object om de geavanceerde eigenschappen door te geven. Hier is hoe:

```csharp
// Maak een TextState-object om geavanceerde eigenschappen over te dragen
TextState ts = new TextState();

// Omtrekkleur instellen
ts.StrokingColor = Color.Gray;

// Definieer de tekstweergavemodus
ts.RenderingMode = TextRenderingMode.StrokeText;
```

De bovenstaande code maakt een nieuw TextState-object en stelt de omtrekkleur in, evenals hoe de tekst wordt weergegeven.

## Stap 3: Het PDF-document laden

Nu het TextState-object gereed is, kunnen we het PDF-document laden op de plek waar we de tekstopvulling en -omtrek willen toepassen. Hier is hoe:

```csharp
// Laad het PDF-document als invoer
Facades.PdfFileStamp fileStamp = new Facades.PdfFileStamp(new Aspose.Pdf.Document(dataDir + "input.pdf"));
```

De bovenstaande code laadt het bestaande PDF-document met behulp van de klasse PdfFileStamp uit de bibliotheek Aspose.PDF.Facades.

## Stap 4: Voeg vulling en lijn toe aan tekst

Nu het PDF-document is geladen, kunnen we de vulling en omtrek aan de tekst toevoegen. Hier is hoe:

```csharp
// Maak een stempel (Stempel) met de gedefinieerde tekst en eigenschappen
Aspose.Pdf.Facades.Stamp stamp = new Aspose.Pdf.Facades.Stamp();
stamp.BindLogo(new Facades.FormattedText("PAID IN FULL", System.Drawing.Color.Gray, "Arial", Facades.EncodingType.Winansi, true, 78));

// Bind het TextState-object
stamp.BindTextState(ts);

// Stel oorsprong X, Y in
stamp.SetOrigin(100, 100);
stamp. Opacity = 5;
stamp.BlendingSpace = Facades.BlendingColorSpace.DeviceRGB;
stamp.Rotation = 45.0F;
stamp. IsBackground = false;

// Voeg de stempel toe aan het document
fileStamp.AddStamp(stamp);
```

Met de bovenstaande code wordt een stempel gemaakt met de opgegeven tekst en gedefinieerde vul- en lijneigenschappen.

## Stap 5: Sla het uitvoerdocument op

Zodra de tekststempel is toegevoegd, kunnen we het gewijzigde PDF-document opslaan. Hier is hoe:

```csharp
// Sla het gewijzigde document op
fileStamp.Save(dataDir + "output_out.pdf");
fileStamp.Close();
```

De bovenstaande code slaat het bewerkte PDF-document op in de opgegeven map.

### Voorbeeldbroncode voor vullijntekst met Aspose.PDF voor .NET 
```csharp

// Het pad naar de documentenmap.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Maak een TextState-object om geavanceerde eigenschappen over te dragen
TextState ts = new TextState();

// Kleur voor lijn instellen
ts.StrokingColor = Color.Gray;

// Stel de tekstweergavemodus in
ts.RenderingMode = TextRenderingMode.StrokeText;

// Laad een invoer-PDF-document
Facades.PdfFileStamp fileStamp = new Facades.PdfFileStamp(new Aspose.Pdf.Document(dataDir + "input.pdf"));
Aspose.Pdf.Facades.Stamp stamp = new Aspose.Pdf.Facades.Stamp();
stamp.BindLogo(new Facades.FormattedText("PAID IN FULL", System.Drawing.Color.Gray, "Arial", Facades.EncodingType.Winansi, true, 78));

// Bind TekstState
stamp.BindTextState(ts);

// Stel de X,Y-oorsprong in
stamp.SetOrigin(100, 100);
stamp.Opacity = 5;
stamp.BlendingSpace = Facades.BlendingColorSpace.DeviceRGB;
stamp.Rotation = 45.0F;
stamp.IsBackground = false;

// Stempel toevoegen
fileStamp.AddStamp(stamp);
fileStamp.Save(dataDir + "ouput_out.pdf");
fileStamp.Close();

```

## Conclusie

Gefeliciteerd! U hebt geleerd hoe u tekst in een PDF-document kunt invullen en schetsen met Aspose.PDF voor .NET. Nu kunt u deze kennis toepassen om de opvul- en omtrekkleuren in uw PDF-documenten aan te passen.

### Veelgestelde vragen over vullijntekst in PDF-bestand

#### Vraag: Wat betekent het om tekst in een PDF-document in te vullen en te schetsen, en wanneer moet ik dit mogelijk doen?

A: Bij het vullen en omlijnen van tekst in een PDF-document worden kleuren toegepast op de binnenkant van de teksttekens (opvulling) en op de randen rond de tekst (omtrek). Dit kan worden gebruikt om de visuele weergave van de tekst te verbeteren, nadruk te leggen of specifieke inhoud in de PDF te markeren.

#### Vraag: Hoe zorgt de meegeleverde C#-broncode voor het vullen en omlijnen van tekst in een PDF-bestand?

 A: De meegeleverde broncode laat zien hoe u een`TextState` object om geavanceerde teksteigenschappen te definiëren, zoals omtrekkleur en weergavemodus. Vervolgens wordt Aspose.PDF.Facades gebruikt om een bestaand PDF-document te laden, een stempel te maken met de tekst met gespecificeerde vul- en lijneigenschappen, en de stempel aan het document toe te voegen.

####  Vraag: Wat is het doel van de`TextState` object in the code?

 EEN: De`TextState`object wordt gebruikt om geavanceerde teksteigenschappen te definiëren, inclusief de kleur van de tekstomtrek (lijn) en de weergavemodus. Hiermee kunt u aanpassen hoe de tekst wordt weergegeven in termen van lijn en vulling.

#### Vraag: Kan ik verschillende opvul- en omtrekkleuren toepassen op verschillende delen van dezelfde tekst?

 A: Ja, u kunt de code wijzigen om andere te maken`TextState` objecten met verschillende vul- en omtrekkleuren en pas deze afzonderlijk toe op specifieke delen van de tekst`Stamp` voorwerpen.

#### Vraag: Kan ik opvul- en omtrekkleuren toepassen op tekst die al in het PDF-document aanwezig is?

 A: Ja, u kunt vergelijkbare principes gebruiken om opvul- en omtrekkleuren toe te passen op bestaande tekst in het PDF-document door de juiste tekstobjecten te selecteren en deze als stempels toe te voegen met de gewenste`TextState` eigenschappen.

#### Vraag: Hoe kan ik de dekking en het overvloeien van de gevulde en omlijnde tekst aanpassen?

 A: Met de meegeleverde code kunt u de dekking en overvloei-eigenschappen van de stempel instellen met behulp van de`Opacity` En`BlendingSpace`eigenschappen, respectievelijk. U kunt deze waarden aanpassen om het gewenste visuele effect te bereiken.

#### Vraag: Hoe kan ik verschillende vul- en omtrekkleuren toepassen op meerdere stempels in hetzelfde PDF-document?

 A: U kunt er meerdere maken`TextState` objecten met verschillende vul- en omtrekkleuren en maak er vervolgens afzonderlijke van`Stamp` objecten voor elke set tekst met verschillende kleuren. Voeg deze stempels toe aan hetzelfde PDF-document met behulp van de`PdfFileStamp` klas.

#### Vraag: Kan ik andere lettertypen dan Arial gebruiken voor de omlijnde en gevulde tekst?

 A: Ja, u kunt het lettertype wijzigen door de parameter voor de lettertypenaam in het`FormattedText` constructor bij het maken van de stempel. U kunt elk lettertype gebruiken dat op uw systeem beschikbaar is.

#### Vraag: Hoe kan ik de rotatiehoek van de omlijnde en gevulde tekst wijzigen?

 A: Met de meegeleverde code kunt u de rotatiehoek van de stempel instellen met behulp van de`Rotation` eigendom. U kunt deze eigenschap aanpassen om de gewenste rotatiehoek voor de tekst op te geven.

#### Vraag: Hoe kan ik de positie en grootte van de omlijnde en gevulde tekst op de pagina bepalen?

Antwoord: U kunt de`SetOrigin` werkwijze van de`Stamp` object om de X- en Y-coördinaten van de positie van de stempel op de pagina in te stellen. Bovendien kunt u de lettergrootte aanpassen in het`FormattedText` constructor om de grootte van de tekst te bepalen.