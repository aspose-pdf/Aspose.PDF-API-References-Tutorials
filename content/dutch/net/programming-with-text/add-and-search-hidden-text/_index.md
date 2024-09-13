---
title: Verborgen tekst toevoegen en zoeken in PDF-bestand
linktitle: Verborgen tekst toevoegen en zoeken in PDF-bestand
second_title: Aspose.PDF voor .NET API-referentie
description: Stapsgewijze handleiding voor het toevoegen en zoeken naar verborgen tekst in een PDF-bestand met Aspose.PDF voor .NET.
type: docs
weight: 20
url: /nl/net/programming-with-text/add-and-search-hidden-text/
---
In deze tutorial laten we u zien hoe u verborgen tekst in een PDF-bestand kunt toevoegen en zoeken met Aspose.PDF voor .NET. Volg deze stappen om deze bewerking eenvoudig uit te voeren.

## 1. Voorwaarden

Voordat u begint, moet u ervoor zorgen dat u het volgende bij de hand hebt:

- Visual Studio of een andere ontwikkelomgeving geïnstalleerd en geconfigureerd.
- Basiskennis van de programmeertaal C#.
- Aspose.PDF bibliotheek voor .NET geïnstalleerd. U kunt het downloaden van de officiële website van Aspose.

## 2. Het PDF-document met verborgen tekst maken

Om te beginnen gebruikt u de volgende code om een nieuw PDF-document met verborgen tekst te maken:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
// Een document maken
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

Zorg ervoor dat u het gewenste pad en de bestandsnaam voor het PDF-document opgeeft.

## 3. Zoek naar tekst in het document

Vervolgens zoeken we de verborgen tekst in het PDF-document. Gebruik de volgende code:

```csharp
doc = new Aspose.Pdf.Document(dataDir + "39400_out.pdf");
TextFragmentAbsorber absorb = new TextFragmentAbsorber();
absorb.Visit(doc.Pages[1]);
foreach(TextFragment fragment in absorber.TextFragments)
{
// Doe iets met de fragmenten
Console.WriteLine("Text '{0}' at position {1}, invisibility: {2} ",
fragment.Text, fragment.Position.ToString(), fragment.TextState.Invisible);
}
doc.Dispose();
```

Hiermee wordt de verborgen tekst op de tweede pagina van het PDF-document doorzocht en wordt de relevante informatie weergegeven.

### Voorbeeldbroncode voor Verborgen tekst toevoegen en zoeken met Aspose.PDF voor .NET 
```csharp
// Het pad naar de documentenmap.
string dataDir = "YOUR DOCUMENT DIRECTORY";
//Document met verborgen tekst maken
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

Gefeliciteerd! U hebt met succes verborgen tekst toegevoegd en gevonden in een PDF-document met Aspose.PDF voor .NET. U kunt deze methode nu toepassen op uw eigen projecten om verborgen tekst in PDF-bestanden te manipuleren en te zoeken.

### Veelgestelde vragen

#### V: Wat is Aspose.PDF voor .NET?

A: Aspose.PDF voor .NET is een robuuste bibliotheek waarmee ontwikkelaars PDF-documenten kunnen maken, bewerken en transformeren in .NET-toepassingen.

#### V: Kan verborgen tekst worden gebruikt voor watermerken?

A: Absoluut! Verborgen tekst kan dienen als een effectief middel om PDF-documenten van een watermerk te voorzien en een extra beveiligingslaag toe te voegen.

#### V: Is het mogelijk om verborgen tekst in een PDF-document zichtbaar te maken?

A: Ja, u kunt verborgen tekst in een PDF-document doorzoeken en zichtbaar maken met behulp van de technieken die in deze tutorial worden beschreven.

#### V: Welke andere functionaliteiten biedt Aspose.PDF voor .NET?

A: Naast het manipuleren van verborgen tekst biedt Aspose.PDF voor .NET een breed scala aan functies, waaronder het genereren, converteren, versleutelen van PDF's en meer.