---
title: Teken XForm op pagina
linktitle: Teken XForm op pagina
second_title: Aspose.PDF voor .NET API-referentie
description: Leer hoe u XForms in PDF kunt tekenen met Aspose.PDF voor .NET met deze uitgebreide stapsgewijze handleiding.
type: docs
weight: 10
url: /nl/net/programming-with-operators/draw-xform-on-page/
---
## Invoering

Het maken van dynamische en visueel aantrekkelijke PDF-documenten is een cruciale vaardigheid geworden in de digitale wereld van vandaag. Of u nu een ontwikkelaar bent die werkt aan documentgeneratie of een ontwerper die zich richt op esthetiek, het begrijpen van hoe u PDF's kunt manipuleren is van onschatbare waarde. In deze tutorial onderzoeken we hoe u een XForm op een pagina kunt tekenen met behulp van de Aspose.PDF-bibliotheek voor .NET. Deze stapsgewijze handleiding leidt u door het maken van XForms en het effectief plaatsen ervan op uw PDF-pagina's.

## Vereisten

Voordat we beginnen, hebt u een paar dingen nodig om een soepele ervaring te garanderen:

1.  Aspose.PDF voor .NET-bibliotheek: Zorg ervoor dat u de Aspose.PDF-bibliotheek hebt geïnstalleerd. Als u deze nog niet hebt geïnstalleerd, download deze dan van[hier](https://releases.aspose.com/pdf/net/).
2. Ontwikkelomgeving: Een werkende .NET-ontwikkelomgeving (zoals Visual Studio 2019 of later).
3. Voorbeeld PDF en afbeeldingsbestanden: U hebt een basis PDF-bestand nodig waar we de XForm tekenen en een afbeelding om de functionaliteit te demonstreren. Voel u vrij om de voorbeeld PDF en een afbeelding te gebruiken die beschikbaar zijn in uw documentenmap.

## Pakketten importeren

Zodra u de vereisten hebt ingesteld, moet u de benodigde naamruimten importeren in uw .NET-project. Hiermee krijgt u toegang tot de klassen en methoden die worden geleverd door Aspose.PDF.

```csharp
using System.IO;
using Aspose.Pdf;
```

Deze naamruimten bieden de essentiële componenten die nodig zijn om PDF-documenten te bewerken en de tekenfuncties te gebruiken.

Laten we het proces opsplitsen in verteerbare stappen. Elke stap bevat duidelijke instructies om u te helpen de concepten te begrijpen en effectief toe te passen.

## Stap 1: Document initialiseren en paden instellen

De basis begrijpen

In deze stap stellen we ons document in en definiëren we de bestandspaden voor de invoer-PDF, de uitvoer-PDF en het afbeeldingsbestand dat in het XForm wordt gebruikt.

```csharp
// Het pad naar de documentenmap.
string dataDir = "YOUR DOCUMENT DIRECTORY"; // vervang door jouw pad
string imageFile = dataDir + "aspose-logo.jpg"; // Het te tekenen beeld
string inFile = dataDir + "DrawXFormOnPage.pdf"; // PDF-bestand invoeren
string outFile = dataDir + "blank-sample2_out.pdf"; // Uitvoer PDF-bestand
```

 Hier,`dataDir`is de basisdirectory waar uw bestanden zich bevinden, dus zorg ervoor dat u deze vervangt`"YOUR DOCUMENT DIRECTORY"` met het werkelijke pad.

## Stap 2: Een nieuw documentexemplaar maken

Het PDF-document laden

Vervolgens maken we een instantie van de klasse Document die onze invoer-PDF vertegenwoordigt.

```csharp
using (Document doc = new Document(inFile))
{
    // Verdere stappen vindt u hier...
}
```

 Met behulp van de`using` De instructie zorgt ervoor dat de bronnen automatisch worden opgeschoond zodra de bewerkingen zijn voltooid.

## Stap 3: Ga naar de pagina-inhoud en begin met tekenen

Instellen voor tekenbewerkingen

Nu gaan we de inhoud van de eerste pagina van ons document benaderen. Hier voegen we onze tekenopdrachten in.

```csharp
OperatorCollection pageContents = doc.Pages[1].Contents;
```

Hiermee krijgen we controle over de inhoud van de pagina en kunnen we grafische operatoren invoegen om ons XForm te tekenen.

## Stap 4: Grafische status opslaan en herstellen

De grafische status behouden

Voordat u de XForm tekent, is het essentieel om de huidige grafische status op te slaan. Dit helpt de renderingcontext te behouden.

```csharp
pageContents.Insert(1, new GSave());
pageContents.Add(new GRestore());
pageContents.Add(new GSave());
```

 De`GSave` operator slaat de huidige grafische status op, terwijl`GRestore`herstelt het later, waardoor we na het tekenen terugkeren naar onze oorspronkelijke context.

## Stap 5: Maak het XForm

Uw XForm samenstellen

Hier maken we ons XForm-object. Dit is de container voor onze tekenbewerkingen, zodat we ze netjes kunnen inkapselen.

```csharp
XForm form = XForm.CreateNewForm(doc.Pages[1], doc);
doc.Pages[1].Resources.Forms.Add(form);
form.Contents.Add(new GSave());
```

 Deze regel maakt een nieuw XForm en voegt het toe aan de resourceformulieren van de pagina.`GSave` wordt opnieuw gebruikt om de grafische status binnen het XForm te behouden.

## Stap 6: Afbeelding toevoegen en afmetingen instellen

Beeldmateriaal integreren

Vervolgens laden we een afbeelding in ons XForm en stellen we de grootte ervan in.

```csharp
form.Contents.Add(new ConcatenateMatrix(200, 0, 0, 200, 0, 0));
Stream imageStream = new FileStream(imageFile, FileMode.Open);
form.Resources.Images.Add(imageStream);
```

 Deze code stelt de afbeeldingsgrootte in met`ConcatenateMatrix`, die definieert hoe de afbeelding wordt getransformeerd. De afbeeldingsstroom wordt toegevoegd aan de resources van XForm.

## Stap 7: Teken de afbeelding

De afbeelding weergeven

 Laten we nu de`Do` operator om de afbeelding die we aan het XForm op onze pagina hebben toegevoegd, daadwerkelijk te tekenen.

```csharp
XImage ximage = form.Resources.Images[form.Resources.Images.Count];
form.Contents.Add(new Do(ximage.Name));
form.Contents.Add(new GRestore());
```

 De`Do` operator is het middel waarmee we de afbeelding op de PDF-pagina renderen. Daarna herstellen we de grafische staat.

## Stap 8: Plaats het XForm op de pagina

Het plaatsen van de XForm

 Om de XForm op specifieke coördinaten op de pagina te renderen, gebruiken we een andere`ConcatenateMatrix` operatie.

```csharp
pageContents.Add(new ConcatenateMatrix(1, 0, 0, 1, 100, 500));
pageContents.Add(new Do(form.Name));
pageContents.Add(new GRestore());
```

 Dit fragment plaatst de XForm op de coördinaten`x=100`, `y=500`.

## Stap 9: Teken het opnieuw op een andere locatie

Hergebruik van XForm

Laten we dezelfde XForm gebruiken en deze op een andere positie op de pagina tekenen.

```csharp
pageContents.Add(new ConcatenateMatrix(1, 0, 0, 1, 100, 300));
pageContents.Add(new Do(form.Name));
pageContents.Add(new GRestore());
```

Hierdoor kunt u hetzelfde XForm hergebruiken, waardoor de efficiëntie van uw documentindeling wordt gemaximaliseerd.

## Stap 10: Het document afronden en opslaan

Uw werk opslaan

Ten slotte moeten we de wijzigingen die we in ons PDF-document hebben aangebracht, opslaan.

```csharp
doc.Save(outFile);
```

Met deze regel wordt uw gewijzigde document naar het opgegeven uitvoerbestandspad geschreven.

## Conclusie

Gefeliciteerd! U hebt succesvol geleerd hoe u een XForm op een PDF-pagina tekent met behulp van de Aspose.PDF-bibliotheek voor .NET. Door deze stappen te volgen, bent u nu uitgerust om uw PDF's te verbeteren met dynamische formulieren en visuele elementen. Of u nu rapporten, marketingmateriaal of elektronische documenten voorbereidt, het opnemen van afbeeldings-XForms kan de inhoud aanzienlijk verrijken. Dus wees creatief en begin met het verkennen van meer functionaliteiten met Aspose.PDF!

## Veelgestelde vragen

### Wat is een XForm in Aspose.PDF?
Een XForm is een herbruikbaar formulier dat afbeeldingen en inhoud kan bevatten, zodat het op meerdere pagina's of op verschillende locaties in een PDF-document kan worden getekend.

### Hoe verander ik de grootte van de afbeelding in XForm?
 U kunt de grootte aanpassen door de parameters in de`ConcatenateMatrix` operator, waarmee de schaal van de getekende inhoud wordt ingesteld.

### Kan ik tekst samen met afbeeldingen toevoegen aan een XForm?
Ja! U kunt ook tekst toevoegen met behulp van de tekstoperatoren die worden aangeboden door de Aspose.PDF-bibliotheek, waarbij u een vergelijkbare aanpak volgt als bij het toevoegen van afbeeldingen.

### Is Aspose.PDF gratis te gebruiken?
 Hoewel Aspose.PDF een gratis proefperiode biedt, is er een licentie vereist voor voortgezet gebruik na de proefperiode. U kunt de licentieopties verkennen[hier](https://purchase.aspose.com/buy).

### Waar kan ik meer gedetailleerde documentatie vinden?
 U kunt de volledige Aspose.PDF-documentatie vinden[hier](https://reference.aspose.com/pdf/net/).