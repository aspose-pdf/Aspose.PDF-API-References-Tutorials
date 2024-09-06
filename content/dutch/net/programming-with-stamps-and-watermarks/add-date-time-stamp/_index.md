---
title: Datum- en tijdstempel toevoegen in PDF-bestand
linktitle: Datum- en tijdstempel toevoegen in PDF-bestand
second_title: Aspose.PDF voor .NET API-referentie
description: Leer hoe u eenvoudig een datum- en tijdstempel aan een PDF-bestand kunt toevoegen met Aspose.PDF voor .NET.
type: docs
weight: 10
url: /nl/net/programming-with-stamps-and-watermarks/add-date-time-stamp/
---
In dit artikel leggen we u stap voor stap uit hoe u een datum- en tijdstempel toevoegt aan een PDF-bestand met Aspose.PDF voor .NET. We laten u zien hoe u de meegeleverde C#-broncode gebruikt om een datum- en tijdstempel toe te voegen aan een bestaand PDF-bestand.

## Vereisten

Voordat u begint, moet u ervoor zorgen dat u het volgende bij de hand hebt:

- Een geïnstalleerde .NET-ontwikkelomgeving.
- De Aspose.PDF-bibliotheek voor .NET is gedownload en wordt in uw project gebruikt.

## Stap 1: De omgeving instellen

Voordat u een datum- en tijdstempel aan een PDF-document kunt toevoegen, moet u uw ontwikkelomgeving instellen. Dit zijn de stappen die u moet volgen:

1. Open uw favoriete IDE (Integrated Development Environment).
2. Maak een nieuw C#-project.
3. Zorg ervoor dat u een verwijzing naar de Aspose.PDF-bibliotheek voor .NET hebt toegevoegd.

## Stap 2: De Aspose.PDF-bibliotheek toevoegen

De Aspose.PDF-bibliotheek voor .NET is vereist om met PDF-documenten in uw project te kunnen werken.

## Stap 3: Het PDF-document laden

De eerste stap om een datum- en tijdstempel toe te voegen is het laden van het bestaande PDF-document in uw project. Dit doet u als volgt:

```csharp
// Het pad naar de documentenmap.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Open het document
Document pdfDocument = new Document(dataDir + "AddTextStamp.pdf");
```

Zorg ervoor dat u "UW DOCUMENTENMAP" vervangt door het daadwerkelijke pad naar de map waarin uw PDF-document zich bevindt.

## Stap 4: Datum- en tijdstempel maken

Nu u het document heeft geüpload

  PDF, je kunt de datum- en tijdstempel maken om toe te voegen. Dit is hoe je dat doet:

```csharp
string annotationText = string.Empty;
annotationText = DateTime.Now.ToString("MM/dd/yy hh:mm:ss tt");

// Een tekstbuffer maken
TextStamp textStamp = new TextStamp(annotationText);
```

De bovenstaande code maakt een nieuwe tekstbuffer aan die de huidige datum en tijd bevat.

## Stap 5: Stempeleigenschappen configureren

Voordat u de stempel aan het PDF-document toevoegt, kunt u verschillende eigenschappen van de stempel configureren, zoals de marge, horizontale en verticale uitlijning, enz. Dit doet u als volgt:

```csharp
// Buffereigenschappen instellen
textStamp.BottomMargin = 10;
textStamp. RightMargin = 20;
textStamp.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Right;
textStamp.VerticalAlignment = VerticalAlignment.Bottom;
```

U kunt deze eigenschappen naar wens aanpassen.

## Stap 6: Stempel toevoegen aan PDF

Nu de datum- en tijdstempel klaar is, kunt u deze toevoegen aan een specifieke pagina van het PDF-document. Dit doet u als volgt:

```csharp
// Voeg de postzegel toe aan de postzegelverzameling van de pagina
pdfDocument.Pages[1].AddStamp(textStamp);
```

De bovenstaande code voegt de stempel toe aan de eerste pagina van het PDF-document. U kunt indien nodig een andere pagina opgeven.

## Stap 7: Sla het uitvoerdocument op

Zodra u de datum- en tijdstempel hebt toegevoegd, kunt u het gewijzigde PDF-document opslaan. Dit doet u als volgt:

```csharp
// Sla het uitvoerdocument op
pdfDocument.Save(dataDir);
```

De bovenstaande code slaat het bewerkte PDF-document op in de opgegeven map.

### Voorbeeldbroncode voor het toevoegen van een datum- en tijdstempel met behulp van Aspose.PDF voor .NET 
```csharp

// Het pad naar de documentenmap.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Document openen
Document pdfDocument = new Document(dataDir+ "AddTextStamp.pdf");
string annotationText = string.Empty;
annotationText = DateTime.Now.ToString("MM/dd/yy hh:mm:ss tt ");

// Tekststempel maken
TextStamp textStamp = new TextStamp(annotationText);

// Eigenschappen van de stempel instellen
textStamp.BottomMargin = 10;
textStamp.RightMargin = 20;
textStamp.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Right;
textStamp.VerticalAlignment = VerticalAlignment.Bottom;

// Postzegel toevoegen aan postzegelverzameling
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

// Uitvoerdocument opslaan
pdfDocument.Save(dataDir);
Console.WriteLine("\nDate time stamp added successfully.\nFile saved at " + dataDir);  
          
```

## Conclusie

Gefeliciteerd! U hebt geleerd hoe u een datum- en tijdstempel kunt toevoegen met Aspose.PDF voor .NET. Nu kunt u deze kennis toepassen op uw eigen projecten om datum- en tijdstempels toe te voegen aan PDF-documenten.

### FAQ's voor het toevoegen van een datum- en tijdstempel aan een PDF-bestand

#### V: Wat is het doel van het toevoegen van een datum- en tijdstempel aan een PDF-document met behulp van Aspose.PDF voor .NET?

A: Het toevoegen van een datum- en tijdstempel aan een PDF-document verhoogt de informatieve waarde ervan door aan te geven wanneer het document is gewijzigd of gemaakt. Deze functie is handig voor het bijhouden van documentwijzigingen en het bieden van een referentiepunt voor de documentgeschiedenis.

#### V: Kan ik de notatie van de datum- en tijdstempel aanpassen aan specifieke vereisten?

 A: Ja, u kunt de opmaak van de datum- en tijdstempel aanpassen aan uw voorkeuren. De meegeleverde C#-broncode gebruikt de`DateTime.Now.ToString()` methode om de tijdstempel in een specifiek formaat te genereren. U kunt deze code aanpassen om de tijdstempel naar wens te formatteren.

#### V: Is het mogelijk om de datum en tijd aan een specifieke locatie op een PDF-pagina toe te voegen?

 A: Absoluut, u kunt de plaatsing van de datum- en tijdstempel op de PDF-pagina aanpassen door de eigenschappen van de`TextStamp` object. De code in de tutorial laat zien hoe u eigenschappen zoals marge, uitlijning en verticale positionering instelt.

#### V: Kan ik meerdere datum- en tijdstempels toevoegen aan verschillende pagina's van hetzelfde PDF-document?

 A: Ja, u kunt meerdere datum- en tijdstempels toevoegen aan verschillende pagina's van hetzelfde PDF-document. Herhaal gewoon het proces van het maken van een`TextStamp` object en het configureren van de eigenschappen ervan voor elke gewenste pagina.

#### V: Hoe kan ik het lettertype, de grootte of de kleur van de datum- en tijdstempeltekst wijzigen?

 A: Om het lettertype, de grootte of de kleur van de datum- en tijdstempeltekst te wijzigen, kunt u de eigenschappen van de`DefaultAppearance` object dat wordt gebruikt om de`TextStamp`Pas de naam, grootte en kleur van het lettertype aan om het gewenste uiterlijk te verkrijgen.

#### V: Is het mogelijk om andere soorten aantekeningen of stempels toe te voegen aan een PDF-document met Aspose.PDF voor .NET?

A: Ja, Aspose.PDF voor .NET biedt een breed scala aan annotatietypen die u aan PDF-documenten kunt toevoegen, waaronder tekstannotaties, stempels, lijnen, vormen en meer. U kunt de Aspose.PDF-documentatie raadplegen voor meer informatie over het werken met annotaties.

#### V: Zijn er beperkingen of overwegingen bij het toevoegen van een datum- en tijdstempel aan een PDF-document?

A: Hoewel het toevoegen van een datum- en tijdstempel eenvoudig is, moet u rekening houden met factoren zoals de lay-out van het document en bestaande inhoud. Zorg ervoor dat de plaatsing van de stempel geen belangrijke informatie verbergt of de leesbaarheid van het document beïnvloedt.

#### V: Hoe kan ik deze methode integreren in mijn eigen projecten om datum- en tijdstempels toe te voegen aan PDF-documenten?

A: Om deze methode te integreren, volgt u de gegeven stappen en past u de code aan zodat deze past bij de structuur van uw project. U kunt datum- en tijdstempels toevoegen aan bestaande PDF-documenten om hun bruikbaarheid te vergroten en een duidelijke tijdlijn van wijzigingen te bieden.

#### V: Kan ik het proces van het toevoegen van datum- en tijdstempels aan meerdere PDF-documenten automatiseren?

A: Ja, u kunt het proces voor het toevoegen van datum- en tijdstempels aan meerdere PDF-documenten automatiseren door een script of programma te maken dat door een lijst met documenten itereert en op elk document hetzelfde stempelproces toepast.