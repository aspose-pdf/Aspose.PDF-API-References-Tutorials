---
title: Kolommentekst uit PDF-bestand extraheren
linktitle: Kolommentekst uit PDF-bestand extraheren
second_title: Aspose.PDF voor .NET API-referentie
description: Leer hoe u tekstkolommen uit PDF-bestanden kunt extraheren met Aspose.PDF voor .NET. Deze gids geeft elke stap weer met codevoorbeelden en uitleg.
type: docs
weight: 150
url: /nl/net/programming-with-text/extract-columns-text/
---
## Invoering

Werkt u met PDF-bestanden en moet u tekst in een specifiek kolomformaat extraheren? Of u nu facturen, rapporten of gestructureerde documenten verwerkt, het nauwkeurig extraheren van tekst uit een PDF kan een lastige klus zijn. Dit is waar Aspose.PDF voor .NET in beeld komt om het proces te vereenvoudigen. In deze tutorial laten we u zien hoe u eenvoudig kolommen tekst uit een PDF-bestand kunt extraheren. 

## Vereisten

Voordat we in de code duiken, bespreken we eerst de essentiële zaken die je nodig hebt:

-  Aspose.PDF voor .NET: Zorg ervoor dat u de nieuwste versie van Aspose.PDF voor .NET hebt geïnstalleerd. Als dat niet zo is, kunt u[download het hier](https://releases.aspose.com/pdf/net/).
- Ontwikkelomgeving: U hebt Visual Studio of een andere .NET-ontwikkelomgeving nodig om met de code te kunnen werken.
- PDF-document: Zorg dat u een voorbeeld-PDF-document bij de hand hebt, bij voorkeur een document met tekstkolommen, aangezien we er tekst uit gaan halen.

 Als u Aspose.PDF voor .NET nog niet hebt geïnstalleerd, kunt u een[gratis proefperiode](https://releases.aspose.com/) of[een licentie kopen](https://purchase.aspose.com/buy) voor alle functies. U kunt ook een aanvraag indienen voor een[tijdelijke licentie](https://purchase.aspose.com/temporary-license) indien nodig.

## Naamruimten importeren

Om Aspose.PDF voor .NET in uw project te gebruiken, moet u de volgende naamruimten importeren:

```csharp
using System.IO;
using Aspose.Pdf;
using Aspose.Pdf.Text;
using System;
```

## Stapsgewijze handleiding: kolommen tekst uit een PDF extraheren

Laten we nu elk deel van de code opsplitsen om beter te begrijpen hoe het werkt. Volg ons terwijl we stap voor stap elk segment van het proces uitleggen.

## Stap 1: Laad het PDF-document

 Het eerste wat u moet doen, is uw PDF-bestand in de`Document`object. Dit is hoe Aspose.PDF met uw document communiceert.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document pdfDocument = new Document(dataDir + "ExtractTextPage.pdf");
```

 In deze stap definiëren we eenvoudigweg de directory waar uw PDF-document is opgeslagen. Vervangen`"YOUR DOCUMENT DIRECTORY"` met het pad naar uw lokale PDF-bestand. De`Document` object laadt de PDF in het geheugen, waardoor deze toegankelijk is voor verdere verwerking.

## Stap 2: De tekstfragmentabsorber instellen

 Vervolgens gebruiken we een`TextFragmentAbsorber` om alle tekst uit het PDF-bestand te absorberen of vast te leggen. Deze absorberklasse is ontworpen om tekstfragmenten uit specifieke gebieden in uw PDF te extraheren, wat het ideaal maakt voor het extraheren van tekstkolommen.

```csharp
TextFragmentAbsorber tfa = new TextFragmentAbsorber();
pdfDocument.Pages.Accept(tfa);
TextFragmentCollection tfc = tfa.TextFragments;
```

Hier maken we een instantie van`TextFragmentAbsorber` en pas het toe op alle pagina's van de PDF met behulp van`Accept()` . De`TextFragmentCollection` slaat de geëxtraheerde tekst op en uit deze verzameling kunnen we tekst naar behoefte manipuleren of extraheren.

## Stap 3: Pas de lettergrootte van de geëxtraheerde tekst aan

Zodra u de tekstfragmenten hebt vastgelegd, wilt u mogelijk de lettergrootte verkleinen, vooral als de originele tekst te groot is. In dit voorbeeld verkleinen we de lettergrootte met 70%.

```csharp
foreach (TextFragment tf in tfc)
{
    // Verklein de lettergrootte met 70%
    tf.TextState.FontSize = tf.TextState.FontSize * 0.7f;
}
```

Deze code loopt door elk`TextFragment` in de collectie en verkleint de lettergrootte met 70%. Door de lettergrootte aan te passen, kunt u de geëxtraheerde tekst gemakkelijker beheren, vooral als u deze voor verschillende doeleinden formatteert.

## Stap 4: Sla het document op in een geheugenstroom

 Nadat we de tekst hebben aangepast, slaan we de PDF op in een`MemoryStream`Hierdoor kunnen we het document in het geheugen bewaren voor verdere verwerking, zonder dat we het terug naar de schijf hoeven te schrijven.

```csharp
Stream st = new MemoryStream();
pdfDocument.Save(st);
pdfDocument = new Document(st);
```

Hier slaan we de PDF op in een geheugenstroom en laden het document vervolgens opnieuw. Deze methode is handig als u met grote bestanden werkt en onnodige schijfbewerkingen wilt vermijden.

## Stap 5: Alle tekst extraheren met Text Absorber

 Nu we de PDF hebben voorbereid, is het tijd om de tekst te extraheren. We gebruiken`TextAbsorber` om alle tekst uit het document te halen.

```csharp
TextAbsorber textAbsorber = new TextAbsorber();
pdfDocument.Pages.Accept(textAbsorber);
String extractedText = textAbsorber.Text;
```

 In deze stap wordt de`TextAbsorber` absorbeert alle tekst uit de PDF en de geëxtraheerde tekst wordt opgeslagen in de`extractedText` string. Dit is waar de magie gebeurt: uw tekstkolommen zijn nu in platte-tekstformaat!

## Stap 6: Sla de geëxtraheerde tekst op in een bestand

 Ten slotte slaan we de geëxtraheerde tekst op in een`.txt` bestand voor eenvoudige toegang en verder gebruik.

```csharp
dataDir = dataDir + "ExtractColumnsText_out.txt";
System.IO.File.WriteAllText(dataDir, extractedText);
Console.WriteLine("\nColumns text extracted successfully from Pages of PDF Document.\nFile saved at " + dataDir);
```

 Deze code schrijft de geëxtraheerde tekst naar een nieuw`.txt` bestand en slaat het op in de door u opgegeven directory. Er wordt een bericht weergegeven in de console om te bevestigen dat het proces succesvol was.

## Conclusie

Daar heb je het! Kolommen tekst extraheren uit een PDF-bestand met Aspose.PDF voor .NET is makkelijker dan je zou denken. Met slechts een paar regels code kun je een PDF laden, specifieke tekst extraheren, de opmaak aanpassen en de resultaten opslaan in een tekstbestand.

Deze techniek is ongelooflijk handig voor het verwerken van gestructureerde documenten zoals tabellen, rapporten of inhoud die in kolommen is georganiseerd. Of u nu gegevensextractie wilt automatiseren of bulkdocumenten wilt verwerken, Aspose.PDF biedt de tools om dit efficiënt te doen.

## Veelgestelde vragen

### Kan ik tekst uit specifieke pagina's van een PDF halen?  
 Ja! U kunt de`TextFragmentAbsorber` om specifieke pagina's te targeten met behulp van de`pdfDocument.Pages[pageIndex].Accept(tfa);` methode.

### Is het mogelijk om tekst uit slechts één kolom te extraheren in een PDF met meerdere kolommen?  
 Ja, maar u moet met de coördinaten van de tekstfragmenten werken met behulp van`TextFragment.Rectangle` om specifieke delen van het document te targeten.

### Hoe kan ik de nauwkeurigheid van tekstextractie verbeteren?  
 Voor een betere nauwkeurigheid, zorg ervoor dat de structuur van de PDF goed gedefinieerd is en vermijd documenten met complexe lay-outs. U kunt ook de`TextFragmentAbsorber` om tekst te extraheren op basis van lettertypen, -groottes of -regio's.

### Ondersteunt Aspose.PDF het extraheren van tekst uit gescande documenten?  
Ja, maar je moet OCR (Optical Character Recognition) technologie gebruiken. Aspose biedt ook tools hiervoor.

### Hoe verwerk ik grote PDF-bestanden met duizenden pagina's?  
Bij grote PDF-bestanden kunt u het document in stukken verwerken door tekst van een paar pagina's tegelijk te extraheren. Zo voorkomt u een hoog geheugengebruik.