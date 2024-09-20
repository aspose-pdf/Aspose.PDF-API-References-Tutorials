---
title: Tekst rond afbeelding in PDF-bestand plaatsen
linktitle: Tekst rond afbeelding in PDF-bestand plaatsen
second_title: Aspose.PDF voor .NET API-referentie
description: Leer hoe u tekst rond afbeeldingen in PDF's plaatst met Aspose.PDF voor .NET. Volg onze stapsgewijze handleiding om professionele PDF's te maken met afbeeldingen en tekst naast elkaar.
type: docs
weight: 260
url: /nl/net/programming-with-text/placing-text-around-image/
---
## Invoering

Heb je ooit geprobeerd om tekst rond een afbeelding in een PDF-bestand te plaatsen, maar vond je het lastig? Dan ben je hier aan het juiste adres! Aspose.PDF voor .NET maakt dit proces eenvoudig, zodat je met slechts een paar regels code tekst naast afbeeldingen kunt plaatsen. Of je nu rapporten, documenten of presentaties maakt, deze functie is een fantastische manier om de lay-out van je content te verbeteren en deze visueel aantrekkelijker te maken. Vandaag laten we je zien hoe je Aspose.PDF voor .NET kunt gebruiken om tekst rond afbeeldingen in een PDF-document te plaatsen.

## Vereisten

Voordat we in de code duiken, zorgen we ervoor dat alles is ingesteld. Dit is wat je nodig hebt:

-  Aspose.PDF voor .NET: U kunt het downloaden van[hier](https://releases.aspose.com/pdf/net/).
- Visual Studio: Zorg ervoor dat u de nieuwste versie hebt geïnstalleerd om soepel te kunnen werken.
- .NET Framework: In dit voorbeeld wordt .NET gebruikt. Zorg er dus voor dat uw omgeving is ingesteld voor .NET-ontwikkeling.
-  Een tijdelijke licentie: U kunt een tijdelijke licentie aanvragen[hier](https://purchase.aspose.com/temporary-license/) als u het product evalueert.

Als u Aspose.PDF voor .NET nog niet hebt ingesteld, volgt u de installatie-instructies in de[documentatie](https://reference.aspose.com/pdf/net/).

## Naamruimten importeren

Voordat we beginnen met coderen, moeten we de benodigde namespaces importeren. Hier is het codefragment om dat te doen:

```csharp
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

 Deze naamruimten zijn essentieel omdat ze toegang bieden tot klassen zoals`Document`, `Page`, `Image` , En`HtmlFragment`, die we gebruiken om de PDF te maken en te bewerken.

Nu we de toon hebben gezet, gaan we kijken hoe je tekst rond een afbeelding in je PDF-bestand plaatst met Aspose.PDF voor .NET. We leiden je hier stap voor stap doorheen.

## Stap 1: Instantieer het documentobject

 Eerst moet u een PDF-document maken. In Aspose.PDF doet u dit door een`Document` object. Dit object zal dienen als basis voor alle content die we zullen toevoegen.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
```

Hier hebben we een leeg PDF-document gemaakt. Het heeft nog geen pagina's, maar maak je geen zorgen, we voegen er in de volgende stap een toe.

## Stap 2: Een pagina toevoegen aan het document

Nu we ons document hebben, is het tijd om een pagina toe te voegen. Zie dit als het maken van een leeg vel papier waar je je content aan toevoegt.

```csharp
Aspose.Pdf.Page page = doc.Pages.Add();
```

Deze code voegt een nieuwe pagina toe aan het document. Standaard is de pagina leeg, maar dat gaan we nu veranderen.

## Stap 3: Maak een tabel om inhoud te organiseren

Om onze afbeelding en tekst goed uitgelijnd te houden, gebruiken we een tabel. Tabellen in PDF's kunnen helpen bij het structureren van uw lay-out, net als in Word-documenten of HTML.

```csharp
Aspose.Pdf.Table table1 = new Aspose.Pdf.Table();
page.Paragraphs.Add(table1);
```

Dit fragment maakt een tabel en voegt deze toe aan de pagina. Zie de tabel als het raamwerk voor het uitlijnen van uw afbeelding en tekst.

## Stap 4: Kolombreedtes voor de tabel instellen

Nu we een tabel hebben toegevoegd, moeten we definiëren hoe breed de kolommen moeten zijn. Dit zorgt ervoor dat de afbeelding en tekst de juiste grootte hebben op de pagina.

```csharp
table1.ColumnWidths = "120 270";
```

Deze lijn stelt de breedte van twee kolommen in: één voor de afbeelding en één voor de tekst. Pas deze waarden aan als uw afbeelding of tekst meer of minder ruimte nodig heeft.

## Stap 5: Marges en opvulling definiëren

Om er zeker van te zijn dat alles er netjes uitziet, voegen we wat marges en opvulling toe aan de tabel.

```csharp
Aspose.Pdf.MarginInfo margin = new Aspose.Pdf.MarginInfo();
margin.Top = 5f;
margin.Left = 5f;
margin.Right = 5f;
margin.Bottom = 5f;
table1.DefaultCellPadding = margin;
```

Met deze instellingen zorgt u ervoor dat uw tabel een consistente spatie heeft, waardoor de inhoud visueel aantrekkelijk wordt.

## Stap 6: Een afbeelding in de tabel invoegen

Nu gaan we naar het leuke gedeelte: een afbeelding toevoegen. In dit geval voegen we het Aspose-logo toe, maar voel je vrij om elke afbeelding te gebruiken die je wilt.

```csharp
Aspose.Pdf.Row row1 = table1.Rows.Add();
Aspose.Pdf.Image logo = new Aspose.Pdf.Image();
logo.File = dataDir + "aspose-logo.jpg";
logo.FixHeight = 120;
logo.FixWidth = 110;
row1.Cells.Add();
row1.Cells[0].Paragraphs.Add(logo);
```

Dit is wat er gebeurt:
- Wij laden de afbeelding uit de door u opgegeven directory.
- Wij stellen de hoogte en breedte van de afbeelding in.
- Ten slotte voegen we de afbeelding toe aan de eerste cel in de tabel.

## Stap 7: Voeg tekst toe naast de afbeelding

Nu de afbeelding op zijn plek staat, voegen we er wat tekst aan toe. Voor dit voorbeeld gebruiken we HTML-geformatteerde tekst om de content te stylen.

```csharp
string TitleString = "<font face=\"Arial\" size=6 color=\"#101090\"><b> Aspose.Pdf for .NET</b></font>";
string BodyString1 = "<font face=\"Arial\" size=2><br/>Aspose.Pdf for .NET is a non-graphical PDF document reporting component that enables .NET applications to <b>create PDF documents from scratch</b> without utilizing Adobe Acrobat.</font>";

Aspose.Pdf.HtmlFragment TitleText = new Aspose.Pdf.HtmlFragment(TitleString + BodyString1);
row1.Cells.Add();
row1.Cells[1].Paragraphs.Add(TitleText);
```

Dit blok voegt een gestileerde titel en beschrijving toe in de cel naast de afbeelding. U kunt de tekst opmaken met HTML-tags voor meer maatwerk.

## Stap 8: Pas de verticale uitlijning aan

Standaard wordt de inhoud van tabelcellen mogelijk niet uitgelijnd zoals u wilt. In dit geval willen we ervoor zorgen dat de tekst bovenaan de cel is uitgelijnd.

```csharp
row1.Cells[1].VerticalAlignment = Aspose.Pdf.VerticalAlignment.Top;
```

Hierdoor staat de tekst bovenaan de cel, waardoor de lay-out netjes en professioneel blijft.

## Stap 9: Voeg meer tekst toe onder de afbeelding en beschrijving

U wilt misschien meer content onder de afbeelding en tekst opnemen. Laten we hiervoor een extra rij aan de tabel toevoegen.

```csharp
Aspose.Pdf.Row SecondRow = table1.Rows.Add();
SecondRow.Cells.Add();
SecondRow.Cells[0].ColSpan = 2;
SecondRow.Cells[0].VerticalAlignment = Aspose.Pdf.VerticalAlignment.Top;

string SecondRowString = "<font face=\"Arial\" size=2>Aspose.Pdf for .NET supports the creation of PDF files through API and XML or XSL-FO templates.</font>";
Aspose.Pdf.HtmlFragment SecondRowText = new Aspose.Pdf.HtmlFragment(SecondRowString);
SecondRow.Cells[0].Paragraphs.Add(SecondRowText);
```

Hier hebben we een extra rij met tekst toegevoegd, verdeeld over beide kolommen, om de balans in de lay-out te behouden.

## Stap 10: Sla het PDF-document op

Ten slotte moeten we het document opslaan, zodat u de wijzigingen kunt bekijken.

```csharp
doc.Save(dataDir + "PlacingTextAroundImage_out.pdf");
```

Hiermee wordt de PDF opgeslagen met de afbeelding en tekst in de gewenste opmaak.

## Conclusie

Tekst rond afbeeldingen in een PDF plaatsen lijkt misschien een lastige klus, maar Aspose.PDF voor .NET vereenvoudigt het proces. Door tabellen, afbeeldingen en opgemaakte tekst te gebruiken, kunt u met minimale inspanning professioneel ogende PDF's maken. Met slechts een paar regels code kunt u inhoud precies op de gewenste plek plaatsen, waardoor uw documenten een gepolijste en goed georganiseerde uitstraling krijgen.

## Veelgestelde vragen

### Kan ik deze methode gebruiken om meerdere afbeeldingen met tekst te plaatsen?
Ja, u kunt eenvoudig meer rijen en cellen aan uw tabel toevoegen om extra afbeeldingen en tekst toe te voegen.

### Kan ik de uitlijning van de afbeelding wijzigen?
Absoluut! U kunt de uitlijning van de afbeelding wijzigen door de uitlijningseigenschappen van de cel aan te passen.

### Hoe kan ik de tekst verder vormgeven?
 U kunt HTML-tags gebruiken binnen de`HtmlFragment` object om verschillende stijlen toe te passen, zoals vet, cursief of verschillende lettertypen.

### Kan ik de afstand tussen de tekst en de afbeelding bepalen?
 Ja, met behulp van de`MarginInfo` Met object kunt u de opvulling en marges tussen elementen bepalen.

### Is het mogelijk om links aan de tekst toe te voegen?
 Zeker! U kunt hyperlinks in de HTML-geformatteerde tekst insluiten met behulp van de`<a>` label.