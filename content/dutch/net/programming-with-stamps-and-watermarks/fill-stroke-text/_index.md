---
title: Vul lijntekst in PDF-bestand
linktitle: Vul lijntekst in PDF-bestand
second_title: Aspose.PDF voor .NET API-referentie
description: Leer hoe u eenvoudig tekst in een PDF-bestand kunt invullen en schetsen met Aspose.PDF voor .NET.
type: docs
weight: 90
url: /nl/net/programming-with-stamps-and-watermarks/fill-stroke-text/
---
In deze tutorial laten we u stap voor stap zien hoe u tekst in een PDF-bestand kunt opvullen en omlijnen met Aspose.PDF voor .NET. We laten u zien hoe u de meegeleverde C#-broncode kunt gebruiken om opvul- en omlijningskleuren toe te passen op tekst in het PDF-bestand.

## Stap 1: De omgeving instellen

Voordat u begint, moet u ervoor zorgen dat u het volgende bij de hand hebt:

- Een geïnstalleerde .NET-ontwikkelomgeving.
- De Aspose.PDF-bibliotheek voor .NET is gedownload en wordt in uw project gebruikt.

## Stap 2: Het TextState-object maken

De eerste stap is het maken van een TextState-object om de geavanceerde eigenschappen door te geven. Dit doet u als volgt:

```csharp
// Maak een TextState-object om geavanceerde eigenschappen over te dragen
TextState ts = new TextState();

// Omtrekkleur instellen
ts.StrokingColor = Color.Gray;

// Definieer de tekstweergavemodus
ts.RenderingMode = TextRenderingMode.StrokeText;
```

De bovenstaande code maakt een nieuw TextState-object en stelt de omtrekkleur in en bepaalt hoe de tekst wordt weergegeven.

## Stap 3: Het PDF-document laden

Nu het TextState-object gereed is, kunnen we het PDF-document laden waar we de tekstopvulling en -omtrek willen toepassen. Dit doet u als volgt:

```csharp
// Laad het PDF-document als invoer
Facades.PdfFileStamp fileStamp = new Facades.PdfFileStamp(new Aspose.Pdf.Document(dataDir + "input.pdf"));
```

De bovenstaande code laadt het bestaande PDF-document met behulp van de klasse PdfFileStamp uit de bibliotheek Aspose.PDF.Facades.

## Stap 4: Vulling en lijn toevoegen aan tekst

Nu het PDF-document is geladen, kunnen we de vulling en omtrek aan de tekst toevoegen. Dit is hoe:

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

De bovenstaande code maakt een stempel met de opgegeven tekst en gedefinieerde eigenschappen voor vulling en lijn.

## Stap 5: Sla het uitvoerdocument op

Zodra de tekststempel is toegevoegd, kunnen we het aangepaste PDF-document opslaan. Dit is hoe:

```csharp
// Sla het gewijzigde document op
fileStamp.Save(dataDir + "output_out.pdf");
fileStamp.Close();
```

De bovenstaande code slaat het bewerkte PDF-document op in de opgegeven map.

### Voorbeeldbroncode voor Fill Stroke Text met behulp van Aspose.PDF voor .NET 
```csharp

// Het pad naar de documentenmap.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Maak een TextState-object om geavanceerde eigenschappen over te dragen
TextState ts = new TextState();

// Kleur voor lijn instellen
ts.StrokingColor = Color.Gray;

// Tekstweergavemodus instellen
ts.RenderingMode = TextRenderingMode.StrokeText;

// Een invoer-PDF-document laden
Facades.PdfFileStamp fileStamp = new Facades.PdfFileStamp(new Aspose.Pdf.Document(dataDir + "input.pdf"));
Aspose.Pdf.Facades.Stamp stamp = new Aspose.Pdf.Facades.Stamp();
stamp.BindLogo(new Facades.FormattedText("PAID IN FULL", System.Drawing.Color.Gray, "Arial", Facades.EncodingType.Winansi, true, 78));

// Bind TextState
stamp.BindTextState(ts);

// Stel X,Y oorsprong in
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

Gefeliciteerd! U hebt geleerd hoe u tekst in een PDF-document kunt vullen en omlijnen met Aspose.PDF voor .NET. Nu kunt u deze kennis toepassen om de kleuren van de vulling en omlijning in uw PDF-documenten aan te passen.

### FAQ's voor vulstreeptekst in PDF-bestand

#### V: Wat betekent het om tekst in een PDF-document in te vullen en te schetsen, en wanneer moet ik dat doen?

A: Tekst in een PDF-document opvullen en omlijnen houdt in dat kleuren worden toegepast op de binnenkant van de teksttekens (opvullen) en op de randen rond de tekst (omlijning). Dit kan worden gebruikt om het visuele uiterlijk van de tekst te verbeteren, nadruk te leggen of specifieke inhoud in de PDF te markeren.

#### V: Hoe wordt met de meegeleverde C#-broncode de tekst in een PDF-bestand ingevuld en omlijnd?

 A: De meegeleverde broncode laat zien hoe je een`TextState` object om geavanceerde teksteigenschappen te definiëren, zoals omtrekkleur en renderingmodus. Vervolgens wordt Aspose.PDF.Facades gebruikt om een bestaand PDF-document te laden, een stempel te maken met de tekst met opgegeven vulling- en lijneigenschappen en de stempel aan het document toe te voegen.

####  V: Wat is het doel van de`TextState` object in the code?

 A: De`TextState`object wordt gebruikt om geavanceerde teksteigenschappen te definiëren, waaronder de kleur van de tekstomtrek (lijn) en de weergavemodus. Hiermee kunt u aanpassen hoe de tekst eruitziet in termen van lijn en vulling.

#### V: Kan ik verschillende opvul- en omtrekkleuren toepassen op verschillende delen van dezelfde tekst?

 A: Ja, u kunt de code aanpassen om verschillende`TextState` objecten met verschillende vul- en omtrekkleuren en pas deze toe op specifieke delen van de tekst met behulp van afzonderlijke`Stamp` objecten.

#### V: Kan ik opvul- en omtrekkleuren toepassen op tekst die al in het PDF-document aanwezig is?

 A: Ja, u kunt vergelijkbare principes gebruiken om opvul- en omtrekkleuren toe te passen op bestaande tekst in het PDF-document door de juiste tekstobjecten te selecteren en ze toe te voegen als stempels met de gewenste`TextState` eigenschappen.

#### V: Hoe kan ik de dekking en overvloeiing van de gevulde en omlijnde tekst aanpassen?

 A: Met de meegeleverde code kunt u de dekking en de mengeigenschappen van de stempel instellen met behulp van de`Opacity` En`BlendingSpace`eigenschappen. U kunt deze waarden aanpassen om het gewenste visuele effect te bereiken.

#### V: Hoe kan ik verschillende vul- en omtrekkleuren toepassen op meerdere stempels in hetzelfde PDF-document?

 A: Je kunt meerdere`TextState` objecten met verschillende vul- en omtrekkleuren en maak vervolgens afzonderlijke`Stamp` objecten voor elke set tekst met verschillende kleuren. Voeg deze stempels toe aan hetzelfde PDF-document met behulp van de`PdfFileStamp` klas.

#### V: Kan ik andere lettertypen dan Arial gebruiken voor de omlijnde en gevulde tekst?

 A: Ja, u kunt het lettertype wijzigen door de parameter voor de lettertypenaam in de`FormattedText` constructor bij het maken van de stempel. U kunt elk lettertype gebruiken dat beschikbaar is op uw systeem.

#### V: Hoe kan ik de rotatiehoek van de omlijnde en gevulde tekst aanpassen?

 A: Met de meegeleverde code kunt u de rotatiehoek van de postzegel instellen met behulp van de`Rotation` eigenschap. U kunt deze eigenschap aanpassen om de gewenste rotatiehoek voor de tekst op te geven.

#### V: Hoe kan ik de positie en grootte van de omlijnde en gevulde tekst op de pagina bepalen?

 A: U kunt de`SetOrigin` methode van de`Stamp` object om de X- en Y-coördinaten van de positie van de postzegel op de pagina in te stellen. Bovendien kunt u de lettergrootte in de`FormattedText` constructor om de grootte van de tekst te bepalen.