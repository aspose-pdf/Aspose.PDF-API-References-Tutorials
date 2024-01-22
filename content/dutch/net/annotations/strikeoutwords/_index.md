---
title: Woorden doorhalen
linktitle: Woorden doorhalen
second_title: Aspose.PDF voor .NET API-referentie
description: Dit artikel biedt een stapsgewijze handleiding voor het gebruik van Aspose.PDF voor de Strike Out Words-functie van .NET, inclusief stapsgewijze handleiding en uitleg
type: docs
weight: 150
url: /nl/net/annotations/strikeoutwords/
---
Aspose.PDF voor .NET is een bibliotheek voor het manipuleren en verwerken van PDF-documenten die verschillende functies biedt voor het maken, wijzigen en converteren van PDF-bestanden. Een van de handige functies van Aspose.PDF is de mogelijkheid om woorden of zinsdelen in een PDF-document door te halen met behulp van de C#-broncode. In dit artikel geven we een stapsgewijze handleiding voor het doorhalen van woorden met Aspose.PDF voor .NET.

## Stap 1: Het PDF-document laden
De eerste stap is het laden van het PDF-document dat u wilt wijzigen. In deze zelfstudie laden we een PDF-document met de naam "input.pdf" uit de map "UW DOCUMENTENMAP". 

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document document = new Document(dataDir + "input.pdf");
```

## Stap 2: Zoeken naar tekstfragmenten
Als u specifieke woorden of zinsdelen in het PDF-document wilt doorhalen, moet u er eerst naar zoeken. Aspose.PDF biedt een TextFragmentAbsorber-klasse die kan worden gebruikt om naar een specifiek tekstfragment in het PDF-document te zoeken.

```csharp
Aspose.Pdf.Text.TextFragmentAbsorber textFragmentAbsorber = new Aspose.Pdf.Text.TextFragmentAbsorber("Estoque");
```

In de bovenstaande code zoeken we naar het tekstfragment "Estoque" in het PDF-document. U kunt dit aanpassen om te zoeken naar een ander woord of zinsnede die u wilt doorhalen.

## Stap 3: Doorstrepen van de tekstfragmenten
Nadat je de tekstfragmenten hebt gevonden, is de volgende stap het doorhalen ervan. Aspose.PDF biedt een klasse StrikeOutAnnotation die kan worden gebruikt om een doorgehaalde annotatie voor het tekstfragment te maken. 

```csharp
Aspose.Pdf.Rectangle rect = new Aspose.Pdf.Rectangle((float)textFragment.Position.XIndent, (float)textFragment.Position.YIndent, (float)textFragment.Position.XIndent + (float)textFragment.Rectangle.Width, (float)textFragment.Position.YIndent + (float)textFragment.Rectangle.Height);

StrikeOutAnnotation strikeOut = new StrikeOutAnnotation(textFragment.Page, rect);
strikeOut.Opacity = .80f;
strikeOut.Border = new Border(strikeOut);
strikeOut.Color = Aspose.Pdf.Color.Red;
textFragment.Page.Annotations.Add(strikeOut);
```

In de bovenstaande code maken we een doorgehaalde annotatie voor elk tekstfragment dat we hebben gevonden. We stellen ook de dekking, rand en kleur van de doorgehaalde annotatie in.

## Stap 4: Het gewijzigde PDF-document opslaan
Nadat u de tekstfragmenten hebt doorgehaald, slaat u het gewijzigde document op.

```csharp
dataDir = dataDir + "StrikeOutWords_out.pdf";
document.Save(dataDir);
```

### Voorbeeldbroncode voor Strike Out Words met Aspose.PDF voor .NET


```csharp

// Het pad naar de documentenmap.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Document openen
Document document = new Document(dataDir + "input.pdf");

// Maak een TextFragment Absorber-instantie om een bepaald tekstfragment te doorzoeken
Aspose.Pdf.Text.TextFragmentAbsorber textFragmentAbsorber = new Aspose.Pdf.Text.TextFragmentAbsorber("Estoque");
// Blader door pagina's van een PDF-document
for (int i = 1; i <= document.Pages.Count; i++)
{
	// Ontvang de eerste pagina van het PDF-document
	Page page = document.Pages[1];
	page.Accept(textFragmentAbsorber);
}

// Maak een verzameling geabsorbeerde tekst
Aspose.Pdf.Text.TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;

//Herhaal de bovenstaande verzameling
for (int j = 1; j <= textFragmentCollection.Count; j++)
{
	Aspose.Pdf.Text.TextFragment textFragment = textFragmentCollection[j];

	// Rechthoekige afmetingen van het TextFragment-object ophalen
	Aspose.Pdf.Rectangle rect = new Aspose.Pdf.Rectangle(
				(float)textFragment.Position.XIndent,
				(float)textFragment.Position.YIndent,
				(float)textFragment.Position.XIndent +
				(float)textFragment.Rectangle.Width,
				(float)textFragment.Position.YIndent +
				(float)textFragment.Rectangle.Height);

	// Instantie van de StrikeOut Annotation-instantie
	StrikeOutAnnotation strikeOut = new StrikeOutAnnotation(textFragment.Page, rect);
	// Stel de dekking voor annotatie in
	strikeOut.Opacity = .80f;
	// Stel de rand voor de annotatie-instantie in
	strikeOut.Border = new Border(strikeOut);
	// Stel de kleur van de annotatie in
	strikeOut.Color = Aspose.Pdf.Color.Red;
	// Voeg annotatie toe aan de annotatieverzameling van TextFragment
	textFragment.Page.Annotations.Add(strikeOut);
}
dataDir = dataDir + "StrikeOutWords_out.pdf";
document.Save(dataDir);
```

## Conclusie

In deze zelfstudie hebben we geleerd hoe u Aspose.PDF voor .NET kunt gebruiken om specifieke woorden in een PDF-document door te halen. Door de stapsgewijze handleiding te volgen en de meegeleverde C#-broncode te gebruiken, kunt u eenvoudig een PDF-document laden, naar specifieke tekstfragmenten zoeken en doorgehaalde annotaties maken om die woorden visueel te markeren en door te halen. Aspose.PDF voor .NET biedt een eenvoudige en effectieve manier om PDF-documenten programmatisch te manipuleren, waardoor het een waardevol hulpmiddel is voor ontwikkelaars die met PDF-bestanden in .NET-toepassingen werken.

### Veelgestelde vragen

#### Vraag: Wat is Aspose.PDF voor .NET?

A: Aspose.PDF voor .NET is een krachtige bibliotheek waarmee ontwikkelaars PDF-documenten programmatisch kunnen maken, bewerken en manipuleren in .NET-toepassingen. Het biedt een breed scala aan functies om met PDF-bestanden te werken, waaronder tekstextractie, het verwerken van annotaties, het invullen van formulieren en nog veel meer.

#### Vraag: Kan ik Aspose.PDF voor .NET gebruiken om specifieke woorden in een PDF-document door te halen?

A: Ja, Aspose.PDF voor .NET biedt functionaliteit om naar specifieke tekstfragmenten in een PDF-document te zoeken en vervolgens doorgehaalde annotaties te maken om die woorden visueel te markeren en door te halen.

#### Vraag: Hoe geef ik de tekst op die ik wil doorhalen in het PDF-document?

 A: Om de tekst op te geven die u wilt doorhalen, kunt u de`TextFragmentAbsorber` klasse geleverd door Aspose.PDF voor .NET. Hiermee kunt u op basis van de door u gewenste criteria naar een specifiek tekstfragment in het PDF-document zoeken.

#### Vraag: Kan ik het uiterlijk van de doorgehaalde annotatie aanpassen?

A: Ja, u kunt verschillende eigenschappen van de doorgehaalde annotatie aanpassen, zoals de dekking, randstijl en kleur. Hierdoor kunt u het uiterlijk van de doorgehaalde annotatie aanpassen aan uw specifieke vereisten.