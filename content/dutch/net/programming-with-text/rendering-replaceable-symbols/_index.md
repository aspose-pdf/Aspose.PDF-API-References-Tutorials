---
title: Vervangbare symbolen in PDF-bestand weergeven
linktitle: Vervangbare symbolen in PDF-bestand weergeven
second_title: Aspose.PDF voor .NET API-referentie
description: Leer hoe u vervangbare symbolen in een PDF-bestand kunt weergeven met Aspose.PDF voor .NET.
type: docs
weight: 310
url: /nl/net/programming-with-text/rendering-replaceable-symbols/
---
In deze tutorial leggen we uit hoe u vervangbare symbolen in een PDF-bestand kunt renderen met behulp van de Aspose.PDF-bibliotheek voor .NET. We doorlopen het stapsgewijze proces van het maken van een PDF, het toevoegen van een tekstfragment met nieuwe regelmarkeringen, het instellen van teksteigenschappen, het positioneren van de tekst en het opslaan van de PDF met behulp van de meegeleverde C#-broncode.

## Vereisten

Voordat u begint, moet u ervoor zorgen dat u over het volgende beschikt:

- De Aspose.PDF voor .NET-bibliotheek is geïnstalleerd.
- Basiskennis van C#-programmering.

## Stap 1: De documentenmap instellen

 Eerst moet u het pad instellen naar de map waar u het gegenereerde PDF-bestand wilt opslaan. Vervangen`"YOUR DOCUMENT DIRECTORY"` in de`dataDir` variabele met het pad naar de gewenste map.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Stap 2: Maak een PDF-document en -pagina

 Vervolgens maken we een nieuw PDF-document en voegen er een pagina aan toe met behulp van de`Document` klasse en`Page` klas uit de Aspose.PDF bibliotheek.

```csharp
Aspose.Pdf.Document pdfApplicationDoc = new Aspose.Pdf.Document();
Aspose.Pdf.Page applicationFirstPage = (Aspose.Pdf.Page)pdfApplicationDoc.Pages.Add();
```

## Stap 3: Voeg een tekstfragment toe met nieuwe regelmarkeringen

 Wij creëren een`TextFragment` object en stel de tekst in om nieuwe regelmarkeringen op te nemen (`Environment.NewLine`) om meerdere tekstregels weer te geven.

```csharp
Aspose.Pdf.Text.TextFragment textFragment = new Aspose.Pdf.Text.TextFragment("Applicant Name: " + Environment.NewLine + " Joe Smoe");
```

## Stap 4: Tekstfragmenteigenschappen instellen

Indien gewenst kunnen we diverse eigenschappen voor het tekstfragment instellen, zoals lettergrootte, lettertype, achtergrondkleur en voorgrondkleur.

```csharp
textFragment.TextState.FontSize = 12;
textFragment.TextState.Font = Aspose.Pdf.Text.FontRepository.FindFont("TimesNewRoman");
textFragment.TextState.BackgroundColor = Aspose.Pdf.Color.LightGray;
textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.Red;
```

## Stap 5: Tekstparagraaf en positie maken

 Wij creëren een`TextParagraph` object, voeg het tekstfragment toe aan de alinea en stel de positie van de alinea op de pagina in.

```csharp
TextParagraph par = new TextParagraph();
par.AppendLine(textFragment);
par.Position = new Aspose.Pdf.Text.Position(100, 600);
```

## Stap 6: Voeg een tekstparagraaf toe aan de pagina

 Wij creëren een`TextBuilder` object met de pagina en voeg de tekstalinea toe aan de tekstbouwer.

```csharp
TextBuilder textBuilder = new TextBuilder(applicationFirstPage);
textBuilder.AppendParagraph(par);
```

## Stap 7: Sla het PDF-document op

Ten slotte slaan we het PDF-document op in het opgegeven uitvoerbestand.

```csharp
dataDir = dataDir + "RenderingReplaceableSymbols_out.pdf";
pdfApplicationDoc.Save(dataDir);
Console.WriteLine("\nReplaceable symbols rendered successfully during PDF creation.\nFile saved at " + dataDir);
```

### Voorbeeldbroncode voor het renderen van vervangbare symbolen met behulp van Aspose.PDF voor .NET 
```csharp
// Het pad naar de documentenmap.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Aspose.Pdf.Document pdfApplicationDoc = new Aspose.Pdf.Document();
Aspose.Pdf.Page applicationFirstPage = (Aspose.Pdf.Page)pdfApplicationDoc.Pages.Add();
// Initialiseer een nieuw TextFragment met tekst die de vereiste nieuwe-regelmarkeringen bevat
Aspose.Pdf.Text.TextFragment textFragment = new Aspose.Pdf.Text.TextFragment("Applicant Name: " + Environment.NewLine + " Joe Smoe");
// Stel indien nodig tekstfragmenteigenschappen in
textFragment.TextState.FontSize = 12;
textFragment.TextState.Font = Aspose.Pdf.Text.FontRepository.FindFont("TimesNewRoman");
textFragment.TextState.BackgroundColor = Aspose.Pdf.Color.LightGray;
textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.Red;
// Maak een TextParagraph-object
TextParagraph par = new TextParagraph();
// Nieuw TextFragment toevoegen aan alinea
par.AppendLine(textFragment);
// Alineapositie instellen
par.Position = new Aspose.Pdf.Text.Position(100, 600);
// TextBuilder-object maken
TextBuilder textBuilder = new TextBuilder(applicationFirstPage);
// Voeg de TextParagraph toe met behulp van TextBuilder
textBuilder.AppendParagraph(par);
dataDir = dataDir + "RenderingReplaceableSymbols_out.pdf";
pdfApplicationDoc.Save(dataDir);
Console.WriteLine("\nReplaceable symbols render successfully duing pdf creation.\nFile saved at " + dataDir);
```

## Conclusie

In deze tutorial hebt u geleerd hoe u vervangbare symbolen in een PDF-document kunt renderen met behulp van de Aspose.PDF-bibliotheek voor .NET. Door de stapsgewijze handleiding te volgen en de meegeleverde C#-code uit te voeren, kunt u een PDF maken, tekst toevoegen met nieuwe-regelmarkeringen, teksteigenschappen instellen, de tekst op de pagina positioneren en de PDF opslaan.

### Veelgestelde vragen

#### V: Wat is het doel van de tutorial 'Vervangbare symbolen in een PDF-bestand renderen'?

A: De tutorial "Rendering Replaceable Symbols In PDF File" laat zien hoe u de Aspose.PDF-bibliotheek voor .NET kunt gebruiken om een PDF-document te maken dat vervangbare symbolen bevat. Deze symbolen worden weergegeven als tekstfragmenten met nieuwe-regelmarkeringen om inhoud met meerdere regels te maken.

#### V: Waarom zou ik vervangbare symbolen in een PDF-document willen weergeven?

A: Het renderen van vervangbare symbolen is handig wanneer u dynamisch PDF-inhoud moet genereren die variabele of gebruikerspecifieke informatie bevat. Deze symbolen fungeren als tijdelijke aanduidingen die tijdens runtime kunnen worden vervangen door werkelijke gegevens, zoals waarden van formuliervelden of gepersonaliseerde details.

#### V: Hoe stel ik de documentenmap in?

A: Om de documentenmap in te stellen:

1.  Vervangen`"YOUR DOCUMENT DIRECTORY"` in de`dataDir` variabele met het pad naar de map waar u het gegenereerde PDF-bestand wilt opslaan.

#### V: Hoe kan ik vervangbare symbolen in een PDF-document weergeven met behulp van de Aspose.PDF-bibliotheek?

A: De tutorial begeleidt u stap voor stap door het proces:

1.  Maak een nieuw PDF-document met behulp van de`Document` klas.
2.  Voeg een pagina toe aan het document met behulp van de`Page` klas.
3.  Maak een`TextFragment` object met nieuwe-regelmarkeringen (`Environment.NewLine`) om inhoud met meerdere regels weer te geven.
4. Pas de eigenschappen van het tekstfragment aan, zoals lettergrootte, lettertype, achtergrondkleur en voorgrondkleur.
5.  Maak een`TextParagraph` object, voeg het tekstfragment eraan toe en stel de positie van de alinea op de pagina in.
6.  Maak een`TextBuilder` object met de pagina en voeg de tekstalinea eraan toe.
7. Sla het PDF-document op.

#### V: Wat is het doel van het gebruik van nieuwe-regelmarkeringen (`Environment.NewLine`) in the text fragment?

 A: Nieuwe regelmarkeringen worden gebruikt om inhoud van meerdere regels binnen een enkel tekstfragment te creëren. Door`Environment.NewLine`kunt u aangeven waar in de tekst regelafbrekingen moeten voorkomen.

#### V: Kan ik het uiterlijk van de vervangbare symbolen aanpassen?

A: Ja, u kunt verschillende eigenschappen van het tekstfragment aanpassen, zoals lettergrootte, lettertype, achtergrondkleur en voorgrondkleur. Deze eigenschappen bepalen het visuele uiterlijk van de vervangbare symbolen in het PDF-document.

#### V: Hoe geef ik de positie van de tekst op de pagina aan?

 A: U kunt de positie van de tekst instellen door een`TextParagraph` object en het gebruik van de`Position` eigenschap om de X- en Y-coördinaten op de pagina op te geven waar de alinea moet worden geplaatst.

#### V: Wat is het verwachte resultaat van het uitvoeren van de verstrekte code?

A: Door de tutorial te volgen en de meegeleverde C#-code uit te voeren, maakt u een PDF-document met vervangbare symbolen. De vervangbare symbolen worden weergegeven als tekstfragmenten met nieuwe-regelmarkeringen en aangepaste eigenschappen.

#### V: Kan ik deze aanpak gebruiken om dynamisch gepersonaliseerde PDF-documenten te genereren?

A: Ja, deze aanpak is geschikt voor het dynamisch genereren van PDF-documenten met gepersonaliseerde informatie. Door de vervangbare symbolen te vervangen door actuele gegevens, kunt u aangepaste PDF-inhoud maken voor elke gebruiker of elk scenario.