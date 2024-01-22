---
title: Bestandsinformatie ophalen in PDF-bestand
linktitle: Bestandsinformatie ophalen in PDF-bestand
second_title: Aspose.PDF voor .NET API-referentie
description: Leer hoe u de GetFileInfo in PDF-bestandsfunctie van Aspose.PDF voor .NET gebruikt om metagegevensinformatie over een PDF-document op te halen.
type: docs
weight: 180
url: /nl/net/programming-with-document/getfileinfo/
---
 Aspose.PDF voor .NET is een populaire bibliotheek voor PDF-manipulatie waarmee ontwikkelaars PDF-bestanden kunnen maken, bewerken en converteren in hun .NET-toepassingen. Een van de functies van deze bibliotheek is de mogelijkheid om informatie over de metagegevens van een PDF-document op te halen. Deze tutorial leidt u door de stappen voor het gebruik van de`GetFileInfo` functie van Aspose.PDF voor .NET om informatie op te halen over de metagegevens van een PDF-document.

## Stap 1: Installeer Aspose.PDF voor .NET

 Om Aspose.PDF voor .NET in uw .NET-toepassingen te gebruiken, moet u eerst de bibliotheek installeren. U kunt de nieuwste versie van de bibliotheek downloaden van de[Aspose.PDF voor .NET-downloadpagina](https://releases.aspose.com/pdf/net).

Nadat u de bibliotheek heeft gedownload, pakt u de inhoud van het ZIP-bestand uit naar een map op uw computer. U moet dan een verwijzing toevoegen naar de Aspose.PDF voor .NET DLL in uw .NET-project.

## Stap 2: Laad het PDF-document

Nadat u Aspose.PDF voor .NET hebt geïnstalleerd en een verwijzing naar de DLL in uw .NET-project hebt toegevoegd, kunt u de`GetFileInfo` functie om informatie op te halen over de metagegevens van een PDF-document.

De eerste stap bij het gebruik van deze functie is het laden van het PDF-document waarover u informatie wilt ophalen. Om dit te doen, kunt u de volgende code gebruiken:

```csharp
// Het pad naar het PDF-document
string dataDir = "YOUR DOCUMENT DIRECTORY";

//Open het PDF-document
Document pdfDocument = new Document(dataDir + "GetFileInfo.pdf");
```

 Vervang in de bovenstaande code`"YOUR DOCUMENT DIRECTORY"` met het pad naar de map waar uw PDF-document zich bevindt. Deze code laadt het PDF-document in een`Document` object, dat u vervolgens kunt gebruiken om informatie over de metagegevens van het document op te halen.

## Stap 3: Haal de metadata van het document op

Om informatie over de metagegevens van een PDF-document op te halen, kunt u de volgende code gebruiken:

```csharp
// Documentinformatie ophalen
DocumentInfo docInfo = pdfDocument.Info;

// Documentinformatie weergeven
Console.WriteLine("Author: {0}", docInfo.Author);
Console.WriteLine("Creation Date: {0}", docInfo.CreationDate);
Console.WriteLine("Keywords: {0}", docInfo.Keywords);
Console.WriteLine("Modify Date: {0}", docInfo.ModDate);
Console.WriteLine("Subject: {0}", docInfo.Subject);
Console.WriteLine("Title: {0}", docInfo.Title);
```

In de bovenstaande code haalt elke regel een andere metadata-eigenschap van het PDF-document op en voert deze uit naar de console. U kunt deze code aanpassen om alleen de eigendommen op te halen waarin u geïnteresseerd bent.

### Voorbeeldbroncode haalt PDF-bestandsinformatie op met Aspose.PDF voor .NET

 Hier vindt u de volledige broncode voor het ophalen van de metagegevens van een PDF-document met behulp van de`GetFileInfo` kenmerk van Aspose.PDF voor .NET:

```csharp
// Het pad naar het PDF-document
string dataDir = "YOUR DOCUMENT DIRECTORY";

//Open het PDF-document
Document pdfDocument = new Document(dataDir + "GetFileInfo.pdf");

// Documentinformatie ophalen
DocumentInfo docInfo = pdfDocument.Info;

// Documentinformatie weergeven
Console.WriteLine("Author: {0}", docInfo.Author);
Console.WriteLine("Creation Date: {0}", docInfo.CreationDate);
Console.WriteLine("Keywords: {0}", docInfo.Keywords);
Console.WriteLine("Modify Date: {0}", docInfo.ModDate);
Console.WriteLine("Subject: {0}", docInfo.Subject);
Console.WriteLine("Title: {0}", docInfo.Title);
```

## Conclusie

In deze zelfstudie hebben we besproken hoe u Aspose.PDF voor .NET kunt gebruiken om informatie over de metagegevens van een PDF-document op te halen. Door een PDF-document te laden en de metagegevenseigenschappen ervan te openen, kunt u informatie verzamelen over de kenmerken en eigenschappen van het document. Aspose.PDF voor .NET biedt een eenvoudige en gebruiksvriendelijke API om met PDF-documenten te werken, inclusief het ophalen van metadata-informatie, waardoor het een waardevol hulpmiddel is voor PDF-manipulatie in .NET-toepassingen.

### Veelgestelde vragen

#### Vraag: Wat zijn metadata in een PDF-document?

A: Metagegevens in een PDF-document verwijzen naar de informatie die de eigenschappen en kenmerken van het document beschrijft. Deze informatie omvat doorgaans de titel, auteur, onderwerp, trefwoorden, aanmaakdatum, wijzigingsdatum van het document en meer.

#### Vraag: Hoe kan ik Aspose.PDF voor .NET in mijn .NET-project installeren?

 A: Om Aspose.PDF voor .NET te installeren, moet u de bibliotheek downloaden van de[Aspose.PDF voor .NET-downloadpagina](https://releases.aspose.com/pdf/net). Na het downloaden extraheert u de inhoud van het ZIP-bestand en voegt u een verwijzing toe naar de Aspose.PDF voor .NET DLL in uw .NET-project.

#### Vraag: Kan ik de code aanpassen om alleen specifieke metadata-eigenschappen op te halen?

A: Ja, u kunt de code aanpassen om specifieke metadata-eigenschappen op te halen door commentaar te geven op de regels die u niet nodig heeft. Elke regel in de code komt overeen met een specifieke metadata-eigenschap, dus u kunt eigenschappen opnemen of uitsluiten op basis van uw vereisten.

#### Vraag: Welke soorten metadata-eigenschappen kan ik ophalen met Aspose.PDF voor .NET?

A: Met Aspose.PDF voor .NET kunt u verschillende metadata-eigenschappen van een PDF-document ophalen, waaronder de auteur, titel, onderwerp, trefwoorden, aanmaakdatum en wijzigingsdatum.