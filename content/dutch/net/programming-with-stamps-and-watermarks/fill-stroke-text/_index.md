---
title: Vul lijntekst in PDF-bestand
linktitle: Vul lijntekst in PDF-bestand
second_title: Aspose.PDF voor .NET API-referentie
description: Leer hoe u moeiteloos lijntekst in PDF-bestanden kunt invullen met Aspose.PDF voor .NET met behulp van deze stapsgewijze handleiding vol praktische voorbeelden.
type: docs
weight: 90
url: /nl/net/programming-with-stamps-and-watermarks/fill-stroke-text/
---
## Invoering

Heb je ooit een PDF-bestand willen aanpassen om het te laten opvallen? Misschien moet je een opvallend watermerk of een vette stempel toevoegen die een belangrijk document onmiskenbaar van jou maakt. Met Aspose.PDF voor .NET kun je eenvoudig tekst in een PDF-bestand invullen, wat een artistieke flair toevoegt die de aandacht trekt. In de tutorial van vandaag doorlopen we het proces om precies dat te doen: tekst in een PDF invullen met C#. Aan het einde heb je een goed begrip van hoe je PDF-bestanden als een professional kunt bewerken.

## Vereisten

Voordat we beginnen met coderen, zijn er een paar dingen die je nodig hebt om deze tutorial makkelijk te kunnen volgen:

1. Visual Studio: Zorg ervoor dat u Visual Studio op uw computer hebt geïnstalleerd, aangezien we C#-code gaan schrijven.
2.  Aspose.PDF-bibliotheek: zorg dat u de Aspose.PDF voor .NET-bibliotheek hebt gedownload. U kunt deze downloaden[hier](https://releases.aspose.com/pdf/net/).
3. Basiskennis van C#: Als u bekend bent met C#-programmering, begrijpt u de tutorial beter.
4. Voorbeeld PDF-bestand: U hebt een voorbeeld PDF-bestand nodig (`input.pdf`voor testdoeleinden. U kunt een eenvoudige maken of een bestaande PDF gebruiken die u hebt.

Nu we alles op zijn plek hebben, gaan we dieper in op het opvullen van tekststroken in uw PDF-bestand.

## Pakketten importeren

Om te beginnen moeten we de benodigde pakketten importeren. Hier is een kort overzicht van de essentiële imports voor ons project:

```csharp
using Aspose.Pdf.Text;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

Met deze pakketten kunnen we de robuuste functionaliteiten van de Aspose.PDF-bibliotheek gebruiken.

Laten we de hoofdtaak opsplitsen in duidelijke stappen. Door deze stappen te volgen, kunt u eenvoudig tekst in uw PDF-bestanden invullen. 

## Stap 1: Stel uw omgeving in

Zorg er eerst voor dat alles correct is ingesteld in uw Visual Studio-project. Maak een nieuw project of kies een bestaand project. Als u hulp nodig hebt, kunt u dit als volgt doen:

1. Open Visual Studio.
2. Maak een nieuw C#-project (bijvoorbeeld een consoletoepassing).
3. Klik met de rechtermuisknop op het project in Solution Explorer en selecteer 'NuGet-pakketten beheren'.
4.  Zoeken naar`Aspose.PDF` en installeer het.

## Stap 2: Definieer uw documentendirectory

Elke reis heeft een startpunt nodig. In ons geval is dat de documentenmap, waar de invoer- en uitvoerbestanden worden opgeslagen. 

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Vervangen`"YOUR DOCUMENT DIRECTORY"` met het werkelijke pad waar uw PDF-invoerbestand zich bevindt. 

## Stap 3: Het TextState-object maken

In deze stap begint u met het definiëren van de eigenschappen van de tekst die u wilt toevoegen. 

```csharp
TextState ts = new TextState();
```

 De`TextState` object bevat de stijlopties voor uw tekstlijn.

## Stap 4: Stel de kleur voor de streek in

Vervolgens wilt u de kleur van de lijn voor uw tekst definiëren. 

```csharp
ts.StrokingColor = Color.Gray;
```

In deze code gebruiken we een grijze kleur voor de streek. Voel je vrij om de kleur te veranderen naar jouw wensen!

## Stap 5: Rendermodus configureren

Om ervoor te zorgen dat uw tekst wordt weergegeven zoals bedoeld, stelt u de renderingmodus in:

```csharp
ts.RenderingMode = TextRenderingMode.StrokeText;
```

Hiermee wordt aan de Aspose-bibliotheek doorgegeven dat we met tekst met een lijntekening werken.

## Stap 6: Laad uw invoer-PDF-document

Nu is het tijd om het PDF-bestand te laden dat u wilt wijzigen. 

```csharp
Facades.PdfFileStamp fileStamp = new Facades.PdfFileStamp(new Aspose.Pdf.Document(dataDir + "input.pdf"));
```

Zorg ervoor dat uw invoer PDF (`input.pdf`bevindt zich in de documentenmap die in eerdere stappen is gedefinieerd.

## Stap 7: Een stempelobject maken

Maak vervolgens een stempel waarop de tekst met de penseelstreek komt te staan. 

```csharp
Aspose.Pdf.Facades.Stamp stamp = new Aspose.Pdf.Facades.Stamp();
```

Deze stempel wordt gebruikt om uw tekst over de PDF te leggen.

## Stap 8: Definieer de tekst die u wilt stempelen

U moet aangeven welke tekst u aan de PDF wilt toevoegen:

```csharp
stamp.BindLogo(new Facades.FormattedText("PAID IN FULL", System.Drawing.Color.Gray, "Arial", Facades.EncodingType.Winansi, true, 78));
```

Hier is "VOLLEDIG BETAALD" de tekst die we toevoegen, samen met de stylingattributen. Pas het aan naar uw wensen!

## Stap 9: Bind de tekststatus

 Bind nu de`TextState` die u eerder aan de postzegel hebt gedefinieerd. 

```csharp
stamp.BindTextState(ts);
```

Met deze stap worden alle stijlen, zoals kleur en renderingmodus, op uw tekst toegepast.

## Stap 10: Stel de positie van de stempel in

Bepaal waar uw postzegel in de PDF zal verschijnen:

```csharp
stamp.SetOrigin(100, 100);
```

 De argumenten`(100, 100)` geven de X- en Y-coördinaten (in punten) aan voor de oorsprong van de tekst. Pas deze waarden aan om uw tekst perfect te positioneren!

## Stap 11: Dekking en rotatie configureren

Hier kunt u experimenteren met het uiterlijk van uw tekst:

```csharp
stamp.Opacity = 5;
stamp.BlendingSpace = Facades.BlendingColorSpace.DeviceRGB;
stamp.Rotation = 45.0F;
```

In dit geval voegen een opaciteitswaarde en een rotatiehoek van 45 graden een unieke flair toe aan uw tekst. U kunt deze instellingen gerust aanpassen voor verschillende effecten.

## Stap 12: Voeg de stempel toe aan de PDF

Dit is de cruciale stap, waarbij we uiteindelijk onze stempel, inclusief de tekst, aan de PDF toevoegen:

```csharp
fileStamp.AddStamp(stamp);
```

En zo is uw tekst klaar om een statement te maken!

## Stap 13: Sla het document op en sluit het

Sla ten slotte uw wijzigingen op en zorg ervoor dat alles goed is opgeruimd. 

```csharp
fileStamp.Save(dataDir + "output_out.pdf");
fileStamp.Close();
```

 Uw nieuw aangepaste PDF-bestand met de lijntekst wordt opgeslagen als`output_out.pdf` in uw documentenmap. 

## Conclusie

En daar heb je het! Door deze eenvoudige stappen te volgen, kun je eenvoudig tekst in een PDF-bestand invullen met Aspose.PDF voor .NET. Of het nu gaat om zakelijke documenten of persoonlijke projecten, met deze techniek kun je een uniek tintje aan je PDF's toevoegen, waardoor ze opvallen in elke stapel papier.

## Veelgestelde vragen

### Wat is Aspose.PDF voor .NET?
Aspose.PDF voor .NET is een bibliotheek waarmee ontwikkelaars programmatisch PDF-bestanden kunnen maken, bewerken en converteren.

### Kan ik Aspose.PDF gratis gebruiken?
Ja, Aspose biedt een gratis proefperiode aan. Je kunt het krijgen[hier](https://releases.aspose.com/).

### Moet ik betalen voor een licentie?
 Hoewel de bibliotheek een gratis proefperiode heeft, kan er ook een tijdelijke licentie worden gekocht bij[deze link](https://purchase.aspose.com/temporary-license/).

### Waar kan ik de documentatie vinden?
 U kunt de volledige documentatie raadplegen[hier](https://reference.aspose.com/pdf/net/).

### Is er ondersteuning beschikbaar als ik problemen tegenkom?
 Absoluut! Je kunt ondersteuning krijgen op het Aspose forum[hier](https://forum.aspose.com/c/pdf/10).