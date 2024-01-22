---
title: Voeg HTML toe met DOM en PDF-overschrijving
linktitle: HTML toevoegen met DOM en overschrijven
second_title: Aspose.PDF voor .NET API-referentie
description: Leer hoe u HTML-inhoud kunt toevoegen met behulp van DOM en PDF-overschrijving in Aspose.PDF voor .NET.
type: docs
weight: 50
url: /nl/net/programming-with-text/add-html-using-dom-and-overwrite/
---
Deze tutorial leidt u door het proces van het toevoegen van HTML-inhoud met behulp van DOM (Document Object Model) in Aspose.PDF voor .NET. Bovendien leert u hoe u stijlen voor de HTML-inhoud kunt overschrijven. De meegeleverde C#-broncode demonstreert de noodzakelijke stappen.

## Vereisten
Zorg ervoor dat u over het volgende beschikt voordat u begint:

- Visual Studio of een andere C#-compiler die op uw computer is geïnstalleerd.
- Aspose.PDF voor .NET-bibliotheek. Je kunt het downloaden van de officiële Aspose-website of een pakketbeheerder zoals NuGet gebruiken om het te installeren.

## Stap 1: Zet het project op
1. Maak een nieuw C#-project in de ontwikkelomgeving van uw voorkeur.
2. Voeg een verwijzing toe naar de Aspose.PDF voor .NET-bibliotheek.

## Stap 2: Importeer de vereiste naamruimten
In het codebestand waaraan u de HTML-inhoud wilt toevoegen, voegt u het volgende toe met behulp van richtlijnen bovenaan het bestand:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

## Stap 3: Stel de documentmap en het uitvoerbestandspad in
 Zoek in de code de regel met de tekst`string dataDir = "YOUR DOCUMENT DIRECTORY";` en vervangen`"YOUR DOCUMENT DIRECTORY"` met het pad naar de map waar uw documenten zijn opgeslagen.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Stap 4: Maak een nieuw Document-object
 Instantieer een nieuwe`Document` object door de volgende regel code toe te voegen:

```csharp
Document doc = new Document();
```

## Stap 5: Voeg een pagina toe aan het document
 Voeg een nieuwe pagina aan het document toe met behulp van de`Add` werkwijze van de`Pages`verzameling. In de opgegeven code wordt de nieuwe pagina aan de variabele toegewezen`page`.

```csharp
Page page = doc.Pages.Add();
```

## Stap 6: Maak een HtmlFragment met de HTML-inhoud
 Instantieer een`HtmlFragment` object en geef de gewenste HTML-inhoud op. In de meegeleverde code wordt de HTML-inhoud aan de variabele toegewezen`title`. U kunt de HTML-inhoud indien nodig wijzigen.

```csharp
HtmlFragment title = new HtmlFragment("<p style='font-family: Verdana'><b><i>Table contains text</i></b></p>");
```

## Stap 7: Overschrijf de stijlen voor de HTML-inhoud
 Om de stijlen van de HTML-inhoud te overschrijven, kunt u de`TextState` eigenschappen van de`HtmlFragment` voorwerp. In de meegeleverde code is de lettertypefamilie gewijzigd in "Arial" en is de lettergrootte ingesteld op 20.

```csharp
title. TextState = new TextState("Arial");
title.TextState.FontSize = 20;
```

## Stap 8: Marge-informatie instellen
Pas indien nodig de onder- en bovenmarge van het HTML-fragment aan. In de opgegeven code is de ondermarge ingesteld op 10 en de bovenmarge op 400.

```csharp
title. Margin. Bottom = 10;
title. Margin. Top = 400;
```

## Stap 9: Voeg het HtmlFragment toe aan de pagina
 Voeg de`HtmlFragment` bezwaar maken tegen het verzamelen van alinea's op de pagina.

```csharp
page.Paragraphs.Add(title);
```

## Stap 10: Sla het PDF-document op
 Sla het PDF-document op met behulp van de`Save` werkwijze van de`Document` voorwerp. Geef het uitvoerbestandspad op dat u in stap 3 hebt ingesteld.

```csharp
dataDir = dataDir + "AddHTMLUsingDOMAndOverwrite_out.pdf";
doc.Save(dataDir);
```

### Voorbeeldbroncode voor HTML toevoegen met DOMANd en overschrijven met Aspose.PDF voor .NET 
```csharp
// Het pad naar de documentenmap.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Instantieer een documentobject
Document doc = new Document();
// Voeg een pagina toe aan de paginaverzameling van een PDF-bestand
Page page = doc.Pages.Add();
// Instantieer HtmlFragment met HTML-contnets
HtmlFragment title = new HtmlFragment("<p style='font-family: Verdana'><b><i>Table contains text</i></b></p>");
//Lettertypefamilie van 'Verdana' wordt gereset naar 'Arial'
title.TextState = new TextState("Arial");
title.TextState.FontSize = 20;
// Stel informatie over de ondermarge in
title.Margin.Bottom = 10;
// Stel informatie over de bovenmarge in
title.Margin.Top = 400;
// Voeg een HTML-fragment toe aan de alineaverzameling van de pagina
page.Paragraphs.Add(title);
// PDF-bestand opslaan
dataDir = dataDir + "AddHTMLUsingDOMAndOverwrite_out.pdf";
// PDF-bestand opslaan
doc.Save(dataDir);
```

## Conclusie
U hebt met succes HTML-inhoud toegevoegd met behulp van DOM in Aspose.PDF voor .NET en de stijlen voor de HTML-inhoud overschreven. Het resulterende PDF-bestand is nu te vinden op het opgegeven uitvoerbestandspad.

### Veelgestelde vragen

#### Vraag: Wat is de focus van deze tutorial?

A: Deze tutorial is bedoeld om u door het proces te leiden van het toevoegen van HTML-inhoud aan een PDF-document met behulp van het Document Object Model (DOM) in Aspose.PDF voor .NET. Bovendien leert u hoe u stijlen voor de HTML-inhoud kunt overschrijven, zodat u het uiterlijk ervan kunt aanpassen. De zelfstudie biedt C#-broncodefragmenten om de vereiste stappen te demonstreren.

#### Vraag: Welke naamruimten moet ik importeren voor deze tutorial?

A: In het codebestand waaraan u HTML-inhoud wilt toevoegen, importeert u de volgende naamruimten aan het begin van het bestand:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

#### Vraag: Hoe geef ik de documentmap en het uitvoerbestandspad op?

 A: Zoek de regel in de code`string dataDir = "YOUR DOCUMENT DIRECTORY";` en vervangen`"YOUR DOCUMENT DIRECTORY"` met het daadwerkelijke pad naar uw documentmap.

#### Vraag: Hoe maak ik een Document-object?

 A: In stap 4 maakt u een nieuw bestand`Document` object met behulp van de volgende coderegel:

```csharp
Document doc = new Document();
```

#### Vraag: Hoe voeg ik een pagina toe aan het document?

 A: In stap 5 voegt u een nieuwe pagina aan het document toe met behulp van de`Add` werkwijze van de`Pages` verzameling:

```csharp
Page page = doc.Pages.Add();
```

#### Vraag: Hoe kan ik HTML-inhoud instellen met behulp van de DOM?

 A: In stap 6 maakt u een`HtmlFragment` object en wijs er de gewenste HTML-inhoud aan toe. De HTML-inhoud wordt aan de variabele toegewezen`title`:

```csharp
HtmlFragment title = new HtmlFragment("<p style='font-family: Verdana'><b><i>Table contains text</i></b></p>");
```

#### Vraag: Hoe kan ik de stijlen van de HTML-inhoud overschrijven?

 A: In stap 7 overschrijft u de stijlen van de HTML-inhoud door de`TextState` eigenschappen van de`HtmlFragment` voorwerp. U kunt bijvoorbeeld de lettertypefamilie wijzigen in "Arial" en de lettergrootte instellen op 20:

```csharp
title.TextState = new TextState("Arial");
title.TextState.FontSize = 20;
```

#### Vraag: Kan ik de marge van de HTML-inhoud aanpassen?

A: Ja, in stap 8 kunt u de onder- en bovenmarges van het HTML-fragment indien nodig aanpassen:

```csharp
title.Margin.Bottom = 10;
title.Margin.Top = 400;
```

#### Vraag: Hoe voeg ik het HtmlFragment toe aan het PDF-document?

 A: In stap 9 voegt u de`HtmlFragment` voorwerp (`title`) naar de alineaverzameling van de pagina:

```csharp
page.Paragraphs.Add(title);
```

#### Vraag: Hoe bewaar ik het resulterende PDF-document?

 A: Nadat u de HTML-inhoud heeft toegevoegd en de stijlen ervan heeft aangepast, gebruikt u de`Save` werkwijze van de`Document` object om het PDF-document op te slaan:

```csharp
dataDir = dataDir + "AddHTMLUsingDOMAndOverwrite_out.pdf";
doc.Save(dataDir);
```

#### Vraag: Wat is de belangrijkste conclusie uit deze tutorial?

A: Door deze tutorial te volgen, heeft u met succes geleerd hoe u HTML-inhoud kunt opnemen met behulp van het Document Object Model (DOM) in Aspose.PDF voor .NET. Bovendien hebt u de mogelijkheid gekregen om stijlen te overschrijven om het uiterlijk van de HTML-inhoud in het resulterende PDF-document aan te passen.