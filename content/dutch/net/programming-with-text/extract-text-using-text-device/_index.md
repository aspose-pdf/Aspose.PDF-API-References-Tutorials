---
title: Tekst extraheren met behulp van een tekstapparaat
linktitle: Tekst extraheren met behulp van een tekstapparaat
second_title: Aspose.PDF voor .NET API-referentie
description: Leer hoe u tekst uit een PDF-document kunt extraheren met behulp van het tekstapparaat in Aspose.PDF voor .NET.
type: docs
weight: 210
url: /nl/net/programming-with-text/extract-text-using-text-device/
---
## Invoering

Tekst uit een PDF extraheren kan lastig zijn, vooral als u te maken hebt met documenten met verschillende formaten, ingesloten lettertypen of complexe lay-outs. Maar met Aspose.PDF voor .NET wordt dit proces een fluitje van een cent! Of u nu pagina's van een PDF wilt converteren naar platte tekst voor verdere analyse of gewoon specifieke secties wilt extraheren, Aspose.PDF heeft het voor u. In deze tutorial leggen we stap voor stap uit hoe u tekst uit een PDF kunt extraheren met behulp van de TextDevice-klasse in Aspose.PDF. We geven ook duidelijke uitleg, zodat u dezelfde methoden eenvoudig op uw eigen projecten kunt toepassen.

## Vereisten

Voordat we in de code duiken, zorg ervoor dat je alles op zijn plaats hebt om te volgen. Dit is wat je nodig hebt:

1.  Aspose.PDF voor .NET: Download de nieuwste versie van de[Aspose.PDF voor .NET downloadpagina](https://releases.aspose.com/pdf/net/).
2. Ontwikkelomgeving: Visual Studio of een andere C#-ontwikkelomgeving.
3. .NET Framework: Zorg ervoor dat uw project gericht is op .NET Framework 4.x of hoger.
4. Input PDF-bestand: Een PDF-bestand dat u gebruikt voor tekstextractie. Plaats dit in een directory op uw machine (we noemen dit`YOUR DOCUMENT DIRECTORY`).

## Pakketten importeren

Bovenaan uw code moet u de benodigde naamruimten importeren om met Aspose.PDF te kunnen werken:

```csharp
using System.IO;
using Aspose.Pdf;
using Aspose.Pdf.Text;
using Aspose.Pdf.Devices;
using System;
using System.Text;
```

## Stap 1: Laad uw PDF-document

 Voordat we tekst extraheren, moeten we het PDF-document in het geheugen laden. In deze stap opent u uw PDF met Aspose.PDF's`Document` klasse. Hiermee krijgt u toegang tot alle pagina's en inhoud in het bestand.

```csharp
// Definieer het pad naar uw PDF-document
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Laad het PDF-document
Document pdfDocument = new Document(dataDir + "input.pdf");
```

 Hier gebruiken we`Document pdfDocument = new Document(dataDir + "input.pdf");` om de PDF te laden. De`dataDir` variabele bevat het directorypad van uw PDF-bestand. Dit geeft ons toegang tot het hele document, waardoor we door pagina's kunnen loopen en inhoud kunnen extraheren.

## Stap 2: Stel een stringbuilder in voor tekstopslag

 Nu het document is geladen, hebben we een manier nodig om de geëxtraheerde tekst op te slaan. Hiervoor gebruiken we een`StringBuilder` wat efficiënte string-aaneenschakeling mogelijk maakt.

```csharp
// StringBuilder om de geëxtraheerde tekst vast te houden
StringBuilder builder = new StringBuilder();
```

 We initialiseren een`StringBuilder`instance, die tekst verzamelt die van elke pagina is geëxtraheerd. Het is een efficiëntere manier om grote strings te verwerken in vergelijking met normale string-aaneenschakeling in een lus.

## Stap 3: Door PDF-pagina's bladeren

 Vervolgens doorlopen we elke pagina van het PDF-document om de tekst te extraheren. We verwerken elke pagina afzonderlijk met behulp van de`TextDevice` klasse, die verantwoordelijk is voor het converteren van de PDF-inhoud naar tekstformaat.

```csharp
// Doorloop alle pagina's in de PDF
foreach (Page pdfPage in pdfDocument.Pages)
{
    // Verwerk elke pagina voor tekst extractie
}
```

Deze lus gaat door elke pagina van de PDF (`pdfDocument.Pages` ). Voor elke pagina halen we de tekst eruit en voegen deze toe aan onze`StringBuilder`.

## Stap 4: Tekst uit elke pagina extraheren

 Nu stellen we het tekstextractieproces voor elke pagina in. Hier maken we een`TextDevice` object en gebruik het om de PDF-pagina's te verwerken. De`TextDevice` extraheert ruwe of opgemaakte tekst op basis van de extractieopties die wij instellen.

```csharp
using (MemoryStream textStream = new MemoryStream())
{
    // Maak een tekstapparaat voor tekstextractie
    TextDevice textDevice = new TextDevice();
    
    // Stel de tekstextractieopties in op de modus 'Puur'
    TextExtractionOptions textExtOptions = new TextExtractionOptions(TextExtractionOptions.TextFormattingMode.Pure);
    textDevice.ExtractionOptions = textExtOptions;

    //Tekst uit de huidige pagina halen en opslaan in de geheugenstroom
    textDevice.Process(pdfPage, textStream);

    // Converteer geheugenstroom naar tekst
    string extractedText = Encoding.Unicode.GetString(textStream.ToArray());

    // Voeg de geëxtraheerde tekst toe aan de StringBuilder
    builder.Append(extractedText);
}
```

- `TextDevice textDevice = new TextDevice();` : De`TextDevice` klasse wordt gebruikt om tekst uit de PDF te extraheren.
- `TextExtractionOptions textExtOptions = new TextExtractionOptions(TextExtractionOptions.TextFormattingMode.Pure);` : Deze optie extraheert de ruwe tekst zonder opmaak zoals lettertypen of posities te behouden. U kunt ook`TextFormattingMode.Raw` als u meer controle over de opmaak nodig hebt.
- `textDevice.Process(pdfPage, textStream);` : Dit verwerkt elke pagina van de PDF en slaat de geëxtraheerde tekst op in een`MemoryStream`.
-  Ten slotte zetten we de tekst om van de`MemoryStream` aan een string toevoegen en deze aan de`StringBuilder`.

## Stap 5: Geëxtraheerde tekst opslaan in een bestand

 Nadat alle pagina's zijn verwerkt, wordt de tekst opgeslagen in de`StringBuilder`De laatste stap is om de geëxtraheerde tekst in een bestand op te slaan.

```csharp
// Definieer het uitvoerpad voor het tekstbestand
dataDir = dataDir + "input_Text_Extracted_out.txt";

// Sla de geëxtraheerde tekst op in een bestand
File.WriteAllText(dataDir, builder.ToString());

Console.WriteLine("\nText extracted successfully from PDF document.\nFile saved at " + dataDir);
```

- `File.WriteAllText(dataDir, builder.ToString());` :Hiermee wordt de volledige inhoud van de`StringBuilder` in een tekstbestand.
- Het pad voor het uitvoerbestand wordt ingesteld door een bestandsnaam toe te voegen (`"input_Text_Extracted_out.txt"` ) naar de`dataDir` pad.

## Conclusie

Het extraheren van tekst uit een PDF met Aspose.PDF voor .NET is een eenvoudig en efficiënt proces. Door de stappen in deze handleiding te volgen, kunt u eenvoudig PDF-documenten openen, door pagina's bladeren en tekst extraheren naar een tekstbestand. Dit is vooral handig voor het verwerken van grote hoeveelheden PDF-gegevens, het uitvoeren van tekstanalyses of het converteren van documenten voor verdere manipulatie.

Met Aspose.PDF bent u niet beperkt tot tekstextractie: u kunt annotaties verwerken, afbeeldingen bewerken of zelfs PDF's converteren naar andere formaten zoals HTML of Word. De flexibiliteit en kracht van deze bibliotheek maken het een onschatbare tool voor PDF-beheer in .NET-applicaties.

## Veelgestelde vragen

### Kan Aspose.PDF tekst uit op afbeeldingen gebaseerde PDF's halen?
Nee, Aspose.PDF is ontworpen om tekst uit content-based PDF's te halen. Voor image-based PDF's is OCR-technologie nodig.

### Behoudt Aspose.PDF de opmaak bij het extraheren van tekst?
Standaard wordt de tekst zonder opmaak geëxtraheerd, maar u kunt de extractieopties aanpassen als u bepaalde opmaak wilt behouden.

### Kan ik tekst uit een specifiek paginabereik halen?
Ja, u kunt de code aanpassen, zodat deze over een specifiek paginabereik loopt in plaats van over alle pagina's.

### Wat zijn de tekstextractiemodi in Aspose.PDF?
Aspose.PDF biedt twee modi: Raw en Pure. De Raw-modus probeert de originele lay-out te behouden, terwijl de Pure-modus alleen de tekst zonder opmaak extraheert.

### Is Aspose.PDF voor .NET compatibel met .NET Core?
Ja, Aspose.PDF voor .NET is volledig compatibel met .NET Core en .NET Framework.