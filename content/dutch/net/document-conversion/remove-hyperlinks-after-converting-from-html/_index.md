---
title: Hyperlinks verwijderen na conversie van HTML
linktitle: Hyperlinks verwijderen na conversie van HTML
second_title: Aspose.PDF voor .NET API-referentie
description: Leer in deze stapsgewijze handleiding hoe u hyperlinks uit HTML-documenten verwijdert na conversie naar PDF met Aspose.PDF voor .NET.
type: docs
weight: 250
url: /nl/net/document-conversion/remove-hyperlinks-after-converting-from-html/
---
## Invoering

In het digitale tijdperk is het converteren van HTML-documenten naar PDF een veelvoorkomende taak. Soms wilt u echter hyperlinks uit de geconverteerde PDF verwijderen om verschillende redenen, zoals het verbeteren van de leesbaarheid of het voorkomen van ongewenste navigatie. In deze tutorial onderzoeken we hoe u dit kunt bereiken met Aspose.PDF voor .NET. 

## Vereisten

Voordat u aan de slag gaat met de code, moet u ervoor zorgen dat u aan de volgende vereisten voldoet:

1. Visual Studio: Zorg ervoor dat Visual Studio op uw machine is geïnstalleerd. Dit wordt uw ontwikkelomgeving.
2.  Aspose.PDF voor .NET: U moet de Aspose.PDF-bibliotheek hebben. U kunt deze downloaden van[hier](https://releases.aspose.com/pdf/net/).
3. Basiskennis van C#: Kennis van C#-programmering helpt u de code beter te begrijpen.

## Pakketten importeren

Om te beginnen moet u de benodigde pakketten importeren in uw C#-project. Dit is hoe u dat kunt doen:

1. Open uw Visual Studio-project.
2. Klik met de rechtermuisknop op uw project in Solution Explorer en selecteer 'NuGet-pakketten beheren'.
3.  Zoeken naar`Aspose.PDF` en installeer het.

```csharp
using Aspose.Pdf.Annotations;
using Aspose.Pdf.Text;
using System.IO;
```

Nu u alles hebt ingesteld, gaan we dieper in op het proces voor het verwijderen van hyperlinks uit een HTML-bestand nadat u het bestand naar PDF hebt geconverteerd.

## Stap 1: De documentenmap instellen

Allereerst moet u het pad naar uw documentenmap opgeven. Dit is waar uw HTML-bestand zich bevindt en waar de PDF-uitvoer wordt opgeslagen.

```csharp
// Het pad naar de documentenmap.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Vervangen`"YOUR DOCUMENT DIRECTORY"` met het daadwerkelijke pad waar uw HTML-bestand is opgeslagen.

## Stap 2: Laad het HTML-document

 Vervolgens laadt u het HTML-document met behulp van de`Document` klasse van Aspose.PDF. Met deze klasse kunt u eenvoudig met PDF-documenten werken.

```csharp
Document doc = new Document(dataDir + "SampleHtmlFile.html", new HtmlLoadOptions());
```

 Hier laden we het HTML-bestand met de naam`SampleHtmlFile.html`Zorg ervoor dat dit bestand in de door u opgegeven map staat.

## Stap 3: Sla het document op in de geheugenstroom

Voordat we beginnen met het verwerken van de annotaties, moeten we het document opslaan in een geheugenstroom. Deze stap is cruciaal omdat het het document voorbereidt op verdere manipulatie.

```csharp
doc.Save(new MemoryStream());
```

Met deze regel wordt het document in het geheugen opgeslagen, zodat we ermee kunnen werken zonder dat we het eerst naar de schijf hoeven te schrijven.

## Stap 4: Herhaal de annotaties

Nu gaan we door de annotaties in het document itereren. Annotaties zijn elementen zoals links, opmerkingen en highlights. We zijn specifiek geïnteresseerd in linkannotaties.

```csharp
foreach (Annotation a in doc.Pages[1].Annotations)
{
    if (a.AnnotationType == AnnotationType.Link)
    {
        // Verwerk de linkannotatie
    }
}
```

In deze lus controleren we of het annotatietype een link is. Als dat zo is, gaan we door naar de volgende stappen.

## Stap 5: Verwijder de hyperlinkactie

Voor elke linkannotatie moeten we controleren of deze een hyperlinkactie heeft. Als dit het geval is, verwijderen we de hyperlink door de URI in te stellen op een lege string.

```csharp
LinkAnnotation la = (LinkAnnotation)a;
if (la.Action is GoToURIAction)
{
    GoToURIAction gta = (GoToURIAction)la.Action;
    gta.URI = "";
```

Met dit codefragment wordt ervoor gezorgd dat de hyperlinkactie effectief wordt verwijderd.

## Stap 6: Tekstfragmenten absorberen

Vervolgens absorberen we de tekstfragmenten die geassocieerd zijn met de linkannotatie. Dit stelt ons in staat om het uiterlijk van de tekst te manipuleren.

```csharp
TextFragmentAbsorber tfa = new TextFragmentAbsorber();
tfa.TextSearchOptions = new TextSearchOptions(a.Rect);
doc.Pages[a.PageIndex].Accept(tfa);
```

 Hier creëren we een`TextFragmentAbsorber` en stel de zoekopties in op de rechthoek van de annotatie. Dit helpt ons de tekst te vinden die was gelinkt.

## Stap 7: Wijzig het uiterlijk van de tekst

Zodra we de tekstfragmenten hebben, kunnen we hun uiterlijk aanpassen. In dit geval verwijderen we de onderstreping en veranderen we de tekstkleur naar zwart.

```csharp
foreach (TextFragment tf in tfa.TextFragments)
{
    tf.TextState.Underline = false;
    tf.TextState.ForegroundColor = Color.Black;
}
```

Met deze stap wordt de leesbaarheid van de tekst verbeterd door de hyperlinkstijl te verwijderen.

## Stap 8: Verwijder de annotatie

Nadat we de tekst hebben aangepast, kunnen we de linkannotatie veilig uit het document verwijderen.

```csharp
doc.Pages[a.PageIndex].Annotations.Delete(a);
}
```

Met deze regel verwijdert u de hyperlink uit het PDF-bestand, zodat deze niet meer in de uiteindelijke uitvoer voorkomt.

## Stap 9: Sla het gewijzigde document op

Ten slotte moeten we het gewijzigde document opslaan in een nieuw PDF-bestand. Dit is de laatste stap in ons proces.

```csharp
doc.Save(dataDir + "RemoveHyperlinksFromText_out.pdf");
```

 Deze regel slaat het document op met de hyperlinks verwijderd, waardoor een nieuw PDF-bestand met de naam wordt gemaakt`RemoveHyperlinksFromText_out.pdf`.

## Conclusie

En daar heb je het! Je hebt met succes hyperlinks verwijderd uit een HTML-document nadat je het hebt geconverteerd naar PDF met Aspose.PDF voor .NET. Dit proces verbetert niet alleen de leesbaarheid van je PDF, maar geeft je ook controle over de inhoud die je presenteert. 

## Veelgestelde vragen

### Kan ik hyperlinks uit elk PDF-document verwijderen?
Ja, u kunt hyperlinks uit elk PDF-document verwijderen met Aspose.PDF voor .NET.

### Is Aspose.PDF gratis te gebruiken?
 Aspose.PDF biedt een gratis proefversie, maar voor volledige functies moet u een licentie kopen. Controleer de[koop pagina](https://purchase.aspose.com/buy).

### Wat moet ik doen als ik problemen ondervind bij het gebruik van Aspose.PDF?
 U kunt hulp zoeken op de[ondersteuningsforum](https://forum.aspose.com/c/pdf/10).

### Kan ik andere bestandsformaten met Aspose naar PDF converteren?
Ja, Aspose ondersteunt verschillende bestandsformaten voor conversie naar PDF.

### Waar kan ik Aspose.PDF voor .NET downloaden?
 Je kunt het downloaden van de[downloadlink](https://releases.aspose.com/pdf/net/).