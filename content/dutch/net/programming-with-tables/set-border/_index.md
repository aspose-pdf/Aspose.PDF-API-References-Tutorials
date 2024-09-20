---
title: Rand in PDF instellen op tabel
linktitle: Rand in PDF instellen op tabel
second_title: Aspose.PDF voor .NET API-referentie
description: Leer hoe u randen in een PDF-tabel instelt met Aspose.PDF voor .NET met onze stapsgewijze handleiding. Verbeter het uiterlijk van uw document eenvoudig.
type: docs
weight: 200
url: /nl/net/programming-with-tables/set-border/
---
## Invoering

Het maken van professioneel ogende PDF-documenten is eenvoudiger dan ooit met Aspose.PDF voor .NET. Of u nu rapporten, facturen of andere gestructureerde documentatie genereert, een van de essentiële aspecten van documentontwerp is het opnemen van randen in tabellen. In deze tutorial onderzoeken we hoe u randen in een PDF-tabel kunt instellen met Aspose.PDF voor .NET. Aan het einde van dit artikel weet u hoe u de visuele aantrekkingskracht van uw PDF-documenten moeiteloos kunt verbeteren.

## Vereisten

Voordat u de code induikt, moet u ervoor zorgen dat u het volgende hebt:

1. Visual Studio: een geschikte Integrated Development Environment (IDE) om uw .NET-toepassingen te schrijven en uit te voeren.
2.  Aspose.PDF voor .NET Library: Zorg ervoor dat u deze bibliotheek hebt geïnstalleerd. U kunt deze rechtstreeks downloaden van[Aspose PDF voor .NET-releases](https://releases.aspose.com/pdf/net/).
3. Basiskennis van C#: Kennis van C#-programmering helpt u de code-implementatie beter te begrijpen.
4. .NET Framework: Elke versie die compatibel is met Aspose.PDF voor .NET.

## Pakketten importeren

Om te beginnen moet u de benodigde pakketten importeren uit de Aspose-bibliotheek. De vereiste primaire naamruimte is:

```csharp
using System.IO;
using System;
using Aspose.Pdf;
```

Hiermee krijgt u toegang tot de klassen en methoden die u nodig hebt om PDF-documenten te maken en te bewerken.

Laten we het proces voor het toevoegen van een tabel met randen aan een PDF-document opsplitsen in beheersbare stappen.

## Stap 1: Definieer de documentdirectory

Eerst het belangrijkste! U wilt de directory opgeven waar uw PDF wordt opgeslagen. Zorg ervoor dat u dit pad bijwerkt volgens uw systeem.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Hiermee wordt het basispad voor uw uitvoerbestand ingesteld, dus vergeet niet om dit te wijzigen`"YOUR DOCUMENT DIRECTORY"` naar een daadwerkelijk pad op uw machine.

## Stap 2: Instantieer het documentobject

 Vervolgens moet u een exemplaar van de maken`Document` klasse. Deze klasse vertegenwoordigt het hele PDF-document waarmee u gaat werken.

```csharp
Document doc = new Document();
```

 Door het instantiëren van de`Document` object, u bereidt zich voor om pagina's en inhoud aan uw PDF toe te voegen.

## Stap 3: Een pagina toevoegen aan het document

Elke PDF bestaat uit één of meer pagina's. In deze stap voegen we een nieuwe pagina toe aan ons PDF-document.

```csharp
Page page = doc.Pages.Add();
```

Hier vergroten we ons document door een lege pagina toe te voegen waar onze tabel komt. Zie het als het voorbereiden van een leeg canvas voor een meesterwerk!

## Stap 4: Het BorderInfo-object maken

 Nu is het tijd om de randen voor onze tafel in te stellen. De`BorderInfo` Met de klasse kunt u randeigenschappen opgeven.

```csharp
Aspose.Pdf.BorderInfo border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All);
```

 In deze lijn creëren we een`BorderInfo` object dat op alle zijden van de cellen van toepassing is.

## Stap 5: Stel de randstijlen in

Vervolgens specificeren we hoe de randen eruit moeten zien. Hier kun je creatief aan de slag!

```csharp
border.Top.IsDoubled = true;
border.Bottom.IsDoubled = true;
```

In dit voorbeeld geven we aan dat de boven- en onderranden verdubbeld moeten worden. Dit is geweldig om nadruk en visuele diepte aan uw tabel toe te voegen.

## Stap 6: Instantieer het tabelobject

Nu de randen zijn gedefinieerd, is het tijd om de tabel te maken.

```csharp
Aspose.Pdf.Table table = new Aspose.Pdf.Table();
```

Nu hebben we een lege tabel die klaar is om data in te bewaren. Het is alsof je een skeletstructuur creëert waarop je kunt bouwen.

## Stap 7: Kolombreedtes definiëren

Voor elke tabel is het cruciaal om de kolombreedtes in te stellen. Dit zorgt ervoor dat uw content goed past en er georganiseerd uitziet.

```csharp
table.ColumnWidths = "100";
```

Deze lijn stelt een uniforme breedte van 100 punten in voor alle kolommen in onze tabel. U kunt dit aanpassen op basis van uw contentbehoeften.

## Stap 8: Maak een rij

Elke tabel heeft minimaal één rij nodig, dus die gaan we nu toevoegen.

```csharp
Aspose.Pdf.Row row = table.Rows.Add();
```

Met deze opdracht voegen we een nieuwe rij toe aan onze zojuist gemaakte tabel. Zoals bij het leggen van de fundering van een gebouw, bouwt alles hierop voort.

## Stap 9: Een cel met tekst toevoegen

Laten we nu wat inhoud toevoegen aan onze tabel door een cel te maken. Cellen zijn de plek waar de daadwerkelijke data zich bevindt.

```csharp
Aspose.Pdf.Cell cell = row.Cells.Add("some text");
```

 Voel je vrij om te vervangen`"some text"` met elke string die u wilt weergeven. Dit kan een label, een nummer of andere tekstuele informatie zijn die nodig is voor uw document.

## Stap 10: Stel de rand voor de cel in

Hier gebeurt de magie! U wijst nu de eerder gedefinieerde rand toe aan de cel in onze tabel.

```csharp
cell.Border = border;
```

Nu is de cel gestyled met een dubbele rand aan de boven- en onderkant, precies zoals we hebben gespecificeerd. Het is alsof je je content aankleedt voor een speciale gelegenheid.

## Stap 11: Voeg de tabel toe aan de pagina

Zodra alles is ingesteld, is het tijd om de tabel toe te voegen aan de pagina waar deze moet worden weergegeven.

```csharp
page.Paragraphs.Add(table);
```

Deze regel integreert de tabel in de inhoud van de pagina. Stel je voor dat je het voltooide schilderij op een galeriemuur plaatst.

## Stap 12: Sla het document op

Ten slotte hoeft u uw document alleen nog maar op te slaan in de opgegeven map.

```csharp
dataDir = dataDir + "TableBorderTest_out.pdf";
doc.Save(dataDir);
```

Zorg ervoor dat u de bestandsnaam indien nodig aanpast! Wanneer u uw programma uitvoert, wordt uw PDF met randen op de tabel gemaakt en opgeslagen op de gedefinieerde locatie.

## Conclusie

Het maken van een PDF-document met een tabel met randen kan de leesbaarheid en professionaliteit aanzienlijk verbeteren. Met behulp van Aspose.PDF voor .NET wordt deze taak eenvoudig en efficiënt. Door de stappen in deze tutorial te volgen, kunt u eenvoudig randen op uw tabellen instellen, waardoor uw PDF-documenten niet alleen functioneel, maar ook visueel aantrekkelijk worden.

## Veelgestelde vragen

### Kan ik de randstijl wijzigen naar stippel- of streepjesrand?  
 Ja! U kunt de randeigenschappen in de`BorderInfo` object om stippel- of streepranden te maken door de juiste eigenschappen in te stellen.

### Ondersteunt Aspose.PDF afbeeldingen in tabellen?  
 Absoluut! U kunt afbeeldingen toevoegen aan tabelcellen, net zoals u dat met tekst kunt doen, door de`Cell` methoden van de klasse.

### Hoe kan ik verschillende breedtes voor verschillende kolommen opgeven?  
 U kunt elke kolombreedte afzonderlijk definiëren door een reeks breedtes te gebruiken, zoals`"100;150;200"`.

### Kan ik meerdere tabellen op dezelfde pagina maken?  
Ja! U kunt zoveel tabellen maken en toevoegen als u nodig hebt op dezelfde pagina door de stappen voor het maken van tabellen te herhalen.

### Is er een manier om stijlen toe te passen op de tabelcellen?  
 Zeker! U kunt verschillende eigenschappen instellen, zoals achtergrondkleur, tekststijl en uitlijning op de`Cell` voorwerp.