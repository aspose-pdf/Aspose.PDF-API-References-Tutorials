---
title: Volgende regels toevoegen Inspringen in PDF-bestand
linktitle: Volgende regels toevoegen Inspringen in PDF-bestand
second_title: Aspose.PDF voor .NET API-referentie
description: Leer hoe u opeenvolgende regels kunt laten inspringen in tekst in een PDF-bestand met Aspose.PDF voor .NET.
type: docs
weight: 60
url: /nl/net/programming-with-text/add-subsequent-lines-indent/
---
Deze tutorial leidt u door het proces van het toevoegen van inspringende regels aan tekst in een PDF-bestand met behulp van Aspose.PDF voor .NET. De meegeleverde C#-broncode demonstreert de noodzakelijke stappen.

## Vereisten
Zorg ervoor dat u over het volgende beschikt voordat u begint:

- Visual Studio of een andere C#-compiler die op uw computer is geïnstalleerd.
- Aspose.PDF voor .NET-bibliotheek. Je kunt het downloaden van de officiële Aspose-website of een pakketbeheerder zoals NuGet gebruiken om het te installeren.

## Stap 1: Zet het project op
1. Maak een nieuw C#-project in de ontwikkelomgeving van uw voorkeur.
2. Voeg een verwijzing toe naar de Aspose.PDF voor .NET-bibliotheek.

## Stap 2: Importeer de vereiste naamruimten
In het codebestand waar u de volgende regels wilt laten inspringen, voegt u de volgende gebruiksinstructie bovenaan het bestand toe:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

## Stap 3: Stel de documentmap in
 Zoek in de code de regel met de tekst`string dataDir = "YOUR DOCUMENT DIRECTORY";` en vervangen`"YOUR DOCUMENT DIRECTORY"` met het pad naar de map waar uw documenten zijn opgeslagen.

## Stap 4: Maak een nieuw Document-object
 Instantieer een nieuwe`Document` object door de volgende regel code toe te voegen:

```csharp
Aspose.Pdf.Document document = new Aspose.Pdf.Document();
```

## Stap 5: Voeg een pagina toe aan het document
 Voeg een nieuwe pagina aan het document toe met behulp van de`Add` werkwijze van de`Pages`verzameling. In de opgegeven code wordt de nieuwe pagina aan de variabele toegewezen`page`.

```csharp
Aspose.Pdf.Page page = document.Pages.Add();
```

## Stap 6: Maak een tekstfragment waarvan de volgende regels inspringen
 Instantieer een`TextFragment` object en geef de gewenste tekst op. In de opgegeven code wordt de tekst aan de variabele toegewezen`text` . Initialiseer vervolgens`TextFormattingOptions` voor de`TextFragment`en specificeer de`SubsequentLinesIndent` waarde.

```csharp
Aspose.Pdf.Text.TextFragment text = new Aspose.Pdf.Text.TextFragment("A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog." );
text.TextState.FormattingOptions = new Aspose.Pdf.Text.TextFormattingOptions()
{
     SubsequentLinesIndent = 20
};
```

## Stap 7: Voeg het TextFragment toe aan de pagina
 Voeg de`TextFragment` bezwaar maken tegen het verzamelen van alinea's op de pagina.

```csharp
page.Paragraphs.Add(text);
```

## Stap 8: Herhaal stap 6 en 7 voor extra regels
Als u volgende regels met dezelfde inspringing wilt toevoegen, herhaalt u stap 6 en 7 voor elke regel. Werk de tekstinhoud indien nodig bij.

```csharp
text = new Aspose.Pdf.Text.TextFragment("Line2");
page.Paragraphs.Add(text);
text = new Aspose.Pdf.Text.TextFragment("Line3");
page.Paragraphs.Add(text);
text = new Aspose.Pdf.Text.TextFragment("Line4");
page.Paragraphs.Add(text);
text = new Aspose.Pdf.Text.TextFragment("Line5");
page.Paragraphs.Add(text);
```

## Stap 9: Sla het PDF-document op
 Sla het PDF-document op met behulp van de`Save` werkwijze van de`Document` voorwerp. Geef het pad voor het uitvoerbestand op.

```csharp
document.Save(dataDir + "SubsequentIndent_out.pdf", Aspose.Pdf.SaveFormat.Pdf);
```

### Voorbeeldbroncode voor Inspringen van volgende regels toevoegen met Aspose.PDF voor .NET 
```csharp
// Het pad naar de documentenmap.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Nieuw documentobject maken
Aspose.Pdf.Document document = new Aspose.Pdf.Document();
Aspose.Pdf.Page page = document.Pages.Add();
Aspose.Pdf.Text.TextFragment text = new Aspose.Pdf.Text.TextFragment("A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog.");
// Initialiseer TextFormattingOptions voor het tekstfragment en geef de waarde SubsequentLinesIndent op
text.TextState.FormattingOptions = new Aspose.Pdf.Text.TextFormattingOptions()
{
	SubsequentLinesIndent = 20
};
page.Paragraphs.Add(text);
text = new Aspose.Pdf.Text.TextFragment("Line2");
page.Paragraphs.Add(text);
text = new Aspose.Pdf.Text.TextFragment("Line3");
page.Paragraphs.Add(text);
text = new Aspose.Pdf.Text.TextFragment("Line4");
page.Paragraphs.Add(text);
text = new Aspose.Pdf.Text.TextFragment("Line5");
page.Paragraphs.Add(text);
document.Save(dataDir + "SubsequentIndent_out.pdf", Aspose.Pdf.SaveFormat.Pdf);
```

## Conclusie
U hebt met succes volgende regels laten inspringen aan tekst met behulp van Aspose.PDF voor .NET. Het resulterende PDF-bestand is nu te vinden op het opgegeven uitvoerbestandspad.

### Veelgestelde vragen

#### Vraag: Wat is de focus van deze tutorial?

A: Deze tutorial biedt een uitgebreide handleiding voor het toevoegen van inspringende regels aan tekst in een PDF-bestand met behulp van de Aspose.PDF voor .NET-bibliotheek. Het bevat C#-broncodevoorbeelden om de stappen te illustreren die nodig zijn om dit te bereiken.

#### Vraag: Welke naamruimten moet ik importeren voor deze tutorial?

A: In het codebestand waarin u de volgende regels wilt laten inspringen, importeert u de volgende naamruimten aan het begin van het bestand:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

#### Vraag: Hoe geef ik de documentmap op?

 A: Zoek de regel in de code`string dataDir = "YOUR DOCUMENT DIRECTORY";` en vervangen`"YOUR DOCUMENT DIRECTORY"` met het daadwerkelijke pad naar uw documentmap.

#### Vraag: Hoe maak ik een Document-object?

 A: In stap 4 maakt u een nieuw bestand`Document` object met behulp van de volgende coderegel:

```csharp
Aspose.Pdf.Document document = new Aspose.Pdf.Document();
```

#### Vraag: Hoe voeg ik een pagina toe aan het document?

 A: In stap 5 voegt u een nieuwe pagina aan het document toe met behulp van de`Add` werkwijze van de`Pages` verzameling:

```csharp
Aspose.Pdf.Page page = document.Pages.Add();
```

#### Vraag: Hoe kan ik volgende regels laten inspringen in tekst?

 A: In stap 6 maakt u een`TextFragment` object en wijs er de gewenste tekst aan toe. Vervolgens initialiseert u`TextFormattingOptions` voor de`TextFragment`en specificeer de`SubsequentLinesIndent` waarde:

```csharp
Aspose.Pdf.Text.TextFragment text = new Aspose.Pdf.Text.TextFragment("Your text here");
text.TextState.FormattingOptions = new Aspose.Pdf.Text.TextFormattingOptions()
{
    SubsequentLinesIndent = 20
};
```

#### Vraag: Hoe voeg ik het TextFragment toe aan het PDF-document?

 A: In stap 7 voegt u de`TextFragment` voorwerp (`text`) naar de alineaverzameling van de pagina:

```csharp
page.Paragraphs.Add(text);
```

#### Vraag: Kan ik het proces herhalen voor extra regels?

 A: Ja, in stap 8 kunt u het proces herhalen voor extra regels met dezelfde inspringing door een nieuwe te maken`TextFragment` objecten en voeg deze toe aan de alineacollectie van de pagina.

#### Vraag: Hoe bewaar ik het resulterende PDF-document?

 A: Nadat u de tekst hebt toegevoegd met de volgende regels, gebruikt u de`Save` werkwijze van de`Document` object om het PDF-document op te slaan:

```csharp
document.Save(dataDir + "SubsequentIndent_out.pdf", Aspose.Pdf.SaveFormat.Pdf);
```

#### Vraag: Wat is de belangrijkste conclusie uit deze tutorial?

A: Door deze tutorial te volgen, heeft u met succes geleerd hoe u de leesbaarheid van tekst in een PDF-document kunt verbeteren door opeenvolgende regels in te laten springen met Aspose.PDF voor .NET. Deze techniek kan nuttig zijn voor verschillende soorten documenten en rapporten.