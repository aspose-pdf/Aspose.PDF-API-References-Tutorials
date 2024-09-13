---
title: Afbeeldingsgrootte in PDF-bestand instellen
linktitle: Afbeeldingsgrootte in PDF-bestand instellen
second_title: Aspose.PDF voor .NET API-referentie
description: Leer hoe u de afbeeldingsgrootte in een PDF instelt met Aspose.PDF voor .NET. Deze stapsgewijze handleiding helpt u bij het aanpassen van de grootte van afbeeldingen, het aanpassen van pagina-eigenschappen en het opslaan van PDF's.
type: docs
weight: 270
url: /nl/net/programming-with-images/set-image-size/
---
## Invoering

Werken met PDF's is een veelvoorkomende vereiste voor veel toepassingen en de mogelijkheid om elementen in een PDF-bestand te manipuleren kan cruciaal zijn. Of u nu een rapportgenerator bouwt of dynamische inhoud toevoegt aan uw PDF, het regelen van de grootte van afbeeldingen in uw document is een essentiële functie. In deze tutorial laten we u zien hoe u de afbeeldingsgrootte in een PDF-bestand instelt met Aspose.PDF voor .NET. Deze krachtige bibliotheek biedt uitgebreide controle over PDF-inhoud en we zullen het stap voor stap uitleggen om u te laten zien hoe eenvoudig het kan zijn. Aan het einde kunt u afbeeldingen met vertrouwen van grootte veranderen en begrijpen hoe deze functionaliteit uw PDF-workflows kan verbeteren.


## Vereisten

Voordat we in de code duiken, zijn er een paar dingen die je nodig hebt om deze tutorial te kunnen volgen.

1.  Aspose.PDF voor .NET: Zorg ervoor dat u de nieuwste versie van de Aspose.PDF-bibliotheek hebt geïnstalleerd. U kunt[download het hier](https://releases.aspose.com/pdf/net/).
2. .NET Framework of .NET Core: Zorg ervoor dat u een werkomgeving hebt met .NET Framework of .NET Core ingesteld.
3. Basiskennis van C#: We gebruiken C# als programmeertaal, dus vertrouwdheid ermee is essentieel.
4. Voorbeeldafbeelding: U hebt een voorbeeldafbeelding nodig om in de PDF te embedden. U kunt elke afbeelding gebruiken die u wilt, maar zorg ervoor dat deze toegankelijk is in uw projectdirectory.

## Pakketten importeren

Om Aspose.PDF voor .NET te gebruiken, moet u eerst de benodigde naamruimten importeren. Hier is een eenvoudige installatie:

```csharp
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

Nu we de basis onder de knie hebben, gaan we verder met het maken en wijzigen van een PDF-document.

## Stap 1: Initialiseer uw PDF-document

 Het eerste wat we moeten doen is een nieuw PDF-document maken. We gebruiken de`Document` klasse van Aspose.PDF om dit te bereiken.

```csharp
// Het pad naar de documentenmap.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Instantieer Document-object
Document doc = new Document();
```
 
 Hier instantiëren we een`Document` object, dat ons PDF-bestand zal vertegenwoordigen. We specificeren ook de directory waar onze bestanden zich bevinden met behulp van de`dataDir` variabele. Dit is het startpunt voor het maken van een PDF met Aspose.PDF.

## Stap 2: Voeg een nieuwe pagina toe aan uw PDF

Zodra we ons document klaar hebben, moeten we er een pagina aan toevoegen. Elke PDF moet minstens één pagina hebben, dus laten we er een toevoegen.

```csharp
// Pagina toevoegen aan paginaverzameling van PDF-bestand
Aspose.Pdf.Page page = doc.Pages.Add();
```
 
 We voegen een nieuwe pagina toe aan het document met behulp van de`Pages.Add()` methode. Deze pagina fungeert als canvas waarop we onze afbeelding plaatsen. Elke pagina in een PDF is in feite een blanco lei waar u tekst, afbeeldingen of andere content aan kunt toevoegen.

## Stap 3: Een afbeeldinginstantie maken

 Nu is het tijd om de afbeelding voor te bereiden die we in de PDF willen invoegen. Aspose.PDF biedt een`Image` klasse om afbeeldingen te verwerken.

```csharp
// Een afbeeldinginstantie maken
Aspose.Pdf.Image img = new Aspose.Pdf.Image();
```
 
 We maken een nieuw exemplaar van de`Image` klasse. Dit object bevat de eigenschappen van de afbeelding die we aan de PDF willen toevoegen. In de volgende stappen configureren we de grootte en het type van de afbeelding.

## Stap 4: Stel de afbeeldingsgrootte in (breedte en hoogte)

Hier komen we tot de kern van onze tutorial: het instellen van de grootte van de afbeelding. Met Aspose.PDF kunt u de breedte en hoogte van de afbeelding in punten opgeven.

```csharp
// Stel de breedte en hoogte van de afbeelding in punten in
img.FixWidth = 100;
img.FixHeight = 100;
```
 
 De`FixWidth` En`FixHeight`Met eigenschappen kunt u de exacte afmetingen van de afbeelding in punten instellen. In dit voorbeeld wijzigen we de grootte van de afbeelding naar 100x100 punten. U kunt deze waarden aanpassen aan uw behoeften.

## Stap 5: Geef het afbeeldingstype op

Afhankelijk van het afbeeldingsformaat waarmee u werkt, moet u mogelijk het afbeeldingstype instellen. Aspose.PDF ondersteunt verschillende afbeeldingsformaten en hier definiëren we het bestandstype.

```csharp
// Stel het afbeeldingstype in als SVG
img.FileType = Aspose.Pdf.ImageFileType.Unknown;
```
 
 In dit geval laten we het bestandstype zoals`Unknown` , waarmee de bibliotheek het afbeeldingstype automatisch kan detecteren. Als u het specifieke bestandstype weet, kunt u dit instellen (bijv.`ImageFileType.Jpeg` voor JPEG-afbeeldingen). Met deze stap weet Aspose hoe de afbeelding correct moet worden verwerkt.

## Stap 6: Stel het pad naar uw afbeeldingsbestand in

Nu moeten we Aspose vertellen waar het het imagebestand kan vinden. Zorg ervoor dat uw image toegankelijk is in de opgegeven directory.

```csharp
// Pad voor bronbestand
img.File = dataDir + "aspose-logo.jpg";
```
 
 Hier stellen we het bestandspad naar de afbeelding in. De afbeelding bevindt zich in dit geval in de`dataDir` map en is genoemd`aspose-logo.jpg`Zorg ervoor dat u dit vervangt door de werkelijke naam en locatie van uw afbeeldingsbestand.

## Stap 7: Voeg de afbeelding toe aan de pagina

Nu de afbeelding geconfigureerd is en het bestandspad is ingesteld, kunnen we de afbeelding aan onze pagina toevoegen.

```csharp
// Voeg de afbeelding toe aan de alineaverzameling
page.Paragraphs.Add(img);
```
 
 De`Paragraphs.Add()` methode stelt ons in staat om de afbeelding aan de pagina toe te voegen. Denk aan de`Paragraphs` verzameling als een lijst met items die op de PDF-pagina worden weergegeven. We kunnen meerdere elementen aan deze verzameling toevoegen, zoals afbeeldingen, tekst en vormen.

## Stap 8: Pagina-eigenschappen aanpassen

Om ervoor te zorgen dat onze afbeelding goed past, passen we de paginagrootte aan. Dit zorgt ervoor dat de pagina-afmetingen overeenkomen met de content die we toevoegen.

```csharp
// Pagina-eigenschappen instellen
page.PageInfo.Width = 800;
page.PageInfo.Height = 800;
```
 
Hier stellen we de paginabreedte en -hoogte in op 800 punten. Deze stap is optioneel, maar zorgt ervoor dat de pagina de aangepaste afbeelding kan bevatten. U kunt deze waarden aanpassen op basis van uw specifieke vereisten.

## Stap 9: Sla de PDF op

Nadat we de afbeeldings- en pagina-eigenschappen hebben geconfigureerd, kunnen we de PDF opslaan.

```csharp
//Sla het resulterende PDF-bestand op
dataDir = dataDir + "SetImageSize_out.pdf";
doc.Save(dataDir);
```
 
 We slaan het gewijzigde document op als`SetImageSize_out.pdf` in dezelfde directory. Dit bestand zal nu de aangepaste afbeelding bevatten die u hebt toegevoegd.

## Conclusie

In deze tutorial hebben we behandeld hoe u de afbeeldingsgrootte in een PDF instelt met Aspose.PDF voor .NET. We hebben u door het maken van een document, het toevoegen van een pagina, het configureren van een afbeelding en het opslaan van het resultaat geleid. Deze stapsgewijze handleiding is slechts het begin van wat u kunt doen met Aspose.PDF voor .NET. Nu u hebt geleerd hoe u de grootte van afbeeldingen kunt wijzigen, kunt u gerust andere functies verkennen, zoals tekstopmaak, het maken van tabellen en zelfs het toevoegen van aantekeningen aan uw PDF.

## Veelgestelde vragen

### Kan ik verschillende afbeeldingsformaten gebruiken met Aspose.PDF voor .NET?  
Ja, Aspose.PDF ondersteunt verschillende afbeeldingsformaten, zoals JPEG, PNG, BMP en SVG.

### Hoe behoud ik de beeldverhouding van de afbeelding?  
 U kunt de beeldverhouding behouden door de volgende instellingen te kiezen:`FixWidth` of`FixHeight` terwijl de andere dimensie oningesteld blijft.

### Kan ik meerdere afbeeldingen aan één PDF-pagina toevoegen?  
Absoluut! Herhaal gewoon het proces van het toevoegen van een afbeeldinginstantie en voeg elk exemplaar toe aan de`Paragraphs` verzameling.

### Is het mogelijk om de afbeeldingsgrootte in andere eenheden dan punten in te stellen?  
Aspose.PDF werkt voornamelijk met punten, maar u kunt ook andere eenheden, zoals inches of millimeters, omzetten in punten (1 inch = 72 punten).

### Hoe plaats ik een afbeelding op een specifieke locatie op de pagina?  
 U kunt de`Image.LowerLeftX` En`Image.LowerLeftY` Eigenschappen om de afbeelding op de pagina te positioneren.