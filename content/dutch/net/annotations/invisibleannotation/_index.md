---
title: Onzichtbare annotatie in PDF-bestand
linktitle: Onzichtbare annotatie in PDF-bestand
second_title: Aspose.PDF voor .NET API-referentie
description: Leer hoe u annotaties in PDF-bestanden onzichtbaar kunt maken met behulp van C#-broncode met Aspose.PDF voor .NET. Stap-voor-stap handleiding.
type: docs
weight: 100
url: /nl/net/annotations/invisibleannotation/
---
Annotaties in PDF-bestanden zijn een krachtige functie waarmee u extra informatie of notities aan een document kunt toevoegen zonder de daadwerkelijke inhoud te wijzigen. Ze kunnen worden gebruikt om tekst te markeren, de aandacht te vestigen op specifieke delen van een document of om opmerkingen of feedback toe te voegen.

Er zijn veel verschillende soorten annotaties die u in PDF-documenten kunt gebruiken, waaronder:

- Tekstannotaties
- Annotaties koppelen
- Stempelannotaties
- Geluidsannotaties
- Annotaties bij bestandsbijlagen
- en nog veel meer

## Stap 1: Een onzichtbare annotatie maken in een PDF-document met Aspose.PDF voor .NET

 Om een onzichtbare annotatie in een PDF-document te maken met Aspose.PDF voor .NET, moeten we eerst een`FreeTextAnnotation` object en specificeer de locatie en grootte van de annotatie.

```csharp
// Het pad naar de documentenmap.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Document openen
Document doc = new Document(dataDir + "input.pdf");

FreeTextAnnotation annotation = new FreeTextAnnotation(doc.Pages[1], new Aspose.Pdf.Rectangle(50, 600, 250, 650), new DefaultAppearance("Helvetica", 16, System.Drawing.Color.Red));
```

 In de bovenstaande code maken we een`FreeTextAnnotation`object en specificeer de locatie van de annotatie op pagina 2 van het PDF-document. We specificeren ook het lettertype, de grootte en de kleur van de tekst die in de annotatie wordt weergegeven.

## Stap 2: Kenmerken toevoegen aan de onzichtbare annotatie

Vervolgens kunnen we enkele kenmerken aan de annotatie toevoegen, zoals een randkleur, achtergrondkleur of dekking.

```csharp
annotation.Characteristics.Border = System.Drawing.Color.Red;
```

In de bovenstaande code hebben we de randkleur van de annotatie ingesteld op rood.

## Stap 3: De annotatievlaggen instellen

Nadat we de annotatie hebben gemaakt en de kenmerken ervan hebben ingesteld, kunnen we de annotatievlaggen specificeren. In deze zelfstudie willen we dat de annotatie afdrukbaar is, maar niet zichtbaar.

```csharp
annotation.Flags = AnnotationFlags.Print | AnnotationFlags.NoView;
doc.Pages[1].Annotations.Add(annotation);
```

## Stap 4: Het gewijzigde PDF-document opslaan

Ten slotte kunnen we het gewijzigde PDF-document opslaan met de nieuwe onzichtbare annotatie.

```csharp
dataDir = dataDir + "InvisibleAnnotation_out.pdf";
doc.Save(dataDir);
```

## Voorbeeldbroncode voor onzichtbare annotatie met Aspose.PDF voor .NET

```csharp
// Het pad naar de documentenmap.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Document openen
Document doc = new Document(dataDir + "input.pdf");

FreeTextAnnotation annotation = new FreeTextAnnotation(doc.Pages[1], new Aspose.Pdf.Rectangle(50, 600, 250, 650), new DefaultAppearance("Helvetica", 16, System.Drawing.Color.Red));
annotation.Contents = "ABCDEFG";
annotation.Characteristics.Border = System.Drawing.Color.Red;
annotation.Flags = AnnotationFlags.Print | AnnotationFlags.NoView;
doc.Pages[1].Annotations.Add(annotation);

dataDir = dataDir + "InvisibleAnnotation_out.pdf";
// Sla het uitvoerbestand op
doc.Save(dataDir);
// ExEnd: onzichtbare annotatie
Console.WriteLine("\nAnnotation nvisible successfully.\nFile saved at " + dataDir);
```

## Conclusie

In deze zelfstudie hebben we geleerd hoe u een onzichtbare annotatie in een PDF-document kunt maken met Aspose.PDF voor .NET. Onzichtbare annotaties zijn een handige functie als u extra informatie of notities aan een document wilt toevoegen zonder deze aan de lezer te tonen. Door de stapsgewijze handleiding te volgen en de meegeleverde C#-broncode te gebruiken, kunnen ontwikkelaars eenvoudig onzichtbare annotaties in hun PDF-documenten maken en aanpassen. Aspose.PDF voor .NET biedt een uitgebreide set hulpmiddelen voor het werken met annotaties, waarmee u de interactiviteit en bruikbaarheid van uw PDF-bestanden kunt verbeteren.

### Veelgestelde vragen

#### Vraag: Wat is een onzichtbare annotatie in een PDF-document?

A: Een onzichtbare annotatie in een PDF-document is een annotatie die niet zichtbaar is op de pagina, maar aanvullende informatie of notities bevat. Hiermee kunt u opmerkingen of feedback toevoegen zonder deze aan de lezer te tonen.

#### Vraag: Welke soorten kenmerken kunnen aan een onzichtbare annotatie worden toegevoegd?

A: Er kunnen verschillende kenmerken aan een onzichtbare annotatie worden toegevoegd, zoals randkleur, achtergrondkleur, dekking, lettertype, grootte en kleur van de tekst die wordt weergegeven.

#### Vraag: Kan ik verschillende annotatievlaggen instellen voor een onzichtbare annotatie?

A: Ja, u kunt verschillende annotatievlaggen instellen voor een onzichtbare annotatie, afhankelijk van uw vereisten. U kunt de annotatie bijvoorbeeld afdrukbaar maar niet zichtbaar maken.

#### Vraag: Hoe kan ik een onzichtbare annotatie toevoegen aan een specifieke pagina van het PDF-document?

 A: Om een onzichtbare annotatie aan een specifieke pagina van het PDF-document toe te voegen, moet u een`FreeTextAnnotation` object en specificeer de locatie en grootte van de annotatie op die pagina.

#### Vraag: Kan ik de kenmerken van een bestaande onzichtbare annotatie in een PDF-bestand wijzigen?

A: Ja, u kunt de kenmerken van een bestaande onzichtbare annotatie in een PDF-bestand wijzigen met Aspose.PDF voor .NET. U kunt het lettertype, de grootte, de kleur, de randkleur, de achtergrondkleur, de dekking en andere eigenschappen van de annotatie wijzigen.