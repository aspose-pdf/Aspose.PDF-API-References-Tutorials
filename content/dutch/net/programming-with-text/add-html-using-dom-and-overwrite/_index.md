---
title: HTML toevoegen met DOM en PDF Overwrite
linktitle: HTML toevoegen met DOM en overschrijven
second_title: Aspose.PDF voor .NET API-referentie
description: Leer hoe u HTML-inhoud toevoegt met behulp van DOM en PDF-overschrijving in Aspose.PDF voor .NET.
type: docs
weight: 50
url: /nl/net/programming-with-text/add-html-using-dom-and-overwrite/
---
Deze tutorial begeleidt u door het proces van het toevoegen van HTML-inhoud met behulp van DOM (Document Object Model) in Aspose.PDF voor .NET. Daarnaast leert u hoe u stijlen voor de HTML-inhoud kunt overschrijven. De meegeleverde C#-broncode demonstreert de benodigde stappen.

## Vereisten
Voordat u begint, moet u ervoor zorgen dat u over het volgende beschikt:

- Visual Studio of een andere C#-compiler die op uw computer is geïnstalleerd.
- Aspose.PDF voor .NET-bibliotheek. U kunt het downloaden van de officiële Aspose-website of een pakketbeheerder zoals NuGet gebruiken om het te installeren.

## Stap 1: Het project opzetten
1. Maak een nieuw C#-project in uw favoriete ontwikkelomgeving.
2. Voeg een verwijzing toe naar de Aspose.PDF voor .NET-bibliotheek.

## Stap 2: Importeer de vereiste naamruimten
Voeg in het codebestand waaraan u de HTML-inhoud wilt toevoegen, het volgende toe met behulp van richtlijnen boven aan het bestand:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

## Stap 3: Stel de documentdirectory en het pad naar het uitvoerbestand in
 Zoek in de code de regel met de tekst`string dataDir = "YOUR DOCUMENT DIRECTORY";` en vervangen`"YOUR DOCUMENT DIRECTORY"` met het pad naar de map waar uw documenten zijn opgeslagen.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Stap 4: Een nieuw Document-object maken
 Een nieuwe instantiëren`Document` object door de volgende regel code toe te voegen:

```csharp
Document doc = new Document();
```

## Stap 5: Voeg een pagina toe aan het document
 Voeg een nieuwe pagina toe aan het document met behulp van de`Add` methode van de`Pages` verzameling. In de meegeleverde code wordt de nieuwe pagina toegewezen aan de variabele`page`.

```csharp
Page page = doc.Pages.Add();
```

## Stap 6: Maak een HtmlFragment met de HTML-inhoud
 Instantieer een`HtmlFragment` object en de gewenste HTML-inhoud leveren. In de meegeleverde code wordt de HTML-inhoud toegewezen aan de variabele`title`U kunt de HTML-inhoud indien nodig wijzigen.

```csharp
HtmlFragment title = new HtmlFragment("<p style='font-family: Verdana'><b><i>Table contains text</i></b></p>");
```

## Stap 7: Overschrijf de stijlen voor de HTML-inhoud
 Om de stijlen van de HTML-inhoud te overschrijven, kunt u de`TextState` eigenschappen van de`HtmlFragment` object. In de meegeleverde code is het lettertype gewijzigd naar "Arial" en is de lettergrootte ingesteld op 20.

```csharp
title. TextState = new TextState("Arial");
title.TextState.FontSize = 20;
```

## Stap 8: Marge-informatie instellen
Pas indien nodig de onder- en bovenmarges van het HTML-fragment aan. In de meegeleverde code is de ondermarge ingesteld op 10 en de bovenmarge op 400.

```csharp
title. Margin. Bottom = 10;
title. Margin. Top = 400;
```

## Stap 9: Voeg het HtmlFragment toe aan de pagina
 Voeg de`HtmlFragment` bezwaar maken tegen de verzameling alinea's van de pagina.

```csharp
page.Paragraphs.Add(title);
```

## Stap 10: Sla het PDF-document op
 Sla het PDF-document op met behulp van de`Save` methode van de`Document` object. Geef het pad op naar het uitvoerbestand dat u in stap 3 hebt ingesteld.

```csharp
dataDir = dataDir + "AddHTMLUsingDOMAndOverwrite_out.pdf";
doc.Save(dataDir);
```

### Voorbeeldbroncode voor HTML toevoegen met DOM en overschrijven met Aspose.PDF voor .NET 
```csharp
// Het pad naar de documentenmap.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Instantieer Document-object
Document doc = new Document();
// Voeg een pagina toe aan de paginaverzameling van een PDF-bestand
Page page = doc.Pages.Add();
// Instantieer HtmlFragment met HTML-inhoud
HtmlFragment title = new HtmlFragment("<p style='font-family: Verdana'><b><i>Table contains text</i></b></p>");
//Lettertypefamilie van 'Verdana' wordt gereset naar 'Arial'
title.TextState = new TextState("Arial");
title.TextState.FontSize = 20;
// Informatie over de ondermarge instellen
title.Margin.Bottom = 10;
// Bovenste marge-informatie instellen
title.Margin.Top = 400;
// HTML-fragment toevoegen aan alineaverzameling van pagina
page.Paragraphs.Add(title);
// PDF-bestand opslaan
dataDir = dataDir + "AddHTMLUsingDOMAndOverwrite_out.pdf";
// PDF-bestand opslaan
doc.Save(dataDir);
```

## Conclusie
hebt HTML-inhoud succesvol toegevoegd met behulp van DOM in Aspose.PDF voor .NET en de stijlen voor de HTML-inhoud overschreven. Het resulterende PDF-bestand is nu te vinden op het opgegeven pad naar het uitvoerbestand.

### Veelgestelde vragen

#### V: Waarop richt deze tutorial zich?

A: Deze tutorial is ontworpen om u door het proces te leiden van het toevoegen van HTML-inhoud aan een PDF-document met behulp van het Document Object Model (DOM) in Aspose.PDF voor .NET. Daarnaast leert u hoe u stijlen voor de HTML-inhoud kunt overschrijven, zodat u het uiterlijk ervan kunt aanpassen. De tutorial biedt C#-broncodefragmenten om de vereiste stappen te demonstreren.

#### V: Welke naamruimten moet ik importeren voor deze tutorial?

A: Importeer de volgende naamruimten aan het begin van het bestand in het codebestand waaraan u HTML-inhoud wilt toevoegen:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

#### V: Hoe geef ik de documentdirectory en het pad naar het uitvoerbestand op?

 A: Zoek in de code de regel`string dataDir = "YOUR DOCUMENT DIRECTORY";` en vervangen`"YOUR DOCUMENT DIRECTORY"` met het daadwerkelijke pad naar uw documentenmap.

#### V: Hoe maak ik een Document-object?

 A: In stap 4 maakt u een nieuwe`Document` object met behulp van de volgende regel code:

```csharp
Document doc = new Document();
```

#### V: Hoe voeg ik een pagina toe aan het document?

 A: In stap 5 voegt u een nieuwe pagina toe aan het document met behulp van de`Add` methode van de`Pages` verzameling:

```csharp
Page page = doc.Pages.Add();
```

#### V: Hoe kan ik HTML-inhoud instellen met behulp van de DOM?

 A: In stap 6 maak je een`HtmlFragment` object en wijs uw gewenste HTML-inhoud eraan toe. De HTML-inhoud wordt toegewezen aan de variabele`title`:

```csharp
HtmlFragment title = new HtmlFragment("<p style='font-family: Verdana'><b><i>Table contains text</i></b></p>");
```

#### V: Hoe kan ik de stijlen van de HTML-inhoud overschrijven?

 A: In stap 7 overschrijft u de stijlen van de HTML-inhoud door de`TextState` eigenschappen van de`HtmlFragment`object. U kunt bijvoorbeeld het lettertype wijzigen naar "Arial" en de lettergrootte instellen op 20:

```csharp
title.TextState = new TextState("Arial");
title.TextState.FontSize = 20;
```

#### V: Kan ik de marge van de HTML-inhoud aanpassen?

A: Ja, in stap 8 kunt u de onder- en bovenmarges van het HTML-fragment naar wens aanpassen:

```csharp
title.Margin.Bottom = 10;
title.Margin.Top = 400;
```

#### V: Hoe voeg ik het HtmlFragment toe aan het PDF-document?

 A: In stap 9 voegt u de`HtmlFragment` voorwerp (`title`) naar de paragrafenverzameling van de pagina:

```csharp
page.Paragraphs.Add(title);
```

#### V: Hoe kan ik het resulterende PDF-document opslaan?

 A: Nadat u de HTML-inhoud hebt toegevoegd en de stijlen hebt aangepast, gebruikt u de`Save` methode van de`Document` object om het PDF-document op te slaan:

```csharp
dataDir = dataDir + "AddHTMLUsingDOMAndOverwrite_out.pdf";
doc.Save(dataDir);
```

#### V: Wat is de belangrijkste les die je uit deze tutorial hebt geleerd?

A: Door deze tutorial te volgen, hebt u succesvol geleerd hoe u HTML-inhoud kunt opnemen met behulp van het Document Object Model (DOM) in Aspose.PDF voor .NET. Daarnaast hebt u de mogelijkheid gekregen om stijlen te overschrijven om het uiterlijk van de HTML-inhoud in het resulterende PDF-document aan te passen.