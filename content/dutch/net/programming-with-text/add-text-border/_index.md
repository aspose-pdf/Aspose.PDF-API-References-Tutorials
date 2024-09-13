---
title: Tekstrand toevoegen in PDF-bestand
linktitle: Tekstrand toevoegen in PDF-bestand
second_title: Aspose.PDF voor .NET API-referentie
description: Leer hoe u een tekstrand toevoegt aan een PDF-bestand met Aspose.PDF voor .NET.
type: docs
weight: 70
url: /nl/net/programming-with-text/add-text-border/
---
Deze tutorial begeleidt u door het proces van het toevoegen van een tekstrand in een PDF-bestand met behulp van Aspose.PDF voor .NET. De meegeleverde C#-broncode demonstreert de benodigde stappen.

## Vereisten
Voordat u begint, moet u ervoor zorgen dat u over het volgende beschikt:

- Visual Studio of een andere C#-compiler die op uw computer is geïnstalleerd.
- Aspose.PDF voor .NET-bibliotheek. U kunt het downloaden van de officiële Aspose-website of een pakketbeheerder zoals NuGet gebruiken om het te installeren.

## Stap 1: Het project opzetten
1. Maak een nieuw C#-project in uw favoriete ontwikkelomgeving.
2. Voeg een verwijzing toe naar de Aspose.PDF voor .NET-bibliotheek.

## Stap 2: Importeer de vereiste naamruimten
Voeg in het codebestand waar u de tekstrand wilt toevoegen de volgende richtlijn toe boven aan het bestand:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

## Stap 3: Stel de documentdirectory in
 Zoek in de code de regel met de tekst`string dataDir = "YOUR DOCUMENT DIRECTORY";` en vervangen`"YOUR DOCUMENT DIRECTORY"` met het pad naar de map waar uw documenten zijn opgeslagen.

## Stap 4: Een nieuw Document-object maken
 Een nieuwe instantiëren`Document` object door de volgende regel code toe te voegen:

```csharp
Document pdfDocument = new Document();
```

## Stap 5: Voeg een pagina toe aan het document
 Voeg een nieuwe pagina toe aan het document met behulp van de`Add` methode van de`Pages` verzameling. In de meegeleverde code wordt de nieuwe pagina toegewezen aan de variabele`pdfPage`.

```csharp
Page pdfPage = (Page)pdfDocument.Pages.Add();
```

## Stap 6: Maak een tekstfragment
 Maak een`TextFragment`object en geef de gewenste tekst op. Stel de positie van het tekstfragment in met behulp van de`Position` eigenschap. In de meegeleverde code is de tekst ingesteld op "hoofdtekst" en gepositioneerd op (100, 600) op de pagina.

```csharp
TextFragment textFragment = new TextFragment("main text");
textFragment.Position = new Position(100, 600);
```

## Stap 7: Teksteigenschappen instellen
Pas de teksteigenschappen aan, zoals lettergrootte, lettertype, achtergrondkleur, voorgrondkleur, enz. In de meegeleverde code worden eigenschappen zoals lettergrootte, lettertype, achtergrondkleur, voorgrondkleur en omlijningskleur ingesteld voor het tekstfragment.

```csharp
textFragment.TextState.FontSize = 12;
textFragment.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment.TextState.BackgroundColor = Aspose.Pdf.Color.LightGray;
textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.Red;
textFragment.TextState.StrokingColor = Aspose.Pdf.Color.DarkRed;
```

## Stap 8: Tekstrand inschakelen
 Om de tekstrand in te schakelen, stelt u de`DrawTextRectangleBorder` eigenschap van het tekstfragment`TextState` naar`true`.

```csharp
textFragment.TextState.DrawTextRectangleBorder = true;
```

## Stap 9: Voeg het TextFragment toe aan de pagina
 Gebruik de`TextBuilder` klasse om toe te voegen`TextFragment` bezwaar tegen de pagina.

```csharp
TextBuilder tb = new TextBuilder(pdfPage);
tb.AppendText(textFragment);
```

## Stap 10: Sla het PDF-document op
 Sla het PDF-document op met behulp van de`Save` methode van de`Document` object. Geef het pad op naar het uitvoerbestand dat u in stap 3 hebt ingesteld.

```csharp
pdfDocument.Save(dataDir + "PDFWithTextBorder_out.pdf");
```

### Voorbeeldbroncode voor Tekstrand toevoegen met Aspose.PDF voor .NET 
```csharp
// Het pad naar de documentenmap.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Nieuw documentobject maken
Document pdfDocument = new Document();
// Specifieke pagina ophalen
Page pdfPage = (Page)pdfDocument.Pages.Add();
// Tekstfragment maken
TextFragment textFragment = new TextFragment("main text");
textFragment.Position = new Position(100, 600);
// Teksteigenschappen instellen
textFragment.TextState.FontSize = 12;
textFragment.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment.TextState.BackgroundColor = Aspose.Pdf.Color.LightGray;
textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.Red;
// Stel de eigenschap StrokingColor in voor het tekenen van een rand (omlijning) rond een tekstrechthoek
textFragment.TextState.StrokingColor = Aspose.Pdf.Color.DarkRed;
// Stel de eigenschapswaarde DrawTextRectangleBorder in op true
textFragment.TextState.DrawTextRectangleBorder = true;
TextBuilder tb = new TextBuilder(pdfPage);
tb.AppendText(textFragment);
// Sla het document op
pdfDocument.Save(dataDir + "PDFWithTextBorder_out.pdf");
```

## Conclusie
hebt met succes een tekstrand toegevoegd aan uw PDF-document met Aspose.PDF voor .NET. Het resulterende PDF-bestand is nu te vinden op het opgegeven pad naar het uitvoerbestand.

### Veelgestelde vragen

#### V: Waarop richt deze tutorial zich vooral?

A: Deze tutorial begeleidt u door het proces van het toevoegen van een tekstrand aan een PDF-bestand met behulp van de Aspose.PDF voor .NET-bibliotheek. De meegeleverde C#-broncode demonstreert de benodigde stappen om dit te bereiken.

#### V: Welke naamruimten moet ik importeren voor deze tutorial?

A: Importeer de volgende naamruimten aan het begin van het bestand in het codebestand waar u de tekstrand wilt toevoegen:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

#### V: Hoe geef ik de documentenmap op?

 A: Zoek in de code de regel`string dataDir = "YOUR DOCUMENT DIRECTORY";` en vervangen`"YOUR DOCUMENT DIRECTORY"` met het daadwerkelijke pad naar uw documentenmap.

#### V: Hoe maak ik een Document-object?

 A: In stap 4 maakt u een nieuwe`Document` object met behulp van de volgende regel code:

```csharp
Document pdfDocument = new Document();
```

#### V: Hoe voeg ik een pagina toe aan het document?

 A: In stap 5 voegt u een nieuwe pagina toe aan het document met behulp van de`Add` methode van de`Pages` verzameling:

```csharp
Page pdfPage = (Page)pdfDocument.Pages.Add();
```

#### V: Hoe maak ik een TextFragment en stel ik de positie ervan in?

 A: In stap 6 maak je een`TextFragment` object en stel de positie ervan op de pagina in met behulp van de`Position` eigendom:

```csharp
TextFragment textFragment = new TextFragment("main text");
textFragment.Position = new Position(100, 600);
```

#### V: Hoe kan ik de teksteigenschappen, inclusief de tekstrand, aanpassen?

A: In stap 7 past u verschillende teksteigenschappen aan, zoals de lettergrootte, het lettertype, de achtergrondkleur, de voorgrondkleur en de tekstrand:

```csharp
textFragment.TextState.FontSize = 12;
textFragment.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment.TextState.BackgroundColor = Aspose.Pdf.Color.LightGray;
textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.Red;
textFragment.TextState.StrokingColor = Aspose.Pdf.Color.DarkRed;
textFragment.TextState.DrawTextRectangleBorder = true;
```

#### V: Hoe voeg ik een TextFragment toe aan het PDF-document?

 A: In stap 9 gebruikt u de`TextBuilder` klasse om toe te voegen`TextFragment` object op de pagina:

```csharp
TextBuilder tb = new TextBuilder(pdfPage);
tb.AppendText(textFragment);
```

#### V: Hoe kan ik het resulterende PDF-document opslaan?

A: Nadat u de tekst met een rand hebt toegevoegd, gebruikt u de`Save` methode van de`Document` object om het PDF-document op te slaan:

```csharp
pdfDocument.Save(dataDir + "PDFWithTextBorder_out.pdf");
```

#### V: Wat is de belangrijkste les die je uit deze tutorial hebt geleerd?

A: Door deze tutorial te volgen, hebt u succesvol geleerd hoe u uw PDF-document kunt verbeteren door een tekstrand toe te voegen met behulp van Aspose.PDF voor .NET. Dit kan met name handig zijn om specifieke tekstinhoud in uw PDF-bestanden te benadrukken.