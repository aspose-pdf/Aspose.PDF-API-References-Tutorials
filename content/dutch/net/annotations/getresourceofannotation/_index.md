---
title: Krijg bron van annotatie
linktitle: Krijg bron van annotatie
second_title: Aspose.PDF voor .NET API-referentie
description: Leer met deze stapsgewijze handleiding hoe u de bron van een annotatie kunt ophalen met Aspose.PDF voor .NET.
type: docs
weight: 90
url: /nl/net/annotations/getresourceofannotation/
---
Het voorbeeld laat zien hoe u annotatiebronnen kunt verkrijgen met Aspose.PDF voor .NET. Volg deze stappen om de bron van een annotatie op te halen met Aspose.PDF voor .NET:

## Stap 1: Stel het pad in van de map waarin het document zich bevindt.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Stap 2: Open het PDF-document dat de annotatie bevat waarvan u de bron wilt ophalen.

```csharp
Document doc = new Document(dataDir + "AddAnnotation.pdf");
```

## Stap 3: Maak een annotatie.

```csharp
ScreenAnnotation sa = new ScreenAnnotation(doc.Pages[1], new Rectangle(100, 400, 300, 600), dataDir + "AddSwfFileAsAnnotation.swf");
```

## Stap 4: Voeg de annotatie toe aan een pagina in het document.

```csharp
doc.Pages[1].Annotations.Add(sa);
```

## Stap 5: Sla het document op.

```csharp
doc.Save(dataDir + "GetResourceOfAnnotation_Out.pdf");
```

## Stap 6: Open het gewijzigde document.

```csharp
Document doc1 = new Document(dataDir + "GetResourceOfAnnotation_Out.pdf");
```

## Stap 7: Haal de actie van de annotatie op.

```csharp
RenditionAction action = (doc.Pages[1].Annotations[1] as ScreenAnnotation).Action as RenditionAction;
```

## Stap 7: Haal de weergave van de actie op.

```csharp
Rendition rendition = ((doc.Pages[1].Annotations[1] as ScreenAnnotation).Action as RenditionAction).Rendition;
```

## Stap 8: Haal de mediaclip op.

```csharp
MediaClip clip = (rendition as MediaRendition).MediaClip;
```

## Stap 9: Haal de bestandsspecificatie op.

```csharp
FileSpecification data = (clip as MediaClipData).Data;
```

## Stap 10: Lees de gegevens van de media.

```csharp
MemoryStream ms = new MemoryStream();
byte[] buffer = new byte[1024];
int read = 0;
Stream source = data.Contents;
while ((read = source.Read(buffer, 0, buffer.Length)) > 0)
{
   ms.Write(buffer, 0, read);
}
```

## Stap 11: Druk de naam van de vertoning en de vertoningsbewerking af.

```csharp
Console.WriteLine(rendition.Name);
Console.WriteLine(action.RenditionOperation);
```

Door deze stappen te volgen, kunt u eenvoudig de bron van een annotatie in een PDF-document verkrijgen met behulp van Aspose.PDF voor .NET.

### Voorbeeldbroncode voor Get Resource Of Annotation met Aspose.PDF voor .NET:

```csharp
// Het pad naar de documentenmap.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Document openen
Document doc = new Document(dataDir + "AddAnnotation.pdf");
//Annotatie maken
ScreenAnnotation sa = new ScreenAnnotation(doc.Pages[1], new Rectangle(100, 400, 300, 600), dataDir + "AddSwfFileAsAnnotation.swf");
doc.Pages[1].Annotations.Add(sa);
// Document opslaan
doc.Save(dataDir + "GetResourceOfAnnotation_Out.pdf");
// Document openen
Document doc1 = new Document(dataDir + "GetResourceOfAnnotation_Out.pdf");
//Actie van de annotatie ophalen
RenditionAction action = (doc.Pages[1].Annotations[1] as ScreenAnnotation).Action as RenditionAction;
//Haal de weergave van de weergaveactie op
Rendition rendition = ((doc.Pages[1].Annotations[1] as ScreenAnnotation).Action as RenditionAction).Rendition;
// Mediaclip
MediaClip clip = (rendition as MediaRendition).MediaClip;
FileSpecification data = (clip as MediaClipData).Data;
MemoryStream ms = new MemoryStream();
byte[] buffer = new byte[1024];
int read = 0;
//Gegevens van media zijn toegankelijk in FileSpecification.Contents
Stream source = data.Contents;
while ((read = source.Read(buffer, 0, buffer.Length)) > 0)
{
ms.Write(buffer, 0, read);
}
Console.WriteLine(rendition.Name);
Console.WriteLine(action.RenditionOperation);
```

## Conclusie

In deze zelfstudie hebben we onderzocht hoe u de bron van een bepaalde annotatie uit een PDF-document kunt halen met behulp van Aspose.PDF voor .NET. Door de stapsgewijze handleiding te volgen en de meegeleverde C#-broncode te gebruiken, kunnen ontwikkelaars eenvoudig annotaties, inclusief weergaveannotaties, in hun PDF-documenten openen en beheren.

### Veelgestelde vragen

#### Vraag: Wat is een weergave in de context van PDF-annotaties?

A: In de context van PDF-annotaties is een weergave een presentatie van multimedia-inhoud. Hiermee kunt u multimedia, zoals audio of video, in het PDF-document insluiten. De weergaveannotatie specificeert de media die moeten worden gepresenteerd en hoe deze moeten worden afgespeeld.

#### Vraag: Kan ik de naam krijgen van het mediabestand dat aan een weergaveannotatie is gekoppeld?

A: Ja, u kunt de naam opvragen van het mediabestand dat aan een weergaveannotatie is gekoppeld met behulp van Aspose.PDF voor .NET. De naam van het mediabestand is toegankelijk via de`FileSpecification` van de`MediaClip` voorwerp.

#### Vraag: Kan Aspose.PDF voor .NET mediabestanden extraheren uit een weergaveannotatie?

A: Ja, Aspose.PDF voor .NET kan de mediagegevens extraheren uit een weergaveannotatie, die audio- of video-inhoud bevat, en deze opslaan als een afzonderlijk bestand.

#### Vraag: Hoe krijg ik toegang tot de mediagegevens van een weergaveannotatie?

 A: De mediagegevens van een weergaveannotatie zijn toegankelijk via de`FileSpecification.Contents` eigendom van de`MediaClipData` voorwerp.

#### Vraag: Kan ik de media die aan een weergaveannotatie zijn gekoppeld, wijzigen met Aspose.PDF voor .NET?

A: Aspose.PDF voor .NET biedt methoden voor het openen en wijzigen van de mediagegevens die aan een weergaveannotatie zijn gekoppeld. U kunt het mediabestand dat door een weergaveannotatie wordt gebruikt, bijwerken of vervangen.