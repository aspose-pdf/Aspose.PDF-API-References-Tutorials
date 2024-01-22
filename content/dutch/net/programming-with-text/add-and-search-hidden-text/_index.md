---
title: Voeg verborgen tekst toe en zoek deze in een PDF-bestand
linktitle: Voeg verborgen tekst toe en zoek deze in een PDF-bestand
second_title: Aspose.PDF voor .NET API-referentie
description: Stapsgewijze handleiding voor het toevoegen en doorzoeken van verborgen tekst in een PDF-bestand met Aspose.PDF voor .NET.
type: docs
weight: 20
url: /nl/net/programming-with-text/add-and-search-hidden-text/
---
In deze zelfstudie laten we u zien hoe u verborgen tekst in een PDF-bestand kunt toevoegen en doorzoeken met Aspose.PDF voor .NET. Volg deze stappen om deze handeling eenvoudig uit te voeren.

## 1. Vereisten

Zorg ervoor dat u over het volgende beschikt voordat u begint:

- Visual Studio of een andere ontwikkelomgeving geïnstalleerd en geconfigureerd.
- Een basiskennis van de programmeertaal C#.
- Aspose.PDF-bibliotheek voor .NET geïnstalleerd. Je kunt het downloaden van de officiële website van Aspose.

## 2. Het PDF-document maken met verborgen tekst

Om aan de slag te gaan, gebruikt u de volgende code om een nieuw PDF-document met verborgen tekst te maken:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
// Maak een document
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
Page page = doc.Pages.Add();
TextFragment frag1 = new TextFragment("This is common text.");
TextFragment frag2 = new TextFragment("This is invisible text.");
// Teksteigenschap instellen - onzichtbaar
frag2.TextState.Invisible = true;
page.Paragraphs.Add(frag1);
page.Paragraphs.Add(frag2);
doc.Save(dataDir + "39400_out.pdf");
doc.Dispose();
```

Zorg ervoor dat u het gewenste pad en de gewenste bestandsnaam voor het PDF-document opgeeft.

## 3. Zoek naar tekst in het document

Vervolgens zoeken we de verborgen tekst in het PDF-document. Gebruik de volgende code:

```csharp
doc = new Aspose.Pdf.Document(dataDir + "39400_out.pdf");
TextFragmentAbsorber absorb = new TextFragmentAbsorber();
absorb.Visit(doc.Pages[1]);
foreach(TextFragment fragment in absorber.TextFragments)
{
//Doe iets met de fragmenten
Console.WriteLine("Text '{0}' at position {1}, invisibility: {2} ",
fragment.Text, fragment.Position.ToString(), fragment.TextState.Invisible);
}
doc.Dispose();
```

Hierdoor wordt de verborgen tekst op de tweede pagina van het PDF-document doorzocht en wordt de relevante informatie weergegeven.

### Voorbeeldbroncode voor het toevoegen en doorzoeken van verborgen tekst met Aspose.PDF voor .NET 
```csharp
// Het pad naar de documentenmap.
string dataDir = "YOUR DOCUMENT DIRECTORY";
//Maak een document met verborgen tekst
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
Page page = doc.Pages.Add();
TextFragment frag1 = new TextFragment("This is common text.");
TextFragment frag2 = new TextFragment("This is invisible text.");
//Teksteigenschap instellen - onzichtbaar
frag2.TextState.Invisible = true;
page.Paragraphs.Add(frag1);
page.Paragraphs.Add(frag2);
doc.Save(dataDir + "39400_out.pdf");
doc.Dispose();
//Zoek tekst in het document
doc = new Aspose.Pdf.Document(dataDir + "39400_out.pdf");
TextFragmentAbsorber absorber = new TextFragmentAbsorber();
absorber.Visit(doc.Pages[1]);
foreach (TextFragment fragment in absorber.TextFragments)
{
	//Doe iets met fragmenten
	Console.WriteLine("Text '{0}' on pos {1} invisibility: {2} ",
	fragment.Text, fragment.Position.ToString(), fragment.TextState.Invisible);
}
doc.Dispose();
```

## Conclusie

Gefeliciteerd! U hebt met succes verborgen tekst toegevoegd en gevonden in een PDF-document met behulp van Aspose.PDF voor .NET. U kunt deze methode nu op uw eigen projecten toepassen om verborgen tekst in PDF-bestanden te manipuleren en te doorzoeken.

### Veelgestelde vragen

#### Vraag: Wat is Aspose.PDF voor .NET?

A: Aspose.PDF voor .NET is een robuuste bibliotheek waarmee ontwikkelaars PDF-documenten kunnen maken, manipuleren en transformeren binnen .NET-toepassingen.

#### Vraag: Kan verborgen tekst worden gebruikt voor watermerken?

EEN: Absoluut! Verborgen tekst kan dienen als een effectief middel om PDF-documenten van een watermerk te voorzien, waardoor een extra beveiligingslaag wordt toegevoegd.

#### Vraag: Is het mogelijk om verborgen tekst in een PDF-document zichtbaar te maken?

A: Ja, het proces van het zoeken en onthullen van verborgen tekst in een PDF-document kan worden bereikt met behulp van de technieken die in deze zelfstudie worden beschreven.

#### Vraag: Welke andere functionaliteiten biedt Aspose.PDF voor .NET?

A: Naast verborgen tekstmanipulatie biedt Aspose.PDF voor .NET een breed scala aan functies, waaronder het genereren van PDF's, conversie, codering en meer.