---
title: Voeg een geordende HTML-lijst toe aan documenten
linktitle: Voeg HTMLOrdered-lijst toe aan documenten
second_title: Aspose.PDF voor .NET API-referentie
description: Leer hoe u een geordende HTML-lijst aan een document toevoegt met Aspose.PDF voor .NET.
type: docs
weight: 30
url: /nl/net/programming-with-text/add-html-ordered-list-into-documents/
---
In deze tutorial leert u hoe u de Aspose.PDF for .NET-bibliotheek gebruikt om een geordende HTML-lijst aan een document toe te voegen. De meegeleverde code demonstreert de benodigde stappen om deze taak uit te voeren.

## Vereisten
Voordat u begint, moet u ervoor zorgen dat u over het volgende beschikt:

- Visual Studio of een andere C#-compiler die op uw computer is geïnstalleerd.
- Aspose.PDF voor .NET-bibliotheek. U kunt het downloaden van de officiële Aspose-website of een pakketbeheerder zoals NuGet gebruiken om het te installeren.

## Stap 1: Het project opzetten
1. Maak een nieuw C#-project in uw favoriete ontwikkelomgeving.
2. Voeg een verwijzing toe naar de Aspose.PDF voor .NET-bibliotheek.

## Stap 2: Importeer de vereiste naamruimten
Voeg in het codebestand waaraan u de geordende HTML-lijst wilt toevoegen, het volgende toe met behulp van richtlijnen boven aan het bestand:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

## Stap 3: Stel de documentdirectory en het pad naar het uitvoerbestand in
 Zoek in de code de regel met de tekst`string dataDir = "YOUR DOCUMENT DIRECTORY";` en vervangen`"YOUR DOCUMENT DIRECTORY"` met het pad naar de map waar uw documenten zijn opgeslagen.

 Zoek vervolgens de regel met de tekst`string outFile = dataDir + "AddHTMLOrderedListIntoDocuments_out.pdf";` en vervangen`"AddHTMLOrderedListIntoDocuments_out.pdf"` met de gewenste naam voor uw PDF-uitvoerbestand.

## Stap 4: Een nieuw Document-object maken
 Een nieuwe instantiëren`Document` object door de volgende regel code toe te voegen:

```csharp
Document doc = new Document();
```

## Stap 5: Maak een HtmlFragment-object met de HTML-inhoud
 Instantieer een`HtmlFragment` object met de HTML-inhoud die u aan het document wilt toevoegen. In de meegeleverde code wordt de HTML-inhoud toegewezen aan de variabele`t`U kunt de HTML-inhoud indien nodig wijzigen.

```csharp
HtmlFragment t = new HtmlFragment("`<body style='line-height: 100px;'><ul><li>First</li><li>Second</li><li>Third</li><li >Fourth</li><li>Fifth</li></ul>Text after the list.<br/>Next line<br/>Last line</body>`");
```

## Stap 6: Voeg een pagina toe aan het document
 Voeg een nieuwe pagina toe aan het document met behulp van de`Add` methode van de`Pages`verzameling. In de meegeleverde code wordt de nieuwe pagina toegewezen aan de variabele`page`.

```csharp
Page page = doc.Pages.Add();
```

## Stap 7: Voeg het HtmlFragment toe aan de pagina
 Voeg de`HtmlFragment` bezwaar maken tegen de pagina door gebruik te maken van de`Add` methode van de`Paragraphs` verzameling.

```csharp
page.Paragraphs.Add(t);
```

## Stap 8: Sla het PDF-document op
 Sla het resulterende PDF-bestand op met behulp van de`Save` methode van de`Document` object. Geef het pad op naar het uitvoerbestand dat u in stap 3 hebt ingesteld.

```csharp
doc.Save(outFile);
```

### Voorbeeldbroncode voor het toevoegen van een HTMLOrdered List in documenten met behulp van Aspose.PDF voor .NET 
```csharp
// Het pad naar de documentenmap.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Het pad naar het uitvoerdocument.
string outFile = dataDir + "AddHTMLOrderedListIntoDocuments_out.pdf";
// Instantieer Document object
Document doc = new Document();
// Instantieer HtmlFragment-object met bijbehorend HTML-fragment
HtmlFragment t = new HtmlFragment("`<body style='line-height: 100px;'><ul><li>First</li><li>Second</li><li>Third</li><li>Fourth</li><li>Fifth</li></ul>Text after the list.<br/>Next line<br/>Last line</body>`");
// Pagina toevoegen in paginaverzameling
Page page = doc.Pages.Add();
// Voeg HtmlFragment toe aan de pagina
page.Paragraphs.Add(t);
// Resulterend PDF-bestand opslaan
doc.Save(outFile);
```

## Conclusie
U hebt met succes een HTML-geordende lijst toegevoegd aan een document met Aspose.PDF voor .NET. Het resulterende PDF-bestand kan nu worden gevonden op het opgegeven pad naar het uitvoerbestand.

Vergeet niet de HTML-inhoud aan te passen en de code aan te passen aan uw specifieke vereisten.

### Veelgestelde vragen

#### V: Wat is het doel van deze tutorial?

A: Deze tutorial is bedoeld om u te begeleiden door het proces van het toevoegen van een HTML-geordende lijst aan een document met behulp van de Aspose.PDF voor .NET-bibliotheek. Het biedt stapsgewijze instructies en codefragmenten om u te helpen deze taak uit te voeren.

#### V: Welke naamruimten moet ik importeren voor deze tutorial?

A: U moet de volgende naamruimten bovenaan uw codebestand importeren:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

#### V: Hoe geef ik de documentdirectory en het pad naar het uitvoerbestand op?

 A: Zoek in de code de regel`string dataDir = "YOUR DOCUMENT DIRECTORY";` en vervangen`"YOUR DOCUMENT DIRECTORY"` met het werkelijke pad naar uw documentdirectory. Zoek ook de regel`string outFile = dataDir + "AddHTMLOrderedListIntoDocuments_out.pdf";` en vervangen`"AddHTMLOrderedListIntoDocuments_out.pdf"` met de gewenste PDF-uitvoerbestandsnaam.

#### V: Kan ik de HTML-inhoud aanpassen die aan het document wordt toegevoegd?

 A: Absoluut! In stap 5 maak je een`HtmlFragment` object genaamd`t` die de HTML-inhoud bevat. U kunt de HTML-inhoud binnen de backticks aanpassen aan uw vereisten.

#### V: Hoe voeg ik de geordende HTML-lijst toe aan een pagina in het document?

 A: In stap 7 voegt u de`HtmlFragment` voorwerp (`t` ) naar de pagina met behulp van de`Add` methode van de`Paragraphs`verzameling. Dit zal de HTML-geordende lijst naadloos integreren in het document.

#### V: Hoe kan ik het resulterende PDF-document opslaan?

 A: Nadat u de HTML-inhoud hebt toegevoegd en op een pagina hebt gerangschikt, kunt u het PDF-document opslaan met behulp van de`Save` methode van de`Document` object. Zorg ervoor dat u het juiste uitvoerbestandspad opgeeft dat u eerder hebt ingesteld.

#### V: Kunt u een samenvatting van de voorbeeldbroncode geven ter referentie?

A: Zeker! Hier is een samengevatte versie van de voorbeeldbroncode die in deze tutorial wordt gegeven:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
string outFile = dataDir + "AddHTMLOrderedListIntoDocuments_out.pdf";
Document doc = new Document();
HtmlFragment t = new HtmlFragment("`<body style='line-height: 100px;'><ul><li>First</li><li>Second</li><li>Third</li><li>Fourth</li><li>Fifth</li></ul>Text after the list.<br/>Next line<br/>Last line</body>`");
Page page = doc.Pages.Add();
page.Paragraphs.Add(t);
doc.Save(outFile);
```

#### V: Wat is de belangrijkste les die je uit deze tutorial hebt geleerd?

A: Door deze tutorial te volgen, hebt u succesvol geleerd hoe u de Aspose.PDF voor .NET-bibliotheek kunt gebruiken om een geordende HTML-lijst in een document op te nemen. Deze nieuwe kennis kan worden toegepast om uw documentcreatie- en manipulatieprocessen te verbeteren.