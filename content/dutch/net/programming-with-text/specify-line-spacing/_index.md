---
title: Regelafstand in PDF-bestand opgeven
linktitle: Regelafstand in PDF-bestand opgeven
second_title: Aspose.PDF voor .NET API-referentie
description: Leer hoe u regelafstand in een PDF specificeert met Aspose.PDF voor .NET met deze stapsgewijze handleiding. Perfect voor ontwikkelaars die op zoek zijn naar nauwkeurige tekstopmaak.
type: docs
weight: 510
url: /nl/net/programming-with-text/specify-line-spacing/
---
## Invoering

Heb je ooit moeite gehad met het regelen van de regelafstand in een PDF-bestand? Misschien had je tekst die er te vol uitzag of er gewoon niet zo gepolijst uitzag als je zou willen. In deze tutorial laten we je zien hoe je eenvoudig regelafstand in een PDF kunt specificeren met Aspose.PDF voor .NET. We gebruiken een eenvoudige, stapsgewijze handleiding om je van een lege PDF naar een PDF met aangepaste regelafstand te brengen. Dit is perfect als je precisie nodig hebt in je tekstlay-out voor documenten zoals rapporten, facturen of certificaten.

## Vereisten

Voordat we in de code duiken, controleren we of je alles hebt wat je nodig hebt:

1.  Aspose.PDF voor .NET geïnstalleerd. Als u het niet hebt, haal het dan uit de[Aspose.PDF downloadpagina](https://releases.aspose.com/pdf/net/).
2. Een .NET-ontwikkelomgeving (zoals Visual Studio).
3. Een TrueType-lettertypebestand (`.ttf` ) die we in het voorbeeld zullen gebruiken. U kunt elk lettertype gebruiken, maar voor deze handleiding gebruiken we het`HPSimplified.TTF` lettertype.
4. Basiskennis van C# en PDF-bewerking.

Als u er klaar voor bent, gaan we verder met het importeren van de benodigde pakketten.

## Pakketten importeren

In uw C#-project moet u de Aspose.PDF-naamruimten importeren om met de PDF-functionaliteiten te werken. Dit is hoe u dat doet:

```csharp
using Aspose.Pdf.Text;
using System.IO;
```

Met deze naamruimten kunt u PDF-documenten maken en bewerken, en kunt u werken met tekstopmaak en lettertypeopties.

We zullen dit opsplitsen in kleine stappen, zodat u het gemakkelijk kunt volgen. Elke stap richt zich op een belangrijk onderdeel van het proces, van het instellen van uw PDF tot het specificeren van de regelafstand.

## Stap 1: Stel uw project in en definieer de documentdirectory

Het eerste wat we moeten doen is definiëren waar onze bestanden zich bevinden. Dit helpt het programma te weten waar het lettertype te vinden is en waar de resulterende PDF opgeslagen moet worden.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
string fontFile = dataDir + "HPSimplified.TTF";
```

 In deze stap vervangt u`"YOUR DOCUMENT DIRECTORY"` met het daadwerkelijke pad naar waar u uw bestanden opslaat. Dit is waar u uw lettertypebestand plaatst (`HPSimplified.TTF`) en waar de PDF wordt opgeslagen.

## Stap 2: Een PDF-document laden

Nu moeten we een nieuw PDF-document maken. Voor deze handleiding beginnen we met een leeg document, maar u kunt indien nodig ook een bestaand PDF-document laden.

```csharp
Document doc = new Document();
```

Dit creëert een nieuw, leeg PDF-document. Makkelijk toch?

## Stap 3: Tekstopmaakopties instellen

 Hier gebeurt de magie. We specificeren de regelafstandmodus voor de tekst die we aan de PDF willen toevoegen. Aspose.PDF geeft ons verschillende opties, maar in deze handleiding gebruiken we`LineSpacingMode.FullSize`, waardoor de regelafstand volledig wordt gerespecteerd.

```csharp
TextFormattingOptions formattingOptions = new TextFormattingOptions();
formattingOptions.LineSpacing = TextFormattingOptions.LineSpacingMode.FullSize;
```

 Deze code stelt de regelafstandmodus in op`FullSize` , zodat de tekst met de juiste spatie wordt weergegeven. Er zijn andere opties zoals`Proportional` als je verschillende spatiegedragingen wilt, maar laten we het voor nu bij`FullSize`.

## Stap 4: Maak een tekstfragment

Nu gaan we de daadwerkelijke tekst maken die in de PDF wordt geplaatst. Deze tekst zal de regelafstand respecteren die we hebben gedefinieerd.

```csharp
TextFragment textFragment = new TextFragment("Hello world");
```

 We hebben een tekstfragment gemaakt met de string`"Hello world"`Uiteraard kunt u deze tekst naar eigen wens aanpassen.

## Stap 5: Een aangepast lettertype laden en toepassen

Om de tekst te laten opvallen, laden we een aangepast TrueType-lettertype uit een bestand. Deze stap is optioneel, maar kan een professionele touch aan uw PDF's toevoegen.

```csharp
if (fontFile != "")
{
    using (FileStream fontStream = System.IO.File.OpenRead(fontFile))
    {
        textFragment.TextState.Font = FontRepository.OpenFont(fontStream, FontTypes.TTF);
```

Hier laden we het lettertypebestand en passen het toe op het tekstfragment. Als het bestandspad geldig is, wordt het lettertype gebruikt. Anders wordt het standaardlettertype toegepast.

## Stap 6: Tekstpositie en opmaak instellen

Vervolgens moeten we de tekst op de PDF positioneren. We passen ook de opmaakopties toe die we eerder hebben gemaakt.

```csharp
textFragment.Position = new Position(100, 600);
textFragment.TextState.FormattingOptions = formattingOptions;
```

 De`Position` methode stelt de coördinaten in waar de tekst op de pagina zal verschijnen (in dit geval 100 eenheden vanaf de linkerkant en 600 eenheden vanaf de onderkant). De opmaakopties, inclusief de regelafstandmodus, worden hier toegepast.

## Stap 7: Tekst toevoegen aan de PDF-pagina

Nu de tekst is opgemaakt en gepositioneerd, is het tijd om deze aan het PDF-document toe te voegen.

```csharp
var page = doc.Pages.Add();
page.Paragraphs.Add(textFragment);
```

Deze code maakt een nieuwe pagina in het PDF-document en voegt het tekstfragment eraan toe.

## Stap 8: Sla de PDF op

We zijn bij de laatste stap! Nu alles is ingesteld, gaan we de PDF opslaan.

```csharp
dataDir = dataDir + "SpecifyLineSpacing_out.pdf";
doc.Save(dataDir);
```

Hiermee wordt de PDF opgeslagen met de opgegeven regelafstand en uw bestand is klaar!

## Conclusie

En dat is alles! U hebt zojuist een PDF-document gemaakt met aangepaste regelafstand met Aspose.PDF voor .NET. Het is een krachtige tool waarmee u elk aspect van uw PDF-bestanden kunt beheren, en dit is slechts een voorbeeld van wat u kunt bereiken. Van tekstplaatsing tot opmaak, de mogelijkheden zijn eindeloos.

Als u dieper in PDF-manipulatie wilt duiken, biedt Aspose.PDF een schat aan functies om te verkennen. Aarzel niet om te experimenteren en de grenzen van wat u met uw documenten kunt doen te verleggen!

## Veelgestelde vragen

### Kan ik de regelafstand aanpassen naar andere modi?  
 Ja, u kunt andere modi gebruiken, zoals`Proportional` of`Fixed` afhankelijk van uw behoeften.

### Is het mogelijk om lettertypen vanuit het systeem te laden in plaats van uit een bestand?  
 Ja, u kunt systeemgeïnstalleerde lettertypen laden met behulp van de`FontRepository`.

### Kan ik Aspose.PDF voor .NET gebruiken met andere bestandsformaten?  
Absoluut! Aspose.PDF voor .NET ondersteunt een verscheidenheid aan formaten zoals XML, HTML en meer.

### Heb ik een licentie nodig om Aspose.PDF voor .NET te gebruiken?  
Ja, voor volledige functionaliteit heb je een licentie nodig, die je kunt verkrijgen[hier](https://purchase.aspose.com/buy).

### Hoe stel ik de regelafstand in voor meerdere alinea's?  
 U kunt zich aanmelden`TextFormattingOptions` aan elk`TextFragment` of`TextParagraph` om de afstand tussen meerdere regels of alinea's te bepalen.