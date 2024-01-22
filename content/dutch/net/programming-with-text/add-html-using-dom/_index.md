---
title: HTML toevoegen met DOM
linktitle: HTML toevoegen met DOM
second_title: Aspose.PDF voor .NET API-referentie
description: Leer hoe u HTML-inhoud kunt toevoegen met DOM in Aspose.PDF voor .NET.
type: docs
weight: 40
url: /nl/net/programming-with-text/add-html-using-dom/
---
Deze tutorial leidt u door het proces van het toevoegen van HTML-inhoud met behulp van DOM (Document Object Model) in Aspose.PDF voor .NET. De meegeleverde C#-broncode demonstreert de noodzakelijke stappen.

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
```

## Stap 3: Stel de documentmap en het uitvoerbestandspad in
 Zoek in de code de regel met de tekst`string dataDir = "YOUR DOCUMENT DIRECTORY";` en vervangen`"YOUR DOCUMENT DIRECTORY"` met het pad naar de map waar uw documenten zijn opgeslagen.

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
 Instantieer een`HtmlFragment` object en geef de gewenste HTML-inhoud op. In de meegeleverde code wordt de HTML-inhoud aan de variabele toegewezen`titel`. U kunt de HTML-inhoud indien nodig wijzigen.

```csharp
HtmlFragment titel = new HtmlFragment("<fontsize=10><b><i>Table</i></b></fontsize>");
```

## Stap 7: Marge-informatie instellen
Pas indien nodig de onder- en bovenmarge van het HTML-fragment aan. In de opgegeven code is de ondermarge ingesteld op 10 en de bovenmarge op 200.

```csharp
title. Margin. Bottom = 10;
title. Margin. Top = 200;
```

## Stap 8: Voeg het HtmlFragment toe aan de pagina
 Voeg de`HtmlFragment` bezwaar maken tegen het verzamelen van alinea's op de pagina.

```csharp
page.Paragraphs.Add(title);
dataDir = dataDir + "AddHTMLUsingDOM_out.pdf";
```

## Stap 9: Sla het PDF-document op
 Sla het PDF-document op met behulp van de`Save` werkwijze van de`Document` voorwerp. Geef het uitvoerbestandspad op dat u in stap 3 hebt ingesteld.

```csharp
doc.Save(dataDir);
```

## Stap 10: Geef het succesbericht weer
Geef een succesbericht weer samen met het pad waar het PDF-bestand is opgeslagen.

```csharp
Console.WriteLine("\nHTML using DOM added successfully.\nFile saved at " + dataDir);
```

### Voorbeeldbroncode voor HTML toevoegen met DOM met Aspose.PDF voor .NET 
```csharp
// Het pad naar de documentenmap.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Instantieer een documentobject
Document doc = new Document();
// Voeg een pagina toe aan de paginaverzameling van een PDF-bestand
Page page = doc.Pages.Add();
// Instantieer HtmlFragment met HTML-contnets
HtmlFragment titel = new HtmlFragment("<fontsize=10><b><i>Table</i></b></fontsize>");
// Stel informatie over de ondermarge in
titel.Margin.Bottom = 10;
// Stel informatie over de bovenmarge in
titel.Margin.Top = 200;
// Voeg een HTML-fragment toe aan de alineaverzameling van de pagina
page.Paragraphs.Add(titel);
dataDir = dataDir + "AddHTMLUsingDOM_out.pdf";
// PDF-bestand opslaan
doc.Save(dataDir);
Console.WriteLine("\nHTML using DOM added successfully.\nFile saved at " + dataDir);
```

## Conclusie
U hebt met succes HTML-inhoud toegevoegd met behulp van DOM in Aspose.PDF voor .NET. Het resulterende PDF-bestand is nu te vinden op het opgegeven uitvoerbestandspad.

### Veelgestelde vragen

#### Vraag: Wat is het doel van deze tutorial?

A: Deze tutorial is bedoeld om stapsgewijze handleidingen te bieden voor het toevoegen van HTML-inhoud aan een PDF-document met behulp van het Document Object Model (DOM) in Aspose.PDF voor .NET. Het bevat C#-broncodefragmenten om u te helpen het proces te begrijpen en te implementeren.

#### Vraag: Welke naamruimten moet ik importeren voor deze tutorial?

A: In het codebestand waaraan u HTML-inhoud wilt toevoegen, importeert u de volgende naamruimte aan het begin van het bestand:

```csharp
using Aspose.Pdf;
```

#### Vraag: Hoe geef ik de documentmap en het uitvoerbestandspad op?

 A: Zoek de regel in de code`string dataDir = "YOUR DOCUMENT DIRECTORY";` en vervangen`"YOUR DOCUMENT DIRECTORY"` met het daadwerkelijke pad naar uw documentmap.

#### Vraag: Hoe maak ik een Document-object?

 A: In stap 4 maakt u een nieuw bestand aan`Document` object door de volgende regel code toe te voegen:

```csharp
Document doc = new Document();
```

#### Vraag: Hoe voeg ik een pagina toe aan het document?

 A: In stap 5 voegt u een nieuwe pagina aan het document toe met behulp van de`Add` werkwijze van de`Pages` verzameling:

```csharp
Page page = doc.Pages.Add();
```

#### Vraag: Hoe kan ik HTML-inhoud instellen met behulp van de DOM?

 A: In stap 6 maakt u een`HtmlFragment` object en wijs er de gewenste HTML-inhoud aan toe. De HTML-inhoud wordt aan de variabele toegewezen`titel`:

```csharp
HtmlFragment titel = new HtmlFragment("<fontsize=10><b><i>Table</i></b></fontsize>");
```

#### Vraag: Kan ik de marge van de HTML-inhoud aanpassen?

A: Ja, in stap 7 kunt u de onder- en bovenmarges van het HTML-fragment indien nodig aanpassen:

```csharp
titel.Margin.Bottom = 10;
titel.Margin.Top = 200;
```

#### Vraag: Hoe voeg ik het HTMLFragment toe aan het PDF-document?

 A: In stap 8 voegt u de`HtmlFragment` voorwerp (`titel`) naar de alineaverzameling van de pagina:

```csharp
page.Paragraphs.Add(titel);
dataDir = dataDir + "AddHTMLUsingDOM_out.pdf";
```

#### Vraag: Hoe bewaar ik het resulterende PDF-document?

 A: Nadat u de HTML-inhoud heeft toegevoegd en de marges heeft aangepast, gebruikt u de`Save` werkwijze van de`Document` object om het PDF-document op te slaan:

```csharp
doc.Save(dataDir);
```

#### Vraag: Is er een manier om te verifiëren of het proces succesvol is geweest?

A: Zeker, in stap 10 wordt een succesbericht weergegeven samen met het pad waar het PDF-bestand is opgeslagen:

```csharp
Console.WriteLine("\nHTML using DOM added successfully.\nFile saved at " + dataDir);
```

#### Vraag: Wat is de belangrijkste conclusie uit deze tutorial?

A: Door deze tutorial te volgen, heeft u met succes geleerd hoe u het Document Object Model (DOM) in Aspose.PDF voor .NET kunt gebruiken om HTML-inhoud aan een PDF-document toe te voegen. Deze kennis stelt u in staat uw mogelijkheden voor het genereren van PDF-bestanden te verbeteren.