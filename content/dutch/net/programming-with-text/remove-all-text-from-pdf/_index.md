---
title: Verwijder alle tekst uit PDF
linktitle: Verwijder alle tekst uit PDF
second_title: Aspose.PDF voor .NET API-referentie
description: Leer hoe u alle tekst uit een PDF-document verwijdert met Aspose.PDF voor .NET.
type: docs
weight: 290
url: /nl/net/programming-with-text/remove-all-text-from-pdf/
---
 In deze tutorial leggen we uit hoe je alle tekst uit een PDF-document kunt verwijderen met behulp van de Aspose.PDF-bibliotheek voor .NET. We doorlopen het stapsgewijze proces van het openen van een PDF met behulp van een`TextFragmentAbsorber` om alle tekst te verwijderen en de gewijzigde PDF op te slaan met behulp van de meegeleverde C#-broncode.

## Vereisten

Zorg ervoor dat u over het volgende beschikt voordat u begint:

- De Aspose.PDF voor .NET-bibliotheek geïnstalleerd.
- Basiskennis van programmeren in C#.

## Stap 1: Stel de documentmap in

 Eerst moet u het pad instellen naar de map waar uw PDF-bestanden zich bevinden. Vervangen`"YOUR DOCUMENT DIRECTORY"` in de`dataDir` variabele met het pad naar uw PDF-bestanden.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Stap 2: Open het PDF-document

 Vervolgens openen we het PDF-document met behulp van de`Document` klasse uit de Aspose.PDF-bibliotheek.

```csharp
Document pdfDocument = new Document(dataDir + "RemoveAllText.pdf");
```

## Stap 3: verwijder alle tekst

 Wij initialiseren a`TextFragmentAbsorber`object en gebruik het om alle geabsorbeerde tekst uit het PDF-document te verwijderen.

```csharp
TextFragmentAbsorber absorb = new TextFragmentAbsorber();
absorb. RemoveAllText(pdfDocument);
```

## Stap 4: Sla de gewijzigde PDF op

Ten slotte slaan we het gewijzigde PDF-document op in het opgegeven uitvoerbestand.

```csharp
pdfDocument.Save(dataDir + "RemoveAllText_out.pdf", Aspose.Pdf.SaveFormat.Pdf);
```

### Voorbeeldbroncode voor het verwijderen van alle tekst uit PDF met Aspose.PDF voor .NET 
```csharp
// Het pad naar de documentenmap.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Document openen
Document pdfDocument = new Document(dataDir + "RemoveAllText.pdf");
// Start TextFragmentAbsorber
TextFragmentAbsorber absorber = new TextFragmentAbsorber();
// Verwijder alle geabsorbeerde tekst
absorber.RemoveAllText(pdfDocument);
// Bewaar het document
pdfDocument.Save(dataDir + "RemoveAllText_out.pdf", Aspose.Pdf.SaveFormat.Pdf);
```

## Conclusie

 In deze zelfstudie hebt u geleerd hoe u alle tekst uit een PDF-document kunt verwijderen met behulp van de Aspose.PDF-bibliotheek voor .NET. Door de stapsgewijze handleiding te volgen en de meegeleverde C#-code uit te voeren, kunt u een PDF openen en alle tekst verwijderen met behulp van een`TextFragmentAbsorber`en sla de gewijzigde PDF op.

### Veelgestelde vragen

#### Vraag: Wat is het doel van de tutorial "Alle tekst uit PDF verwijderen"?

 A: De tutorial "Alle tekst uit PDF verwijderen" biedt instructies over hoe u de Aspose.PDF-bibliotheek voor .NET kunt gebruiken om alle tekst uit een PDF-document te verwijderen. De tutorial begeleidt u bij het openen van een PDF met behulp van een`TextFragmentAbsorber` om alle tekst te verwijderen en de gewijzigde PDF op te slaan.

#### Vraag: Waarom zou ik alle tekst uit een PDF-document willen verwijderen?

A: Het verwijderen van alle tekst uit een PDF-document kan handig zijn in scenario's waarin u een versie van het document moet maken zonder enige tekstuele inhoud. Dit kan handig zijn om privacyredenen of om een visuele weergave van de lay-out van het document te genereren zonder de tekstuele informatie weer te geven.

#### Vraag: Hoe stel ik de documentmap in?

A: Om de documentmap in te stellen:

1.  Vervangen`"YOUR DOCUMENT DIRECTORY"` in de`dataDir` variabele met het pad naar de map waar uw PDF-bestanden zich bevinden.

#### Vraag: Hoe verwijder ik alle tekst uit een PDF-document met behulp van de Aspose.PDF-bibliotheek?

A: De tutorial begeleidt u stap voor stap door het proces:

1.  Open het PDF-document met behulp van de`Document` klas.
2.  Initialiseer een`TextFragmentAbsorber` voorwerp.
3. Gebruik de absorber om alle geabsorbeerde tekst uit het PDF-document te verwijderen.
4. Sla het gewijzigde PDF-document op.

#### Vraag: Kan ik selectief tekst verwijderen uit specifieke delen van het document?

A: De tutorial richt zich op het verwijderen van alle tekst uit het volledige PDF-document. Als u selectief tekst uit specifieke gebieden wilt verwijderen, moet u de aanpak aanpassen en complexere logica gebruiken om specifieke tekstfragmenten te identificeren en te verwijderen.

####  Vraag: Hoe werkt de`TextFragmentAbsorber` work to remove text?

 EEN: De`TextFragmentAbsorber`is een klasse die wordt aangeboden door de Aspose.PDF-bibliotheek en die tekstfragmenten uit een PDF-document kan absorberen. Door gebruik te maken van de`RemoveAllText` werkwijze van de`TextFragmentAbsorber` class, kunt u alle geabsorbeerde tekstfragmenten uit het document verwijderen.

#### Vraag: Wat is het verwachte resultaat van het uitvoeren van de opgegeven code?

A: Door de tutorial te volgen en de meegeleverde C#-code uit te voeren, verwijdert u alle tekst uit het invoer-PDF-document en slaat u de gewijzigde versie op als het uitvoer-PDF-bestand.

#### Vraag: Kan ik de code aanpassen om alleen tekst van specifieke pagina's of gebieden te verwijderen?

A: Ja, u kunt de code aanpassen om dat te bereiken. Voor selectieve tekstverwijdering moet u de code aanpassen zodat deze zich richt op specifieke pagina's of regio's binnen het PDF-document.

#### Vraag: Is een geldige Aspose-licentie vereist voor deze zelfstudie?

A: Ja, een geldige Aspose-licentie is nodig om de code in deze tutorial succesvol uit te voeren. U kunt een volledige licentie of een tijdelijke licentie van 30 dagen verkrijgen via de Aspose-website.