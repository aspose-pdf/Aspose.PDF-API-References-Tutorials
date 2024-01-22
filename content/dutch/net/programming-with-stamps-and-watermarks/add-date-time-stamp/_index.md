---
title: Datum-tijdstempel toevoegen in PDF-bestand
linktitle: Datum-tijdstempel toevoegen in PDF-bestand
second_title: Aspose.PDF voor .NET API-referentie
description: Leer hoe u eenvoudig een datum- en tijdstempel kunt toevoegen aan een PDF-bestand met Aspose.PDF voor .NET.
type: docs
weight: 10
url: /nl/net/programming-with-stamps-and-watermarks/add-date-time-stamp/
---
In dit artikel laten we u stap voor stap zien hoe u een datum- en tijdstempel aan een PDF-bestand kunt toevoegen met Aspose.PDF voor .NET. We laten u zien hoe u de meegeleverde C#-broncode kunt gebruiken om een datum- en tijdstempel toe te voegen aan een bestaand PDF-bestand.

## Vereisten

Zorg ervoor dat u over het volgende beschikt voordat u begint:

- Een geïnstalleerde .NET-ontwikkelomgeving.
- De Aspose.PDF-bibliotheek voor .NET gedownload en waarnaar wordt verwezen in uw project.

## Stap 1: De omgeving instellen

Voordat u een datum- en tijdstempel aan een PDF-document kunt toevoegen, moet u uw ontwikkelomgeving instellen. Hier zijn de stappen die u moet volgen:

1. Open uw favoriete IDE (Integrated Development Environment).
2. Maak een nieuw C#-project.
3. Zorg ervoor dat u een verwijzing naar de Aspose.PDF-bibliotheek voor .NET hebt toegevoegd.

## Stap 2: De Aspose.PDF-bibliotheek toevoegen

De Aspose.PDF-bibliotheek voor .NET is vereist om met PDF-documenten in uw project te kunnen werken.

## Stap 3: Het PDF-document laden

De eerste stap bij het toevoegen van een datum- en tijdstempel is het laden van het bestaande PDF-document in uw project. Hier is hoe:

```csharp
// Het pad naar de documentenmap.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Open het document
Document pdfDocument = new Document(dataDir + "AddTextStamp.pdf");
```

Zorg ervoor dat u "UW DOCUMENTENMAP" vervangt door het daadwerkelijke pad naar de map waar uw PDF-document zich bevindt.

## Stap 4: De datum- en tijdstempel maken

Nu u het document hebt geüpload

  PDF, u kunt de datum- en tijdstempel maken om toe te voegen. Hier leest u hoe u het moet doen:

```csharp
string annotationText = string.Empty;
annotationText = DateTime.Now.ToString("MM/dd/yy hh:mm:ss tt");

// Maak een tekstbuffer
TextStamp textStamp = new TextStamp(annotationText);
```

De bovenstaande code maakt een nieuwe tekstbuffer met de huidige datum en tijd.

## Stap 5: Stempeleigenschappen configureren

Voordat u de stempel aan het PDF-document toevoegt, kunt u verschillende eigenschappen van de stempel configureren, zoals marge, horizontale en verticale uitlijning, enz. Zo gaat u te werk:

```csharp
// Buffereigenschappen instellen
textStamp.BottomMargin = 10;
textStamp. RightMargin = 20;
textStamp.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Right;
textStamp.VerticalAlignment = VerticalAlignment.Bottom;
```

U kunt deze eigenschappen aanpassen aan uw behoeften.

## Stap 6: Stempel toevoegen aan PDF

Nu de datum- en tijdstempel gereed is, kunt u deze toevoegen aan een specifieke pagina van het PDF-document. Hier is hoe:

```csharp
// Voeg de stempel toe aan de postzegelverzameling van de pagina
pdfDocument.Pages[1].AddStamp(textStamp);
```

De bovenstaande code voegt de stempel toe aan de eerste pagina van het PDF-document. Indien nodig kunt u een andere pagina opgeven.

## Stap 7: Sla het uitvoerdocument op

Nadat u de datum- en tijdstempel heeft toegevoegd, kunt u het gewijzigde PDF-document opslaan. Hier is hoe:

```csharp
// Sla het uitvoerdocument op
pdfDocument.Save(dataDir);
```

De bovenstaande code slaat het bewerkte PDF-document op in de opgegeven map.

### Voorbeeldbroncode voor het toevoegen van een datum-tijdstempel met Aspose.PDF voor .NET 
```csharp

// Het pad naar de documentenmap.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Document openen
Document pdfDocument = new Document(dataDir+ "AddTextStamp.pdf");
string annotationText = string.Empty;
annotationText = DateTime.Now.ToString("MM/dd/yy hh:mm:ss tt ");

// Maak een tekststempel
TextStamp textStamp = new TextStamp(annotationText);

// Stel eigenschappen van de stempel in
textStamp.BottomMargin = 10;
textStamp.RightMargin = 20;
textStamp.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Right;
textStamp.VerticalAlignment = VerticalAlignment.Bottom;

// Stempel toevoegen aan postzegelverzameling
pdfDocument.Pages[1].AddStamp(textStamp);
DefaultAppearance default_appearance = new DefaultAppearance("Arial", 6, System.Drawing.Color.Black);
FreeTextAnnotation textAnnotation = new FreeTextAnnotation(pdfDocument.Pages[1], new Aspose.Pdf.Rectangle(0, 0, 0, 0), default_appearance);
textAnnotation.Name = "Stamp";
textAnnotation.Accept(new AnnotationSelector(textAnnotation));
textAnnotation.Contents = textStamp.Value;

Border border = new Border(textAnnotation);
border.Width = 0;
border.Dash = new Dash(1, 1);
textAnnotation.Border = border;
textAnnotation.Rect = new Aspose.Pdf.Rectangle(0, 0, 0, 0);
pdfDocument.Pages[1].Annotations.Add(textAnnotation);
dataDir = dataDir + "AddDateTimeStamp_out.pdf";

// Sla het uitvoerdocument op
pdfDocument.Save(dataDir);
Console.WriteLine("\nDate time stamp added successfully.\nFile saved at " + dataDir);  
          
```

## Conclusie

Gefeliciteerd! U hebt geleerd hoe u een datum- en tijdstempel kunt toevoegen met Aspose.PDF voor .NET. Nu kunt u deze kennis toepassen op uw eigen projecten om datum- en tijdstempels toe te voegen aan PDF-documenten.

### Veelgestelde vragen over het toevoegen van een datum-tijdstempel aan een PDF-bestand

#### Vraag: Wat is het doel van het toevoegen van een datum- en tijdstempel aan een PDF-document met Aspose.PDF voor .NET?

A: Het toevoegen van een datum- en tijdstempel aan een PDF-document vergroot de informatieve waarde ervan door aan te geven wanneer het document is gewijzigd of gemaakt. Deze functie is handig voor het bijhouden van documentwijzigingen en het bieden van een referentiepunt voor de documentgeschiedenis.

#### Vraag: Kan ik het formaat van de datum- en tijdstempel aanpassen aan specifieke vereisten?

 A: Ja, u kunt het formaat van de datum- en tijdstempel aanpassen aan uw voorkeuren. De meegeleverde C#-broncode maakt gebruik van de`DateTime.Now.ToString()` methode om de tijdstempel in een specifiek formaat te genereren. U kunt deze code zo nodig wijzigen om de tijdstempel op te maken.

#### Vraag: Is het mogelijk om de datum- en tijdstempel toe te voegen aan een specifieke locatie op een PDF-pagina?

 A: Absoluut, u kunt de plaatsing van de datum- en tijdstempel op de PDF-pagina aanpassen door de eigenschappen van het`TextStamp` voorwerp. De code in de zelfstudie laat zien hoe u eigenschappen zoals marge, uitlijning en verticale positionering instelt.

#### Vraag: Kan ik meerdere datum- en tijdstempels toevoegen aan verschillende pagina's van hetzelfde PDF-document?

 A: Ja, u kunt meerdere datum- en tijdstempels toevoegen aan verschillende pagina's van hetzelfde PDF-document. Herhaal eenvoudigweg het proces van het maken van een`TextStamp` object en configureert de eigenschappen ervan voor elke gewenste pagina.

#### Vraag: Hoe kan ik het lettertype, de grootte of de kleur van de datum- en tijdstempeltekst wijzigen?

 A: Om het lettertype, de grootte of de kleur van de datum- en tijdstempeltekst te wijzigen, kunt u de eigenschappen van het`DefaultAppearance` object dat is gebruikt om de`TextStamp`. Pas de lettertypenaam, -grootte en kleurwaarden aan om het gewenste uiterlijk te bereiken.

#### Vraag: Is het mogelijk om andere soorten annotaties of stempels aan een PDF-document toe te voegen met Aspose.PDF voor .NET?

A: Ja, Aspose.PDF voor .NET biedt een breed scala aan annotatietypen die u aan PDF-documenten kunt toevoegen, inclusief tekstannotaties, stempels, lijnen, vormen en meer. U kunt de Aspose.PDF-documentatie raadplegen voor meer informatie over het werken met annotaties.

#### Vraag: Zijn er beperkingen of overwegingen bij het toevoegen van een datum- en tijdstempel aan een PDF-document?

A: Hoewel het toevoegen van een datum- en tijdstempel eenvoudig is, moet u rekening houden met factoren zoals de lay-out van het document en de bestaande inhoud. Zorg ervoor dat de plaatsing van de stempel belangrijke informatie niet verhult of de leesbaarheid van het document beïnvloedt.

#### Vraag: Hoe kan ik deze methode in mijn eigen projecten integreren om datum- en tijdstempels aan PDF-documenten toe te voegen?

A: Om deze methode te integreren, volgt u de aangegeven stappen en past u de code aan zodat deze past bij de structuur van uw project. U kunt datum- en tijdstempels toevoegen aan bestaande PDF-documenten om de bruikbaarheid ervan te vergroten en een duidelijke tijdlijn van wijzigingen weer te geven.

#### Vraag: Kan ik het proces van het toevoegen van datum- en tijdstempels aan meerdere PDF-documenten automatiseren?

A: Ja, u kunt het proces van het toevoegen van datum- en tijdstempels aan meerdere PDF-documenten automatiseren door een script of programma te maken dat een lijst met documenten doorloopt en op elk document hetzelfde stempelproces toepast.