---
title: Sta hergebruik van pagina-inhoud toe
linktitle: Sta hergebruik van pagina-inhoud toe
second_title: Aspose.PDF voor .NET API-referentie
description: Leer hoe u PDF's kunt optimaliseren door de functie "Hergebruik pagina-inhoud toestaan" in te schakelen met Aspose.PDF voor .NET. Verklein de bestandsgrootte en verbeter de prestaties.
type: docs
weight: 50
url: /nl/net/programming-with-document/allowresusepagecontent/
---
In deze zelfstudie leggen we uit hoe u de functie 'Hergebruik pagina-inhoud toestaan' kunt inschakelen met behulp van Aspose.PDF voor .NET. Deze functie optimaliseert het PDF-document door pagina-inhoud te hergebruiken, de bestandsgrootte te verkleinen en de prestaties te verbeteren. Volg de onderstaande stap-voor-stap handleiding:

## Stap 1: Laad het PDF-document

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document pdfDocument = new Document(dataDir + "OptimizeDocument.pdf");
```

## Stap 2: Stel de optie AllowReusePageContent in

```csharp
var optimizeOptions = new Pdf.Optimization.OptimizationOptions
{
    AllowReusePageContent = true
};
```

## Stap 3: Optimaliseer het PDF-document

```csharp
pdfDocument.OptimizeResources(optimizeOptions);
```

## Stap 4: Sla het bijgewerkte document op

```csharp
pdfDocument.Save(dataDir + "OptimizeDocument_out.pdf");
```

## Stap 5: Controleer de verkleining van de bestandsgrootte

```csharp
var fi1 = new System.IO.FileInfo(dataDir + "OptimizeDocument.pdf");
var fi2 = new System.IO.FileInfo(dataDir + "OptimizeDocument_out.pdf");
Console.WriteLine("Original file size: {0}. Reduced file size: {1}", fi1.Length, fi2.Length);
```

Gefeliciteerd! U hebt hergebruik van pagina-inhoud in uw PDF-document toegestaan.

### Voorbeeldbroncode voor het toestaan van hergebruik van pagina-inhoud met Aspose.PDF voor .NET:

```csharp
// Het pad naar de documentenmap.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Document openen
Document pdfDocument = new Document(dataDir + "OptimizeDocument.pdf");

// Stel de optie AllowReusePageContent in
var optimizeOptions = new Pdf.Optimization.OptimizationOptions
{
    AllowReusePageContent = true
};

Console.WriteLine("Start");

// Optimaliseer een PDF-document met OptimizationOptions
pdfDocument.OptimizeResources(optimizeOptions);

// Bewaar het bijgewerkte document
pdfDocument.Save(dataDir + "OptimizeDocument_out.pdf");

Console.WriteLine("Finished");

var fi1 = new System.IO.FileInfo(dataDir + "OptimizeDocument.pdf");
var fi2 = new System.IO.FileInfo(dataDir + "OptimizeDocument_out.pdf");
Console.WriteLine("Original file size: {0}. Reduced file size: {1}", fi1.Length, fi2.Length);

Console.WriteLine("\nAllowed reuse of page content successfully.\nFile saved at " + dataDir);
```

Nu kunt u uw PDF-documenten effectief optimaliseren door hergebruik van pagina-inhoud toe te staan.

## Conclusie

In deze zelfstudie hebben we uitgelegd hoe u de functie "Hergebruik van pagina-inhoud toestaan" kunt inschakelen met behulp van Aspose.PDF voor .NET. Door de meegeleverde stapsgewijze handleiding te volgen en de C#-broncode te gebruiken, kunt u uw PDF-documenten effectief optimaliseren door hergebruik van pagina-inhoud toe te staan. Deze optimalisatie resulteert in kleinere PDF-bestanden, wat kan leiden tot snellere laadtijden en betere prestaties bij het verwerken van grote PDF-documenten. Aspose.PDF voor .NET biedt een robuuste en gebruiksvriendelijke oplossing voor PDF-optimalisatie, waarmee u eenvoudig efficiënte en hoogwaardige PDF-bestanden kunt maken.

### Veelgestelde vragen

#### Vraag: Wat is het doel van het inschakelen van de functie "Hergebruik pagina-inhoud toestaan" in een PDF-document?

A: Als u de functie "Hergebruik van pagina-inhoud toestaan" in een PDF-document inschakelt, wordt het bestand geoptimaliseerd door de pagina-inhoud opnieuw te gebruiken, waardoor de bestandsgrootte wordt verkleind en de algehele prestaties worden verbeterd. Deze optimalisatie resulteert in kleinere PDF-bestanden zonder concessies te doen aan de inhoudskwaliteit.

#### Vraag: Hoe werkt de functie 'Hergebruik van pagina-inhoud toestaan'?

A: Wanneer de functie "Hergebruik pagina-inhoud toestaan" is ingeschakeld, worden identieke pagina-objecten in het PDF-document gedeeld en hergebruikt, in plaats van dat ze voor elk exemplaar worden gedupliceerd. Door het delen van pagina-inhoud wordt de totale bestandsgrootte aanzienlijk kleiner.

#### Vraag: Kan ik de optimalisatie ongedaan maken en het originele document herstellen?

A: Nee, zodra de optimalisatie met "Hergebruik pagina-inhoud toestaan" is uitgevoerd en het PDF-document is opgeslagen, zijn de wijzigingen permanent. Het is raadzaam om een back-up van het originele document te maken voordat u enige optimalisatie uitvoert.

#### Vraag: Heeft het inschakelen van deze functie invloed op het uiterlijk of de inhoud van het PDF-document?

A: Het inschakelen van de functie "Hergebruik van pagina-inhoud toestaan" heeft geen invloed op het uiterlijk of de inhoud van het PDF-document. Het optimaliseert uitsluitend de interne structuur van het bestand om redundantie te verminderen en de efficiëntie te verbeteren.

#### Vraag: Is Aspose.PDF voor .NET een betrouwbare oplossing voor PDF-optimalisatie en -manipulatie?

A: Ja, Aspose.PDF voor .NET is een betrouwbare en veelzijdige bibliotheek voor PDF-optimalisatie en -manipulatie. Het biedt uitgebreide opties om PDF-bestanden te optimaliseren, waaronder het verkleinen van de bestandsgrootte, het verwijderen van ongebruikte bronnen en het verbeteren van de algehele prestaties.