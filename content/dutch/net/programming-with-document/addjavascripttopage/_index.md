---
title: Voeg Javascript toe aan PDF-bestand
linktitle: Voeg een Javascript PDF-bestand toe
second_title: Aspose.PDF voor .NET API-referentie
description: Leer hoe u JavaScript aan een PDF-bestand toevoegt met Aspose.PDF voor .NET. Stapsgewijze handleiding met codetutorials voor scripting op document- en paginaniveau.
type: docs
weight: 10
url: /nl/net/programming-with-document/addjavascripttopage/
---
Om JavaScript aan een PDF-bestand toe te voegen, gebruiken we Aspose.PDF voor .NET. Deze bibliotheek biedt een eenvoudige en efficiënte manier om met PDF-bestanden te werken in .NET-toepassingen. De volgende stappen begeleiden u bij het toevoegen van JavaScript aan een PDF-bestand met behulp van Aspose.PDF voor .NET.

## Stap 1: Laad het PDF-bestand

 De eerste stap is het laden van het PDF-bestand waaraan u JavaScript wilt toevoegen. Dit kunt u doen met behulp van de`Document` klasse geleverd door Aspose.PDF voor .NET. De`Document` class biedt methoden voor het laden, opslaan en manipuleren van PDF-bestanden.

```csharp
// Het pad naar de documentenmap.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Laad een bestaand PDF-bestand
Document doc = new Document(dataDir + "input.pdf");
```

## Stap 2: Voeg JavaScript toe op documentniveau

Om JavaScript op documentniveau toe te voegen, gebruiken we de`JavascriptAction` klasse geleverd door Aspose.PDF voor .NET. Met deze klasse kunt u de JavaScript-instructie opgeven die u aan het PDF-bestand wilt toevoegen.

```csharp
// JavaScript toevoegen op documentniveau
// Instantieer JavascriptAction met de gewenste JavaScript-instructie
JavascriptAction javaScript = new JavascriptAction("this.print({bUI:true,bSilent:false,bShrinkToFit:true});");

// Wijs het JavascriptAction-object toe aan de gewenste actie van Document
doc.OpenAction = javaScript;
```

In deze zelfstudie voegen we een JavaScript-instructie toe die het PDF-bestand met de opgegeven opties afdrukt wanneer het document wordt geopend.

## Stap 3: Voeg JavaScript toe op paginaniveau

 Om JavaScript op paginaniveau toe te voegen, gebruiken we de`JavascriptAction` klasse en de`Actions` eigendom geleverd door Aspose.PDF voor .NET. Met deze eigenschap kunt u JavaScript-instructies opgeven die worden uitgevoerd wanneer de pagina wordt geopend of gesloten.

```csharp
// JavaScript toevoegen op paginaniveau
doc.Pages[2].Actions.OnOpen = new JavascriptAction("app.alert('page 1 opened')");
doc.Pages[2].Actions.OnClose = new JavascriptAction("app.alert('page 1 closed')");
```

In deze zelfstudie voegen we JavaScript-instructies toe die een waarschuwingsbericht weergeven wanneer de pagina wordt geopend of gesloten.

## Stap 4: Sla het PDF-bestand op

Nadat u het JavaScript aan het PDF-bestand heeft toegevoegd, moet u het gewijzigde bestand opslaan. Dit kunt u doen met behulp van de`Save` methode aangeboden door de`Document` klas.

```csharp
dataDir = dataDir + "JavaScript-Added_out.pdf";
// PDF-document opslaan
doc.Save(dataDir);

Console.WriteLine("\nJavascript added successfully to a page.\nFile saved at " + dataDir);
```

Met deze code wordt het gewijzigde PDF-bestand in de opgegeven map opgeslagen.

### Voorbeeldbroncode voor het toevoegen van Javascript aan pagina met Aspose.PDF voor .NET

```csharp
            
// Het pad naar de documentenmap.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Laad een bestaand PDF-bestand
Document doc = new Document(dataDir + "input.pdf");

// JavaScript toevoegen op documentniveau
// Instantieer JavascriptAction met de beschreven JavaScript-instructie
JavascriptAction javaScript = new JavascriptAction("this.print({bUI:true,bSilent:false,bShrinkToFit:true});");

// Wijs het JavascriptAction-object toe aan de gewenste actie van Document
doc.OpenAction = javaScript;

// JavaScript toevoegen op paginaniveau
doc.Pages[2].Actions.OnOpen = new JavascriptAction("app.alert('page 1 opened')");
doc.Pages[2].Actions.OnClose = new JavascriptAction("app.alert('page 1 closed')");

dataDir = dataDir + "JavaScript-Added_out.pdf";
// PDF-document opslaan
doc.Save(dataDir);

Console.WriteLine("\nJavascript added successfully to a page.\nFile saved at " + dataDir);     
```

## Conclusie

In dit artikel hebben we uitgelegd hoe u JavaScript aan een PDF-bestand kunt toevoegen, zowel op documentniveau als op paginaniveau, met behulp van Aspose.PDF voor .NET. We hebben stapsgewijze instructies gegeven en voor elk voorbeeld de volledige broncode toegevoegd. Met deze kennis kunt u JavaScript aan uw PDF-bestanden toevoegen en het gedrag ervan aanpassen aan uw behoeften.


### Veelgestelde vragen over het toevoegen van Java-script aan een PDF-bestand

#### Vraag: Wat is Aspose.PDF voor .NET?

A: Aspose.PDF voor .NET is een krachtige bibliotheek waarmee ontwikkelaars met PDF-bestanden in .NET-toepassingen kunnen werken. Het biedt een breed scala aan functies voor het maken, wijzigen en manipuleren van PDF-documenten.

#### Vraag: Kan ik JavaScript aan een PDF-document toevoegen met Aspose.PDF voor .NET?

A: Ja, met Aspose.PDF voor .NET kunt u JavaScript toevoegen aan zowel het documentniveau als het paginaniveau van een PDF-bestand, waardoor u dynamische en interactieve PDF-documenten kunt maken.

#### Vraag: Hoe laad ik een bestaand PDF-bestand met Aspose.PDF voor .NET?

 A: U kunt een bestaand PDF-bestand laden met behulp van de`Document` klasse en de bijbehorende methoden, zoals weergegeven in de stapsgewijze handleiding.

#### Vraag: Welke typen JavaScript-acties kan ik aan een PDF-document toevoegen?

A: Met Aspose.PDF voor .NET kunt u een grote verscheidenheid aan JavaScript-acties toevoegen, zoals afdrukken, waarschuwingsberichten, manipulatie van formuliervelden en meer.

#### Vraag: Is Aspose.PDF voor .NET geschikt voor commerciële projecten?

A: Ja, Aspose.PDF voor .NET is een betrouwbare en robuuste bibliotheek die vaak wordt gebruikt in commerciële projecten voor PDF-manipulatie en -generatietaken.

