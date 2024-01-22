---
title: Afbeelding toevoegen in PDF-bestand
linktitle: Afbeelding toevoegen in PDF-bestand
second_title: Aspose.PDF voor .NET API-referentie
description: Voeg eenvoudig een afbeelding toe in een PDF-bestand met Aspose.PDF voor .NET.
type: docs
weight: 10
url: /nl/net/programming-with-images/add-image/
---
In deze handleiding wordt stap voor stap uitgelegd hoe u een afbeelding in een PDF-bestand kunt toevoegen met Aspose.PDF voor .NET. Zorg ervoor dat u uw omgeving al heeft ingesteld en volg de onderstaande stappen:

## Stap 1: Definieer de documentmap

 Zorg ervoor dat u, voordat u begint, de juiste map voor de documenten instelt. Vervangen`"YOUR DOCUMENT DIRECTORY"` in de code met het pad naar de map waar uw PDF-document zich bevindt.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Stap 2: Open het document

In deze stap openen we het PDF-document met behulp van de`Document` klasse van Aspose.PDF. Gebruik de`Document` constructor en geef het pad door naar het PDF-document.

```csharp
Document pdfDocument = new Document(dataDir + "AddImage.pdf");
```

## Stap 3: Stel beeldcoördinaten in

 Stel de coördinaten in van de afbeelding die u wilt toevoegen. De variabelen`lowerLeftX`, `lowerLeftY`, `upperRightX` En`upperRightY` vertegenwoordigen respectievelijk de coördinaten van de linkerbenedenhoek en de rechterbovenhoek van de afbeelding.

```csharp
int lowerLeftX = 100;
int lowerLeftY = 100;
int upperRightX = 200;
int upperRightY = 200;
```

## Stap 4: Haal de pagina op waar de afbeelding moet worden toegevoegd

Om de afbeelding aan een specifieke pagina van het PDF-document toe te voegen, moeten we eerst die pagina ophalen. In dit voorbeeld voegen we de afbeelding toe aan de tweede pagina (index 1) van het document.

```csharp
Page page = pdfDocument.Pages[1];
```

## Stap 5: Laad de afbeelding uit een stream

 We zullen nu de afbeelding laden die we aan het PDF-document willen toevoegen. In dit voorbeeld wordt ervan uitgegaan dat u een afbeeldingsbestand hebt met de naam`aspose-logo.jpg` in dezelfde map als uw document. Vervang indien nodig de bestandsnaam.

```csharp
FileStream imageStream = new FileStream(dataDir + "aspose-logo.jpg", FileMode.Open);
```

## Stap 6: Voeg de afbeelding toe aan pagina-elementen

Om de afbeelding in het PDF-document te gebruiken, moeten we deze toevoegen aan de verzameling bronafbeeldingen van de pagina.

```csharp
page.Resources.Images.Add(imageStream);
```

## Stap 7: Bewaar de huidige grafische status

 Voordat we de afbeelding tekenen, moeten we de huidige grafische status opslaan met behulp van de`GSave` exploitant. Dit zorgt ervoor dat wijzigingen in de grafische status later kunnen worden teruggedraaid.

```csharp
page.Contents.Add(new Aspose.Pdf.Operators.GSave());
```

## Stap 8: Creëer rechthoekige en matrixobjecten

 We gaan nu een`Rectangle` voorwerp en een`Matrix`voorwerp. De rechthoek vertegenwoordigt de positie en grootte van de afbeelding, terwijl de matrix definieert hoe de afbeelding moet worden geplaatst.

```csharp
Aspose.Pdf.Rectangle rectangle = new Aspose.Pdf.Rectangle(lower

LeftX, lowerLeftY, upperRightX, upperRightY);
Matrix matrix = new Matrix(new double[] { rectangle.URX - rectangle.LLX, 0, 0, rectangle.URY - rectangle.LLY, rectangle.LLX, rectangle.LLY });
```

## Stap 9: Voeg de matrix samen voor het plaatsen van afbeeldingen

 Om aan te geven hoe de afbeelding in de rechthoek moet worden geplaatst, gebruiken we de`ConcatenateMatrix` exploitant. Deze operator definieert de transformatiematrix die de coördinatenruimte van de afbeelding toewijst aan de coördinatenruimte van de pagina.

```csharp
page.Contents.Add(new Aspose.Pdf.Operators.ConcatenateMatrix(matrix));
```

## Stap 10: Teken de afbeelding

 In deze stap tekenen we de afbeelding op de pagina met behulp van de`Do` exploitant. De`Do` operator haalt de afbeeldingsnaam uit de bronnen en tekent deze op de pagina.

```csharp
XImage ximage = page.Resources.Images[page.Resources.Images.Count];
page.Contents.Add(new Aspose.Pdf.Operators.Do(ximage.Name));
```

## Stap 11: Herstel de grafische staat

 Nadat we de afbeelding hebben getekend, moeten we de vorige grafische staat herstellen met behulp van de`GRestore` exploitant.

```csharp
page.Contents.Add(new Aspose.Pdf.Operators.GRestore());
```

## Stap 12: Sla het bijgewerkte document op

 Ten slotte slaan we het bijgewerkte document op in een nieuw bestand. Update de`dataDir` variabele met de gewenste uitvoermap en bestandsnaam.

```csharp
dataDir = dataDir + "AddImage_out.pdf";
pdfDocument.Save(dataDir);
```

### Voorbeeldbroncode voor Afbeelding toevoegen met Aspose.PDF voor .NET 
```csharp
// Het pad naar de documentenmap.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Document openen
Document pdfDocument = new Document(dataDir+ "AddImage.pdf");
// Coördinaten instellen
int lowerLeftX = 100;
int lowerLeftY = 100;
int upperRightX = 200;
int upperRightY = 200;
//Haal de pagina op waar de afbeelding moet worden toegevoegd
Page page = pdfDocument.Pages[1];
// Laad afbeelding in stream
FileStream imageStream = new FileStream(dataDir + "aspose-logo.jpg", FileMode.Open);
// Voeg een afbeelding toe aan de afbeeldingenverzameling van paginabronnen
page.Resources.Images.Add(imageStream);
// Met behulp van de GSave-operator: deze operator slaat de huidige grafische status op
page.Contents.Add(new Aspose.Pdf.Operators.GSave());
// Creëer rechthoekige en matrixobjecten
Aspose.Pdf.Rectangle rectangle = new Aspose.Pdf.Rectangle(lowerLeftX, lowerLeftY, upperRightX, upperRightY);
Matrix matrix = new Matrix(new double[] { rectangle.URX - rectangle.LLX, 0, 0, rectangle.URY - rectangle.LLY, rectangle.LLX, rectangle.LLY });
// Met behulp van ConcatenateMatrix (samengevoegde matrix) operator: definieert hoe de afbeelding moet worden geplaatst
page.Contents.Add(new Aspose.Pdf.Operators.ConcatenateMatrix(matrix));
XImage ximage = page.Resources.Images[page.Resources.Images.Count];
// Met behulp van de Do-operator: deze operator tekent een afbeelding
page.Contents.Add(new Aspose.Pdf.Operators.Do(ximage.Name));
// Met behulp van de GRestore-operator: deze operator herstelt de grafische status
page.Contents.Add(new Aspose.Pdf.Operators.GRestore());
dataDir = dataDir + "AddImage_out.pdf";
// Bewaar het bijgewerkte document
pdfDocument.Save(dataDir);
Console.WriteLine("\nImage added successfully.\nFile saved at " + dataDir); 
```

## Conclusie

In deze zelfstudie hebben we geleerd hoe u een afbeelding aan een PDF-document kunt toevoegen met Aspose.PDF voor .NET. We hebben elke stap tot in detail besproken, van het openen van het document tot het opslaan van de bijgewerkte versie. Door deze handleiding te volgen, zou u nu afbeeldingen programmatisch in uw PDF-bestanden moeten kunnen insluiten met behulp van C# en Aspose.PDF.

### Veelgestelde vragen over het toevoegen van een afbeelding aan een PDF-bestand

#### Vraag: Waarom zou ik een afbeelding aan een PDF-document willen toevoegen?

A: Het toevoegen van afbeeldingen aan een PDF-document kan de visuele inhoud verbeteren, extra context bieden of logo's en afbeeldingen in uw PDF-bestanden opnemen.

#### Vraag: Kan ik afbeeldingen toevoegen aan specifieke pagina's binnen een PDF-document?

A: Ja, u kunt de pagina opgeven waar u de afbeelding wilt toevoegen. In de opgegeven code wordt de afbeelding toegevoegd aan de tweede pagina van het PDF-document.

#### Vraag: Hoe pas ik de positie en grootte van de toegevoegde afbeelding aan?

 A: U kunt de`lowerLeftX`, `lowerLeftY`, `upperRightX` , En`upperRightY` variabelen in de code om de coördinaten van de afbeelding in te stellen en de grootte en positie op de pagina te bepalen.

#### Vraag: Welk type afbeeldingsindelingen kan ik met deze methode toevoegen?

A: In het gegeven codevoorbeeld wordt ervan uitgegaan dat u een JPG-afbeelding laadt (`aspose-logo.jpg`). Aspose.PDF voor .NET ondersteunt verschillende afbeeldingsformaten, waaronder PNG, BMP, GIF en meer.

#### Vraag: Hoe zorg ik ervoor dat de toegevoegde afbeelding binnen de opgegeven coördinaten past?

 A: Zorg ervoor dat u de coördinaten en de grootte van het bestand aanpast`Rectangle` voorwerp (`rectangle`zodat deze overeenkomt met de afmetingen van de afbeelding en de gewenste plaatsing op de pagina.

#### Vraag: Kan ik meerdere afbeeldingen aan één PDF-pagina toevoegen?

A: Ja, u kunt meerdere afbeeldingen aan één PDF-pagina toevoegen door het proces voor elke afbeelding te herhalen en de coördinaten en andere parameters dienovereenkomstig aan te passen.

####  Vraag: Hoe werkt de`GSave` and `GRestore` operator work in the code?

 EEN: De`GSave` operator slaat de huidige grafische status op, zodat u wijzigingen kunt aanbrengen zonder de algehele grafische context te beïnvloeden. De`GRestore` operator herstelt de vorige grafische status nadat er wijzigingen zijn aangebracht.

#### Vraag: Wat gebeurt er als het afbeeldingsbestand niet op het opgegeven pad wordt gevonden?

A: Als het afbeeldingsbestand niet op het opgegeven pad wordt gevonden, genereert de code een uitzondering wanneer wordt geprobeerd de afbeeldingsstream te laden. Zorg ervoor dat het afbeeldingsbestand zich in de juiste map bevindt.

#### Vraag: Kan ik de plaatsing en het uiterlijk van de afbeelding verder aanpassen?

 A: Ja, u kunt het uiterlijk van de afbeelding aanpassen door de`Matrix`object en het aanpassen van andere operators binnen de code. Raadpleeg de Aspose.PDF-documentatie voor geavanceerde aanpassingen.

#### Vraag: Hoe kan ik testen of de afbeelding succesvol aan de PDF is toegevoegd?

A: Nadat u de meegeleverde code hebt toegepast om de afbeelding toe te voegen, opent u het gewijzigde PDF-bestand en controleert u of de afbeelding met de juiste plaatsing op de opgegeven pagina wordt weergegeven.

#### Vraag: Heeft het toevoegen van afbeeldingen invloed op de originele inhoud van het PDF-document?

A: Het toevoegen van afbeeldingen heeft geen invloed op de originele inhoud van het PDF-document. Het verbetert het document door visuele elementen op te nemen.