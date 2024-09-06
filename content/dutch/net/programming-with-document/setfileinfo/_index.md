---
title: Stel bestandsinfo in PDF-bestand in
linktitle: Stel bestandsinfo in PDF-bestand in
second_title: Aspose.PDF voor .NET API-referentie
description: Leer hoe u Aspose.PDF voor .NET kunt gebruiken om bestandsinformatie in een PDF-bestand in te stellen met deze stapsgewijze handleiding.
type: docs
weight: 310
url: /nl/net/programming-with-document/setfileinfo/
---
Als u werkt aan een project waarbij PDF-bestanden moeten worden beheerd met Aspose.PDF voor .NET, is een van de functies die u wellicht wilt gebruiken de mogelijkheid om bestandsinformatie voor een PDF-document in te stellen. De bestandsinformatie bevat verschillende details, zoals de auteur, de aanmaakdatum, trefwoorden, de wijzigingsdatum, het onderwerp en de titel. Deze handleiding leidt u door het proces van het instellen van bestandsinformatie voor een PDF-document met behulp van C#-broncode met Aspose.PDF voor .NET.

## Stapsgewijze handleiding voor het instellen van bestandsinfo met Aspose.PDF voor .NET

1. Maak een nieuw C#-project in uw Visual Studio IDE.
2. Voeg een verwijzing naar de Aspose.PDF voor .NET-bibliotheek toe aan uw project.
3. Maak een nieuw PDF-documentobject door het pad op te geven naar het PDF-bestand waarvan u de bestandsinformatie wilt wijzigen.

## Stap 1: Stel het pad naar de documentenmap in.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Stap 2: Open het PDF-document

```csharp
// Document openen
Document pdfDocument = new Document(dataDir + "SetFileInfo.pdf");
```

## Stap 3: Gebruik het DocumentInfo-object om toegang te krijgen tot de bestandsinformatie van het PDF-document.

```csharp
DocumentInfo docInfo = new DocumentInfo(pdfDocument);
```

## Stap 4: Stel de gewenste bestandsinformatiewaarden in met behulp van de eigenschappen van het DocumentInfo-object.

```csharp
docInfo.Author = "Aspose";
docInfo.CreationDate = DateTime.Now;
docInfo.Keywords = "Aspose.Pdf, DOM, API";
docInfo.ModDate = DateTime.Now;
docInfo.Subject = "PDF Information";
docInfo.Title = "Setting PDF Document Information";
```

## Stap 5: Sla het bijgewerkte PDF-document op de opgegeven locatie op.

```csharp
dataDir = dataDir + "SetFileInfo_out.pdf";
pdfDocument.Save(dataDir);
```

## Stap 6: Controleer of de bestandsinformatie succesvol is bijgewerkt.

```csharp
Console.WriteLine("\nFile informations setup successfully.\nFile saved at " + dataDir);
```

U hebt met succes bestandsinformatie voor een PDF-document ingesteld met Aspose.PDF voor .NET.

### Voorbeeldbroncode voor Set File Info met behulp van Aspose.PDF voor .NET


```csharp
// Het pad naar de documentenmap.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Document openen
Document pdfDocument = new Document(dataDir + "SetFileInfo.pdf");

// Documentinformatie specificeren
DocumentInfo docInfo = new DocumentInfo(pdfDocument);

docInfo.Author = "Aspose";
docInfo.CreationDate = DateTime.Now;
docInfo.Keywords = "Aspose.Pdf, DOM, API";
docInfo.ModDate = DateTime.Now;
docInfo.Subject = "PDF Information";
docInfo.Title = "Setting PDF Document Information";

dataDir = dataDir + "SetFileInfo_out.pdf";
// Uitvoerdocument opslaan
pdfDocument.Save(dataDir);

Console.WriteLine("\nFile informations setup successfully.\nFile saved at " + dataDir);
```

## Conclusie

Concluderend biedt Aspose.PDF voor .NET een eenvoudige en effectieve manier om bestandsinformatie in te stellen voor PDF-documenten. Door de hierboven genoemde stappen te volgen, kunt u eenvoudig de gewenste bestandsinformatiewaarden voor uw PDF-documenten instellen met behulp van C#-broncode.

### FAQ's voor setbestandsinfo in PDF-bestand

#### V: Kan ik aanvullende bestandsinformatie-eigenschappen instellen die niet in het voorbeeld worden genoemd?

 A: Ja, u kunt aanvullende bestandsinformatie-eigenschappen instellen met behulp van de`DocumentInfo` object in Aspose.PDF voor .NET. De`DocumentInfo`klasse biedt verschillende eigenschappen waarmee u aanvullende informatie kunt instellen, zoals de producent, versie en aangepaste eigenschappen.

#### V: Is het mogelijk om de bestandsinformatie uit een bestaand PDF-document op te halen?

 A: Ja, u kunt de bestandsinformatie ophalen uit een bestaand PDF-document met Aspose.PDF voor .NET. Hiervoor kunt u de`DocumentInfo` object om toegang te krijgen tot de bestandsinformatie-eigenschappen en de informatie te lezen die is opgeslagen in het PDF-document.

#### V: Wijzigt het instellen van de bestandsinformatie het originele PDF-document?

A: Nee, het instellen van de bestandsinformatie met Aspose.PDF voor .NET wijzigt het originele PDF-document niet. In plaats daarvan wordt een nieuw PDF-document gemaakt met de bijgewerkte bestandsinformatie. Het originele PDF-document blijft ongewijzigd.