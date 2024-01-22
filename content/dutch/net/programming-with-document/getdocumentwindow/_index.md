---
title: Documentvenster ophalen
linktitle: Documentvenster ophalen
second_title: Aspose.PDF voor .NET API-referentie
description: Leer hoe u de GetDocumentWindow-functie van Aspose.PDF voor .NET kunt gebruiken om informatie op te halen over de venstereigenschappen van een PDF-document.
type: docs
weight: 170
url: /nl/net/programming-with-document/getdocumentwindow/
---
 Aspose.PDF voor .NET is een krachtige bibliotheek voor PDF-manipulatie waarmee ontwikkelaars PDF-bestanden in hun .NET-toepassingen kunnen maken, bewerken en converteren. Een van de functies van deze bibliotheek is de mogelijkheid om informatie op te halen over de venstereigenschappen van een document. Deze tutorial leidt u door de stappen voor het gebruik van de`GetDocumentWindow` functie van Aspose.PDF voor .NET om informatie op te halen over de venstereigenschappen van een PDF-document.

## Stap 1: Installeer Aspose.PDF voor .NET

 Om Aspose.PDF voor .NET in uw .NET-toepassingen te gebruiken, moet u eerst de bibliotheek installeren. U kunt de nieuwste versie van de bibliotheek downloaden van de[Aspose.PDF voor .NET-downloadpagina](https://releases.aspose.com/pdf/net).

Nadat u de bibliotheek heeft gedownload, pakt u de inhoud van het ZIP-bestand uit naar een map op uw computer. U moet dan een verwijzing toevoegen naar de Aspose.PDF voor .NET DLL in uw .NET-project.

## Stap 2: Laad het PDF-document

Nadat u Aspose.PDF voor .NET hebt geïnstalleerd en een verwijzing naar de DLL in uw .NET-project hebt toegevoegd, kunt u de`GetDocumentWindow` functie om informatie op te halen over de venstereigenschappen van een PDF-document.

De eerste stap bij het gebruik van deze functie is het laden van het PDF-document waarover u informatie wilt ophalen. Om dit te doen, kunt u de volgende code gebruiken:

```csharp
// Het pad naar het PDF-document
string dataDir = "YOUR DOCUMENT DIRECTORY";

//Open het PDF-document
Document pdfDocument = new Document(dataDir + "GetDocumentWindow.pdf");
```

 Vervang in de bovenstaande code`"YOUR DOCUMENT DIRECTORY"` met het pad naar de map waar uw PDF-document zich bevindt. Deze code laadt het PDF-document in een`Document` object, dat u vervolgens kunt gebruiken om informatie over de venstereigenschappen van het document op te halen.

## Stap 3: Haal de venstereigenschappen van het document op

Om informatie over de venstereigenschappen van een PDF-document op te halen, kunt u de volgende code gebruiken:

```csharp
// Haal de venstereigenschappen van het document op
Console.WriteLine("CenterWindow : {0}", pdfDocument.CenterWindow);
Console.WriteLine("Direction : {0}", pdfDocument.Direction);
Console.WriteLine("DisplayDocTitle : {0}", pdfDocument.DisplayDocTitle);
Console.WriteLine("FitWindow : {0}", pdfDocument.FitWindow);
Console.WriteLine("HideMenuBar : {0}", pdfDocument.HideMenubar);
Console.WriteLine("HideToolBar : {0}", pdfDocument.HideToolBar);
Console.WriteLine("HideWindowUI : {0}", pdfDocument.HideWindowUI);
Console.WriteLine("NonFullScreenPageMode : {0}", pdfDocument.NonFullScreenPageMode);
Console.WriteLine("PageLayout : {0}", pdfDocument.PageLayout);
Console.WriteLine("pageMode : {0}", pdfDocument.PageMode);
```

In de bovenstaande code haalt elke regel een andere venstereigenschap van het PDF-document op en voert deze uit naar de console. U kunt deze code aanpassen om alleen de eigendommen op te halen waarin u geïnteresseerd bent.

### Voorbeeldbroncode voor het ophalen van een documentvenster van een PDF-bestand met Aspose.PDF voor .NET 

 Hier vindt u de volledige broncode voor het ophalen van de venstereigenschappen van een PDF-document met behulp van de`GetDocumentWindow` kenmerk van Aspose.PDF voor .NET:

```csharp
// Het pad naar de documentenmap.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Document openen
Document pdfDocument = new Document(dataDir + "GetDocumentWindow.pdf");

// Krijg verschillende documenteigenschappen
// Positie van het documentvenster - Standaard: false
Console.WriteLine("CenterWindow : {0}", pdfDocument.CenterWindow);

// Overheersende leesvolgorde; bepaalt de positie van de pagina
// Wanneer ze naast elkaar worden weergegeven - Standaard: L2R
Console.WriteLine("Direction : {0}", pdfDocument.Direction);

// Of de titelbalk van het venster de documenttitel moet weergeven
// Als dit niet waar is, wordt in de titelbalk de PDF-bestandsnaam weergegeven - Standaard: onwaar
Console.WriteLine("DisplayDocTitle : {0}", pdfDocument.DisplayDocTitle);

// Of het formaat van het documentvenster moet worden aangepast aan de grootte van
// Eerst weergegeven pagina - Standaard: false
Console.WriteLine("FitWindow : {0}", pdfDocument.FitWindow);

// Of de menubalk van de viewertoepassing moet worden verborgen - Standaard: false
Console.WriteLine("HideMenuBar : {0}", pdfDocument.HideMenubar);

//Of de werkbalk van de viewertoepassing moet worden verborgen - Standaard: false
Console.WriteLine("HideToolBar : {0}", pdfDocument.HideToolBar);

// Of u UI-elementen zoals schuifbalken wilt verbergen
// En laat alleen de pagina-inhoud weergegeven - Standaard: false
Console.WriteLine("HideWindowUI : {0}", pdfDocument.HideWindowUI);

// Paginamodus van document. Document weergeven bij het afsluiten van de modus Volledig scherm.
Console.WriteLine("NonFullScreenPageMode : {0}", pdfDocument.NonFullScreenPageMode);

// De pagina-indeling, dwz één pagina, één kolom
Console.WriteLine("PageLayout : {0}", pdfDocument.PageLayout);

// Hoe het document moet worden weergegeven wanneer het wordt geopend
// Dat wil zeggen miniaturen weergeven, volledig scherm, bijlagenpaneel tonen
Console.WriteLine("pageMode : {0}", pdfDocument.PageMode);
```

## Conclusie

In deze zelfstudie hebben we geleerd hoe u Aspose.PDF voor .NET kunt gebruiken om informatie op te halen over de venstereigenschappen van een PDF-document. Door een PDF-document te laden en de venstereigenschappen te openen, kunt u informatie verzamelen over hoe het document moet worden weergegeven wanneer het in een viewertoepassing wordt geopend. Aspose.PDF voor .NET biedt een krachtige reeks functies voor het programmatisch werken met PDF-bestanden, waardoor het een waardevol hulpmiddel is voor PDF-manipulatie in .NET-toepassingen.

### Veelgestelde vragen

#### Vraag: Wat is het doel van het ophalen van de venstereigenschappen van een PDF-document?

A: Door de venstereigenschappen van een PDF-document op te halen, kunt u informatie verzamelen over hoe het PDF-document moet worden weergegeven wanneer het in een viewertoepassing wordt geopend. Deze eigenschappen bepalen verschillende aspecten, zoals vensterpositie, weergavemodus en zichtbaarheid van UI-elementen.

#### Vraag: Hoe kan ik Aspose.PDF voor .NET in mijn .NET-project installeren?

 A: Om Aspose.PDF voor .NET te installeren, moet u de bibliotheek downloaden van de[Aspose.PDF voor .NET-downloadpagina](https://releases.aspose.com/pdf/net). Na het downloaden extraheert u de inhoud van het ZIP-bestand en voegt u een verwijzing toe naar de Aspose.PDF voor .NET DLL in uw .NET-project.

#### Vraag: Kan ik de code aanpassen om alleen specifieke venstereigenschappen op te halen?

A: Ja, u kunt de code aanpassen om specifieke venstereigenschappen op te halen door de regels die u niet nodig heeft van commentaar te voorzien. Elke regel in de code komt overeen met een specifieke venstereigenschap, dus u kunt eigenschappen opnemen of uitsluiten op basis van uw vereisten.

#### Vraag: Welke soorten venstereigenschappen kan ik ophalen met Aspose.PDF voor .NET?

A: Met Aspose.PDF voor .NET kunt u verschillende venstereigenschappen van een PDF-document ophalen, waaronder het centreren van het venster, het instellen van de pagina-indeling, het regelen van de weergave van werkbalken en menubalken, en meer.