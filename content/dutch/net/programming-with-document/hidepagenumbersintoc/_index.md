---
title: Verberg paginanummers in inhoudsopgave
linktitle: Verberg paginanummers in inhoudsopgave
second_title: Aspose.PDF voor .NET API-referentie
description: Leer hoe u paginanummers in de inhoudsopgave verbergt met Aspose.PDF voor .NET. Volg deze gedetailleerde handleiding met codevoorbeelden om professionele PDF's te maken.
type: docs
weight: 220
url: /nl/net/programming-with-document/hidepagenumbersintoc/
---
## Invoering

Wanneer u met PDF's werkt, wilt u soms een inhoudsopgave (TOC) genereren, maar de zaken overzichtelijk houden door de paginanummers te verbergen. Misschien leest het document beter zonder, of misschien is het een esthetische keuze. Wat uw reden ook is, als u met Aspose.PDF voor .NET werkt, laat deze tutorial u precies zien hoe u paginanummers in uw TOC kunt verbergen.

## Vereisten

Voordat we beginnen, zijn er een paar dingen die je op orde moet hebben. Hier is een snelle checklist:

- Visual Studio geïnstalleerd: U hebt een werkende versie van Visual Studio nodig om te kunnen coderen.
- Aspose.PDF voor .NET-bibliotheek: Zorg ervoor dat u de Aspose.PDF voor .NET-bibliotheek hebt geïnstalleerd.
  -  Downloadlink:[Aspose.PDF voor .NET](https://releases.aspose.com/pdf/net/)
- Tijdelijke licentie: Als u de functies uitprobeert, is het handig om een tijdelijke licentie te hebben.
  -  Tijdelijke licentie:[Hier verkrijgbaar](https://purchase.aspose.com/temporary-license/)

## Pakketten importeren

Voordat u in de code duikt, moet u ervoor zorgen dat u de volgende naamruimten in uw C#-project importeert. Deze bieden de benodigde klassen en methoden voor het werken met PDF-documenten en het maken van uw inhoudsopgave (TOC).

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

Nu uw omgeving gereed is en de pakketten zijn geïmporteerd, gaan we elke stap van het proces uitsplitsen. We behandelen elk onderdeel van de code om duidelijkheid te garanderen, zodat u het gemakkelijk kunt volgen.

## Stap 1: Initialiseer uw PDF-document

Het eerste wat we moeten doen is een nieuw PDF-document maken en een pagina voor de inhoudsopgave (TOC) toevoegen.


```csharp
// Het pad naar de documentenmap.
string dataDir = "YOUR DOCUMENT DIRECTORY";
string outFile = dataDir + "HiddenPageNumbers_out.pdf";
Document doc = new Document();
Page tocPage = doc.Pages.Add();
```

- dataDir: Dit is de map waar uw uitvoerbestand wordt opgeslagen.
- Document(): Initialiseert een nieuw PDF-document.
- Pages.Add(): Voegt een nieuwe, lege pagina toe aan het document, die later uw inhoudsopgave zal bevatten.

## Stap 2: Inhoudsopgave-info en titel instellen

Vervolgens definiëren we de inhoudsopgave-informatie, inclusief de titel die bovenaan de inhoudsopgave wordt weergegeven.

```csharp
TocInfo tocInfo = new TocInfo();
TextFragment title = new TextFragment("Table Of Contents");
title.TextState.FontSize = 20;
title.TextState.FontStyle = FontStyles.Bold;
tocInfo.Title = title;
tocPage.TocInfo = tocInfo;
```

- TocInfo: Dit object bevat alle informatie over de inhoudsopgave.
- TextFragment: Geeft de tekst van de TOC-titel weer. Hier hebben we deze ingesteld als 'Inhoudsopgave'.
- FontStyle: We stylen de inhoudsopgavetitel door de grootte in te stellen op 20 en deze vet te maken.
- tocPage.TocInfo: We wijzen de inhoudsopgave-info toe aan de pagina waarop de inhoudsopgave wordt weergegeven.

## Stap 3: Verberg paginanummers in de inhoudsopgave

Nu het leuke gedeelte! Hier configureren we de TOC om de paginanummers te verbergen.

```csharp
tocInfo.IsShowPageNumbers = false;
tocInfo.FormatArrayLength = 4;
```

-  IsShowPageNumbers: Dit is de magische schakelaar die de paginanummers verbergt. Stel deze in op`false`, en de paginanummers verschijnen niet in de inhoudsopgave.
- FormatArrayLength: We stellen dit in op 4, wat aangeeft dat we de opmaak willen definiëren voor vier niveaus van inhoudsopgavekoppen.

## Stap 4: Pas de opmaak van de inhoudsopgave aan

Om uw inhoudsopgave meer stijl te geven, definiëren we nu de opmaak voor verschillende niveaus van koppen.

```csharp
tocInfo.FormatArray[0].Margin.Right = 0;
tocInfo.FormatArray[0].TextState.FontStyle = FontStyles.Bold | FontStyles.Italic;
tocInfo.FormatArray[1].Margin.Left = 30;
tocInfo.FormatArray[1].TextState.Underline = true;
tocInfo.FormatArray[1].TextState.FontSize = 10;
tocInfo.FormatArray[2].TextState.FontStyle = FontStyles.Bold;
tocInfo.FormatArray[3].TextState.FontStyle = FontStyles.Bold;
```

- FormatArray: Deze array regelt de opmaak van TOC-items. Elke index vertegenwoordigt een ander kopniveau.
- Marges en tekststijl: We stellen marges in en passen lettertypen toe, zoals vet, cursief en onderstrepen, voor elk kopniveau.

## Stap 5: Koppen toevoegen aan het document

Tot slot voegen we de koppen toe die deel uitmaken van de inhoudsopgave.

```csharp
Page page = doc.Pages.Add();
for (int Level = 1; Level != 5; Level++)
{ 
    Heading heading2 = new Heading(Level); 
    TextSegment segment2 = new TextSegment(); 
    heading2.TocPage = tocPage; 
    heading2.Segments.Add(segment2); 
    heading2.IsAutoSequence = true; 
    segment2.Text = "this is heading of level " + Level; 
    heading2.IsInList = true; 
    page.Paragraphs.Add(heading2); 
}
```

- Heading en TextSegment: Deze vertegenwoordigen de koppen die in uw TOC verschijnen. Elk niveau krijgt zijn eigen kop.
- IsAutoSequence: Nummert de koppen automatisch.
- IsInList: zorgt ervoor dat elke kop in de inhoudsopgave wordt weergegeven.

## Stap 6: Sla het document op

Zodra alles is ingesteld, slaat u het PDF-document op in het door u opgegeven uitvoerbestand.

```csharp
doc.Save(outFile);
```

En dat is alles! U hebt succesvol een PDF met een inhoudsopgave gemaakt, en de paginanummers zijn verborgen!

## Conclusie

Het maken van een inhoudsopgave in een PDF en het verbergen van paginanummers lijkt misschien lastig, maar met Aspose.PDF voor .NET is het een fluitje van een cent. Door deze stapsgewijze handleiding te volgen, hebt u geleerd hoe u de TOC-indeling kunt aanpassen, paginanummers kunt verbergen en verschillende stijlen op uw koppen kunt toepassen. Nu kunt u professionele PDF's maken die zijn afgestemd op uw exacte behoeften.

## Veelgestelde vragen

### Kan ik paginanummers weergeven voor specifieke koppen in de inhoudsopgave?
Nee, Aspose.PDF verbergt of toont paginanummers voor de gehele TOC. U kunt ze niet selectief verbergen voor specifieke items.

### Is het mogelijk om meer niveaus aan de inhoudsopgave toe te voegen?
 Ja, u kunt de`FormatArrayLength` om meer niveaus van inhoudsopgavekoppen te definiëren.

### Hoe kan ik het lettertype voor alle inhoudsopgave-items wijzigen?
 U kunt het lettertype wijzigen door de`TextState.Font` eigenschap voor elk niveau in de`FormatArray`.

### Kan ik hyperlinks in de inhoudsopgave invoegen?
 Ja, u kunt elk TOC-item koppelen aan een specifieke sectie in het document met behulp van de`Heading.TocPage` eigendom.

### Heb ik een licentie nodig voor Aspose.PDF?
Ja, een geldige licentie is vereist voor productiegebruik. U kunt een tijdelijke licentie krijgen[hier](https://purchase.aspose.com/temporary-license/) om de functies te testen.