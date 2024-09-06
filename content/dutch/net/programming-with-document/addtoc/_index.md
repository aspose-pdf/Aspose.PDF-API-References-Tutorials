---
title: Inhoudsopgave toevoegen aan PDF-bestand
linktitle: Inhoudsopgave toevoegen aan PDF-bestand
second_title: Aspose.PDF voor .NET API-referentie
description: Leer hoe u een inhoudsopgave aan een PDF toevoegt met Aspose.PDF voor .NET. Deze stapsgewijze handleiding vereenvoudigt het proces en zorgt voor eenvoudige navigatie binnen uw documenten.
type: docs
weight: 40
url: /nl/net/programming-with-document/addtoc/
---
## Invoering

Heb je ooit eindeloos door een lange PDF gescrold, terwijl je wenste dat er een goed georganiseerde inhoudsopgave in zat? Nou, vandaag is je geluksdag! In deze tutorial leer je hoe je een inhoudsopgave aan je PDF-bestand toevoegt met Aspose.PDF voor .NET. Of je nu werkt aan een complex rapport, een e-book of een zakelijk voorstel, een inhoudsopgave kan je document transformeren in een professioneel, navigeerbaar meesterwerk.

## Vereisten

Voordat we in de code duiken, controleren we of je alles hebt wat je nodig hebt:

1. Aspose.PDF voor .NET: Zorg ervoor dat u de Aspose.PDF-bibliotheek hebt gedownload en geïnstalleerd. U kunt deze downloaden van[hier](https://releases.aspose.com/pdf/net/).
   
2. Ontwikkelomgeving: Zorg ervoor dat u een .NET-ontwikkelomgeving zoals Visual Studio op uw computer hebt ingesteld.

3.  Licentie: Als u geen licentie hebt, kunt u een gratis proefversie krijgen of een tijdelijke licentie aanvragen[hier](https://purchase.aspose.com/temporary-license/).

## Pakketten importeren

Om te beginnen, zorg ervoor dat u de benodigde namespaces aan het begin van uw codebestand importeert. Dit is hoe:

```csharp
using System.IO;
using System;
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

Met deze naamruimten krijgt u toegang tot PDF-specifieke functionaliteiten en kunt u tekstelementen in uw document bewerken.

Laten we deze taak opsplitsen in kleine stapjes. Elke stap begeleidt u door het proces van het maken en invoegen van een TOC in uw PDF-document.

## Stap 1: Laad het PDF-document

Het eerste wat we moeten doen, is het bestaande PDF-bestand laden waaraan we de inhoudsopgave willen toevoegen.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "AddTOC.pdf");
```

 In deze stap specificeren we het pad naar de documentenmap en laden we de PDF met behulp van de`Document` object. Zorg ervoor dat u het vervangt`"YOUR DOCUMENT DIRECTORY"` met het daadwerkelijke pad naar uw bestand.

## Stap 2: Voeg een nieuwe pagina in voor de inhoudsopgave

Vervolgens voegen we een nieuwe pagina toe aan het begin van het PDF-document. Deze pagina zal de inhoudsopgave hosten.

```csharp
Page tocPage = doc.Pages.Insert(1);
```

Door de inhoudsopgavepagina aan het begin te plaatsen, zorgen we ervoor dat deze het allereerste is wat lezers in de PDF zien.

## Stap 3: Maak een TOC-informatieobject

Laten we nu een object maken dat de TOC-informatie vertegenwoordigt. We voegen ook een titel toe aan de TOC om deze te laten opvallen.

```csharp
TocInfo tocInfo = new TocInfo();
TextFragment title = new TextFragment("Table Of Contents");
title.TextState.FontSize = 20;
title.TextState.FontStyle = FontStyles.Bold;
tocInfo.Title = title;
tocPage.TocInfo = tocInfo;
```

Hier hebben we de titel van de inhoudsopgave ingesteld op 'Inhoudsopgave', het lettertype vergroot en de tekst vetgedrukt gemaakt om de tekst te benadrukken.

## Stap 4: Definieer TOC-elementen

In deze stap definiëren we de elementen (of koppen) die in de TOC worden weergegeven. Deze elementen helpen lezers om naar specifieke secties van het document te navigeren.

```csharp
string[] titles = new string[4];
titles[0] = "First page";
titles[1] = "Second page";
titles[2] = "Third page";
titles[3] = "Fourth page";
```

We hebben een reeks strings gemaakt die als inhoudsopgave-items dienen en die overeenkomen met verschillende pagina's in de PDF.

## Stap 5: Inhoudsopgavekoppen maken

Nu komt het cruciale onderdeel: het toevoegen van koppen aan de inhoudsopgave en het koppelen ervan aan de bijbehorende pagina's.

```csharp
for (int i = 0; i < 2; i++)
{
    Aspose.Pdf.Heading heading2 = new Aspose.Pdf.Heading(1);
    TextSegment segment2 = new TextSegment();
    heading2.TocPage = tocPage;
    heading2.Segments.Add(segment2);

    heading2.DestinationPage = doc.Pages[i + 2];
    heading2.Top = doc.Pages[i + 2].Rect.Height;
    segment2.Text = titles[i];

    tocPage.Paragraphs.Add(heading2);
}
```

Dit is wat er gebeurt:
- Kop: Wij creëren een`Heading` object en voeg een toe`TextSegment` ernaartoe.
- Bestemmingspagina: Wij stellen de pagina in waarnaar elke koptekst zal linken.
- Bovenste positie: Wij geven de positie op de pagina aan waar de koptekst naar verwijst.
- Tekst: Elke kop krijgt een bijbehorende titel uit de matrix die we eerder hebben gemaakt.

Deze lus maakt koppen voor de eerste twee elementen in de inhoudsopgave en koppelt deze aan de bijbehorende pagina's.

## Stap 6: Sla de PDF op met de inhoudsopgave

Nadat we alle elementen van de inhoudsopgave hebben toegevoegd, is het tijd om de bijgewerkte PDF op te slaan.

```csharp
dataDir = dataDir + "TOC_out.pdf";
doc.Save(dataDir);
```

Het bestand is nu opgeslagen met de TOC toegevoegd aan de PDF. Gefeliciteerd, u hebt succesvol een inhoudsopgave toegevoegd!

## Stap 7: Bevestigingsbericht

Om de gebruiker te laten weten dat het proces is voltooid, tonen we een eenvoudig bericht in de console.

```csharp
Console.WriteLine("\nTOC added successfully to an existing PDF.\nFile saved at " + dataDir);
```

## Conclusie

En daar heb je het! Met Aspose.PDF voor .NET is het toevoegen van een inhoudsopgave aan een PDF niet alleen eenvoudig, maar ook aanpasbaar. Of je nu simpele navigatielinks of complexe structuren moet maken, deze tool heeft het voor je. Dus vergeet niet om de volgende keer dat je aan een lange PDF werkt, een inhoudsopgave toe te voegen voor een professionele touch!

## Veelgestelde vragen

### Kan ik het uiterlijk van de inhoudsopgave in Aspose.PDF aanpassen?  
Ja, u kunt het uiterlijk van de inhoudsopgave volledig aanpassen, inclusief het lettertype, de grootte en de uitlijning.

### Hoe voeg ik subkoppen toe aan de inhoudsopgave?  
 U kunt subkoppen toevoegen door de`Heading` niveau (bijv.`Heading(2)`) om een hiërarchische inhoudsopgave te maken.

### Is het mogelijk om de inhoudsopgave automatisch bij te werken als het document verandert?  
Nee, de TOC wordt niet automatisch bijgewerkt. U moet deze opnieuw maken als de documentstructuur verandert.

### Kan ik inhoudsopgavevermeldingen koppelen aan externe documenten?  
Ja, u kunt hyperlinks gebruiken om inhoudsopgave-items te koppelen aan externe PDF's of URL's.

### Ondersteunt Aspose.PDF inhoudsopgaven met meerdere niveaus?  
Ja, Aspose.PDF ondersteunt inhoudsopgaven op meerdere niveaus voor complexe documenten met subsecties.