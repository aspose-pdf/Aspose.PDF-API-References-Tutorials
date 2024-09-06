---
title: Aangepaste tabstops in PDF-bestand
linktitle: Aangepaste tabstops in PDF-bestand
second_title: Aspose.PDF voor .NET API-referentie
description: Leer hoe u aangepaste tabstops in een PDF-bestand maakt met Aspose.PDF voor .NET.
type: docs
weight: 120
url: /nl/net/programming-with-text/custom-tab-stops/
---

Deze tutorial begeleidt u door het proces van het maken van aangepaste tabstops in een PDF-bestand met behulp van Aspose.PDF voor .NET. De meegeleverde C#-broncode demonstreert de benodigde stappen.

## Vereisten
Voordat u begint, moet u ervoor zorgen dat u over het volgende beschikt:

- Visual Studio of een andere C#-compiler die op uw computer is geïnstalleerd.
- Aspose.PDF voor .NET-bibliotheek. U kunt het downloaden van de officiële Aspose-website of een pakketbeheerder zoals NuGet gebruiken om het te installeren.

## Stap 1: Het project opzetten
1. Maak een nieuw C#-project in uw favoriete ontwikkelomgeving.
2. Voeg een verwijzing toe naar de Aspose.PDF voor .NET-bibliotheek.

## Stap 2: Importeer de vereiste naamruimten
Voeg in het codebestand waar u aangepaste tabstops wilt maken het volgende toe met behulp van richtlijnen boven aan het bestand:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

## Stap 3: Stel de documentdirectory in
 Zoek in de code de regel met de tekst`string dataDir = "YOUR DOCUMENT DIRECTORY";` en vervangen`"YOUR DOCUMENT DIRECTORY"` met het pad naar de map waar uw documenten zijn opgeslagen.

## Stap 4: Maak een nieuw Document-exemplaar
 Een nieuwe instantiëren`Document` object door de volgende regel code toe te voegen:

```csharp
Document _pdfdocument = new Document();
```

## Stap 5: Voeg een pagina toe aan het document
 Voeg een nieuwe pagina toe aan het document met behulp van de`Add` methode van de`Pages`verzameling. In de meegeleverde code wordt de nieuwe pagina toegewezen aan de variabele`page`.

```csharp
Page page = _pdfdocument.Pages.Add();
```

## Stap 6: Aangepaste tabstops maken
 Maak een`TabStops` object en voeg aangepaste tabstops toe. Stel het uitlijningstype en leadertype in voor elke tabstop.

```csharp
TabStops ts = new TabStops();
TabStop ts1 = ts.Add(100);
ts1.AlignmentType = TabAlignmentType.Right;
ts1.LeaderType = TabLeaderType.Solid;

TabStop ts2 = ts.Add(200);
ts2.AlignmentType = TabAlignmentType.Center;
ts2.LeaderType = TabLeaderType.Dash;

TabStop ts3 = ts.Add(300);
ts3.AlignmentType = TabAlignmentType.Left;
ts3.LeaderType = TabLeaderType.Dot;
```

## Stap 7: Tekstfragmenten maken met tabstops
 Creëren`TextFragment` objecten en geef de aangepaste tabstops aan hen door. Gebruik de speciale tekens`#$TAB` om de tabstops in de tekst aan te geven.

```csharp
TextFragment header = new TextFragment("This is an example of forming a table with TAB stops", ts);
TextFragment text0 = new TextFragment("#$TABHead1 #$TABHead2 #$TABHead3", ts);
TextFragment text1 = new TextFragment("#$TABdata11 #$TABdata12 #$TABdata13", ts);
TextFragment text2 = new TextFragment("#$TABdata21 ", ts);
text2.Segments.Add(new TextSegment("#$TAB"));
text2.Segments.Add(new TextSegment("data22 "));
text2.Segments.Add(new TextSegment("#$TAB"));
text2.Segments.Add(new TextSegment("data23"));

page.Paragraphs.Add(header);
page.Paragraphs.Add(text0);
page.Paragraphs.Add(text1);
page.Paragraphs.Add(text2);
```

## Stap 8: Sla het PDF-document op
 Sla het PDF-document op met behulp van de`Save` methode van de`Document` voorwerp.

```csharp
_pdfdocument.Save(dataDir);
Console.WriteLine("\nCustom tab stops setup successfully.\nFile saved at " + dataDir);
```

### Voorbeeldbroncode voor aangepaste tabstops met Aspose.PDF voor .NET 
```csharp
// Het pad naar de documentenmap.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document _pdfdocument = new Document();
Page page = _pdfdocument.Pages.Add();
Aspose.Pdf.Text.TabStops ts = new Aspose.Pdf.Text.TabStops();
Aspose.Pdf.Text.TabStop ts1 = ts.Add(100);
ts1.AlignmentType = TabAlignmentType.Right;
ts1.LeaderType = TabLeaderType.Solid;
Aspose.Pdf.Text.TabStop ts2 = ts.Add(200);
ts2.AlignmentType = TabAlignmentType.Center;
ts2.LeaderType = TabLeaderType.Dash;
Aspose.Pdf.Text.TabStop ts3 = ts.Add(300);
ts3.AlignmentType = TabAlignmentType.Left;
ts3.LeaderType = TabLeaderType.Dot;
TextFragment header = new TextFragment("This is a example of forming table with TAB stops", ts);
TextFragment text0 = new TextFragment("#$TABHead1 #$TABHead2 #$TABHead3", ts);
TextFragment text1 = new TextFragment("#$TABdata11 #$TABdata12 #$TABdata13", ts);
TextFragment text2 = new TextFragment("#$TABdata21 ", ts);
text2.Segments.Add(new TextSegment("#$TAB"));
text2.Segments.Add(new TextSegment("data22 "));
text2.Segments.Add(new TextSegment("#$TAB"));
text2.Segments.Add(new TextSegment("data23"));
page.Paragraphs.Add(header);
page.Paragraphs.Add(text0);
page.Paragraphs.Add(text1);
page.Paragraphs.Add(text2);
dataDir = dataDir + "CustomTabStops_out.pdf";
_pdfdocument.Save(dataDir);
Console.WriteLine("\nCustom tab stops setup successfully.\nFile saved at " + dataDir);
```

## Conclusie
U hebt met succes een PDF-document met aangepaste tabstops gemaakt met Aspose.PDF voor .NET. Het resulterende PDF-bestand is nu te vinden op het opgegeven pad naar het uitvoerbestand.

### Veelgestelde vragen

#### V: Waarop richt deze tutorial zich?

A: Deze tutorial is gericht op het begeleiden van u door het proces van het maken van aangepaste tabstops in een PDF-bestand met behulp van de Aspose.PDF voor .NET-bibliotheek. De meegeleverde C#-broncode demonstreert de benodigde stappen om dit te bereiken.

#### V: Welke naamruimten moet ik importeren voor deze tutorial?

A: Importeer de volgende naamruimten aan het begin van het bestand in het codebestand waarin u aangepaste tabstops wilt maken:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

#### V: Hoe geef ik de documentenmap op?

 A: Zoek in de code de regel`string dataDir = "YOUR DOCUMENT DIRECTORY";` en vervangen`"YOUR DOCUMENT DIRECTORY"` met het daadwerkelijke pad naar uw documentenmap.

#### V: Hoe maak ik een nieuw Document-exemplaar?

 A: In stap 4 maakt u een nieuwe`Document` object met behulp van de verstrekte code.

#### V: Hoe voeg ik een pagina toe aan het document?

 A: In stap 5 voegt u een nieuwe pagina toe aan het document met behulp van de`Add` methode van de`Pages` verzameling.

#### V: Hoe maak ik aangepaste tabstops?

 A: In stap 6 maak je een`TabStops` object en voeg aangepaste tabstops toe. U stelt ook de uitlijning en leader-typen in voor elke tabstop.

#### V: Hoe maak ik tekstfragmenten met tabstops?

 A: In stap 7 maak je`TextFragment` objecten en geef de aangepaste tabstops aan hen door. U gebruikt de speciale tekens`#$TAB` om de tabstops in de tekst aan te geven.

#### V: Hoe kan ik het PDF-document opslaan?

 A: In stap 8 slaat u het PDF-document op met behulp van de`Save` methode van de`Document` voorwerp.

#### V: Wat is de belangrijkste les die je uit deze tutorial hebt geleerd?

A: Door deze tutorial te volgen, hebt u geleerd hoe u een PDF-document met aangepaste tabstops kunt maken met Aspose.PDF voor .NET. Dit kan handig zijn voor het op een gestructureerde manier organiseren en uitlijnen van tekst.