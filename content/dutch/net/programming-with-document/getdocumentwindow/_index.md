---
title: Documentvenster ophalen
linktitle: Documentvenster ophalen
second_title: Aspose.PDF voor .NET API-referentie
description: Leer hoe u de GetDocumentWindow-functie van Aspose.PDF voor .NET kunt gebruiken om informatie over de venstereigenschappen van een PDF-document op te halen.
type: docs
weight: 170
url: /nl/net/programming-with-document/getdocumentwindow/
---
# Invoering

Werkt u met PDF's en wilt u meer controle over hoe ze eruitzien wanneer ze worden geopend? Of het nu gaat om het verbergen van de menubalk of het aanpassen van de grootte van het venster zodat het op de eerste pagina past, Aspose.PDF voor .NET biedt u alle tools die u nodig hebt om aan te passen hoe een PDF zich gedraagt wanneer deze wordt geopend in een viewer. In deze tutorial leggen we uit hoe u documentvensterinstellingen in Aspose.PDF voor .NET kunt ophalen en bewerken.


# Vereisten

Voordat u met de tutorial begint, moet u ervoor zorgen dat u aan de volgende vereisten voldoet:

- Aspose.PDF voor .NET geïnstalleerd in uw ontwikkelomgeving.
  - [Download Aspose.PDF voor .NET](https://releases.aspose.com/pdf/net/)
-  Een geldige licentie voor Aspose.PDF, of u kunt een[gratis proefperiode](https://releases.aspose.com/) of[tijdelijke licentie](https://purchase.aspose.com/temporary-license/).
- Basiskennis van .NET en C#.
- Visual Studio of een andere geschikte IDE.

# Pakketten importeren

Voordat u begint met het schrijven van code, moet u de benodigde pakketten importeren. Open uw project en voeg bovenaan uw C#-bestand de volgende naamruimte toe:

```csharp
using System.IO;
using System;
using Aspose.Pdf;
```

Hiermee krijgt u toegang tot alle klassen en methoden die nodig zijn voor het bewerken van PDF-documenten met Aspose.PDF voor .NET.

 Laten we nu het proces van het ophalen van verschillende documentvensterinstellingen opsplitsen. Voor dit voorbeeld gebruiken we een voorbeeld-PDF-bestand met de naam`GetDocumentWindow.pdf`.

## Stap 1: Stel het pad naar de documentdirectory in

Allereerst moeten we het pad naar ons PDF-bestand definiëren. Het is cruciaal dat u het juiste bestandspad hebt om fouten tijdens de uitvoering te voorkomen.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Hier, vervang`"YOUR DOCUMENT DIRECTORY"` met de werkelijke directory waar uw PDF-bestand zich bevindt. Dit is uw werkdirectory van waaruit u het PDF-document laadt.

## Stap 2: Open het PDF-document

Nu het bestandspad is ingesteld, is de volgende stap het openen van het PDF-document met Aspose.PDF. Dit laadt het document in het geheugen, zodat u de eigenschappen ervan kunt ophalen.

```csharp
Document pdfDocument = new Document(dataDir + "GetDocumentWindow.pdf");
```

Met deze eenvoudige coderegel hebt u uw PDF-bestand succesvol in de`pdfDocument` object, waardoor u nu toegang hebt tot alle eigenschappen ervan.

## Stap 3: Venstercentreringsstatus ophalen

 Laten we vervolgens controleren of het documentvenster gecentreerd moet worden wanneer het wordt geopend. De standaardwaarde hiervoor is`false`.

```csharp
Console.WriteLine("CenterWindow : {0}", pdfDocument.CenterWindow);
```

 Als de uitvoer is`true`, wordt het venster van het document geopend in het midden van het scherm. Anders wordt het geopend op de standaardpositie.

## Stap 4: Controleer de tekstrichting

Een ander cruciaal aspect van het uiterlijk van een PDF is de tekstrichting, die bepaalt of de tekst van links naar rechts (L2R) of van rechts naar links (R2L) wordt gelezen. U kunt deze informatie ophalen met behulp van de volgende code:

```csharp
Console.WriteLine("Direction : {0}", pdfDocument.Direction);
```

 De uitvoer zal zijn`L2R` voor tekst van links naar rechts en`R2L` voor tekst van rechts naar links. Deze instelling is vooral handig voor documenten in talen zoals Arabisch of Hebreeuws.

## Stap 5: Documenttitel weergeven in venster

Met de volgende eigenschap kunt u bepalen of de documenttitel of de bestandsnaam op de titelbalk van het venster moet worden weergegeven. Standaard is dit ingesteld op`false`, wat betekent dat de bestandsnaam wordt weergegeven.

```csharp
Console.WriteLine("DisplayDocTitle : {0}", pdfDocument.DisplayDocTitle);
```

Als u wilt dat de titel van het document wordt weergegeven in plaats van de bestandsnaam, moet u deze instelling inschakelen.

## Stap 6: Vensterformaat aanpassen zodat het op de eerste pagina past

Soms wilt u dat het documentvenster zichzelf automatisch aanpast aan de eerste pagina van de PDF wanneer deze wordt geopend. Hier leest u hoe u kunt controleren of deze functie is ingeschakeld:

```csharp
Console.WriteLine("FitWindow : {0}", pdfDocument.FitWindow);
```

 Standaard is dit ingesteld op`false`, wat betekent dat de venstergrootte hetzelfde blijft, ongeacht de grootte van de eerste pagina.

## Stap 7: Verberg de menubalk

Voor een meer gerichte leeservaring wilt u mogelijk de menubalk van de viewer-applicatie verbergen. U kunt deze instelling ophalen met de volgende regel:

```csharp
Console.WriteLine("HideMenuBar : {0}", pdfDocument.HideMenubar);
```

 Dit zal terugkeren`true` als de menubalk verborgen is, en`false` anders.

## Stap 8: Verberg de werkbalk

Op dezelfde manier wilt u misschien ook de werkbalk in de PDF-viewer verbergen voor een schonere gebruikersinterface. Deze instelling kan als volgt worden opgehaald:

```csharp
Console.WriteLine("HideToolBar : {0}", pdfDocument.HideToolBar);
```

Als deze instelling is ingeschakeld, wordt de werkbalk verborgen wanneer het PDF-bestand wordt geopend.

## Stap 9: Verberg de schuifbalken en UI-elementen

Als u alleen de pagina-inhoud wilt weergeven zonder extra gebruikersinterface-elementen zoals schuifbalken, kunt u dat gedrag met deze instelling bepalen:

```csharp
Console.WriteLine("HideWindowUI : {0}", pdfDocument.HideWindowUI);
```

 Wanneer ingesteld op`true`, verbergt de PDF-viewer schuifbalken en andere elementen van de gebruikersinterface, zodat alleen de inhoud van het document overblijft.

## Stap 10: Stel de modus voor pagina's in die niet op volledig scherm wordt weergegeven

 U kunt bepalen hoe het document eruitziet wanneer u de modus Volledig scherm verlaat met behulp van`NonFullScreenPageMode` eigenschap. Deze instelling is handig om te definiëren hoe de gebruiker met het document moet omgaan in de niet-volledige schermmodus.

```csharp
Console.WriteLine("NonFullScreenPageMode : {0}", pdfDocument.NonFullScreenPageMode);
```

De uitvoer kan worden ingesteld op verschillende modi, zoals miniaturen, contouren of bijlagenpaneel.

## Stap 11: Definieer de pagina-indeling

Met deze instelling kunt u bepalen hoe de documentpagina's worden ingedeeld. U kunt bijvoorbeeld kiezen voor een enkele paginaweergave of een doorlopende kolomweergave:

```csharp
Console.WriteLine("PageLayout : {0}", pdfDocument.PageLayout);
```

Hierdoor hebben gebruikers meer flexibiliteit in de manier waarop ze de inhoud van het document lezen of bekijken.

## Stap 12: Geef de paginamodus op

 Ten slotte is de`PageMode` eigenschap definieert hoe het document moet worden weergegeven wanneer het wordt geopend. Opties omvatten het weergeven van miniaturen, het openen van de modus voor volledig scherm of het weergeven van het bijlagenpaneel.

```csharp
Console.WriteLine("PageMode : {0}", pdfDocument.PageMode);
```

U kunt deze modus naar wens instellen op de modus die het beste past bij het doel van uw PDF.

## Conclusie

Zoals u kunt zien, biedt Aspose.PDF voor .NET uitgebreide tools om te manipuleren hoe uw PDF-documenten worden weergegeven in verschillende PDF-viewers. Of u nu de werkbalk wilt verbergen, het venster wilt centreren of de tekstrichting wilt regelen, Aspose.PDF biedt de flexibiliteit om de kijkervaring van de gebruiker te verbeteren.

# Veelgestelde vragen

### Kan ik het initiële zoomniveau van de PDF aanpassen?
Ja, met Aspose.PDF kunt u het zoomniveau instellen wanneer het document is geopend.

### Hoe kan ik de venstergrootte van een PDF vergrendelen?
 U kunt de`FitWindow` eigenschap om te voorkomen dat het venster van formaat verandert.

### Ondersteunt Aspose.PDF verschillende leesmodi?
Ja, het ondersteunt verschillende modi, zoals volledig scherm, miniaturen en bijlagen.

### Is het mogelijk om schuifbalken in de PDF-viewer te verbergen?
 Absoluut, u kunt schuifbalken verbergen door de`HideWindowUI` eigendom van`true`.

### Kan ik het documentvenster centreren wanneer het geopend is?
 Ja, u kunt dit regelen door de`CenterWindow` eigendom.