---
title: Maak een gevulde rechthoek
linktitle: Maak een gevulde rechthoek
second_title: Aspose.PDF voor .NET API-referentie
description: Leer hoe u een gevulde rechthoek in een PDF maakt met Aspose.PDF voor .NET met deze stapsgewijze tutorial. Perfect voor ontwikkelaars van alle niveaus.
type: docs
weight: 50
url: /nl/net/programming-with-graphs/create-filled-rectangle/
---
## Invoering

Heb je ooit visueel aantrekkelijke PDF's willen maken via een programma? Dan ben je hier aan het juiste adres! In deze tutorial duiken we in de wereld van Aspose.PDF voor .NET, een krachtige bibliotheek waarmee je PDF-documenten eenvoudig kunt bewerken. Vandaag richten we ons op het maken van een gevulde rechthoek in een PDF-bestand. Of je nu een doorgewinterde ontwikkelaar bent of net begint, deze gids leidt je op een vriendelijke en boeiende manier door elke stap. Dus pak je codeerhoed en laten we beginnen!

## Vereisten

Voordat we met de code aan de slag gaan, zijn er een paar dingen die je moet regelen:

1. Visual Studio: Zorg ervoor dat u Visual Studio op uw machine hebt geïnstalleerd. Het is een fantastische IDE voor .NET-ontwikkeling.
2.  Aspose.PDF voor .NET: U moet de Aspose.PDF-bibliotheek downloaden en installeren. U kunt deze vinden[hier](https://releases.aspose.com/pdf/net/).
3. Basiskennis van C#: Een beetje vertrouwdheid met C#-programmering helpt u de codefragmenten beter te begrijpen.

## Pakketten importeren

Om te beginnen moet u de benodigde pakketten importeren in uw C#-project. Dit is hoe u dat kunt doen:

### Een nieuw project maken

Open Visual Studio en maak een nieuw C#-project. U kunt een Console Application kiezen voor de eenvoud.

### Voeg Aspose.PDF-referentie toe

1. Klik met de rechtermuisknop op uw project in de Solution Explorer.
2. Selecteer 'NuGet-pakketten beheren'.
3. Zoek naar "Aspose.PDF" en installeer de nieuwste versie.

```csharp
using System.IO;
using System;
using Aspose.Pdf;
```

Nu we alles hebben ingesteld, kunnen we beginnen met de code!

## Stap 1: Stel uw documentenmap in

Allereerst moet u het pad opgeven waar uw PDF wordt opgeslagen. Dit is cruciaal omdat het het programma vertelt waar het bestand moet worden gemaakt.

```csharp
// Het pad naar de documentenmap.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Vervangen`"YOUR DOCUMENT DIRECTORY"` met het daadwerkelijke pad op uw computer waar u de PDF wilt opslaan.

## Stap 2: Een documentinstantie maken

 Vervolgens maken we een exemplaar van de`Document`klasse. Deze klasse vertegenwoordigt het PDF-document waarmee u gaat werken.

```csharp
// Documentinstantie maken
Document doc = new Document();
```

Deze regel initialiseert een nieuw PDF-document dat we kunnen bewerken.

## Stap 3: Een pagina toevoegen aan het document

Laten we nu een pagina aan ons document toevoegen. Elke PDF heeft minstens één pagina nodig, toch?

```csharp
// Pagina toevoegen aan paginaverzameling van PDF-bestand
Page page = doc.Pages.Add();
```

Deze code voegt een nieuwe pagina toe aan het document, zodat we er vormen op kunnen tekenen.

## Stap 4: Een grafiekinstantie maken

 Om vormen te tekenen, moeten we een`Graph` Bijvoorbeeld. Denk aan een grafiek als een canvas waarop je verschillende vormen kunt tekenen.

```csharp
// Grafiekinstantie maken
Aspose.Pdf.Drawing.Graph graph = new Aspose.Pdf.Drawing.Graph(100.0, 400.0);
```

Hier maken we een grafiek met een breedte van 100 en een hoogte van 400.

## Stap 5: Voeg de grafiek toe aan de pagina

Nu we de grafiek hebben, kunnen we deze toevoegen aan de pagina die we eerder hebben gemaakt.

```csharp
// Grafiekobject toevoegen aan alineaverzameling van pagina-instantie
page.Paragraphs.Add(graph);
```

Deze lijn koppelt de grafiek aan de pagina, zodat deze gereed is om te tekenen.

## Stap 6: Maak een rechthoekinstantie

Vervolgens maken we een rechthoek die we met kleur willen vullen.

```csharp
// Maak een rechthoek-instantie
Aspose.Pdf.Drawing.Rectangle rect = new Aspose.Pdf.Drawing.Rectangle(100, 100, 200, 120);
```

In deze code definiëren we de positie en grootte van de rechthoek. De parameters representeren de x- en y-coördinaten, breedte en hoogte.

## Stap 7: Geef de vulkleur op

Laten we nu een kleur kiezen voor onze rechthoek. We vullen het met rood voor dit voorbeeld.

```csharp
// Geef de vulkleur voor het grafiekobject op
rect.GraphInfo.FillColor = Aspose.Pdf.Color.Red;
```

Deze lijn stelt de vulkleur van de rechthoek in op rood. U kunt elke gewenste kleur kiezen!

## Stap 8: Voeg de rechthoek toe aan de grafiek

Nu de rechthoek klaar is, kunnen we deze aan de grafiek toevoegen.

```csharp
// Rechthoekig object toevoegen aan vormenverzameling van Grafiekobject
graph.Shapes.Add(rect);
```

Deze code voegt de rechthoek toe aan de grafiek, waardoor deze onderdeel wordt van onze tekening.

## Stap 9: Sla het PDF-document op

Ten slotte moeten we ons document opslaan in de opgegeven directory.

```csharp
dataDir = dataDir + "CreateFilledRectangle_out.pdf";
// PDF-bestand opslaan
doc.Save(dataDir);
```

 Deze code slaat het PDF-bestand op met de naam`CreateFilledRectangle_out.pdf` in de map die u eerder hebt opgegeven.

## Stap 10: Bevestigingsbericht

Om ons te laten weten dat alles goed is verlopen, kunnen wij een bevestigingsbericht afdrukken.

```csharp
Console.WriteLine("\nFilled rectangle object created successfully.\nFile saved at " + dataDir);
```

Deze regel genereert een bericht in de console, waarin wordt bevestigd dat de gevulde rechthoek succesvol is gemaakt.

## Conclusie

En daar heb je het! Je hebt met succes een gevulde rechthoek gemaakt in een PDF-document met Aspose.PDF voor .NET. Deze krachtige bibliotheek opent een wereld aan mogelijkheden voor PDF-manipulatie, waardoor je verbluffende documenten programmatisch kunt maken. Of je nu rapporten, facturen of een ander type PDF genereert, Aspose.PDF heeft het allemaal.

## Veelgestelde vragen

### Wat is Aspose.PDF voor .NET?
Aspose.PDF voor .NET is een bibliotheek waarmee ontwikkelaars programmatisch PDF-documenten kunnen maken, bewerken en converteren.

### Kan ik Aspose.PDF gratis gebruiken?
 Ja, Aspose biedt een gratis proefversie die u kunt gebruiken om de functies van de bibliotheek te verkennen. U kunt deze downloaden[hier](https://releases.aspose.com/).

### Is er een manier om ondersteuning te krijgen voor Aspose.PDF?
 Absoluut! Je kunt ondersteuning krijgen via het Aspose forum[hier](https://forum.aspose.com/c/pdf/10).

### Hoe kan ik Aspose.PDF kopen?
 U kunt Aspose.PDF kopen door de aankooppagina te bezoeken[hier](https://purchase.aspose.com/buy).

### Welke soorten vormen kan ik maken met Aspose.PDF?
Met de Aspose.PDF-bibliotheek kunt u verschillende vormen maken, waaronder rechthoeken, cirkels, lijnen en meer.