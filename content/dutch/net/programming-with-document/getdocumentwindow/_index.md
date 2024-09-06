---
title: Documentvenster ophalen
linktitle: Documentvenster ophalen
second_title: Aspose.PDF voor .NET API-referentie
description: Leer hoe u de GetDocumentWindow-functie van Aspose.PDF voor .NET kunt gebruiken om informatie over de venstereigenschappen van een PDF-document op te halen.
type: docs
weight: 170
url: /nl/net/programming-with-document/getdocumentwindow/
---
Aspose.PDF voor .NET is een krachtige PDF-manipulatiebibliotheek waarmee ontwikkelaars PDF-bestanden kunnen maken, bewerken en converteren in hun .NET-toepassingen. Een van de functies die deze bibliotheek biedt, is de mogelijkheid om informatie over de venstereigenschappen van een document op te halen. Deze tutorial leidt u door de stappen van het gebruik van de`GetDocumentWindow` Functie van Aspose.PDF voor .NET om informatie over de venstereigenschappen van een PDF-document op te halen.

## Stap 1: Aspose.PDF voor .NET installeren

 Om Aspose.PDF voor .NET in uw .NET-toepassingen te gebruiken, moet u eerst de bibliotheek installeren. U kunt de nieuwste versie van de bibliotheek downloaden van de[Aspose.PDF voor .NET downloadpagina](https://releases.aspose.com/pdf/net).

Zodra u de bibliotheek hebt gedownload, pakt u de inhoud van het ZIP-bestand uit naar een map op uw computer. Vervolgens moet u een verwijzing naar de Aspose.PDF voor .NET DLL toevoegen aan uw .NET-project.

## Stap 2: Het PDF-document laden

 Nadat u Aspose.PDF voor .NET hebt geïnstalleerd en een verwijzing naar de DLL in uw .NET-project hebt toegevoegd, kunt u de`GetDocumentWindow`Functie om informatie over de venstereigenschappen van een PDF-document op te halen.

De eerste stap bij het gebruiken van deze functie is het laden van het PDF-document waarvan u informatie wilt ophalen. Hiervoor kunt u de volgende code gebruiken:

```csharp
// Het pad naar het PDF-document
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Open het PDF-document
Document pdfDocument = new Document(dataDir + "GetDocumentWindow.pdf");
```

 Vervang in de bovenstaande code`"YOUR DOCUMENT DIRECTORY"` met het pad naar de directory waar uw PDF-document zich bevindt. Deze code laadt het PDF-document in een`Document` object, dat u vervolgens kunt gebruiken om informatie over de venstereigenschappen van het document op te halen.

## Stap 3: De venstereigenschappen van het document ophalen

Om informatie over de venstereigenschappen van een PDF-document op te halen, kunt u de volgende code gebruiken:

```csharp
// De venstereigenschappen van het document ophalen
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

In de bovenstaande code haalt elke regel een andere venstereigenschap van het PDF-document op en geeft deze uit aan de console. U kunt deze code aanpassen om alleen de eigenschappen op te halen waarin u geïnteresseerd bent.

### Voorbeeldbroncode voor het ophalen van een documentvenster van een PDF-bestand met behulp van Aspose.PDF voor .NET 

 Hier is de volledige broncode voor het ophalen van de venstereigenschappen van een PDF-document met behulp van de`GetDocumentWindow` kenmerk van Aspose.PDF voor .NET:

```csharp
// Het pad naar de documentenmap.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Document openen
Document pdfDocument = new Document(dataDir + "GetDocumentWindow.pdf");

// Verschillende documenteigenschappen verkrijgen
// Positie van het documentvenster - Standaard: false
Console.WriteLine("CenterWindow : {0}", pdfDocument.CenterWindow);

// Overheersende leesvolgorde; bepaalt de positie van de pagina
// Bij weergave naast elkaar - Standaard: L2R
Console.WriteLine("Direction : {0}", pdfDocument.Direction);

// Of de titelbalk van het venster de documenttitel moet weergeven
// Als dit onwaar is, wordt in de titelbalk de naam van het PDF-bestand weergegeven - Standaard: onwaar
Console.WriteLine("DisplayDocTitle : {0}", pdfDocument.DisplayDocTitle);

// Of het formaat van het documentvenster moet worden aangepast aan de grootte van
// Eerste weergegeven pagina - Standaard: false
Console.WriteLine("FitWindow : {0}", pdfDocument.FitWindow);

// Of de menubalk van de viewer-applicatie moet worden verborgen - Standaard: false
Console.WriteLine("HideMenuBar : {0}", pdfDocument.HideMenubar);

// Of de werkbalk van de viewer-applicatie moet worden verborgen - Standaard: false
Console.WriteLine("HideToolBar : {0}", pdfDocument.HideToolBar);

// Of UI-elementen zoals schuifbalken moeten worden verborgen
// En alleen de inhoud van de pagina wordt weergegeven - Standaard: false
Console.WriteLine("HideWindowUI : {0}", pdfDocument.HideWindowUI);

//Paginamodus van document. Hoe het document wordt weergegeven bij het verlaten van de volledig-schermmodus.
Console.WriteLine("NonFullScreenPageMode : {0}", pdfDocument.NonFullScreenPageMode);

// De pagina-indeling, d.w.z. één pagina, één kolom
Console.WriteLine("PageLayout : {0}", pdfDocument.PageLayout);

// Hoe het document eruit moet zien als het wordt geopend
// Bijvoorbeeld miniaturen weergeven, volledig scherm, bijlagepaneel weergeven
Console.WriteLine("pageMode : {0}", pdfDocument.PageMode);
```

## Conclusie

In deze tutorial hebben we geleerd hoe u Aspose.PDF voor .NET kunt gebruiken om informatie over de venstereigenschappen van een PDF-document op te halen. Door een PDF-document te laden en de venstereigenschappen te openen, kunt u informatie verzamelen over hoe het document moet worden weergegeven wanneer het wordt geopend in een viewertoepassing. Aspose.PDF voor .NET biedt een krachtige set functies voor het programmatisch werken met PDF-bestanden, waardoor het een waardevolle tool is voor PDF-manipulatie in .NET-toepassingen.

### Veelgestelde vragen

#### V: Wat is het doel van het ophalen van de venstereigenschappen van een PDF-document?

A: Door de venstereigenschappen van een PDF-document op te halen, kunt u informatie verzamelen over hoe het PDF-document moet worden weergegeven wanneer het wordt geopend in een viewertoepassing. Deze eigenschappen regelen verschillende aspecten, zoals de vensterpositie, weergavemodus en zichtbaarheid van UI-elementen.

#### V: Hoe kan ik Aspose.PDF voor .NET in mijn .NET-project installeren?

 A: Om Aspose.PDF voor .NET te installeren, moet u de bibliotheek downloaden van de[Aspose.PDF voor .NET downloadpagina](https://releases.aspose.com/pdf/net). Pak na het downloaden de inhoud van het ZIP-bestand uit en voeg een verwijzing naar de Aspose.PDF voor .NET DLL toe aan uw .NET-project.

#### V: Kan ik de code aanpassen zodat alleen specifieke venstereigenschappen worden opgehaald?

A: Ja, u kunt de code aanpassen om specifieke venstereigenschappen op te halen door de regels die u niet nodig hebt uit te schakelen. Elke regel in de code komt overeen met een specifieke venstereigenschap, dus u kunt eigenschappen opnemen of uitsluiten op basis van uw vereisten.

#### V: Welke typen venstereigenschappen kan ik ophalen met Aspose.PDF voor .NET?

A: Met Aspose.PDF voor .NET kunt u verschillende venstereigenschappen van een PDF-document ophalen, zoals het centreren van het venster, het instellen van de pagina-indeling, het regelen van de weergave van werkbalken en menubalken, en meer.