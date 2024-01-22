---
title: Lagen toevoegen aan PDF-bestand
linktitle: Lagen toevoegen aan PDF-bestand
second_title: Aspose.PDF voor .NET API-referentie
description: Leer hoe u lagen aan PDF-bestanden toevoegt met Aspose.PDF voor .NET. Stapsgewijze handleiding met codetutorials voor het maken en opslaan van gelaagde PDF's.
type: docs
weight: 20
url: /nl/net/programming-with-document/addlayers/
---
Om lagen aan een PDF-bestand toe te voegen, gebruiken we Aspose.PDF voor .NET. Met deze bibliotheek kunnen we effectief met PDF-bestanden in .NET-toepassingen werken. Volg de stapsgewijze instructies hieronder om lagen toe te voegen met Aspose.PDF voor .NET.

## Stap 1: Maak een nieuw PDF-document

 Begin met het maken van een nieuw exemplaar van de`Document` klasse geleverd door Aspose.PDF voor .NET. Dit zal dienen als het PDF-document waarin we de lagen zullen toevoegen.

```csharp
// Het pad naar de documentenmap.
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
```

## Stap 2: Voeg een pagina toe aan het document

 Voeg vervolgens een pagina toe aan het document met behulp van de`Add` werkwijze van de`Pages` collectie in de`Document` klas.

```csharp
Page page = doc.Pages.Add();
```

## Stap 3: Lagen maken en toevoegen aan de pagina

 Maak exemplaren van de`Layer` klasse voor elke laag die u aan het PDF-bestand wilt toevoegen. Geef een unieke identificatie en een naam op voor elke laag.

```csharp
Layer layer = new Layer("oc1", "Red Line");
layer.Contents.Add(new Aspose.Pdf.Operators.SetRGBColorStroke(1, 0, 0));
layer.Contents.Add(new Aspose.Pdf.Operators.MoveTo(500, 700));
layer.Contents.Add(new Aspose.Pdf.Operators.LineTo(400, 700));
layer.Contents.Add(new Aspose.Pdf.Operators.Stroke());
page.Layers = new List<Layer>();
page.Layers.Add(layer);

layer = new Layer("oc2", "Green Line");
layer.Contents.Add(new Aspose.Pdf.Operators.SetRGBColorStroke(0, 1, 0));
layer.Contents.Add(new Aspose.Pdf.Operators.MoveTo(500, 750));
layer.Contents.Add(new Aspose.Pdf.Operators.LineTo(400, 750));
layer.Contents.Add(new Aspose.Pdf.Operators.Stroke());
page.Layers.Add(layer);

layer = new Layer("oc3", "Blue Line");
layer.Contents.Add(new Aspose.Pdf.Operators.SetRGBColorStroke(0, 0, 1));
layer.Contents.Add(new Aspose.Pdf.Operators.MoveTo(500, 800));
layer.Contents.Add(new Aspose.Pdf.Operators.LineTo(400, 800));
layer.Contents.Add(new Aspose.Pdf.Operators.Stroke());
page.Layers.Add(layer);
```

In deze zelfstudie hebben we drie lagen met verschillende kleuren en namen aan de pagina toegevoegd.

## Stap 4: Sla het PDF-bestand op

 Sla het gewijzigde PDF-bestand op met behulp van de`Save` werkwijze van de`Document` klas.

```csharp
dataDir = dataDir + "AddLayers_out.pdf";
doc.Save(dataDir);

Console.WriteLine("\nLayers added successfully to PDF file.\nFile saved at " + dataDir);
```

Met deze code wordt het gewijzigde PDF-bestand in de opgegeven map opgeslagen.

### Voorbeeldbroncode voor het toevoegen van lagen aan PDF-pagina's met Aspose.PDF voor .NET

```csharp            
// Het pad naar de documentenmap.
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
Page page = doc.Pages.Add();
Layer layer = new Layer("oc1", "Red Line");
layer.Contents.Add(new Aspose.Pdf.Operators.SetRGBColorStroke(1, 0, 0));
layer.Contents.Add(new Aspose.Pdf.Operators.MoveTo(500, 700));
layer.Contents.Add(new Aspose.Pdf.Operators.LineTo(400, 700));
layer.Contents.Add(new Aspose.Pdf.Operators.Stroke());
page.Layers = new  List<Layer>();
page.Layers.Add(layer);
layer = new Layer("oc2", "Green Line");
layer.Contents.Add(new Aspose.Pdf.Operators.SetRGBColorStroke(0, 1, 0));
layer.Contents.Add(new Aspose.Pdf.Operators.MoveTo(500, 750));
layer.Contents.Add(new Aspose.Pdf.Operators.LineTo(400, 750));
layer.Contents.Add(new Aspose.Pdf.Operators.Stroke());
page.Layers.Add(layer);
layer = new Layer("oc3", "Blue Line");
layer.Contents.Add(new Aspose.Pdf.Operators.SetRGBColorStroke(0, 0, 1));
layer.Contents.Add(new Aspose.Pdf.Operators.MoveTo(500, 800));
layer.Contents.Add(new Aspose.Pdf.Operators.LineTo(400, 800));
layer.Contents.Add(new Aspose.Pdf.Operators.Stroke());
page.Layers.Add(layer);
dataDir = dataDir + "AddLayers_out.pdf";
doc.Save(dataDir);

Console.WriteLine("\nLayers added successfully to PDF file.\nFile saved at " + dataDir);

```

## Conclusie

In dit artikel hebben we een stapsgewijze handleiding gegeven voor het toevoegen van lagen aan PDF-bestanden met Aspose.PDF voor .NET. Door de instructies te volgen en de meegeleverde codetutorials te gebruiken, kunt u eenvoudig lagen in uw PDF-documenten opnemen. Met lagen kunt u de zichtbaarheid van inhoud organiseren en beheren, waardoor uw gebruikers een meer interactieve en aanpasbare ervaring krijgen.


### Veelgestelde vragen over het toevoegen van lagen aan een PDF-bestand

#### Vraag: Wat is Aspose.PDF voor .NET?

A: Aspose.PDF voor .NET is een krachtige bibliotheek waarmee ontwikkelaars effectief met PDF-bestanden kunnen werken in .NET-toepassingen. Het biedt een breed scala aan functies voor het maken, wijzigen en manipuleren van PDF-documenten.

#### Vraag: Wat zijn PDF-lagen?

A: Met PDF-lagen, ook wel Optionele Inhoudsgroepen (OCG's) genoemd, kunt u de zichtbaarheid en weergave van specifieke inhoud in een PDF-bestand bepalen. Ze zijn handig voor het organiseren van inhoud en het maken van interactieve documenten.

#### Vraag: Kan ik meerdere lagen aan een PDF-bestand toevoegen met Aspose.PDF voor .NET?

A: Ja, u kunt meerdere lagen aan een PDF-bestand toevoegen met Aspose.PDF voor .NET. Elke laag kan zijn eigen unieke identificatie en naam hebben, zoals gedemonstreerd in de tutorial.

#### Vraag: Hoe kan ik het uiterlijk van de lagen aanpassen?

A: U kunt het uiterlijk van de lagen aanpassen door verschillende eigenschappen op te geven, zoals kleur, dekking en zichtbaarheid. Aspose.PDF voor .NET biedt verschillende opties om dit te bereiken.

#### Vraag: Is Aspose.PDF voor .NET geschikt voor professionele projecten?

A: Ja, Aspose.PDF voor .NET is een betrouwbare en veelgebruikte bibliotheek voor PDF-manipulatie in professionele projecten. Het biedt uitgebreide functionaliteit en uitstekende prestaties voor het werken met PDF-bestanden in .NET-toepassingen.