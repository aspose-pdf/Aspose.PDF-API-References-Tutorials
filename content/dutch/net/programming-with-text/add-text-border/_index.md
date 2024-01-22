---
title: Tekstrand toevoegen aan PDF-bestand
linktitle: Tekstrand toevoegen aan PDF-bestand
second_title: Aspose.PDF voor .NET API-referentie
description: Leer hoe u een tekstrand aan een PDF-bestand toevoegt met Aspose.PDF voor .NET.
type: docs
weight: 70
url: /nl/net/programming-with-text/add-text-border/
---
Deze tutorial leidt u door het proces van het toevoegen van een tekstrand aan een PDF-bestand met behulp van Aspose.PDF voor .NET. De meegeleverde C#-broncode demonstreert de noodzakelijke stappen.

## Vereisten
Zorg ervoor dat u over het volgende beschikt voordat u begint:

- Visual Studio of een andere C#-compiler die op uw computer is geïnstalleerd.
- Aspose.PDF voor .NET-bibliotheek. Je kunt het downloaden van de officiële Aspose-website of een pakketbeheerder zoals NuGet gebruiken om het te installeren.

## Stap 1: Zet het project op
1. Maak een nieuw C#-project in de ontwikkelomgeving van uw voorkeur.
2. Voeg een verwijzing toe naar de Aspose.PDF voor .NET-bibliotheek.

## Stap 2: Importeer de vereiste naamruimten
In het codebestand waaraan u de tekstrand wilt toevoegen, voegt u de volgende gebruiksinstructie bovenaan het bestand toe:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

## Stap 3: Stel de documentmap in
 Zoek in de code de regel met de tekst`string dataDir = "YOUR DOCUMENT DIRECTORY";` en vervangen`"YOUR DOCUMENT DIRECTORY"` met het pad naar de map waar uw documenten zijn opgeslagen.

## Stap 4: Maak een nieuw Document-object
 Instantieer een nieuwe`Document` object door de volgende regel code toe te voegen:

```csharp
Document pdfDocument = new Document();
```

## Stap 5: Voeg een pagina toe aan het document
 Voeg een nieuwe pagina aan het document toe met behulp van de`Add` werkwijze van de`Pages`verzameling. In de opgegeven code wordt de nieuwe pagina aan de variabele toegewezen`pdfPage`.

```csharp
Page pdfPage = (Page)pdfDocument.Pages.Add();
```

## Stap 6: Maak een tekstfragment
 Maak een`TextFragment` object en geef de gewenste tekst op. Stel de positie van het tekstfragment in met behulp van de`Position` eigendom. In de opgegeven code is de tekst ingesteld op 'hoofdtekst' en gepositioneerd op (100, 600) op de pagina.

```csharp
TextFragment textFragment = new TextFragment("main text");
textFragment.Position = new Position(100, 600);
```

## Stap 7: Stel teksteigenschappen in
Pas de teksteigenschappen aan, zoals lettergrootte, lettertype, achtergrondkleur, voorgrondkleur, enz. In de meegeleverde code worden eigenschappen zoals lettergrootte, lettertype, achtergrondkleur, voorgrondkleur en lijnkleur ingesteld voor het tekstfragment.

```csharp
textFragment.TextState.FontSize = 12;
textFragment.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment.TextState.BackgroundColor = Aspose.Pdf.Color.LightGray;
textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.Red;
textFragment.TextState.StrokingColor = Aspose.Pdf.Color.DarkRed;
```

## Stap 8: Schakel tekstrand in
 Om de tekstrand in te schakelen, stelt u de`DrawTextRectangleBorder`eigenschap van het tekstfragment`TextState` naar`true`.

```csharp
textFragment.TextState.DrawTextRectangleBorder = true;
```

## Stap 9: Voeg het TextFragment toe aan de pagina
 Gebruik de`TextBuilder` klasse om de`TextFragment` bezwaar maken tegen de pagina.

```csharp
TextBuilder tb = new TextBuilder(pdfPage);
tb.AppendText(textFragment);
```

## Stap 10: Sla het PDF-document op
 Sla het PDF-document op met behulp van de`Save` werkwijze van de`Document` voorwerp. Geef het uitvoerbestandspad op dat u in stap 3 hebt ingesteld.

```csharp
pdfDocument.Save(dataDir + "PDFWithTextBorder_out.pdf");
```

### Voorbeeldbroncode voor het toevoegen van tekstrand met Aspose.PDF voor .NET 
```csharp
// Het pad naar de documentenmap.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Nieuw documentobject maken
Document pdfDocument = new Document();
// Krijg een specifieke pagina
Page pdfPage = (Page)pdfDocument.Pages.Add();
// Maak een tekstfragment
TextFragment textFragment = new TextFragment("main text");
textFragment.Position = new Position(100, 600);
// Teksteigenschappen instellen
textFragment.TextState.FontSize = 12;
textFragment.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment.TextState.BackgroundColor = Aspose.Pdf.Color.LightGray;
textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.Red;
// Stel de eigenschap StrokingColor in voor het tekenen van een rand (strepen) rond de tekstrechthoek
textFragment.TextState.StrokingColor = Aspose.Pdf.Color.DarkRed;
// Stel de eigenschapswaarde van DrawTextRectangleBorder in op true
textFragment.TextState.DrawTextRectangleBorder = true;
TextBuilder tb = new TextBuilder(pdfPage);
tb.AppendText(textFragment);
// Bewaar het document
pdfDocument.Save(dataDir + "PDFWithTextBorder_out.pdf");
```

## Conclusie
U hebt met succes een tekstrand aan uw PDF-document toegevoegd met Aspose.PDF voor .NET. Het resulterende PDF-bestand is nu te vinden op het opgegeven uitvoerbestandspad.

### Veelgestelde vragen

#### Vraag: Wat is de belangrijkste focus van deze tutorial?

A: Deze tutorial begeleidt u bij het toevoegen van een tekstrand aan een PDF-bestand met behulp van de Aspose.PDF voor .NET-bibliotheek. De meegeleverde C#-broncode demonstreert de noodzakelijke stappen om dit te bereiken.

#### Vraag: Welke naamruimten moet ik importeren voor deze tutorial?

A: In het codebestand waaraan u de tekstrand wilt toevoegen, importeert u de volgende naamruimten aan het begin van het bestand:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

#### Vraag: Hoe geef ik de documentmap op?

 A: Zoek de regel in de code`string dataDir = "YOUR DOCUMENT DIRECTORY";` en vervangen`"YOUR DOCUMENT DIRECTORY"` met het daadwerkelijke pad naar uw documentmap.

#### Vraag: Hoe maak ik een Document-object?

 A: In stap 4 maakt u een nieuw bestand`Document` object met behulp van de volgende coderegel:

```csharp
Document pdfDocument = new Document();
```

#### Vraag: Hoe voeg ik een pagina toe aan het document?

 A: In stap 5 voegt u een nieuwe pagina aan het document toe met behulp van de`Add` werkwijze van de`Pages` verzameling:

```csharp
Page pdfPage = (Page)pdfDocument.Pages.Add();
```

#### Vraag: Hoe maak ik een TextFragment en bepaal ik de positie ervan?

 A: In stap 6 maakt u een`TextFragment`object en stel de positie ervan op de pagina in met behulp van de`Position` eigendom:

```csharp
TextFragment textFragment = new TextFragment("main text");
textFragment.Position = new Position(100, 600);
```

#### Vraag: Hoe kan ik de teksteigenschappen aanpassen, inclusief de tekstrand?

A: In stap 7 past u verschillende teksteigenschappen aan, zoals lettergrootte, lettertype, achtergrondkleur, voorgrondkleur en tekstrand:

```csharp
textFragment.TextState.FontSize = 12;
textFragment.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment.TextState.BackgroundColor = Aspose.Pdf.Color.LightGray;
textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.Red;
textFragment.TextState.StrokingColor = Aspose.Pdf.Color.DarkRed;
textFragment.TextState.DrawTextRectangleBorder = true;
```

#### Vraag: Hoe voeg ik het TextFragment toe aan het PDF-document?

 A: In stap 9 gebruikt u de`TextBuilder` klasse om de`TextFragment` bezwaar maken tegen de pagina:

```csharp
TextBuilder tb = new TextBuilder(pdfPage);
tb.AppendText(textFragment);
```

#### Vraag: Hoe bewaar ik het resulterende PDF-document?

 A: Nadat u de tekst met een rand hebt toegevoegd, gebruikt u de`Save` werkwijze van de`Document` object om het PDF-document op te slaan:

```csharp
pdfDocument.Save(dataDir + "PDFWithTextBorder_out.pdf");
```

#### Vraag: Wat is de belangrijkste conclusie uit deze tutorial?

A: Door deze tutorial te volgen, heeft u met succes geleerd hoe u uw PDF-document kunt verbeteren door een tekstrand toe te voegen met Aspose.PDF voor .NET. Dit kan met name handig zijn als u specifieke tekstinhoud in uw PDF-bestanden wilt benadrukken.