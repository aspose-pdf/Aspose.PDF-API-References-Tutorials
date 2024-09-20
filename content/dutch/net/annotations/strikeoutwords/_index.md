---
title: Woorden doorhalen
linktitle: Woorden doorhalen
second_title: Aspose.PDF voor .NET API-referentie
description: Leer hoe u woorden in een PDF kunt doorhalen met Aspose.PDF voor .NET met deze uitgebreide stapsgewijze handleiding. Verbeter uw vaardigheden in het bewerken van documenten.
type: docs
weight: 150
url: /nl/net/annotations/strikeoutwords/
---
## Invoering

Heb je ooit gemerkt dat je specifieke tekst in een PDF moest benadrukken door deze door te strepen? Of je nu documenten bekijkt, tekst markeert of gewoon bepaalde secties wilt markeren, het doorstrepen van woorden kan een waardevol hulpmiddel zijn. In deze tutorial onderzoeken we hoe je dat kunt doen met Aspose.PDF voor .NET. Deze uitgebreide gids leidt je door elke stap en zorgt ervoor dat je alle informatie hebt die je nodig hebt om deze functie effectief te implementeren in je .NET-toepassingen. 

## Vereisten

Voordat we met de code aan de slag gaan, zijn er een paar vereisten waaraan je moet voldoen om deze tutorial te kunnen volgen:

1.  Aspose.PDF voor .NET-bibliotheek: Zorg ervoor dat u de Aspose.PDF voor .NET-bibliotheek hebt geïnstalleerd. U kunt[download het hier](https://releases.aspose.com/pdf/net/).

2. .NET Framework: Zorg ervoor dat u .NET Framework op uw machine hebt geïnstalleerd. Deze tutorial is ontworpen voor .NET-applicaties.

3. Ontwikkelomgeving: U hebt een IDE zoals Visual Studio nodig om uw code te schrijven en uit te voeren.

4. PDF-document: Zorg dat u een voorbeeld-PDF-bestand bij de hand hebt waarmee u wilt werken. Dit is het document waarin we de tekst doorhalen.

5. Basiskennis van C#: Kennis van C#-programmering is noodzakelijk om de stappen in deze tutorial te begrijpen en te implementeren.

## Pakketten importeren

Voordat we kunnen beginnen met coderen, moeten we de benodigde namespaces importeren in ons .NET-project. Dit geeft ons toegang tot de klassen en methoden die nodig zijn om PDF-bestanden te manipuleren met Aspose.PDF.

```csharp
using System;
using System.IO;
using Aspose.Pdf.Annotations;
using Aspose.Pdf;
```

Deze naamruimten zijn essentieel voor het werken met PDF-documenten, het verwerken van tekst en het toevoegen van aantekeningen, zoals doorhalingen.

In deze sectie zullen we het proces van het doorstrepen van woorden in een PDF-document opsplitsen in eenvoudige, beheersbare stappen. Elke stap wordt vergezeld door een gedetailleerde uitleg om ervoor te zorgen dat u begrijpt hoe alles werkt.

## Stap 1: Laad het PDF-document

De eerste stap is het laden van het PDF-document dat u wilt bewerken. Dit document is het document waarin u specifieke woorden of zinnen doorstreept.

```csharp
// Het pad naar de documentenmap.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Open het PDF-document
Document document = new Document(dataDir + "input.pdf");
```

- `dataDir` : Deze variabele bevat het pad naar uw documentdirectory. Vervangen`"YOUR DOCUMENT DIRECTORY"` met het werkelijke pad waar uw PDF-bestand zich bevindt.
- `Document` : De`Document` klasse vertegenwoordigt een PDF-document. Door het bestandspad door te geven aan de constructor, openen we het PDF-bestand voor verwerking.

## Stap 2: Maak een TextFragment Absorber om specifieke tekst te vinden

 Vervolgens maken we een instantie van`TextFragmentAbsorber` om te zoeken naar een specifiek tekstfragment in het PDF-document. Hiermee kunnen we de tekst vinden die we willen doorhalen.

```csharp
// Maak een TextFragment Absorber-instantie om naar een specifiek tekstfragment te zoeken
Aspose.Pdf.Text.TextFragmentAbsorber textFragmentAbsorber = new Aspose.Pdf.Text.TextFragmentAbsorber("Estoque");
```

- `TextFragmentAbsorber`Deze klasse wordt gebruikt om specifieke tekstfragmenten in het PDF-document te vinden en ermee te werken. In dit voorbeeld zoeken we naar het woord "Estoque". Vervang "Estoque" door het woord of de zin die u in uw document wilt vinden.

## Stap 3: Loop door de pagina's van het PDF-document

 Nu we onze`TextFragmentAbsorber`moeten we door elke pagina van het PDF-document itereren om de opgegeven tekst te vinden.

```csharp
// Door de pagina's van het PDF-document bladeren
for (int i = 1; i <= document.Pages.Count; i++)
{
    // De huidige pagina van het PDF-document ophalen
    Page page = document.Pages[i];
    page.Accept(textFragmentAbsorber);
}
```

- `for (int i = 1; i <= document.Pages.Count; i++)`: Deze lus doorloopt elke pagina van het PDF-document.
- `document.Pages[i]`: Haalt de huidige pagina op die wordt verwerkt.
- `page.Accept(textFragmentAbsorber)` : Deze methode past de`TextFragmentAbsorber` naar de huidige pagina, op zoek naar de opgegeven tekst.

## Stap 4: Verzamel en verwerk de tekstfragmenten

Nadat we de pagina's hebben doorgenomen, verzamelen we de gevonden tekstfragmenten en bereiden we deze voor op verdere verwerking.

```csharp
// Maak een verzameling van opgenomen tekstfragmenten
Aspose.Pdf.Text.TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
```

- `TextFragmentCollection`Deze collectie slaat alle tekstfragmenten op die in het document zijn gevonden. We gebruiken deze collectie in de volgende stap om de tekst door te strepen.

## Stap 5: Loop door de tekstfragmenten en streep ze door

In deze stap doorlopen we elk tekstfragment in onze verzameling en passen we er een doorhalingsaantekening op toe.

```csharp
// Itereren over de verzameling tekstfragmenten
for (int j = 1; j <= textFragmentCollection.Count; j++)
{
	Aspose.Pdf.Text.TextFragment textFragment = textFragmentCollection[j];

    // De rechthoekige afmetingen van het TextFragment-object ophalen
    Aspose.Pdf.Rectangle rect = new Aspose.Pdf.Rectangle(
        (float)textFragment.Position.XIndent,
        (float)textFragment.Position.YIndent,
        (float)textFragment.Position.XIndent + (float)textFragment.Rectangle.Width,
        (float)textFragment.Position.YIndent + (float)textFragment.Rectangle.Height);

    // Instantieer StrikeOut Annotation-instantie
    StrikeOutAnnotation strikeOut = new StrikeOutAnnotation(textFragment.Page, rect);

    // Eigenschappen van de doorhalingsannotatie instellen
    strikeOut.Opacity = .80f;
    strikeOut.Border = new Border(strikeOut);
    strikeOut.Color = Aspose.Pdf.Color.Red;

    // Voeg de annotatie toe aan de annotatieverzameling van de pagina van het tekstfragment
    textFragment.Page.Annotations.Add(strikeOut);
}
```

- `TextFragment textFragment = textFragmentCollection[j]`: Deze regel haalt het huidige tekstfragment op.
- `Aspose.Pdf.Rectangle`:We berekenen de rechthoekige afmetingen van het tekstfragment om te bepalen waar de doorhaling moet plaatsvinden.
- `StrikeOutAnnotation`: Deze klasse vertegenwoordigt de strikeout-annotatie. We instantiëren deze met de berekende rechthoek en de huidige pagina.
- `strikeOut.Opacity`: Met deze eigenschap wordt de dekking van de doorhaling ingesteld, waardoor deze 80% zichtbaar wordt.
- `strikeOut.Color`We zetten de kleur van de strikeout op rood. U kunt dit veranderen naar elke gewenste kleur.
- `textFragment.Page.Annotations.Add(strikeOut)`: Hiermee wordt de doorgehaalde annotatie aan de pagina toegevoegd.

## Stap 6: Sla het gewijzigde PDF-document op

De laatste stap is het opslaan van het gewijzigde PDF-document met de doorhalingen.

```csharp
// Sla het bijgewerkte PDF-document op
dataDir = dataDir + "StrikeOutWords_out.pdf";
document.Save(dataDir);
```

- `dataDir + "StrikeOutWords_out.pdf"`: Hiermee wordt een nieuwe bestandsnaam voor het gewijzigde document gemaakt. Het originele bestand blijft ongewijzigd.
- `document.Save(dataDir)`: Slaat het PDF-document met de doorhalingen op de opgegeven locatie op.

## Conclusie

Gefeliciteerd! U hebt met succes specifieke woorden in een PDF-document doorgehaald met Aspose.PDF voor .NET. Door deze stapsgewijze handleiding te volgen, kunt u nu PDF-documenten aanpassen door tekst te markeren of door te halen, waardoor ze dynamischer worden en beter aansluiten op uw behoeften. Of u nu juridische documenten annoteert, rapporten voorbereidt of gewoon tekst markeert voor controle, deze tutorial heeft u de vaardigheden gegeven om dit efficiënt te doen.

## Veelgestelde vragen

### Kan ik de kleur van de doorhaling veranderen?

 Ja, u kunt de kleur wijzigen door de`strikeOut.Color`eigenschap. U kunt het bijvoorbeeld instellen op`Aspose.Pdf.Color.Blue` voor een blauwe strikeout.

### Is het mogelijk om meerdere woorden tegelijk door te strepen?

 Absoluut! De`TextFragmentAbsorber` kan worden gebruikt om te zoeken naar een woord of zin in het document. U kunt de doorhaling op meerdere instanties toepassen door te itereren door de`TextFragmentCollection`.

### Wat als ik alleen tekst op specifieke pagina's wil doorhalen?

 U kunt de lus die door de pagina's itereert, aanpassen zodat deze alleen de pagina's bevat die u wilt aanpassen. Bijvoorbeeld:`for (int i = 1; i <= 3; i++)` zou de doorhaling alleen op de eerste drie pagina's toepassen.

### Hoe kan ik de dikte van de doorhaallijn aanpassen?

 U kunt de dikte van de doorhaallijn aanpassen door de`Border` eigendom van de`StrikeOutAnnotation`Hiermee kunt u het uiterlijk van de strikeout aanpassen.

### Is er een manier om de doorhaling ongedaan te maken nadat ik het document heb opgeslagen?

Zodra het document is opgeslagen, is de doorhaling permanent. Als u de originele tekst zonder doorhaling wilt behouden, overweeg dan om een back-up van het originele document op te slaan voordat u wijzigingen toepast.