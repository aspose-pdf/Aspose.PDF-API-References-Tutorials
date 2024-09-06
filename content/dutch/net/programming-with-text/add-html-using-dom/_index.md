---
title: HTML toevoegen met behulp van DOM
linktitle: HTML toevoegen met behulp van DOM
second_title: Aspose.PDF voor .NET API-referentie
description: Leer hoe u HTML-inhoud toevoegt met behulp van DOM in Aspose.PDF voor .NET.
type: docs
weight: 40
url: /nl/net/programming-with-text/add-html-using-dom/
---
Deze tutorial begeleidt u door het proces van het toevoegen van HTML-inhoud met behulp van DOM (Document Object Model) in Aspose.PDF voor .NET. De meegeleverde C#-broncode demonstreert de benodigde stappen.

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
```

## Stap 3: Stel de documentdirectory en het pad naar het uitvoerbestand in
 Zoek in de code de regel met de tekst`string dataDir = "YOUR DOCUMENT DIRECTORY";` en vervangen`"YOUR DOCUMENT DIRECTORY"` met het pad naar de map waar uw documenten zijn opgeslagen.

## Stap 4: Een nieuw Document-object maken
 Een nieuwe instantiëren`Document` object door de volgende regel code toe te voegen:

```csharp
Document doc = new Document();
```

## Stap 5: Voeg een pagina toe aan het document
 Voeg een nieuwe pagina toe aan het document met behulp van de`Add` methode van de`Pages`verzameling. In de meegeleverde code wordt de nieuwe pagina toegewezen aan de variabele`page`.

```csharp
Page page = doc.Pages.Add();
```

## Stap 6: Maak een HtmlFragment met de HTML-inhoud
 Instantieer een`HtmlFragment` object en de gewenste HTML-inhoud leveren. In de meegeleverde code wordt de HTML-inhoud toegewezen aan de variabele`titel`U kunt de HTML-inhoud indien nodig wijzigen.

```csharp
HtmlFragment titel = new HtmlFragment("<fontsize=10><b><i>Table</i></b></fontsize>");
```

## Stap 7: Marge-informatie instellen
Pas indien nodig de onder- en bovenmarge van het HTML-fragment aan. In de meegeleverde code is de ondermarge ingesteld op 10 en de bovenmarge op 200.

```csharp
title. Margin. Bottom = 10;
title. Margin. Top = 200;
```

## Stap 8: Voeg het HtmlFragment toe aan de pagina
 Voeg de`HtmlFragment` bezwaar maken tegen de verzameling alinea's van de pagina.

```csharp
page.Paragraphs.Add(title);
dataDir = dataDir + "AddHTMLUsingDOM_out.pdf";
```

## Stap 9: Sla het PDF-document op
 Sla het PDF-document op met behulp van de`Save` methode van de`Document` object. Geef het pad op naar het uitvoerbestand dat u in stap 3 hebt ingesteld.

```csharp
doc.Save(dataDir);
```

## Stap 10: Geef het succesbericht weer
Geef een succesbericht weer, samen met het pad waar het PDF-bestand is opgeslagen.

```csharp
Console.WriteLine("\nHTML using DOM added successfully.\nFile saved at " + dataDir);
```

### Voorbeeldbroncode voor HTML toevoegen met behulp van DOM met Aspose.PDF voor .NET 
```csharp
// Het pad naar de documentenmap.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Instantieer Document object
Document doc = new Document();
// Voeg een pagina toe aan de paginaverzameling van een PDF-bestand
Page page = doc.Pages.Add();
// Instantieer HtmlFragment met HTML-inhoud
HtmlFragment titel = new HtmlFragment("<fontsize=10><b><i>Table</i></b></fontsize>");
// Informatie over de ondermarge instellen
titel.Margin.Bottom = 10;
// Bovenste marge-informatie instellen
titel.Margin.Top = 200;
// HTML-fragment toevoegen aan alineaverzameling van pagina
page.Paragraphs.Add(titel);
dataDir = dataDir + "AddHTMLUsingDOM_out.pdf";
// PDF-bestand opslaan
doc.Save(dataDir);
Console.WriteLine("\nHTML using DOM added successfully.\nFile saved at " + dataDir);
```

## Conclusie
U hebt HTML-inhoud met DOM succesvol toegevoegd in Aspose.PDF voor .NET. Het resulterende PDF-bestand is nu te vinden op het opgegeven pad naar het uitvoerbestand.

### Veelgestelde vragen

#### V: Wat is het doel van deze tutorial?

A: Deze tutorial is bedoeld om een stapsgewijze handleiding te bieden over hoe u HTML-inhoud toevoegt aan een PDF-document met behulp van het Document Object Model (DOM) in Aspose.PDF voor .NET. Het bevat C#-broncodefragmenten om u te helpen het proces te begrijpen en te implementeren.

#### V: Welke naamruimten moet ik importeren voor deze tutorial?

A: Importeer de volgende naamruimte aan het begin van het bestand in het codebestand waaraan u HTML-inhoud wilt toevoegen:

```csharp
using Aspose.Pdf;
```

#### V: Hoe geef ik de documentdirectory en het pad naar het uitvoerbestand op?

 A: Zoek in de code de regel`string dataDir = "YOUR DOCUMENT DIRECTORY";` en vervangen`"YOUR DOCUMENT DIRECTORY"` met het daadwerkelijke pad naar uw documentenmap.

#### V: Hoe maak ik een Document-object?

 A: In stap 4, instantiëren een nieuwe`Document` object door de volgende regel code toe te voegen:

```csharp
Document doc = new Document();
```

#### V: Hoe voeg ik een pagina toe aan het document?

 A: In stap 5 voegt u een nieuwe pagina toe aan het document met behulp van de`Add` methode van de`Pages` verzameling:

```csharp
Page page = doc.Pages.Add();
```

#### V: Hoe kan ik HTML-inhoud instellen met behulp van de DOM?

 A: In stap 6 maak je een`HtmlFragment` object en wijs uw gewenste HTML-inhoud eraan toe. De HTML-inhoud wordt toegewezen aan de variabele`titel`:

```csharp
HtmlFragment titel = new HtmlFragment("<fontsize=10><b><i>Table</i></b></fontsize>");
```

#### V: Kan ik de marge van de HTML-inhoud aanpassen?

A: Ja, in stap 7 kunt u de onder- en bovenmarges van het HTML-fragment naar wens aanpassen:

```csharp
titel.Margin.Bottom = 10;
titel.Margin.Top = 200;
```

#### V: Hoe voeg ik het HTMLFragment toe aan het PDF-document?

 A: In stap 8 voegt u de`HtmlFragment` voorwerp (`titel`) naar de paragrafenverzameling van de pagina:

```csharp
page.Paragraphs.Add(titel);
dataDir = dataDir + "AddHTMLUsingDOM_out.pdf";
```

#### V: Hoe kan ik het resulterende PDF-document opslaan?

 A: Nadat u de HTML-inhoud hebt toegevoegd en de marges hebt aangepast, gebruikt u de`Save` methode van de`Document` object om het PDF-document op te slaan:

```csharp
doc.Save(dataDir);
```

#### V: Is er een manier om te controleren of het proces succesvol is geweest?

A: Zeker, in stap 10 wordt een succesbericht weergegeven, samen met het pad waar het PDF-bestand is opgeslagen:

```csharp
Console.WriteLine("\nHTML using DOM added successfully.\nFile saved at " + dataDir);
```

#### V: Wat is de belangrijkste les die je uit deze tutorial hebt geleerd?

A: Door deze tutorial te volgen, hebt u succesvol geleerd hoe u het Document Object Model (DOM) in Aspose.PDF voor .NET kunt gebruiken om HTML-inhoud toe te voegen aan een PDF-document. Deze kennis stelt u in staat om uw PDF-generatiemogelijkheden te verbeteren.