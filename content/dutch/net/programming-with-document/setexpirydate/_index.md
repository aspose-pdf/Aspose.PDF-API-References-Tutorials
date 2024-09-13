---
title: Vervaldatum instellen in PDF-bestand
linktitle: Vervaldatum instellen in PDF-bestand
second_title: Aspose.PDF voor .NET API-referentie
description: Leer hoe u een vervaldatum in PDF-bestanden instelt met Aspose.PDF voor .NET. Verbeter de beveiliging van documenten met deze stapsgewijze handleiding.
type: docs
weight: 300
url: /nl/net/programming-with-document/setexpirydate/
---
## Invoering

In het digitale tijdperk van vandaag is het beheren en beveiligen van documenten belangrijker dan ooit. Stel je voor dat je een PDF verstuurt die na een bepaalde datum automatisch ontoegankelijk wordt. Klinkt als magie, toch? Nou, met Aspose.PDF voor .NET kun je eenvoudig een vervaldatum instellen voor je PDF-bestanden. Deze functie is vooral handig voor gevoelige documenten die na een bepaalde periode moeten worden geblokkeerd. In deze tutorial leiden we je stap voor stap door het proces van het instellen van een vervaldatum in een PDF-bestand. Dus pak je codeerhoed en laten we erin duiken!

## Vereisten

Voordat we beginnen, zijn er een paar dingen die u moet regelen:

1. Development Environment: Zorg ervoor dat u een .NET development environment hebt ingesteld. Dit kan Visual Studio zijn of een andere IDE die .NET ondersteunt.
2.  Aspose.PDF voor .NET: U moet de Aspose.PDF-bibliotheek geïnstalleerd hebben. Als u dit nog niet gedaan hebt, kunt u deze downloaden van[hier](https://releases.aspose.com/pdf/net/).
3. Basiskennis van C#: Deze tutorial gaat ervan uit dat u een basiskennis van C#-programmering hebt. Als u nieuw bent met C#, maak u dan geen zorgen! We houden het simpel en duidelijk.

## Pakketten importeren

Om aan de slag te gaan met Aspose.PDF, moet u de benodigde namespaces importeren in uw C#-project. Dit is hoe u dat kunt doen:

```csharp
using System.IO;
using System;
using Aspose.Pdf;
using Aspose.Pdf.Annotations;
using Aspose.Pdf.Text;
```

Met deze naamruimten krijgt u toegang tot de kernfunctionaliteiten die nodig zijn voor het werken met PDF-documenten in Aspose.PDF.

## Stap 1: Stel uw documentenmap in

Allereerst moet u het pad naar uw documentenmap opgeven. Dit is waar uw output-PDF wordt opgeslagen. 

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Vervangen`"YOUR DOCUMENT DIRECTORY"` met het daadwerkelijke pad waar u uw PDF-bestand wilt opslaan. Het is alsof u tegen uw programma zegt: "Hé, hier bewaar ik mijn bestanden!"

## Stap 2: Instantieer het documentobject

 Vervolgens moet u een nieuw exemplaar van de`Document` klasse. Dit is je canvas waar je je PDF gaat maken.

```csharp
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
```

 Denk aan de`Document` object als een leeg vel papier. Je kunt er inhoud aan toevoegen zoals je wilt!

## Stap 3: Voeg een pagina toe aan de PDF

Nu u uw document hebt ingesteld, is het tijd om er een pagina aan toe te voegen. Dit is waar uw content komt.

```csharp
doc.Pages.Add();
```

Je hebt zojuist een nieuwe pagina in je PDF gemaakt. Het is alsof je een nieuwe pagina in je notitieboek toevoegt waar je je gedachten kunt opschrijven.

## Stap 4: Voeg tekst toe aan de pagina

Laten we deze pagina wat interessanter maken door wat tekst toe te voegen. We voegen een eenvoudig "Hello World"-bericht toe.

```csharp
doc.Pages[1].Paragraphs.Add(new TextFragment("Hello World..."));
```

Deze regel code voegt een tekstfragment toe aan de eerste pagina van uw PDF. Het is alsof u een titel bovenaan uw pagina schrijft!

## Stap 5: Maak JavaScript voor de vervaldatum

Nu komt het leuke gedeelte! Je maakt een JavaScript-actie die de vervaldatum van de PDF controleert. Als de huidige datum de vervaldatum overschrijdt, wordt de gebruiker gewaarschuwd met een bericht.

```csharp
JavascriptAction javaScript = new JavascriptAction(
"var year=2017;"
+ "var month=5;"
+ "today = new Date(); today = new Date(today.getFullYear(), today.getMonth());"
+ "expiry = new Date(year, month);"
+ "if (today.getTime() > expiry.getTime())"
+ "app.alert('The file is expired. You need a new one.');");
```

Dit is wat er gebeurt:
- U bepaalt het vervaljaar en de vervalmaand.
- Je krijgt de datum van vandaag.
- Je vergelijkt de datum van vandaag met de houdbaarheidsdatum.
- Als de houdbaarheidsdatum van vandaag verstreken is, verschijnt er een bericht!

## Stap 6: Stel JavaScript in als PDF-openactie

Nu moet u de JavaScript-actie instellen als de open-actie voor uw PDF-document. Dit betekent dat de JavaScript wordt uitgevoerd zodra de PDF wordt geopend.

```csharp
doc.OpenAction = javaScript;
```

Deze regel vertelt de PDF om de JavaScript uit te voeren wanneer iemand deze opent. Het is alsof je een herinnering instelt die afgaat zodra je je agenda opent!

## Stap 7: Sla het PDF-document op

Ten slotte is het tijd om uw PDF-document op te slaan met de vervaldatumfunctie. 

```csharp
dataDir = dataDir + "SetExpiryDate_out.pdf";
doc.Save(dataDir);
```

Deze regel slaat uw PDF op in de opgegeven directory met de naam "SetExpiryDate_out.pdf". Het is alsof u uw voltooide kunstwerk in een lijst plaatst!

## Conclusie

En daar heb je het! Je hebt met succes een PDF-bestand met een vervaldatum gemaakt met Aspose.PDF voor .NET. Deze functie verbetert niet alleen de beveiliging, maar zorgt er ook voor dat gevoelige informatie onder controle blijft. Of je nu contracten, rapporten of andere belangrijke documenten verstuurt, het instellen van een vervaldatum kan een game changer zijn.

## Veelgestelde vragen

### Wat is Aspose.PDF voor .NET?
Aspose.PDF voor .NET is een krachtige bibliotheek waarmee ontwikkelaars PDF-documenten in .NET-toepassingen kunnen maken, bewerken en converteren.

### Kan ik Aspose.PDF gratis gebruiken?
 Ja, u kunt een gratis proefversie van Aspose.PDF gebruiken. U kunt het downloaden[hier](https://releases.aspose.com/).

### Hoe kan ik Aspose.PDF kopen?
 kunt Aspose.PDF kopen door de website te bezoeken[aankooppagina](https://purchase.aspose.com/buy).

### Wat als ik ondersteuning nodig heb?
Als u vragen heeft of hulp nodig heeft, kunt u terecht op de[Aspose ondersteuningsforum](https://forum.aspose.com/c/pdf/10).

### Kan ik een tijdelijke licentie voor Aspose.PDF krijgen?
 Ja, u kunt een tijdelijke vergunning aanvragen[hier](https://purchase.aspose.com/temporary-license/).