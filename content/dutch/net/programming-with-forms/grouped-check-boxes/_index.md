---
title: Gegroepeerde selectievakjes in PDF-document
linktitle: Gegroepeerde selectievakjes in PDF-document
second_title: Aspose.PDF voor .NET API-referentie
description: Leer hoe u gegroepeerde selectievakjes (keuzerondjes) in een PDF-document kunt maken met Aspose.PDF voor .NET met deze stapsgewijze zelfstudie.
type: docs
weight: 170
url: /nl/net/programming-with-forms/grouped-check-boxes/
---
## Invoering

Het maken van interactieve PDF's is niet zo moeilijk als het klinkt, vooral niet als u krachtige tools als Aspose.PDF voor .NET tot uw beschikking hebt. Een van de interactieve elementen die u mogelijk aan uw PDF-documenten moet toevoegen, zijn gegroepeerde selectievakjes, of specifieker, keuzerondjes waarmee gebruikers één optie uit een set kunnen selecteren. Deze tutorial leidt u door het proces van het toevoegen van gegroepeerde selectievakjes (keuzerondjes) aan een PDF-document met behulp van Aspose.PDF voor .NET. Of u nu een beginner of een doorgewinterde ontwikkelaar bent, u zult deze gids boeiend, gedetailleerd en gemakkelijk te volgen vinden.

## Vereisten

Voordat we in de stapsgewijze handleiding duiken, bespreken we eerst enkele essentiële vereisten:

1.  Aspose.PDF voor .NET: Zorg ervoor dat u de Aspose.PDF-bibliotheek hebt geïnstalleerd. Als dat niet zo is, kunt u[download het hier](https://releases.aspose.com/pdf/net/).
2. IDE: U moet een ontwikkelomgeving hebben ingesteld, zoals Visual Studio.
3. .NET Framework: Het project moet gericht zijn op een versie van .NET Framework die compatibel is met Aspose.PDF.
4. Basiskennis van C#: Kennis van C# en PDF-bewerking is vereist om de cursus soepel te kunnen volgen.
5.  Licentie: Aspose.PDF vereist een licentie voor volledige functionaliteit. U kunt[een tijdelijke licentie verkrijgen](https://purchase.aspose.com/temporary-license/) indien nodig.

## Pakketten importeren

Voordat u begint, moet u ervoor zorgen dat u de benodigde naamruimten in uw project hebt geïmporteerd:

```csharp
using System;
using System.IO;
using Aspose.Pdf;
using Aspose.Pdf.Annotations;
using Aspose.Pdf.Forms;
```

Met deze pakketten krijgt u toegang tot alle klassen en methoden die nodig zijn om PDF-documenten te bewerken, inclusief het maken van keuzerondjes en het definiëren van hun eigenschappen.

In dit gedeelte leggen we het proces voor het maken van gegroepeerde selectievakjes (keuzerondjes) uit in duidelijke, gemakkelijk te volgen stappen.

## Stap 1: Maak een nieuw PDF-document

 De eerste stap is het maken van een exemplaar van de`Document` object, dat uw PDF-bestand zal vertegenwoordigen. Voeg vervolgens een lege pagina toe aan uw document waar u uw gegroepeerde selectievakjes zult plaatsen.

```csharp
// Instantieer Document-object
Document pdfDocument = new Document();

// Een pagina toevoegen aan het PDF-bestand
Page page = pdfDocument.Pages.Add();
```

Hiermee wordt de basis gelegd voor het toevoegen van elementen, zoals keuzerondjes, aan de PDF.

## Stap 2: Initialiseer het keuzerondjeveld

Vervolgens moeten we een`RadioButtonField` object, dat de gegroepeerde selectievakjes (keuzerondjes) zal bevatten. Dit veld wordt toegevoegd aan de specifieke pagina waar de selectievakjes zullen verschijnen.

```csharp
// Instantieer RadioButtonField-object en wijs het toe aan de eerste pagina
RadioButtonField radio = new RadioButtonField(pdfDocument.Pages[1]);
```

U kunt dit zien als de container waarin de afzonderlijke keuzerondjes worden gegroepeerd.

## Stap 3: Opties voor keuzerondjes toevoegen

 Laten we nu de individuele radioknopopties aan het veld toevoegen. In dit voorbeeld voegen we twee radioknoppen toe en specificeren we hun posities met behulp van de`Rectangle` voorwerp.

```csharp
// Voeg de eerste keuzerondje-optie toe en specificeer de positie ervan met behulp van Rechthoek
RadioButtonOptionField opt1 = new RadioButtonOptionField(page, new Aspose.Pdf.Rectangle(0, 0, 20, 20));
RadioButtonOptionField opt2 = new RadioButtonOptionField(page, new Aspose.Pdf.Rectangle(100, 0, 120, 20));

// Optienamen instellen voor identificatie
opt1.OptionName = "Option1";
opt2.OptionName = "Option2";
```

 Hier, de`Rectangle` object definieert de coördinaten en de grootte van elke keuzerondje op de pagina.

## Stap 4: Pas de stijl van de keuzerondjes aan

 U kunt het uiterlijk van de keuzerondjes aanpassen door hun`Style` eigenschap. U wilt bijvoorbeeld vierkante selectievakjes of kruisvormige selectievakjes.

```csharp
// De stijl van de keuzerondjes instellen
opt1.Style = BoxStyle.Square;
opt2.Style = BoxStyle.Cross;
```

Hiermee kunt u het uiterlijk van de selectievakjes bepalen, waardoor ze gebruiksvriendelijker en visueel aantrekkelijker worden.

## Stap 5: Randeigenschappen configureren

Randen spelen een belangrijke rol bij het gemakkelijk herkenbaar maken van de selectievakjes. Hier voegen we stevige randen toe rond elke radioknopoptie en definiëren we hun breedte en kleur.

```csharp
// Configureer de rand van de eerste keuzerondje
opt1.Border = new Border(opt1);
opt1.Border.Style = BorderStyle.Solid;
opt1.Border.Width = 1;
opt1.Characteristics.Border = Color.Black;

// Configureer de rand van de tweede keuzerondje
opt2.Border = new Border(opt2);
opt2.Border.Style = BorderStyle.Solid;
opt2.Border.Width = 1;
opt2.Characteristics.Border = Color.Black;
```

Met deze stap wordt ervoor gezorgd dat elk keuzerondje een duidelijk gedefinieerde rand heeft, waardoor de leesbaarheid van het document wordt verbeterd.

## Stap 6: Voeg keuzerondjes toe aan het formulier

Nu voegen we de radioknoppen toe aan het formulier van het document. Dit is de laatste stap in het groeperen van de selectievakjes onder één veld.

```csharp
// Voeg een keuzerondje toe aan het formulierobject van het document
pdfDocument.Form.Add(radio);
```

Het formulierobject fungeert als een container voor alle interactieve elementen, inclusief onze gegroepeerde selectievakjes.

## Stap 7: Sla het PDF-document op

Zodra alles is ingesteld, kunt u het PDF-document opslaan op de gewenste locatie.

```csharp
// Definieer het pad van het uitvoerbestand
string dataDir = "YOUR DOCUMENT DIRECTORY" + "GroupedCheckBoxes_out.pdf";

// Sla het PDF-document op
pdfDocument.Save(dataDir);

// Bevestig succesvolle creatie
Console.WriteLine("Grouped checkboxes added successfully. File saved at " + dataDir);
```

En dat is alles! U hebt met succes een PDF met gegroepeerde selectievakjes gemaakt met Aspose.PDF voor .NET.

## Conclusie

Het toevoegen van interactieve elementen zoals gegroepeerde selectievakjes aan PDF-documenten kan in eerste instantie lastig lijken, maar met Aspose.PDF voor .NET wordt het een fluitje van een cent. Door deze stapsgewijze handleiding te volgen, hebt u geleerd hoe u een basis-PDF-document opzet, gegroepeerde keuzerondjes toevoegt, hun uiterlijk aanpast en het uiteindelijke resultaat opslaat. Of u nu formulieren, enquêtes of een ander type interactieve PDF bouwt, deze handleiding geeft u een solide basis om mee te beginnen.

## Veelgestelde vragen

### Kan ik meer dan twee keuzerondjes aan een groep toevoegen?
 Absoluut! Instantieer gewoon extra`RadioButtonOptionField` objecten en voeg ze toe aan de`RadioButtonField` zoals getoond in de tutorial.

### Hoe kan ik meerdere groepen selectievakjes in één document verwerken?
Om meerdere groepen te maken, moet u afzonderlijke groepen instantiëren`RadioButtonField` objecten voor elke groep.

### Is er een limiet aan het aantal selectievakjes dat ik kan toevoegen?
Nee, Aspose.PDF voor .NET stelt geen beperkingen aan het aantal selectievakjes dat u aan een PDF kunt toevoegen.

### Kan ik het uiterlijk van selectievakjes wijzigen nadat ik ze heb toegevoegd?
Ja, u kunt eigenschappen zoals randstijl, breedte en kleur wijzigen nadat u de selectievakjes hebt toegevoegd.

### Is het mogelijk om afbeeldingen als keuzerondjes te gebruiken?
 Ja, met Aspose.PDF kunt u aangepaste afbeeldingen gebruiken als keuzerondjes door de volgende instellingen in te stellen:`Appearance` eigenschap van elke keuzerondjeoptie.