---
title: Vervangbare symbolen weergeven in PDF-bestand
linktitle: Vervangbare symbolen weergeven in PDF-bestand
second_title: Aspose.PDF voor .NET API-referentie
description: Leer hoe u vervangbare symbolen in een PDF-bestand kunt weergeven met Aspose.PDF voor .NET.
type: docs
weight: 310
url: /nl/net/programming-with-text/rendering-replaceable-symbols/
---
In deze zelfstudie leggen we uit hoe u vervangbare symbolen in een PDF-bestand kunt weergeven met behulp van de Aspose.PDF-bibliotheek voor .NET. We doorlopen het stapsgewijze proces van het maken van een PDF, het toevoegen van een tekstfragment met nieuweregelmarkeringen, het instellen van teksteigenschappen, het positioneren van de tekst en het opslaan van de PDF met behulp van de meegeleverde C#-broncode.

## Vereisten

Zorg ervoor dat u over het volgende beschikt voordat u begint:

- De Aspose.PDF voor .NET-bibliotheek geïnstalleerd.
- Basiskennis van programmeren in C#.

## Stap 1: Stel de documentmap in

 Eerst moet u het pad instellen naar de map waarin u het gegenereerde PDF-bestand wilt opslaan. Vervangen`"YOUR DOCUMENT DIRECTORY"` in de`dataDir`variabele met het pad naar de gewenste map.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Stap 2: Maak een PDF-document en -pagina

 Vervolgens maken we een nieuw PDF-document en voegen er een pagina aan toe met behulp van de`Document` klasse en`Page` klasse uit de Aspose.PDF-bibliotheek.

```csharp
Aspose.Pdf.Document pdfApplicationDoc = new Aspose.Pdf.Document();
Aspose.Pdf.Page applicationFirstPage = (Aspose.Pdf.Page)pdfApplicationDoc.Pages.Add();
```

## Stap 3: tekstfragment toevoegen met nieuwe regelmarkeringen

 Wij creëren een`TextFragment`object en stel de tekst zo in dat deze nieuwe regelmarkeringen bevat (`Environment.NewLine`) om meerdere regels tekst weer te geven.

```csharp
Aspose.Pdf.Text.TextFragment textFragment = new Aspose.Pdf.Text.TextFragment("Applicant Name: " + Environment.NewLine + " Joe Smoe");
```

## Stap 4: Stel de eigenschappen van tekstfragmenten in

Voor het tekstfragment kunnen wij desgewenst verschillende eigenschappen instellen, zoals lettergrootte, lettertype, achtergrondkleur en voorgrondkleur.

```csharp
textFragment.TextState.FontSize = 12;
textFragment.TextState.Font = Aspose.Pdf.Text.FontRepository.FindFont("TimesNewRoman");
textFragment.TextState.BackgroundColor = Aspose.Pdf.Color.LightGray;
textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.Red;
```

## Stap 5: Maak een tekstparagraaf en positie

 Wij creëren een`TextParagraph` object, voeg het tekstfragment toe aan de alinea en stel de positie van de alinea op de pagina in.

```csharp
TextParagraph par = new TextParagraph();
par.AppendLine(textFragment);
par.Position = new Aspose.Pdf.Text.Position(100, 600);
```

## Stap 6: Voeg een tekstparagraaf toe aan de pagina

 Wij creëren een`TextBuilder` object met de pagina en voeg de tekstparagraaf toe aan de tekstbuilder.

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

### Voorbeeldbroncode voor het weergeven van vervangbare symbolen met Aspose.PDF voor .NET 
```csharp
// Het pad naar de documentenmap.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Aspose.Pdf.Document pdfApplicationDoc = new Aspose.Pdf.Document();
Aspose.Pdf.Page applicationFirstPage = (Aspose.Pdf.Page)pdfApplicationDoc.Pages.Add();
// Initialiseer een nieuw tekstfragment met tekst die de vereiste nieuweregelmarkeringen bevat
Aspose.Pdf.Text.TextFragment textFragment = new Aspose.Pdf.Text.TextFragment("Applicant Name: " + Environment.NewLine + " Joe Smoe");
// Stel indien nodig de eigenschappen van tekstfragmenten in
textFragment.TextState.FontSize = 12;
textFragment.TextState.Font = Aspose.Pdf.Text.FontRepository.FindFont("TimesNewRoman");
textFragment.TextState.BackgroundColor = Aspose.Pdf.Color.LightGray;
textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.Red;
// Maak een TextParagraph-object
TextParagraph par = new TextParagraph();
// Voeg een nieuw tekstfragment toe aan de alinea
par.AppendLine(textFragment);
// Stel de alineapositie in
par.Position = new Aspose.Pdf.Text.Position(100, 600);
// Maak een TextBuilder-object
TextBuilder textBuilder = new TextBuilder(applicationFirstPage);
// Voeg de TextParagraph toe met TextBuilder
textBuilder.AppendParagraph(par);
dataDir = dataDir + "RenderingReplaceableSymbols_out.pdf";
pdfApplicationDoc.Save(dataDir);
Console.WriteLine("\nReplaceable symbols render successfully duing pdf creation.\nFile saved at " + dataDir);
```

## Conclusie

In deze zelfstudie hebt u geleerd hoe u vervangbare symbolen in een PDF-document kunt weergeven met behulp van de Aspose.PDF-bibliotheek voor .NET. Door de stapsgewijze handleiding te volgen en de meegeleverde C#-code uit te voeren, kunt u een PDF maken, tekst toevoegen met nieuweregelmarkeringen, teksteigenschappen instellen, de tekst op de pagina plaatsen en de PDF opslaan.

### Veelgestelde vragen

#### Vraag: Wat is het doel van de tutorial "Vervangbare symbolen weergeven in een PDF-bestand"?

A: In de tutorial "Vervangbare symbolen weergeven in PDF-bestanden" wordt gedemonstreerd hoe u de Aspose.PDF-bibliotheek voor .NET kunt gebruiken om een PDF-document te maken dat vervangbare symbolen bevat. Deze symbolen worden weergegeven als tekstfragmenten met nieuweregelmarkeringen om inhoud met meerdere regels te creëren.

#### Vraag: Waarom zou ik vervangbare symbolen in een PDF-document willen weergeven?

A: Het weergeven van vervangbare symbolen is handig wanneer u dynamisch PDF-inhoud moet genereren die variabele of gebruikersspecifieke informatie bevat. Deze symbolen fungeren als tijdelijke aanduidingen die tijdens runtime kunnen worden vervangen door daadwerkelijke gegevens, zoals formulierveldwaarden of gepersonaliseerde details.

#### Vraag: Hoe stel ik de documentmap in?

A: Om de documentmap in te stellen:

1.  Vervangen`"YOUR DOCUMENT DIRECTORY"` in de`dataDir` variabele met het pad naar de map waarin u het gegenereerde PDF-bestand wilt opslaan.

#### Vraag: Hoe geef ik vervangbare symbolen in een PDF-document weer met behulp van de Aspose.PDF-bibliotheek?

A: De tutorial begeleidt u stap voor stap door het proces:

1.  Maak een nieuw PDF-document met behulp van de`Document` klas.
2.  Voeg een pagina toe aan het document met behulp van de`Page` klas.
3.  Maak een`TextFragment` object met nieuwelijnmarkeringen (`Environment.NewLine`) om inhoud met meerdere regels weer te geven.
4. Pas de eigenschappen van het tekstfragment aan, zoals lettergrootte, lettertype, achtergrondkleur en voorgrondkleur.
5.  Maak een`TextParagraph` object, voeg het tekstfragment eraan toe en stel de positie van de alinea op de pagina in.
6.  Maak een`TextBuilder` object met de pagina en voeg de tekstparagraaf eraan toe.
7. Sla het PDF-document op.

#### Vraag: Wat is het doel van het gebruik van nieuweregelmarkeringen (`Environment.NewLine`) in the text fragment?

 A: Nieuweregelmarkeringen worden gebruikt om inhoud met meerdere regels binnen één tekstfragment te creëren. Door het gebruiken van`Environment.NewLine`kunt u aangeven waar in de tekst regeleinden moeten voorkomen.

#### Vraag: Kan ik het uiterlijk van de vervangbare symbolen aanpassen?

A: Ja, u kunt verschillende eigenschappen van het tekstfragment aanpassen, zoals lettergrootte, lettertype, achtergrondkleur en voorgrondkleur. Deze eigenschappen bepalen de visuele weergave van de vervangbare symbolen in het PDF-document.

#### Vraag: Hoe geef ik de positie van de tekst op de pagina op?

 A: U kunt de positie van de tekst instellen door een`TextParagraph` object en het gebruik van de`Position` eigenschap om de X- en Y-coördinaten op te geven op de pagina waar de alinea moet worden geplaatst.

#### Vraag: Wat is het verwachte resultaat van het uitvoeren van de opgegeven code?

A: Door de tutorial te volgen en de meegeleverde C#-code uit te voeren, maakt u een PDF-document met vervangbare symbolen. De vervangbare symbolen worden weergegeven als tekstfragmenten met nieuweregelmarkeringen en aangepaste eigenschappen.

#### Vraag: Kan ik deze aanpak gebruiken om dynamisch gepersonaliseerde PDF-documenten te genereren?

A: Ja, deze aanpak is geschikt voor het dynamisch genereren van PDF-documenten met gepersonaliseerde informatie. Door de vervangbare symbolen te vervangen door daadwerkelijke gegevens, kunt u voor elke gebruiker of scenario aangepaste PDF-inhoud maken.