---
title: HTML-tags in tabel in PDF-bestand
linktitle: HTML-tags in tabel in PDF-bestand
second_title: Aspose.PDF voor .NET API-referentie
description: Leer hoe u HTML-tags in tabelcellen in een PDF kunt insluiten met Aspose.PDF voor .NET met deze stapsgewijze handleiding. Maak dynamische, professionele PDF-documenten.
type: docs
weight: 100
url: /nl/net/programming-with-tables/html-tags-inside-table/
---
## Invoering

Bij het werken met PDF's in .NET is de Aspose.PDF-bibliotheek een uitzonderlijke tool voor het maken, bewerken en transformeren van PDF-documenten. Een van de geavanceerde functies die Aspose.PDF biedt, is de mogelijkheid om HTML-inhoud in tabelcellen in een PDF-bestand op te nemen. Deze tutorial leidt u door hoe u dit kunt bereiken met Aspose.PDF voor .NET. Aan het einde van deze handleiding kunt u dynamisch tabellen genereren met HTML-inhoud die in de cellen is ingesloten.

## Vereisten

Voordat u de stapsgewijze handleiding doorneemt, controleren we eerst of u over de benodigde hulpmiddelen en bronnen beschikt.

-  Aspose.PDF voor .NET: U hebt de nieuwste versie van Aspose.PDF nodig.[Download het hier](https://releases.aspose.com/pdf/net/).
- .NET-omgeving: zorg ervoor dat u Visual Studio of een andere compatibele IDE hebt ingesteld met het .NET Framework.
-  Licentie: Als u geen gelicentieerde versie van Aspose.PDF gebruikt, kunt u een[tijdelijke licentie](https://purchase.aspose.com/temporary-license/).
- Basiskennis van C#: Kennis van C# en objectgeoriënteerd programmeren is nuttig.
- Kennis van HTML: Voor deze tutorial is enige kennis van de HTML-structuur nuttig.

## Noodzakelijke pakketten importeren

Voordat we beginnen met het schrijven van de code, is het cruciaal om de benodigde naamruimten te importeren. Deze naamruimten stellen ons in staat om te werken met de Aspose.PDF-klassen en -methoden die we zullen gebruiken om PDF-documenten te manipuleren.

```csharp
using System;
using System.Data;
```

Laten we de taak nu opsplitsen in gedetailleerde stappen, waarbij we elk onderdeel van het proces duidelijk en beknopt uitleggen.

## Stap 1: Stel uw documentenmap in

De eerste stap is het definiëren van het pad naar uw documentenmap. Dit is waar de PDF wordt opgeslagen nadat we deze hebben gemaakt en bewerkt.

```csharp
// Definieer het pad naar de documentenmap.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Zorg ervoor dat u vervangt`"YOUR DOCUMENT DIRECTORY"`met het daadwerkelijke pad waar u uw PDF-bestand wilt opslaan. Dit is essentieel zodat u het document gemakkelijk kunt vinden wanneer het wordt gegenereerd.

## Stap 2: DataTable maken en vullen met HTML-inhoud

 Nu maken we een`DataTable` om de gegevens vast te houden die in de tabel in onze PDF worden weergegeven. Dit`DataTable` zal de HTML-inhoud opslaan, zoals`<li>` tags, die we in de cellen willen insluiten.

```csharp
// Maak een DataTable en voeg kolommen toe
DataTable dt = new DataTable("Employee");
dt.Columns.Add("data", System.Type.GetType("System.String"));
```

 Zodra de`DataTable` is gemaakt, moet u deze vullen met de HTML-inhoud die u in de tabel wilt weergeven. In dit geval voegen we HTML-lijstitems met adressen toe.

```csharp
// Rijen met HTML-inhoud toevoegen
DataRow dr = dt.NewRow();
dr[0] = "<li>Department of Emergency Medicine: 3400 Spruce Street Ground Silverstein Bldg Philadelphia PA 19104-4206</li>";
dt.Rows.Add(dr);
dr = dt.NewRow();
dr[0] = "<li>Penn Observation Medicine Service: 3400 Spruce Street Ground Floor Donner Philadelphia PA 19104-4206</li>";
dt.Rows.Add(dr);
dr = dt.NewRow();
dr[0] = "<li>UPHS/Presbyterian - Dept. of Emergency Medicine: 51 N. 39th Street . Philadelphia PA 19104-2640</li>";
dt.Rows.Add(dr);
```

Met deze stap wordt ervoor gezorgd dat de tabelcellen HTML-geformatteerde inhoud bevatten, die correct wordt weergegeven in het PDF-document.

## Stap 3: Maak een nieuw PDF-document

Zodra we onze data hebben, is de volgende stap het initialiseren van een nieuw PDF-document. Dit document zal dienen als canvas waar we onze tabel aan toevoegen.

```csharp
// Een nieuw PDF-document initialiseren
Document doc = new Document();
doc.Pages.Add();
```

Met dit eenvoudige codefragment wordt een leeg PDF-document gemaakt en wordt er een nieuwe pagina aan toegevoegd. Deze pagina zal later de tabel bevatten.

## Stap 4: De tafel opzetten

Nu gaan we de tabel in het PDF-document maken en instellen. Deze tabel definieert de kolombreedtes en randinstellingen.

```csharp
// Initialiseer een nieuw exemplaar van de tabel
Aspose.Pdf.Table tableProvider = new Aspose.Pdf.Table();
// Kolombreedtes van de tabel instellen
tableProvider.ColumnWidths = "400 50";
// Stel de kleur van de tabelrand in op Lichtgrijs
tableProvider.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.5F, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
// De rand voor afzonderlijke tabelcellen instellen
tableProvider.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.5F, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
```

In deze stap hebt u succesvol een tabel gemaakt en aangepaste kolombreedtes en randen ingesteld voor zowel de tabel als de cellen. De kolombreedtes zorgen voor een correcte uitlijning van gegevens in de tabel.

## Stap 5: Definieer opvulling en importeer gegevens

 Om de visuele esthetiek van de tabel te verbeteren, definiëren we padding voor de cellen. Vervolgens importeren we de`DataTable` met HTML-inhoud in de PDF-tabel.

```csharp
// Opvulling voor tabelcellen instellen
Aspose.Pdf.MarginInfo margin = new Aspose.Pdf.MarginInfo();
margin.Top = 2.5F;
margin.Left = 2.5F;
margin.Bottom = 1.0F;
tableProvider.DefaultCellPadding = margin;

// Importeer de DataTable in de PDF-tabel
tableProvider.ImportDataTable(dt, false, 0, 0, 3, 1, true);
```

Door marges in te stellen, geven we de tabelcellen wat ademruimte, waardoor de inhoud visueel aantrekkelijker wordt.`ImportDataTable` methode trekt de`DataTable` die we eerder hebben gemaakt, om ervoor te zorgen dat de HTML-inhoud in de cellen wordt ingesloten.

## Stap 6: Voeg de tabel toe aan de PDF en sla deze op

Tot slot voegen we de tabel toe aan de eerste pagina van het PDF-document en slaan het bestand op.

```csharp
// Voeg de tabel toe aan de eerste pagina van het PDF-document
doc.Pages[1].Paragraphs.Add(tableProvider);

// Sla het PDF-document op
doc.Save(dataDir + "HTMLInsideTableCell_out.pdf");
```

In deze stap wordt de tabel met HTML-inhoud op de eerste pagina van de PDF geplaatst en wordt het bestand opgeslagen in de opgegeven map.

## Conclusie

Door de bovenstaande stappen te volgen, hebt u HTML-tags succesvol ingesloten in tabelcellen in een PDF-document met Aspose.PDF voor .NET. Deze tutorial laat zien hoe u kunt profiteren van de krachtige functies van Aspose.PDF om dynamische en visueel aantrekkelijke PDF-documenten te maken in uw .NET-toepassingen. Of u nu facturen, rapporten of gedetailleerde tabellen met HTML-inhoud genereert, deze methode biedt een solide basis voor uw PDF-manipulatiebehoeften.

## Veelgestelde vragen

### Kan Aspose.PDF complexe HTML-inhoud in tabelcellen verwerken?  
Ja, Aspose.PDF kan een breed scala aan HTML-tags in tabelcellen verwerken en weergeven, waaronder lijsten, afbeeldingen en links.

### Hoe kan ik de grootte van de kolommen in de tabel aanpassen?  
 U kunt de breedte van kolommen regelen met behulp van de`ColumnWidths` eigenschap door de breedte voor elke kolom op te geven.

### Is het mogelijk om de tekst in tabelcellen op te maken?  
 Absoluut! Je kunt HTML-tags gebruiken zoals`<b>`, `<i>` , En`<u>` binnen de inhoud om de tekst in de tabelcellen op te maken.

### Wat gebeurt er als mijn HTML-inhoud te groot is voor de tabelcel?  
Als de inhoud groter is dan de cel, wordt de tabel automatisch aangepast. U kunt echter de celgrootte en de opties voor tekstomloop aanpassen om te bepalen hoe de inhoud wordt weergegeven.

### Kan ik meer dan één tabel aan een PDF-document toevoegen?  
Ja, u kunt meerdere tabellen aan een PDF-document toevoegen door de stappen voor het toevoegen van tabellen te herhalen, elke tabel op een nieuwe pagina of sectie van de PDF.