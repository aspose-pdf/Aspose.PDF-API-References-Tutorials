---
title: Lokale hyperlink maken in PDF-bestand
linktitle: Lokale hyperlink maken in PDF-bestand
second_title: Aspose.PDF voor .NET API-referentie
description: Maak eenvoudig lokale hyperlinks in een PDF-bestand met Aspose.PDF voor .NET.
type: docs
weight: 40
url: /nl/net/programming-with-links-and-actions/create-local-hyperlink/
---
Door lokale hyperlinks in een PDF-bestand te maken, kunt u klikbare links maken die gebruikers naar andere pagina's in hetzelfde PDF-document brengen. Met Aspose.PDF voor .NET kunt u dergelijke links eenvoudig maken door de volgende broncode te volgen:

## Stap 1: Importeer vereiste bibliotheken

Voordat u begint, moet u de benodigde bibliotheken voor uw C#-project importeren. Dit is de benodigde importrichtlijn:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
using Aspose.Pdf.InteractiveFeatures;
```

## Stap 2: Stel het pad naar de documentenmap in

 In deze stap moet u het pad opgeven naar de map waarin u het resulterende PDF-bestand wilt opslaan. Vervangen`"YOUR DOCUMENT DIRECTORY"` in de volgende code met het daadwerkelijke pad naar uw documentenmap:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Stap 3: Maak een exemplaar van Document

 We zullen een instantie van de maken`Document` klasse om ons PDF-document te vertegenwoordigen. Hier is de bijbehorende code:

```csharp
Document doc = new Document();
```

## Stap 4: Voeg pagina en tekst toe met hyperlinks

In deze stap gaan we een pagina toevoegen aan ons PDF-document en wat tekst toevoegen met lokale hyperlinks. We definiëren de doelpagina's voor elke link. Hier is de bijbehorende code:

```csharp
Page page = doc.Pages.Add();

TextFragment text = new TextFragment("Link to page 7");
LocalHyperlink link = new LocalHyperlink();
link.TargetPageNumber = 7;
text. Hyperlink = link;
page.Paragraphs.Add(text);

text = new TextFragment("Link to page 1");
text. IsInNewPage = true;
link = new LocalHyperlink();
link.TargetPageNumber = 1;
text. Hyperlink = link;
page.Paragraphs.Add(text);
```

## Stap 5: Sla het bijgewerkte document op

Laten we nu het bijgewerkte PDF-bestand opslaan met behulp van de`Save` methode van de`doc` object. Hier is de bijbehorende code:

```csharp
dataDir = dataDir + "CreateLocalHyperlink_out.pdf";
doc.Save(dataDir);
```

### Voorbeeldbroncode voor het maken van een lokale hyperlink met behulp van Aspose.PDF voor .NET 
```csharp
// Het pad naar de documentenmap.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Documentinstantie maken
Document doc = new Document();
// Pagina toevoegen aan paginaverzameling van PDF-bestand
Page page = doc.Pages.Add();
// Maak een tekstfragmentinstantie
Aspose.Pdf.Text.TextFragment text = new Aspose.Pdf.Text.TextFragment("link page number test to page 7");
// Lokale hyperlinkinstantie maken
Aspose.Pdf.LocalHyperlink link = new Aspose.Pdf.LocalHyperlink();
// Doelpagina instellen voor linkinstantie
link.TargetPageNumber = 7;
// Hyperlink TextFragment instellen
text.Hyperlink = link;
// Voeg tekst toe aan de alineaverzameling van de pagina
page.Paragraphs.Add(text);
// Nieuw TextFragment-exemplaar maken
text = new TextFragment("link page number test to page 1");
// TextFragment moet over een nieuwe pagina worden toegevoegd
text.IsInNewPage = true;
// Een ander lokaal hyperlinkexemplaar maken
link = new LocalHyperlink();
// Doelpagina voor tweede hyperlink instellen
link.TargetPageNumber = 1;
// Link instellen voor tweede TextFragment
text.Hyperlink = link;
// Tekst toevoegen aan alineaverzameling van pagina-object
page.Paragraphs.Add(text);    
dataDir = dataDir + "CreateLocalHyperlink_out.pdf";
// Bijgewerkt document opslaan
doc.Save(dataDir);
Console.WriteLine("\nLocal hyperlink created successfully.\nFile saved at " + dataDir);            
```

## Conclusie

Gefeliciteerd! U hebt nu een stapsgewijze handleiding om lokale hyperlinks in een PDF te maken met Aspose.PDF voor .NET. U kunt deze code gebruiken om klikbare links te maken die gebruikers naar andere pagina's in hetzelfde document brengen.

Raadpleeg de officiële Aspose.PDF-documentatie voor meer informatie over geavanceerde hyperlinkfuncties.

### FAQ's voor het maken van een lokale hyperlink in een PDF-bestand

#### V: Wat zijn lokale hyperlinks in een PDF-bestand?

A: Lokale hyperlinks in een PDF-bestand zijn klikbare links die gebruikers naar verschillende pagina's binnen hetzelfde document navigeren. Deze links verbeteren de navigatie en stellen lezers in staat om snel toegang te krijgen tot relevante secties.

#### V: Hoe kunnen lokale hyperlinks mijn PDF-document ten goede komen?

A: Lokale hyperlinks bieden een efficiënte manier om gerelateerde content binnen hetzelfde PDF-document te verbinden. Ze verbeteren de gebruikerservaring door lezers in staat te stellen snel naar specifieke secties te springen zonder door het hele document te scrollen.

#### V: Hoe ondersteunt Aspose.PDF voor .NET het maken van lokale hyperlinks?
A: Aspose.PDF voor .NET biedt uitgebreide ondersteuning voor het maken van lokale hyperlinks. De stapsgewijze tutorial in deze gids laat zien hoe u lokale hyperlinks toevoegt aan uw PDF-document met behulp van C#.

#### V: Kan ik het uiterlijk van lokale hyperlinks aanpassen?

A: Ja, u kunt het uiterlijk van lokale hyperlinks aanpassen, inclusief de tekstkleur en -stijl, zodat ze passen bij het ontwerp van uw document en een consistente visuele ervaring bieden.

#### V: Is het mogelijk om meerdere lokale hyperlinks binnen één PDF-pagina te maken?

A: Absoluut! U kunt meerdere lokale hyperlinks maken binnen een enkele PDF-pagina, zodat lezers naar verschillende secties of pagina's kunnen springen als dat nodig is. Elke lokale hyperlink kan worden afgestemd op het betreffende doel.

#### V: Kan ik met behulp van lokale hyperlinks naar specifieke delen van een pagina linken?

A: Terwijl lokale hyperlinks doorgaans naar hele pagina's navigeren, kunt u ankers of bladwijzers in uw PDF-document maken om gerichte koppelingen te bereiken. Aspose.PDF voor .NET ondersteunt verschillende hyperlinkopties.

#### V: Hoe kan ik controleren of mijn lokale hyperlinks correct functioneren?

A: Door de meegeleverde tutorial en voorbeeldcode te volgen, kunt u vol vertrouwen functionele lokale hyperlinks maken. U kunt de links testen door het gegenereerde PDF-document te openen en op de hyperlinktekst te klikken.

#### V: Zijn er beperkingen bij het gebruik van lokale hyperlinks?

A: Lokale hyperlinks zijn een effectieve manier om de navigatie in documenten te verbeteren, maar het is belangrijk om ervoor te zorgen dat de structuur van het document duidelijk en intuïtief blijft. Correct gelabelde hyperlinks en ankers dragen bij aan een positieve gebruikerservaring.

#### V: Kan ik lokale hyperlinks maken in tabellen of afbeeldingen?

A: Ja, u kunt lokale hyperlinks maken binnen verschillende elementen van uw PDF-document, inclusief tabellen, afbeeldingen en tekst. Aspose.PDF voor .NET biedt flexibiliteit bij het toevoegen van hyperlinks aan verschillende soorten content.