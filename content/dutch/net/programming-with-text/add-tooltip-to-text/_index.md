---
title: Tooltip toevoegen aan tekst in PDF-bestand
linktitle: Tooltip toevoegen aan tekst in PDF-bestand
second_title: Aspose.PDF voor .NET API-referentie
description: Leer hoe u knopinfo aan tekst in een PDF-bestand kunt toevoegen met Aspose.PDF voor .NET.
type: docs
weight: 90
url: /nl/net/programming-with-text/add-tooltip-to-text/
---
Deze tutorial leidt u door het proces van het toevoegen van tooltips aan tekst in een PDF-bestand met behulp van Aspose.PDF voor .NET. De meegeleverde C#-broncode demonstreert de noodzakelijke stappen.

## Vereisten
Zorg ervoor dat u over het volgende beschikt voordat u begint:

- Visual Studio of een andere C#-compiler die op uw computer is geïnstalleerd.
- Aspose.PDF voor .NET-bibliotheek. Je kunt het downloaden van de officiële Aspose-website of een pakketbeheerder zoals NuGet gebruiken om het te installeren.

## Stap 1: Zet het project op
1. Maak een nieuw C#-project in de ontwikkelomgeving van uw voorkeur.
2. Voeg een verwijzing toe naar de Aspose.PDF voor .NET-bibliotheek.

## Stap 2: Importeer de vereiste naamruimten
In het codebestand waarin u knopinfo aan tekst wilt toevoegen, voegt u het volgende toe met behulp van richtlijnen bovenaan het bestand:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Forms;
using Aspose.Pdf.Text;
```

## Stap 3: Stel de documentmap in
 Zoek in de code de regel met de tekst`string dataDir = "YOUR DOCUMENT DIRECTORY";` en vervangen`"YOUR DOCUMENT DIRECTORY"` met het pad naar de map waar uw documenten zijn opgeslagen.

## Stap 4: Maak een voorbeelddocument met tekst
 Maak een nieuwe`Document` object en pagina's met tekstfragmenten toevoegen. In de meegeleverde code worden twee tekstfragmenten met de betreffende tooltiptekst aan het document toegevoegd.

```csharp
Document doc = new Document();
doc.Pages.Add().Paragraphs.Add(new TextFragment("Move the mouse cursor here to display a tooltip"));
doc.Pages[1].Paragraphs.Add(new TextFragment("Move the mouse cursor here to display a very long tooltip"));
doc.Save(outputFile);
```

## Stap 5: Open het document en zoek de tekstfragmenten
 Laad het gemaakte document met behulp van de`Document` constructor en vind de tekstfragmenten waarvoor tooltips nodig zijn`TextFragmentAbsorber`.

```csharp
Document document = new Document(outputFile);
TextFragmentAbsorber absorber = new TextFragmentAbsorber("Move the mouse cursor here to display a tooltip");
document.Pages.Accept(absorb);
TextFragmentCollection textFragments = absorb.TextFragments;
```

## Stap 6: Voeg tooltips toe aan de tekstfragmenten
 Loop door de geëxtraheerde tekstfragmenten en creëer onzichtbare knoppen op hun posities. Wijs de gewenste tooltiptekst toe aan de`AlternateName` eigendom van de`ButtonField`. Voeg de knopvelden toe aan het formulier van het document.

```csharp
foreach(TextFragment fragment in textFragments)
{
     ButtonField field = new ButtonField(fragment.Page, fragment.Rectangle);
     field. AlternateName = "Tooltip for text.";
     document.Form.Add(field);
}
```

## Stap 7: Herhaal dit voor extra tekstfragmenten met lange tooltips
Herhaal stap 5 en 6 voor tekstfragmenten met lange tooltips. Pas de zoekcriteria en tooltip-tekst dienovereenkomstig aan.

```csharp
absorb = new TextFragmentAbsorber("Move the mouse cursor here to display a very long tooltip");
document.Pages.Accept(absorb);
textFragments = absorb.TextFragments;

foreach(TextFragment fragment in textFragments)
{
     ButtonField field = new ButtonField(fragment.Page, fragment.Rectangle);
     field. AlternateName = "Long tooltip text goes here...";
     document.Form.Add(field);
}
```

## Stap 8: Sla het gewijzigde document op
 Sla het gewijzigde PDF-document op met behulp van de`Save` werkwijze van de`Document` voorwerp.

```csharp
document. Save(outputFile);
```

### Voorbeeldbroncode voor het toevoegen van knopinfo aan tekst met Aspose.PDF voor .NET 
```csharp
// Het pad naar de documentenmap.
string dataDir = "YOUR DOCUMENT DIRECTORY";
string outputFile = dataDir + "Tooltip_out.pdf";
// Maak een voorbeelddocument met tekst
Document doc = new Document();
doc.Pages.Add().Paragraphs.Add(new TextFragment("Move the mouse cursor here to display a tooltip"));
doc.Pages[1].Paragraphs.Add(new TextFragment("Move the mouse cursor here to display a very long tooltip"));
doc.Save(outputFile);
// Document met tekst openen
Document document = new Document(outputFile);
// Maak een TextAbsorber-object om alle zinnen te vinden die overeenkomen met de reguliere expressie
TextFragmentAbsorber absorber = new TextFragmentAbsorber("Move the mouse cursor here to display a tooltip");
// Accepteer het absorber voor de documentpagina's
document.Pages.Accept(absorber);
// Haal de geëxtraheerde tekstfragmenten op
TextFragmentCollection textFragments = absorber.TextFragments;
// Loop door de fragmenten
foreach (TextFragment fragment in textFragments)
{
	// Maak een onzichtbare knop op de positie van het tekstfragment
	ButtonField field = new ButtonField(fragment.Page, fragment.Rectangle);
	// De waarde van AlternateName wordt weergegeven als tooltip door een viewertoepassing
	field.AlternateName = "Tooltip for text.";
	// Knopveld toevoegen aan het document
	document.Form.Add(field);
}
// Het volgende zal een stukje zeer lange tooltip zijn
absorber = new TextFragmentAbsorber("Move the mouse cursor here to display a very long tooltip");
document.Pages.Accept(absorber);
textFragments = absorber.TextFragments;
foreach (TextFragment fragment in textFragments)
{
	ButtonField field = new ButtonField(fragment.Page, fragment.Rectangle);
	// Zeer lange tekst instellen
	field.AlternateName = "Lorem ipsum dolor sit amet, consectetur adipiscing elit," +
							" sed do eiusmod tempor incididunt ut labore et dolore magna" +
							" aliqua. Ut enim ad minim veniam, quis nostrud exercitation" +
							" ullamco laboris nisi ut aliquip ex ea commodo consequat." +
							" Duis aute irure dolor in reprehenderit in voluptate velit" +
							" esse cillum dolore eu fugiat nulla pariatur. Excepteur sint" +
							" occaecat cupidatat non proident, sunt in culpa qui officia" +
							" deserunt mollit anim id est laborum.";
	document.Form.Add(field);
}
// Bewaar document
document.Save(outputFile);
```

## Conclusie
U hebt met succes tooltips toegevoegd aan tekst in een PDF-document met Aspose.PDF voor .NET. Het resulterende PDF-bestand is nu te vinden op het opgegeven uitvoerbestandspad.

## Veelgestelde vragen

#### Vraag: Wat is de focus van deze tutorial?

A: Deze tutorial richt zich op het toevoegen van tooltips aan tekst in een PDF-bestand met behulp van de Aspose.PDF voor .NET-bibliotheek. De meegeleverde C#-broncode demonstreert de stappen die nodig zijn om dit te bereiken.

#### Vraag: Welke naamruimten moeten voor deze tutorial worden geïmporteerd?

A: In het codebestand waarin u knopinfo aan tekst wilt toevoegen, importeert u de volgende naamruimten aan het begin van het bestand:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Forms;
using Aspose.Pdf.Text;
```

#### Vraag: Hoe geef ik de documentmap op?

 A: Zoek de regel in de code`string dataDir = "YOUR DOCUMENT DIRECTORY";` en vervangen`"YOUR DOCUMENT DIRECTORY"` met het daadwerkelijke pad naar uw documentmap.

#### Vraag: Hoe kan ik een voorbeelddocument met tekst maken?

 A: In stap 4 maakt u een nieuw`Document` object en pagina's met tekstfragmenten toevoegen. De meegeleverde code voegt twee tekstfragmenten toe met de bijbehorende tooltiptekst.

#### Vraag: Hoe open ik het document en vind ik de tekstfragmenten?

 A: In stap 5 laadt u het gemaakte document met behulp van de`Document` constructor en zoek de tekstfragmenten waarvoor tooltips nodig zijn met behulp van de`TextFragmentAbsorber`.

#### Vraag: Hoe voeg ik tooltips toe aan de tekstfragmenten?

 A: In stap 6 doorloopt u de geëxtraheerde tekstfragmenten en maakt u onzichtbare knoppen op hun posities. De tooltiptekst wordt toegewezen aan de`AlternateName` eigendom van de`ButtonField`dat wordt toegevoegd aan het formulier van het document.

#### Vraag: Hoe herhaal ik het proces voor extra tekstfragmenten met lange tooltips?

A: Herhaal stap 5 en 6 voor tekstfragmenten met lange tooltips. Pas de zoekcriteria en tooltip-tekst dienovereenkomstig aan.

#### Vraag: Hoe bewaar ik het gewijzigde document?

 A: In stap 8 slaat u het gewijzigde PDF-document op met behulp van de`Save` werkwijze van de`Document` voorwerp.

#### Vraag: Wat is de belangrijkste conclusie uit deze tutorial?

A: Door deze tutorial te volgen, heeft u geleerd hoe u uw PDF-document kunt verbeteren door tooltips aan tekst toe te voegen met Aspose.PDF voor .NET. Dit kan waardevolle aanvullende informatie opleveren voor lezers wanneer ze interactie hebben met de PDF-inhoud.