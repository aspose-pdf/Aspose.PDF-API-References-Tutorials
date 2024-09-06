---
title: Bestandsinfo ophalen in PDF-bestand
linktitle: Bestandsinfo ophalen in PDF-bestand
second_title: Aspose.PDF voor .NET API-referentie
description: Leer hoe u de GetFileInfo-functie in PDF-bestanden van Aspose.PDF voor .NET kunt gebruiken om metagegevens over een PDF-document op te halen.
type: docs
weight: 180
url: /nl/net/programming-with-document/getfileinfo/
---
 Aspose.PDF voor .NET is een populaire PDF-manipulatiebibliotheek waarmee ontwikkelaars PDF-bestanden kunnen maken, bewerken en converteren in hun .NET-toepassingen. Een van de functies die deze bibliotheek biedt, is de mogelijkheid om informatie over de metagegevens van een PDF-document op te halen. Deze tutorial leidt u door de stappen van het gebruik van de`GetFileInfo` Functie van Aspose.PDF voor .NET om informatie over de metagegevens van een PDF-document op te halen.

## Stap 1: Aspose.PDF voor .NET installeren

 Om Aspose.PDF voor .NET in uw .NET-toepassingen te gebruiken, moet u eerst de bibliotheek installeren. U kunt de nieuwste versie van de bibliotheek downloaden van de[Aspose.PDF voor .NET downloadpagina](https://releases.aspose.com/pdf/net).

Zodra u de bibliotheek hebt gedownload, pakt u de inhoud van het ZIP-bestand uit naar een map op uw computer. Vervolgens moet u een verwijzing naar de Aspose.PDF voor .NET DLL toevoegen aan uw .NET-project.

## Stap 2: Het PDF-document laden

 Nadat u Aspose.PDF voor .NET hebt geïnstalleerd en een verwijzing naar de DLL in uw .NET-project hebt toegevoegd, kunt u de`GetFileInfo` Functie om informatie over de metagegevens van een PDF-document op te halen.

De eerste stap bij het gebruiken van deze functie is het laden van het PDF-document waarvan u informatie wilt ophalen. Hiervoor kunt u de volgende code gebruiken:

```csharp
// Het pad naar het PDF-document
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Open het PDF-document
Document pdfDocument = new Document(dataDir + "GetFileInfo.pdf");
```

 Vervang in de bovenstaande code`"YOUR DOCUMENT DIRECTORY"` met het pad naar de directory waar uw PDF-document zich bevindt. Deze code laadt het PDF-document in een`Document` object, dat u vervolgens kunt gebruiken om informatie over de metagegevens van het document op te halen.

## Stap 3: De metagegevens van het document ophalen

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

In de bovenstaande code haalt elke regel een andere metadata-eigenschap van het PDF-document op en geeft deze uit aan de console. U kunt deze code aanpassen om alleen de eigenschappen op te halen waarin u geïnteresseerd bent.

### Voorbeeldbroncode om PDF-bestandsinformatie te verkrijgen met behulp van Aspose.PDF voor .NET

 Hier is de volledige broncode voor het ophalen van de metagegevens van een PDF-document met behulp van de`GetFileInfo` kenmerk van Aspose.PDF voor .NET:

```csharp
// Het pad naar het PDF-document
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Open het PDF-document
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

In deze tutorial hebben we besproken hoe u Aspose.PDF voor .NET kunt gebruiken om informatie over de metagegevens van een PDF-document op te halen. Door een PDF-document te laden en de metagegevenseigenschappen te openen, kunt u informatie verzamelen over de kenmerken en eigenschappen van het document. Aspose.PDF voor .NET biedt een eenvoudige en gebruiksvriendelijke API om met PDF-documenten te werken, inclusief het ophalen van metagegevensinformatie, waardoor het een waardevolle tool is voor PDF-manipulatie in .NET-toepassingen.

### Veelgestelde vragen

#### V: Wat zijn metagegevens in een PDF-document?

A: Metadata in een PDF-document verwijst naar de informatie die de eigenschappen en kenmerken van het document beschrijft. Deze informatie omvat doorgaans de titel van het document, auteur, onderwerp, trefwoorden, aanmaakdatum, wijzigingsdatum en meer.

#### V: Hoe kan ik Aspose.PDF voor .NET in mijn .NET-project installeren?

 A: Om Aspose.PDF voor .NET te installeren, moet u de bibliotheek downloaden van de[Aspose.PDF voor .NET downloadpagina](https://releases.aspose.com/pdf/net). Pak na het downloaden de inhoud van het ZIP-bestand uit en voeg een verwijzing naar de Aspose.PDF voor .NET DLL toe aan uw .NET-project.

#### V: Kan ik de code aanpassen om alleen specifieke metadata-eigenschappen op te halen?

A: Ja, u kunt de code aanpassen om specifieke metadata-eigenschappen op te halen door de regels die u niet nodig hebt uit te commentariëren. Elke regel in de code komt overeen met een specifieke metadata-eigenschap, dus u kunt eigenschappen opnemen of uitsluiten op basis van uw vereisten.

#### V: Welke typen metagegevenseigenschappen kan ik ophalen met Aspose.PDF voor .NET?

A: Met Aspose.PDF voor .NET kunt u verschillende metagegevenseigenschappen van een PDF-document ophalen, waaronder de auteur, titel, onderwerp, trefwoorden, aanmaakdatum en wijzigingsdatum.