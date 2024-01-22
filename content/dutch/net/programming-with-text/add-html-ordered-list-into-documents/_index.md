---
title: HTML-geordende lijst toevoegen aan documenten
linktitle: HTML-geordende lijst toevoegen aan documenten
second_title: Aspose.PDF voor .NET API-referentie
description: Leer hoe u een in HTML geordende lijst aan een document kunt toevoegen met Aspose.PDF voor .NET.
type: docs
weight: 30
url: /nl/net/programming-with-text/add-html-ordered-list-into-documents/
---
In deze zelfstudie leert u hoe u de Aspose.PDF voor .NET-bibliotheek kunt gebruiken om een HTML-geordende lijst aan een document toe te voegen. De meegeleverde code demonstreert de noodzakelijke stappen om deze taak te volbrengen.

## Vereisten
Zorg ervoor dat u over het volgende beschikt voordat u begint:

- Visual Studio of een andere C#-compiler die op uw computer is geïnstalleerd.
- Aspose.PDF voor .NET-bibliotheek. Je kunt het downloaden van de officiële Aspose-website of een pakketbeheerder zoals NuGet gebruiken om het te installeren.

## Stap 1: Zet het project op
1. Maak een nieuw C#-project in de ontwikkelomgeving van uw voorkeur.
2. Voeg een verwijzing toe naar de Aspose.PDF voor .NET-bibliotheek.

## Stap 2: Importeer de vereiste naamruimten
In het codebestand waaraan u de HTML-geordende lijst wilt toevoegen, voegt u het volgende toe met behulp van richtlijnen bovenaan het bestand:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

## Stap 3: Stel de documentmap en het uitvoerbestandspad in
 Zoek in de code de regel met de tekst`string dataDir = "YOUR DOCUMENT DIRECTORY";` en vervangen`"YOUR DOCUMENT DIRECTORY"` met het pad naar de map waar uw documenten zijn opgeslagen.

 Zoek vervolgens de regel met de tekst`string outFile = dataDir + "AddHTMLOrderedListIntoDocuments_out.pdf";` en vervangen`"AddHTMLOrderedListIntoDocuments_out.pdf"` met de gewenste naam voor uw uitvoer-PDF-bestand.

## Stap 4: Maak een nieuw Document-object
 Instantieer een nieuwe`Document` object door de volgende regel code toe te voegen:

```csharp
Document doc = new Document();
```

## Stap 5: Maak een HtmlFragment-object met de HTML-inhoud
 Instantieer een`HtmlFragment` object met de HTML-inhoud die u aan het document wilt toevoegen. In de meegeleverde code wordt de HTML-inhoud aan de variabele toegewezen`t`. U kunt de HTML-inhoud indien nodig wijzigen.

```csharp
HtmlFragment t = new HtmlFragment("`<body style='line-height: 100px;'><ul><li>First</li><li>Second</li><li>Third</li><li >Fourth</li><li>Fifth</li></ul>Text after the list.<br/>Next line<br/>Last line</body>`");
```

## Stap 6: Voeg een pagina toe aan het document
 Voeg een nieuwe pagina aan het document toe met behulp van de`Add` werkwijze van de`Pages`verzameling. In de opgegeven code wordt de nieuwe pagina aan de variabele toegewezen`page`.

```csharp
Page page = doc.Pages.Add();
```

## Stap 7: Voeg het HtmlFragment toe aan de pagina
 Voeg de`HtmlFragment` maak bezwaar tegen de pagina met behulp van de`Add` werkwijze van de`Paragraphs` verzameling.

```csharp
page.Paragraphs.Add(t);
```

## Stap 8: Sla het PDF-document op
 Sla het resulterende PDF-bestand op met behulp van de`Save` werkwijze van de`Document` voorwerp. Geef het uitvoerbestandspad op dat u in stap 3 hebt ingesteld.

```csharp
doc.Save(outFile);
```

### Voorbeeldbroncode voor het toevoegen van een HTML-geordende lijst aan documenten met behulp van Aspose.PDF voor .NET 
```csharp
// Het pad naar de documentenmap.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Het pad naar het uitvoerdocument.
string outFile = dataDir + "AddHTMLOrderedListIntoDocuments_out.pdf";
// Instantieer een documentobject
Document doc = new Document();
// Instantieer het HtmlFragment-object met het bijbehorende HTML-fragment
HtmlFragment t = new HtmlFragment("`<body style='line-height: 100px;'><ul><li>First</li><li>Second</li><li>Third</li><li>Fourth</li><li>Fifth</li></ul>Text after the list.<br/>Next line<br/>Last line</body>`");
// Pagina toevoegen aan Paginaverzameling
Page page = doc.Pages.Add();
// Voeg HtmlFragment binnenpagina toe
page.Paragraphs.Add(t);
// Sla het resulterende PDF-bestand op
doc.Save(outFile);
```

## Conclusie
U hebt met succes een HTML-geordende lijst aan een document toegevoegd met behulp van Aspose.PDF voor .NET. Het resulterende PDF-bestand is nu te vinden op het opgegeven uitvoerbestandspad.

Vergeet niet om de HTML-inhoud aan te passen en de code aan te passen aan uw specifieke vereisten.

### Veelgestelde vragen

#### Vraag: Wat is het doel van deze tutorial?

A: Deze tutorial is bedoeld om u door het proces te leiden van het toevoegen van een HTML-geordende lijst aan een document met behulp van de Aspose.PDF voor .NET-bibliotheek. Het biedt stapsgewijze instructies en codefragmenten om u te helpen deze taak te volbrengen.

#### Vraag: Welke naamruimten moet ik importeren voor deze tutorial?

A: U moet de volgende naamruimten bovenaan uw codebestand importeren:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

#### Vraag: Hoe geef ik de documentmap en het uitvoerbestandspad op?

 A: Zoek de regel in de code`string dataDir = "YOUR DOCUMENT DIRECTORY";` en vervangen`"YOUR DOCUMENT DIRECTORY"` met het daadwerkelijke pad naar uw documentmap. Zoek ook de lijn`string outFile = dataDir + "AddHTMLOrderedListIntoDocuments_out.pdf";` en vervangen`"AddHTMLOrderedListIntoDocuments_out.pdf"` met de gewenste uitvoer-PDF-bestandsnaam.

#### Vraag: Kan ik de HTML-inhoud die aan het document wordt toegevoegd aanpassen?

 EEN: Absoluut! In stap 5 maakt u een`HtmlFragment` voorwerp genoemd`t` dat de HTML-inhoud bevat. U kunt de HTML-inhoud binnen de backticks aanpassen aan uw wensen.

#### Vraag: Hoe voeg ik de HTML-geordende lijst toe aan een pagina in het document?

 A: In stap 7 voegt u de`HtmlFragment` voorwerp (`t` ) naar de pagina met behulp van de`Add` werkwijze van de`Paragraphs`verzameling. Hierdoor wordt de HTML-geordende lijst naadloos in het document geïntegreerd.

#### Vraag: Hoe bewaar ik het resulterende PDF-document?

 A: Nadat u de HTML-inhoud heeft toegevoegd en op een pagina heeft geplaatst, kunt u het PDF-document opslaan met behulp van de`Save` werkwijze van de`Document` voorwerp. Zorg ervoor dat u het juiste uitvoerbestandspad opgeeft dat u eerder hebt ingesteld.

#### Vraag: Kunt u ter referentie een samenvatting geven van de voorbeeldbroncode?

EEN: Zeker! Hier is een samengevatte versie van de voorbeeldbroncode in deze zelfstudie:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
string outFile = dataDir + "AddHTMLOrderedListIntoDocuments_out.pdf";
Document doc = new Document();
HtmlFragment t = new HtmlFragment("`<body style='line-height: 100px;'><ul><li>First</li><li>Second</li><li>Third</li><li>Fourth</li><li>Fifth</li></ul>Text after the list.<br/>Next line<br/>Last line</body>`");
Page page = doc.Pages.Add();
page.Paragraphs.Add(t);
doc.Save(outFile);
```

#### Vraag: Wat is de belangrijkste conclusie uit deze tutorial?

A: Door deze tutorial te volgen, heeft u met succes geleerd hoe u de Aspose.PDF voor .NET-bibliotheek kunt gebruiken om een HTML-geordende lijst in een document op te nemen. Deze nieuwe kennis kan worden toegepast om uw processen voor het maken en manipuleren van documenten te verbeteren.