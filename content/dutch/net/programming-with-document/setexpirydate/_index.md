---
title: Stel de vervaldatum in in het PDF-bestand
linktitle: Stel de vervaldatum in in het PDF-bestand
second_title: Aspose.PDF voor .NET API-referentie
description: Leer hoe u de vervaldatum in een PDF-bestand instelt met Aspose.PDF voor .NET met deze stapsgewijze handleiding.
type: docs
weight: 300
url: /nl/net/programming-with-document/setexpirydate/
---
Aspose.PDF voor .NET is een krachtige bibliotheek die verschillende functies biedt voor het werken met PDF-bestanden. Eén zo'n functie is de mogelijkheid om een vervaldatum voor een PDF-document in te stellen. In deze zelfstudie begeleiden we u bij het instellen van een vervaldatum voor een PDF-document met Aspose.PDF voor .NET. 

## Stap 1: Stel het pad naar de documentmap in

Voordat we beginnen, moeten we het pad instellen naar de map waar ons PDF-document zich bevindt. We slaan dit pad op in een variabele genaamd "dataDir".

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Stap 2: Een nieuw PDF-document maken

 Om een nieuw PDF-document te maken, moeten we een nieuw document instantiëren`Aspose.Pdf.Document` voorwerp. Dit kunnen we doen met behulp van de volgende code:

```csharp
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
```

## Stap 3: Een nieuwe pagina toevoegen aan het PDF-document

Nadat we het PDF-document hebben gemaakt, kunnen we er een nieuwe pagina aan toevoegen. Dit kunnen we doen met behulp van de volgende code:

```csharp
doc.Pages.Add();
```

## Stap 4: Tekst toevoegen aan het PDF-document

Nadat we een pagina aan het PDF-document hebben toegevoegd, kunnen we er tekst aan toevoegen met behulp van de`Paragraphs` verzameling. Dit kunnen we doen met behulp van de volgende code:

```csharp
doc.Pages[1].Paragraphs.Add(new TextFragment("Hello World..."));
```

## Stap 5: De vervaldatum van de PDF instellen met JavaScript

Om de vervaldatum van de PDF in te stellen, moeten we een JavaScript-object maken. Dit kunnen we doen met behulp van de volgende code:

```csharp
JavascriptAction javaScript = new JavascriptAction(
"var year=2017;"
+ "var month=5;"
+ "today = new Date(); today = new Date(today.getFullYear(), today.getMonth());"
+ "expiry = new Date(year, month);"
+ "if (today.getTime() > expiry.getTime())"
+ "app.alert('The file is expired. You need a new one.');");

// Stel JavaScript in als PDF-openactie
doc.OpenAction = javaScript;
```

In deze code stellen we de vervaldatum in op mei 2017.

## Stap 6: Sla het PDF-bestand op

 Nadat u de vervaldatum heeft ingesteld, moet u het PDF-bestand opslaan. Om dit te doen, kunt u gebruik maken van de`Save` werkwijze van de`Document` object en geef het pad door naar waar u het bijgewerkte PDF-bestand wilt opslaan.

```csharp
dataDir = dataDir + "SetExpiryDate_out.pdf";
// PDF-document opslaan
doc.Save(dataDir);
```

### Voorbeeldbroncode voor Set Expiry Date met Aspose.PDF voor .NET

Hier is de volledige voorbeeldbroncode voor het instellen van de vervaldatum met Aspose.PDF voor .NET:

```csharp
// Het pad naar de documentenmap.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Instantieer een documentobject
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
// Pagina toevoegen aan paginaverzameling van PDF-bestand
doc.Pages.Add();
// Voeg een tekstfragment toe aan de alineaverzameling van het paginaobject
doc.Pages[1].Paragraphs.Add(new TextFragment("Hello World..."));
// Maak een JavaScript-object om de vervaldatum van de PDF in te stellen
JavascriptAction javaScript = new JavascriptAction(
"var year=2017;"
+ "var month=5;"
+ "today = new Date(); today = new Date(today.getFullYear(), today.getMonth());"
+ "expiry = new Date(year, month);"
+ "if (today.getTime() > expiry.getTime())"
+ "app.alert('The file is expired. You need a new one.');");
// Stel JavaScript in als PDF-openactie
doc.OpenAction = javaScript;

dataDir = dataDir + "SetExpiryDate_out.pdf";
// PDF-document opslaan
doc.Save(dataDir);
```

## Conclusie

Het instellen van een vervaldatum voor een PDF-document met Aspose.PDF voor .NET is een handige functie om ervoor te zorgen dat het document slechts gedurende een bepaalde periode geldig is. Door de stapsgewijze handleiding te volgen en de meegeleverde C#-broncode te gebruiken, kunnen ontwikkelaars eenvoudig de vervaldatum instellen en PDF's maken met een in de tijd beperkte geldigheid. Deze functie kan met name handig zijn voor documenten die voor een beperkte duur moeten worden geopend of gedistribueerd.

### Veelgestelde vragen over de ingestelde vervaldatum in PDF-bestand

#### Vraag: Kan ik een andere vervaldatum instellen voor het PDF-document?

 A: Ja, u kunt een andere vervaldatum voor het PDF-document instellen door de JavaScript-code in stap 5 te wijzigen. In het gegeven voorbeeld is de vervaldatum ingesteld op mei 2017. Om een andere vervaldatum in te stellen, moet u de`year` En`month` variabelen in de JavaScript-code naar het gewenste jaar en de gewenste maand.

#### Vraag: Wat gebeurt er als het PDF-document is verlopen?

A: Wanneer het PDF-document is verlopen, zoals gespecificeerd in de JavaScript-code, geeft de viewer een waarschuwingsbericht weer waarin wordt aangegeven dat het bestand is verlopen en dat de gebruiker een nieuw bestand nodig heeft. Dit waarschuwingsbericht wordt weergegeven wanneer de PDF wordt geopend.

#### Vraag: Kan ik een specifiek tijdstip voor de vervaldatum gebruiken in plaats van alleen de datum?

 A: Ja, u kunt een specifieke tijd voor de vervaldatum instellen in de JavaScript-code. Door het wijzigen van de`expiry` variabele in de JavaScript-code om de gewenste tijd op te nemen, kunt u een specifieke tijd voor de vervaldatum instellen.