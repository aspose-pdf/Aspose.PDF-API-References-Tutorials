---
title: Link-annotatie toevoegen
linktitle: Link-annotatie toevoegen
second_title: Aspose.PDF voor .NET API-referentie
description: Leer hoe u de functie Inktannotatie kunt toevoegen aan PDF-documenten in C# met behulp van Aspose.PDF voor .NET met stapsgewijze handleiding en volledige broncode.
type: docs
weight: 20
url: /nl/net/annotations/addlnkannotation/
---
Aspose.PDF voor .NET is een krachtige bibliotheek waarmee ontwikkelaars verschillende PDF-bewerkingen kunnen uitvoeren. Eén van deze bewerkingen is het toevoegen van inktannotaties aan PDF-documenten. In dit artikel geven we een stapsgewijze handleiding om de C#-broncode uit te leggen voor het toevoegen van Ink Annotation met behulp van Aspose.PDF voor .NET. Laten we beginnen!

## Inzicht in de inktannotatiefunctie van Aspose.PDF voor .NET

Voordat we in de C#-broncode duiken, moeten we eerst begrijpen wat Ink Annotation is en wat het gebruik ervan is.

Inktannotatie is een manier om inktannotaties in vrije vorm op PDF-documenten te tekenen. Hiermee kunt u aantekeningen maken met een stylus of een muis. Deze functie is handig in situaties waarin u diagrammen, schetsen of andere soorten annotaties moet tekenen.

## Stap 1: Een nieuw document maken

De eerste stap bij het toevoegen van Inktannotatie aan een PDF-document is het maken van een nieuw exemplaar van de Document-klasse. Dit wordt bereikt met behulp van het volgende codefragment:

```csharp
string dataDir = "YOUR DATA DIRECTORY";
Document doc = new Document();
Page pdfPage = doc.Pages.Add();
```

Hier maken we een nieuw exemplaar van de klasse Document en voegen er een nieuwe pagina aan toe.

## Stap 2: Inktannotatie maken

De volgende stap is het maken van een exemplaar van de klasse InkAnnotation. Dit wordt gedaan met behulp van het volgende codefragment:

```csharp
System.Drawing.Rectangle drect = new System.Drawing.Rectangle();
drect.Height = (int)pdfPage.Rect.Height;
drect.Width = (int)pdfPage.Rect.Width;
drect.X = 0;
drect.Y = 0;
Aspose.Pdf.Rectangle arect = Aspose.Pdf.Rectangle.FromRect(drect);
IList<Point[]> inkList = new List<Point[]>();
Aspose.Pdf.Point[] arrpt = new Aspose.Pdf.Point[3];
inkList.Add(arrpt);
arrpt[0] = new Aspose.Pdf.Point(100, 800);
arrpt[1] = new Aspose.Pdf.Point(200, 800);
arrpt[2] = new Aspose.Pdf.Point(200, 700);
InkAnnotation ia = new InkAnnotation(pdfPage, arect, inkList);
ia.Title = "XXX";
ia.Color = Aspose.Pdf.Color.LightBlue; // (GetColorFromString(streek.Inktkleur));
ia.CapStyle = CapStyle.Rounded;
Border border = new Border(ia);
border.Width = 25;
ia.Opacity = 0.5;
pdfPage.Annotations.Add(ia);
```

Hier maken we eerst een rechthoek met behulp van de klasse System.Drawing.Rectangle en converteren deze naar Aspose.Pdf.Rectangle met behulp van de FromRect-methode. Vervolgens maken we een exemplaar van de klasse InkAnnotation met behulp van de rechthoek, een lijst met punten en de pagina waarop de annotatie is toegevoegd.

Vervolgens stellen we verschillende eigenschappen van de InkAnnotation in, zoals de titel, kleur, kapstijl, rand en dekking. Ten slotte voegen we de annotatie toe aan de pagina met behulp van de Annotations.Add-methode.

## Stap 3: Het document opslaan

De laatste stap is het opslaan van het PDF-document met de toegevoegde inktannotatie. Dit wordt bereikt met behulp van het volgende codefragment:

```csharp
dataDir = dataDir + "AddlnkAnnotation_out.pdf";
doc.Save(dataDir);
```

Hier voegen we de naam van het uitvoerbestand samen aan de gegevensmap en slaan we het document op met behulp van de Save-methode.

### Voorbeeldbroncode voor het toevoegen van inktannotaties met Aspose.PDF voor .NET

```csharp
// Het pad naar de documentenmap.
string dataDir = "YOUR DATA DIRECTORY";


Document doc = new Document();
Page pdfPage = doc.Pages.Add();
System.Drawing.Rectangle drect = new System.Drawing.Rectangle();
drect.Height = (int)pdfPage.Rect.Height;
drect.Width = (int)pdfPage.Rect.Width;
drect.X = 0;
drect.Y = 0;
Aspose.Pdf.Rectangle arect = Aspose.Pdf.Rectangle.FromRect(drect);
IList<Point[]> inkList = new List<Point[]>();
Aspose.Pdf.Point[] arrpt = new Aspose.Pdf.Point[3];
inkList.Add(arrpt);
arrpt[0] = new Aspose.Pdf.Point(100, 800);
arrpt[1] = new Aspose.Pdf.Point(200, 800);
arrpt[2] = new Aspose.Pdf.Point(200, 700);
InkAnnotation ia = new InkAnnotation(pdfPage, arect, inkList);
ia.Title = "XXX";
ia.Color = Aspose.Pdf.Color.LightBlue; // (GetColorFromString(streek.Inktkleur));
ia.CapStyle = CapStyle.Rounded;
Border border = new Border(ia);
border.Width = 25;
ia.Opacity = 0.5;
pdfPage.Annotations.Add(ia);

dataDir = dataDir + "AddlnkAnnotation_out.pdf";
// Sla het uitvoerbestand op
doc.Save(dataDir);
```

## Conclusie

In deze zelfstudie hebben we onderzocht hoe u inktannotaties aan een PDF-document kunt toevoegen met Aspose.PDF voor .NET. Door de stapsgewijze handleiding en de meegeleverde C#-broncode te volgen, kunnen ontwikkelaars eenvoudig de functionaliteit Inktannotatie in hun PDF-verwerkingstoepassingen implementeren.

### Veelgestelde vragen

#### Vraag: Wat is een inktannotatie in een PDF-document?

A: Met een inktannotatie in een PDF-document kunnen gebruikers inktannotaties in vrije vorm tekenen met een stylus of muis. Het wordt vaak gebruikt om handgetekende schetsen, diagrammen of andere annotaties uit de vrije hand aan een PDF toe te voegen.

#### Vraag: Kan ik het uiterlijk van de inktannotatie aanpassen?

A: Ja, Aspose.PDF voor .NET biedt verschillende eigenschappen om het uiterlijk van de inktannotatie aan te passen, zoals kleur, dekking, kapstijl, randbreedte en meer. Ontwikkelaars kunnen deze eigenschappen aanpassen aan hun specifieke vereisten.

#### Vraag: Is het mogelijk om meerdere inktannotaties toe te voegen aan één PDF-pagina?

A: Ja, u kunt meerdere inktannotaties toevoegen aan één PDF-pagina met Aspose.PDF voor .NET. Elke inktannotatie kan zijn eigen set punten en een aangepast uiterlijk hebben.

#### Vraag: Kan ik inktannotaties toevoegen aan bestaande PDF-documenten?

A: Ja, met Aspose.PDF voor .NET kunt u inktannotaties toevoegen aan zowel nieuw gemaakte PDF-documenten als bestaande PDF-bestanden. U kunt een bestaande PDF openen, inktannotaties toevoegen en het bijgewerkte document opslaan.

#### Vraag: Wat zijn enkele veelvoorkomende toepassingen voor inktannotaties in PDF-documenten?

A: Inktannotaties zijn handig voor een breed scala aan toepassingen, waaronder het toevoegen van handtekeningen of handgeschreven notities aan PDF-formulieren, het annoteren van bouwkundige blauwdrukken of technische tekeningen en het markeren van documenten voor gezamenlijke beoordeling.