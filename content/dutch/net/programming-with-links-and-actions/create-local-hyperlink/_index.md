---
title: Maak een lokale hyperlink in een PDF-bestand
linktitle: Maak een lokale hyperlink in een PDF-bestand
second_title: Aspose.PDF voor .NET API-referentie
description: Maak eenvoudig lokale hyperlinks in een PDF-bestand met Aspose.PDF voor .NET.
type: docs
weight: 40
url: /nl/net/programming-with-links-and-actions/create-local-hyperlink/
---
Door lokale hyperlinks in een PDF-bestand te maken, kunt u klikbare koppelingen maken die gebruikers naar andere pagina's in hetzelfde PDF-document leiden. Met Aspose.PDF voor .NET kunt u eenvoudig dergelijke koppelingen maken door de volgende broncode te volgen:

## Stap 1: Importeer de vereiste bibliotheken

Voordat u begint, moet u de benodigde bibliotheken voor uw C#-project importeren. Hier is de noodzakelijke importrichtlijn:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
using Aspose.Pdf.InteractiveFeatures;
```

## Stap 2: Stel het pad naar de documentenmap in

 In deze stap moet u het pad opgeven naar de map waarin u het resulterende PDF-bestand wilt opslaan. Vervangen`"YOUR DOCUMENT DIRECTORY"`in de volgende code met het daadwerkelijke pad naar uw documentenmap:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Stap 3: Maak een exemplaar van Document

 We zullen een exemplaar maken van de`Document` klasse om ons PDF-document weer te geven. Hier is de bijbehorende code:

```csharp
Document doc = new Document();
```

## Stap 4: Pagina en tekst toevoegen met hyperlinks

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

 Laten we nu het bijgewerkte PDF-bestand opslaan met behulp van de`Save` werkwijze van de`doc` voorwerp. Hier is de bijbehorende code:

```csharp
dataDir = dataDir + "CreateLocalHyperlink_out.pdf";
doc.Save(dataDir);
```

### Voorbeeldbroncode voor het maken van een lokale hyperlink met Aspose.PDF voor .NET 
```csharp
// Het pad naar de documentenmap.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Documentinstantie maken
Document doc = new Document();
// Pagina toevoegen aan paginaverzameling van PDF-bestand
Page page = doc.Pages.Add();
// Maak een tekstfragmentinstantie
Aspose.Pdf.Text.TextFragment text = new Aspose.Pdf.Text.TextFragment("link page number test to page 7");
// Maak een lokale hyperlinkinstantie
Aspose.Pdf.LocalHyperlink link = new Aspose.Pdf.LocalHyperlink();
// Stel de doelpagina in voor de linkinstantie
link.TargetPageNumber = 7;
// Stel de TextFragment-hyperlink in
text.Hyperlink = link;
//Voeg tekst toe aan de alineaverzameling van Pagina
page.Paragraphs.Add(text);
// Maak een nieuwe TextFragment-instantie
text = new TextFragment("link page number test to page 1");
// TextFragment moet over een nieuwe pagina worden toegevoegd
text.IsInNewPage = true;
// Maak nog een lokale hyperlinkinstantie
link = new LocalHyperlink();
// Stel de doelpagina in voor de tweede hyperlink
link.TargetPageNumber = 1;
// Link instellen voor tweede TextFragment
text.Hyperlink = link;
// Voeg tekst toe aan de alineaverzameling van het paginaobject
page.Paragraphs.Add(text);    
dataDir = dataDir + "CreateLocalHyperlink_out.pdf";
// Bewaar het bijgewerkte document
doc.Save(dataDir);
Console.WriteLine("\nLocal hyperlink created successfully.\nFile saved at " + dataDir);            
```

## Conclusie

Gefeliciteerd! Nu hebt u een stapsgewijze handleiding voor het maken van lokale hyperlinks in een PDF met behulp van Aspose.PDF voor .NET. U kunt deze code gebruiken om klikbare links te maken die gebruikers naar andere pagina's in hetzelfde document leiden.

Zorg ervoor dat u de officiële Aspose.PDF-documentatie raadpleegt voor meer informatie over geavanceerde hyperlinkfuncties.

### Veelgestelde vragen over het maken van een lokale hyperlink in een PDF-bestand

#### Vraag: Wat zijn lokale hyperlinks in een PDF-bestand?

A: Lokale hyperlinks in een PDF-bestand zijn klikbare links waarmee gebruikers naar verschillende pagina's binnen hetzelfde document kunnen navigeren. Deze links verbeteren de navigatie en zorgen ervoor dat lezers snel toegang krijgen tot relevante secties.

#### Vraag: Hoe kunnen lokale hyperlinks mijn PDF-document ten goede komen?

A: Lokale hyperlinks bieden een efficiënte manier om gerelateerde inhoud binnen hetzelfde PDF-document met elkaar te verbinden. Ze verbeteren de gebruikerservaring doordat lezers snel naar specifieke secties kunnen springen zonder door het hele document te hoeven scrollen.

#### Vraag: Hoe ondersteunt Aspose.PDF voor .NET het maken van lokale hyperlinks?
A: Aspose.PDF voor .NET biedt uitgebreide ondersteuning voor het maken van lokale hyperlinks. De stapsgewijze zelfstudie in deze handleiding laat zien hoe u met C# lokale hyperlinks aan uw PDF-document kunt toevoegen.

#### Vraag: Kan ik het uiterlijk van lokale hyperlinks aanpassen?

A: Ja, u kunt het uiterlijk van lokale hyperlinks aanpassen, inclusief tekstkleur en -stijl, om ervoor te zorgen dat ze overeenkomen met het ontwerp van uw document en een consistente visuele ervaring bieden.

#### Vraag: Is het mogelijk om meerdere lokale hyperlinks te maken binnen één PDF-pagina?

EEN: Absoluut! U kunt binnen één PDF-pagina meerdere lokale hyperlinks maken, zodat lezers indien nodig naar verschillende secties of pagina's kunnen springen. Elke lokale hyperlink kan worden afgestemd op het betreffende doel.

#### Vraag: Kan ik via lokale hyperlinks naar specifieke secties van een pagina linken?

A: Terwijl lokale hyperlinks doorgaans naar hele pagina's navigeren, kunt u in uw PDF-document ankers of bladwijzers maken om gerichte koppelingen te bewerkstelligen. Aspose.PDF voor .NET ondersteunt verschillende hyperlinkopties.

#### Vraag: Hoe kan ik controleren of mijn lokale hyperlinks correct functioneren?

A: Door de meegeleverde tutorial en voorbeeldcode te volgen, kunt u vol vertrouwen functionele lokale hyperlinks maken. U kunt de koppelingen testen door het gegenereerde PDF-document te openen en op de hyperlinktekst te klikken.

#### Vraag: Zijn er beperkingen bij het gebruik van lokale hyperlinks?

A: Lokale hyperlinks zijn een effectieve manier om de documentnavigatie te verbeteren, maar het is belangrijk om ervoor te zorgen dat de structuur van het document duidelijk en intuïtief blijft. Correct gelabelde hyperlinks en ankers dragen bij aan een positieve gebruikerservaring.

#### Vraag: Kan ik lokale hyperlinks maken binnen tabellen of afbeeldingen?

A: Ja, u kunt lokale hyperlinks maken binnen verschillende elementen van uw PDF-document, inclusief tabellen, afbeeldingen en tekst. Aspose.PDF voor .NET biedt flexibiliteit bij het toevoegen van hyperlinks naar verschillende soorten inhoud.