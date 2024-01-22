---
title: Extraheer gemarkeerde tekst in PDF-bestand
linktitle: Extraheer gemarkeerde tekst in PDF-bestand
second_title: Aspose.PDF voor .NET API-referentie
description: Leer hoe u gemarkeerde tekst uit een PDF-bestand kunt extraheren met Aspose.PDF voor .NET met deze stapsgewijze handleiding.
type: docs
weight: 60
url: /nl/net/annotations/extracthighlightedtext/
---
Om gemarkeerde tekst uit een PDF-bestand te extraheren, kunt u de Aspose.PDF voor .NET API gebruiken. Deze API biedt een eenvoudige manier om alle tekst op te halen die in een document is gemarkeerd.

## Stap 1: Laad het PDF-document

 De eerste stap bij het extraheren van gemarkeerde tekst in een PDF-bestand is het laden van het document met behulp van de Aspose.PDF voor .NET API. U kunt dit doen door een nieuw exemplaar van de`Document` class en geef het pad naar het PDF-document door als parameter. 

```csharp
// Het pad naar de documentenmap.
string dataDir ="YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "ExtractHighlightedText.pdf");
```

## Stap 2: Loop door alle annotaties

 De volgende stap is het doorlopen van alle annotaties in het PDF-document. U kunt dit doen met behulp van een`foreach` lus, zoals zo:

```csharp
foreach (Annotation annotation in doc.Pages[1].Annotations)
{
	// Code komt hier
}
```

## Stap 3: Filter annotaties van tekstopmaak

 Binnen in de`foreach` loop, moet u alle annotaties eruit filteren die geen annotaties voor tekstopmaak zijn. U kunt dit doen door te controleren of de annotatie een exemplaar is van de`TextMarkupAnnotation` klas.

```csharp
if (annotation is TextMarkupAnnotation)
{
	// Code komt hier
}
```

## Stap 4: Haal gemarkeerde tekstfragmenten op

 Nadat u alle tekstopmaakannotaties heeft uitgefilterd, kunt u voor elke annotatie de gemarkeerde tekstfragmenten ophalen. Dit kunt u doen door te bellen naar`GetMarkedTextFragments()` methode op de`TextMarkupAnnotation` voorwerp.

```csharp
TextMarkupAnnotation highlightedAnnotation = annotation as TextMarkupAnnotation;
TextFragmentCollection collection = highlightedAnnotation.GetMarkedTextFragments();
```

## Stap 5: Geef de gemarkeerde tekst weer

 Ten slotte kunt u de gemarkeerde tekst aan de gebruiker tonen. Dit kun je doen door ze allemaal te doorlopen`TextFragment` voorwerp in de`TextFragmentCollection` en bellen met de`Text` eigendom.

```csharp
foreach (TextFragment tf in collection)
{
	Console.WriteLine(tf.Text);
}
```

### Voorbeeldbroncode voor het extraheren van gemarkeerde tekst met Aspose.PDF voor .NET

```csharp
// Het pad naar de documentenmap.
string dataDir ="YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "ExtractHighlightedText.pdf");

foreach (Annotation annotation in doc.Pages[1].Annotations)
{
	if (annotation is TextMarkupAnnotation)
	{
		TextMarkupAnnotation highlightedAnnotation = annotation as TextMarkupAnnotation;
		TextFragmentCollection collection = highlightedAnnotation.GetMarkedTextFragments();
		foreach (TextFragment tf in collection)
		{
			Console.WriteLine(tf.Text);
		}
	}
}
```

## Conclusie

In deze zelfstudie hebben we onderzocht hoe u gemarkeerde tekst uit een PDF-document kunt extraheren met Aspose.PDF voor .NET. Door de stapsgewijze handleiding te volgen en de meegeleverde C#-broncode te gebruiken, kunnen ontwikkelaars eenvoudig gemarkeerde tekst in hun PDF-documenten extraheren en beheren.

### Veelgestelde vragen over het extraheren van gemarkeerde tekst in een PDF-bestand

#### Vraag: Wat zijn tekstopmaakannotaties in een PDF-document?

A: Annotaties met tekstmarkeringen zijn annotaties die specifieke tekst in een PDF-document markeren of markeren. Voorbeelden van annotaties met tekstmarkeringen zijn highlights, onderstrepingen en doorhalingen.

#### Vraag: Kan ik tekst uit andere typen annotaties extraheren met Aspose.PDF voor .NET?

A: Ja, Aspose.PDF voor .NET biedt verschillende methoden om tekst uit verschillende soorten annotaties te extraheren, waaronder annotaties met tekstmarkeringen, annotaties met vrije tekst en meer.

#### Vraag: Ondersteunt Aspose.PDF voor .NET het extraheren van tekst uit met een wachtwoord beveiligde PDF-bestanden?

 A: Ja, Aspose.PDF voor .NET ondersteunt het extraheren van tekst uit met een wachtwoord beveiligde PDF-bestanden. U moet het juiste wachtwoord opgeven wanneer u het PDF-document laadt met behulp van de`Document` klas.

#### Vraag: Kan ik gemarkeerde tekst filteren op basis van andere criteria, zoals kleur of auteur?

A: Ja, u kunt gemarkeerde tekst filteren op basis van andere criteria, zoals kleur, auteur of aanmaakdatum. Aspose.PDF voor .NET biedt methoden om annotaties te openen en te filteren op basis van hun eigenschappen.

#### Vraag: Is het mogelijk om de geëxtraheerde gemarkeerde tekst in een apart bestand op te slaan?

A: Ja, u kunt de geëxtraheerde gemarkeerde tekst in een apart bestand opslaan of in een datastructuur opslaan voor verdere verwerking of analyse.
