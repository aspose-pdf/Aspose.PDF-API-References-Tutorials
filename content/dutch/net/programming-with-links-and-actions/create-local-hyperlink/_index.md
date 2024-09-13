---
title: Lokale hyperlink maken in PDF-bestand
linktitle: Lokale hyperlink maken in PDF-bestand
second_title: Aspose.PDF voor .NET API-referentie
description: Leer hoe u moeiteloos lokale hyperlinks in PDF-bestanden kunt maken met Aspose.PDF voor .NET met onze stapsgewijze handleiding.
type: docs
weight: 40
url: /nl/net/programming-with-links-and-actions/create-local-hyperlink/
---
## Invoering

In deze gids leiden we u door het proces van het maken van lokale hyperlinks in een PDF-bestand met Aspose.PDF voor .NET. We zullen elke stap duidelijk uiteenzetten, zodat u het moeiteloos kunt volgen, zelfs als u nieuw bent in de wereld van PDF-manipulatie.

## Vereisten

Voordat we ons in de code storten, controleren we eerst of je alles hebt wat je nodig hebt:

1.  Visual Studio: Dit heb je nodig om je .NET-applicaties te ontwikkelen. Download het van de[website](https://visualstudio.microsoft.com/).
2.  Aspose.PDF voor .NET: U kunt deze bibliotheek downloaden via de[downloadlink hier](https://releases.aspose.com/pdf/net/)Het wordt geleverd met een uitgebreide set functies voor PDF-manipulatie.
3. Basiskennis van C#: Een beetje kennis van C#-programmering is handig, maar maak je geen zorgen: we gaan de code regel voor regel doornemen.
4.  .NET Framework: Zorg ervoor dat u het .NET Framework op uw machine hebt geïnstalleerd. U kunt de vereisten controleren op Aspose.PDF[documentatie](https://reference.aspose.com/pdf/net/).

Nu u aan deze vereisten hebt voldaan, kunt u leren hoe u lokale hyperlinks in uw PDF-documenten kunt maken!

## Pakketten importeren

Nu u helemaal voorbereid bent, is het tijd om de benodigde pakketten in uw C#-project te importeren. De Aspose.PDF-bibliotheek bevat alle klassen die we nodig hebben. Dit is hoe u dat doet:

### Open uw project

Open uw bestaande .NET-project of maak een nieuw project in Visual Studio. Als u helemaal opnieuw begint, selecteert u 'Een nieuw project maken' in het opstartscherm.

### Referentie toevoegen aan Aspose.PDF

 Klik met de rechtermuisknop op "Dependencies" in uw projectmap in Solution Explorer. Selecteer "Manage NuGet Packages" en zoek vervolgens naar`Aspose.PDF`. Installeer de nieuwste versie die beschikbaar is. Dit brengt alle tools die u nodig hebt voor het maken en bewerken van PDF's.

### Naamruimten importeren

Voeg bovenaan uw .cs-bestand using-richtlijnen toe voor de Aspose.PDF-bibliotheek, zoals deze:

```csharp
using System;
using System.IO;
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

Op deze manier krijgt u toegang tot de functies van de bibliotheek.

Laten we het proces van het maken van lokale hyperlinks opsplitsen in eenvoudige stappen. Elke stap wordt uitgebreid uitgelegd om u te helpen de logica erachter te begrijpen.

## Stap 1: Documentinstantie instellen

In deze stap maakt u een nieuw exemplaar van de klasse Document. Dit exemplaar vertegenwoordigt het PDF-bestand waarmee u gaat werken.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY"; // Stel uw documentmap in
Document doc = new Document(); // Documentinstantie maken
```
 De`dataDir` variabele is waar uw nieuw gecreëerde PDF zal verblijven. U zult moeten vervangen`"YOUR DOCUMENT DIRECTORY"` met het werkelijke pad op uw systeem. De`Document` klasse maakt een nieuw PDF-document waar we pagina's en links aan kunnen toevoegen.

## Stap 2: Een pagina toevoegen aan het document

Vervolgens gaat u een pagina toevoegen aan uw PDF-document. 

```csharp
Page page = doc.Pages.Add(); // Pagina toevoegen aan paginaverzameling
```
 De`Pages.Add()` methode voegt een nieuwe pagina toe aan het document. Dit is waar al uw content zal staan.

## Stap 3: Maak een tekstfragment

Laten we nu een tekststuk maken dat als klikbare link fungeert.

```csharp
Aspose.Pdf.Text.TextFragment text = new Aspose.Pdf.Text.TextFragment("link page number test to page 7");
```
 De`TextFragment` vertegenwoordigt een tekstsegment in de PDF. Hier maken we een link die gebruikers vertelt dat ze naar pagina 7 gaan.

## Stap 4: Lokale hyperlink maken

Hier gebeurt de magie! Je moet een lokale hyperlink maken die het tekstfragment vertelt waar het naartoe moet wijzen.

```csharp
Aspose.Pdf.LocalHyperlink link = new Aspose.Pdf.LocalHyperlink(); // Lokale hyperlink maken
link.TargetPageNumber = 7; //Doelpagina instellen voor linkinstantie
text.Hyperlink = link; // Hyperlink TextFragment instellen
```
 De`LocalHyperlink` klasse is wat ons in staat stelt om naar andere pagina's in hetzelfde document te verwijzen. Door in te stellen`TargetPageNumber` tot 7, vertelt u de hyperlink dat deze naar die specifieke pagina moet springen wanneer erop wordt geklikt.

## Stap 5: Voeg het tekstfragment toe aan de pagina

Nadat u de hyperlink hebt ingesteld, is het tijd om ons tekstfragment toe te voegen aan de pagina die u hebt gemaakt.

```csharp
page.Paragraphs.Add(text); // Voeg tekst toe aan de alineaverzameling van de pagina
```
Met deze regel voegt u uw klikbare tekst toe aan de verzameling alinea's van de pagina.

## Stap 6: Maak een ander tekstfragment (optioneel)

Laten we een extra hyperlink toevoegen om terug te navigeren naar pagina 1.

```csharp
text = new TextFragment("link page number test to page 1"); // Nieuw TextFragment maken
text.IsInNewPage = true; // Voeg het toe aan een nieuwe pagina
```
 Een nieuwe maken`TextFragment` voor de tweede link stellen we in`IsInNewPage` naar true, wat aangeeft dat deze tekst op een nieuwe pagina wordt geplaatst.

## Stap 7: De tweede lokale hyperlink instellen

Net als voorheen maakt u een nieuwe lokale hyperlink voor pagina 1.

```csharp
link = new LocalHyperlink(); // Een ander lokaal hyperlinkexemplaar maken
link.TargetPageNumber = 1; //Doelpagina voor tweede hyperlink instellen
text.Hyperlink = link; // Link instellen voor tweede TextFragment
```
Deze hyperlink verwijst naar pagina 1, zodat gebruikers terug kunnen gaan als ze de tweede pagina bereiken.

## Stap 8: Voeg het tweede tekstfragment toe aan de nieuwe pagina

Laten we deze tekst nu aan de pagina toevoegen.

```csharp
page.Paragraphs.Add(text); // Tekst toevoegen aan alineaverzameling van pagina-object
```
Net als bij stap 5 voegt deze regel de nieuwe hyperlinktekst toe aan de nieuw aangemaakte pagina.

## Stap 9: Sla het document op

Eindelijk is het tijd om je harde werk op te slaan! 

```csharp
dataDir = dataDir + "CreateLocalHyperlink_out.pdf"; // Geef de naam van het uitvoerbestand op
doc.Save(dataDir); // Bijgewerkt document opslaan
Console.WriteLine("\nLocal hyperlink created successfully.\nFile saved at " + dataDir);
```
 Dit combineert uw directorypad met de bestandsnaam.`Save()` Met deze methode wordt uw document opgeslagen en ontvangt u een bevestigingsbericht dat alles goed is verlopen!

## Conclusie

Lokale hyperlinks maken in PDF-bestanden met Aspose.PDF voor .NET is niet alleen een coole truc; het is een praktische functie die de navigatie en gebruikerservaring verbetert. U bent nu uitgerust met de kennis om uw lezers rechtstreeks naar de informatie te verwijzen die ze nodig hebben. Denk maar eens terug aan onze eerste analogie: geen verloren zielen meer die door eindeloze pagina's dwalen.

## Veelgestelde vragen

### Wat is Aspose.PDF voor .NET?
Aspose.PDF voor .NET is een bibliotheek waarmee ontwikkelaars programmatisch PDF-documenten kunnen maken, bewerken en converteren met behulp van het .NET Framework.

### Kan ik hyperlinks naar externe webpagina's maken?
Ja, Aspose.PDF ondersteunt ook het maken van hyperlinks naar externe URL's, naast lokale hyperlinks binnen de PDF.

### Is er een gratis proefversie voor Aspose.PDF?
 Absoluut! U kunt de gratis proefperiode openen via de[plaats](https://releases.aspose.com/).

### Welke programmeertalen ondersteunt Aspose?
Aspose biedt bibliotheken voor verschillende programmeertalen, waaronder Java, C++, en Python, onder andere.

### Hoe krijg ik ondersteuning voor Aspose-producten?
 U kunt ondersteuning zoeken via de[Aspose-forum](https://forum.aspose.com/c/pdf/10).