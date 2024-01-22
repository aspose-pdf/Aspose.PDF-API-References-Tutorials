---
title: Voeg JavaScript toe aan PDF-document
linktitle: Voeg JavaScript toe aan Doc
second_title: Aspose.PDF voor .NET API-referentie
description: Leer hoe u JavaScript aan een PDF-document kunt toevoegen en verwijderen met Aspose.PDF voor .NET. Stapsgewijze handleiding met codetutorials voor scripting op documentniveau.
type: docs
weight: 30
url: /nl/net/programming-with-document/addremovejavascripttodoc/
---
Om JavaScript aan een PDF-document toe te voegen of te verwijderen, gebruiken we de Aspose.PDF voor .NET-bibliotheek. Met deze krachtige bibliotheek kunnen we PDF-bestanden in .NET-toepassingen manipuleren. Volg de onderstaande stapsgewijze instructies om JavaScript toe te voegen en te verwijderen met Aspose.PDF voor .NET.

## Stap 1: Maak een nieuw PDF-document

 Begin met het maken van een nieuw exemplaar van de`Document` klasse geleverd door Aspose.PDF voor .NET. Dit zal dienen als het PDF-document waarin we JavaScript zullen toevoegen.

```csharp
// Het pad naar de documentenmap.
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
doc.Pages.Add();
```

## Stap 2: Voeg JavaScript toe op documentniveau

 Om JavaScript op documentniveau toe te voegen, gebruikt u de`JavaScript` eigendom van de`Document` klas. Wijs JavaScript-functies toe aan toetsen in het JavaScript-woordenboek.

```csharp
doc.JavaScript["func1"] = "function func1() { hello(); }";
doc.JavaScript["func2"] = "function func2() { hello(); }";
doc.Save(dataDir + "AddJavascript.pdf");
```

 In deze tutorial hebben we twee JavaScript-functies toegevoegd,`func1` En`func2`, naar het PDF-document.

## Stap 3: JavaScript op documentniveau verwijderen

 Om JavaScript op documentniveau te verwijderen, laadt u het PDF-document en opent u het`JavaScript`woordenboek. Herhaal de toetsen en verwijder de gewenste JavaScript-functie.

```csharp
Document doc1 = new Document(dataDir + "AddJavascript.pdf");
IList keys = (System.Collections.IList)doc1.JavaScript.Keys;

foreach (string key in keys)
{
    Console.WriteLine(key + " ==> " + doc1.JavaScript[key]);
}

doc1.JavaScript.Remove("func1");
Console.WriteLine("Key 'func1' removed");
```

 In deze zelfstudie verwijderen we de`func1` JavaScript-functie van het PDF-document.

## Stap 4: Wijzigingen opslaan en verifiëren

Sla het gewijzigde PDF-document op en verifieer de wijzigingen.

```csharp
Console.WriteLine("\nJavascript added/removed successfully to a document.");
```

Deze code slaat het gewijzigde PDF-document op en geeft het succesbericht weer.

### Voorbeeldbroncode voor Toevoegen Verwijder Javascript uit PDF-documenten met Aspose.PDF voor .NET

```csharp
// Het pad naar de documentenmap.
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
doc.Pages.Add();
doc.JavaScript["func1"] = "function func1() { hello(); }";
doc.JavaScript["func2"] = "function func2() { hello(); }";
doc.Save(dataDir + "AddJavascript.pdf");

// JavaScript op documentniveau verwijderen
Document doc1 = new Document(dataDir + "AddJavascript.pdf");
IList keys = (System.Collections.IList)doc1.JavaScript.Keys;
Console.WriteLine("=============================== ");
foreach (string key in keys)
{
	Console.WriteLine(key + " ==> " + doc1.JavaScript[key]);
}

doc1.JavaScript.Remove("func1");
Console.WriteLine("Key 'func1' removed ");
Console.WriteLine("=============================== ");

Console.WriteLine("\nJavascript added/removed successfully to a document.");
```

## Conclusie

In dit artikel hebben we een stapsgewijze handleiding gegeven voor het toevoegen en verwijderen van JavaScript uit PDF-documenten met Aspose.PDF voor .NET. Door de instructies te volgen en de meegeleverde code-tutorials te gebruiken, kunt u eenvoudig JavaScript in uw PDF-documenten opnemen en indien nodig verwijderen. JavaScript maakt dynamische functionaliteit en interactiviteit in uw PDF-bestanden mogelijk, waardoor de gebruikerservaring wordt verbeterd.


### Veelgestelde vragen over het toevoegen en verwijderen van JavaScript aan een PDF-document

#### Vraag: Wat is Aspose.PDF voor .NET?

A: Aspose.PDF voor .NET is een krachtige bibliotheek waarmee ontwikkelaars PDF-bestanden in .NET-toepassingen effectief kunnen manipuleren. Het biedt uitgebreide functies voor het programmatisch werken met PDF-documenten.

#### Vraag: Hoe kan ik JavaScript aan een PDF-document toevoegen met Aspose.PDF voor .NET?

 A: U kunt JavaScript op documentniveau toevoegen met behulp van de`JavaScript` eigendom van de`Document` klas. Wijs eenvoudig JavaScript-functies toe aan toetsen in het JavaScript-woordenboek.

#### Vraag: Kan ik JavaScript uit een PDF-document verwijderen met Aspose.PDF voor .NET?

 A: Ja, u kunt JavaScript uit een PDF-document verwijderen door naar het`JavaScript` woordenboek en het verwijderen van de gewenste JavaScript-functie.

#### Vraag: Is Aspose.PDF voor .NET geschikt voor professionele projecten?

A: Absoluut, Aspose.PDF voor .NET wordt veel gebruikt in professionele projecten voor PDF-manipulatie en generatietaken. Het biedt hoge prestaties en betrouwbare functionaliteit.

#### Vraag: Welke voordelen biedt het toevoegen van JavaScript aan een PDF-document?

A: Door JavaScript aan een PDF-document toe te voegen, kunt u interactieve en dynamische PDF-bestanden maken. U kunt formuliervalidatie implementeren, berekeningen uitvoeren en verschillende interactiviteitsfuncties toevoegen om de gebruikerservaring te verbeteren.