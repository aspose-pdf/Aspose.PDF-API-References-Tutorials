---
title: Stel de standaardlettertypenaam in
linktitle: Stel de standaardlettertypenaam in
second_title: Aspose.PDF voor .NET API-referentie
description: Stapsgewijze handleiding voor het instellen van de standaardlettertypenaam in een PDF-bestand met Aspose.PDF voor .NET.
type: docs
weight: 270
url: /nl/net/document-conversion/set-default-font-name/
---
In deze zelfstudie laten we u zien hoe u de standaardlettertypenaam in een PDF-bestand instelt met Aspose.PDF voor .NET. Wanneer u afbeeldingen uit een PDF-bestand extraheert, kunt u soms problemen met ontbrekende lettertypen tegenkomen. Door een standaardlettertypenaam op te geven, kunt u ervoor zorgen dat de geëxtraheerde tekst correct wordt weergegeven. Volg de onderstaande stappen om de standaardlettertypenaam in een PDF-bestand in te stellen.

## Vereisten
Zorg ervoor dat u aan de volgende vereisten voldoet voordat u begint:

- Basiskennis van de programmeertaal C#.
- Aspose.PDF-bibliotheek voor .NET geïnstalleerd op uw systeem.
- Een ontwikkelomgeving zoals Visual Studio.

## Stap 1: Het PDF-document laden
 De eerste stap is het laden van het PDF-document in een`Document` voorwerp. Gebruik de volgende code:

```csharp
// Pad naar de documentenmap.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

using (Document pdfDocument = new Document(dataDir + "input.pdf"))
{
     // Code om toe te voegen
}
```

 Zeker vervangen`"YOUR DOCUMENTS DIRECTORY"` met de daadwerkelijke map waar uw PDF-bestand zich bevindt.

## Stap 2: Stel de standaardlettertypenaam in
 Vervolgens stellen we de standaardlettertypenaam in met behulp van de`DefaultFontName` optie van de`RenderingOptions` voorwerp. Gebruik de volgende code:

```csharp
using (Document pdfDocument = new Document(dataDir + "input.pdf"))
{
     using (FileStream imageStream = new FileStream(dataDir + "SetDefaultFontName.png", FileMode.Create))
     {
         Resolution resolution = new Resolution(300);
         PngDevice pngDevice = new PngDevice(resolution);
         RenderingOptions ro = new RenderingOptions();
         ro.DefaultFontName = "Arial";
         pngDevice.RenderingOptions = ro;
        
         // Code om toe te voegen
     }
}
```

 Zeker vervangen`"Arial"` met de gewenste lettertypenaam.

## Stap 3: Afbeeldingsextractie
Vervolgens extraheren we de afbeelding van de opgegeven pagina van het PDF-document. Gebruik de volgende code:

```csharp
pngDevice.Process(pdfDocument.Pages[1], imageStream);
```

 Zorg ervoor dat u het juiste paginanummer opgeeft`pdfDocument.Pages[1]`.

### Voorbeeldbroncode voor het instellen van de standaardlettertypenaam met Aspose.PDF voor .NET

```csharp
// Het pad naar de documentenmap.
string dataDir = "YOUR DOCUMENT DIRECTORY";

using (Document pdfDocument = new Document(dataDir + "input.pdf"))
{
	using (FileStream imageStream = new FileStream(dataDir + "SetDefaultFontName.png", FileMode.Create))
	{
		Resolution resolution = new Resolution(300);
		PngDevice pngDevice = new PngDevice(resolution);
		RenderingOptions ro = new RenderingOptions();
		ro.DefaultFontName = "Arial";
		pngDevice.RenderingOptions = ro;
		pngDevice.Process(pdfDocument.Pages[1], imageStream);
	}
}
```

## Conclusie
In deze zelfstudie hebben we geleerd hoe u de standaardlettertypenaam in een PDF-bestand kunt instellen met Aspose.PDF voor .NET. Door een standaardlettertypenaam op te geven, kunt u ervoor zorgen dat de geëxtraheerde tekst correct wordt weergegeven. Gebruik deze methode om problemen met ontbrekende lettertypen op te lossen bij het extraheren van afbeeldingen uit PDF-bestanden.

### Veelgestelde vragen

#### Vraag: Wat is Aspose.PDF voor .NET?

A: Aspose.PDF voor .NET is een krachtige bibliotheek waarmee ontwikkelaars met PDF-documenten in C#-toepassingen kunnen werken. Het biedt verschillende functionaliteiten, waaronder het instellen van de standaardlettertypenaam in een PDF-bestand.

#### Vraag: Waarom moet ik de standaardlettertypenaam instellen in een PDF-bestand?

A: Het instellen van de standaardlettertypenaam is handig bij het extraheren van tekst uit een PDF-document. Als de PDF tekst bevat met lettertypen die niet beschikbaar zijn op de extractiemachine, zorgt het opgeven van een standaardlettertypenaam ervoor dat de tekst correct wordt weergegeven.

#### Vraag: Hoe kan ik een PDF-document laden en de standaardlettertypenaam instellen met Aspose.PDF voor .NET?

 A: Om een PDF-document te laden en de standaardlettertypenaam in te stellen, kunt u de`Document`class om het PDF-bestand te laden en de`RenderingOptions.DefaultFontName` eigenschap om de gewenste standaardlettertypenaam op te geven.

#### Vraag: Kan ik elk lettertype als standaardlettertypenaam kiezen?

A:Ja, u kunt elk lettertype dat beschikbaar is op de extractiemachine als standaardlettertypenaam kiezen. Gebruik een lettertype dat nauw aansluit bij de ontbrekende lettertypen in de originele PDF om een nauwkeurige weergave van de tekst te garanderen.

#### Vraag: Is het instellen van de standaardlettertypenaam een permanente wijziging van het PDF-bestand?

A: Nee, het instellen van de standaardlettertypenaam met Aspose.PDF voor .NET is een tijdelijke wijziging die wordt aangebracht tijdens het extraheren van tekst. Het wijzigt het originele PDF-bestand niet.