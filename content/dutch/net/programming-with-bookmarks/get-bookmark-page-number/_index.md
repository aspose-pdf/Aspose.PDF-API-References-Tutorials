---
title: Haal bladwijzerpaginanummer op in PDF-bestand
linktitle: Haal bladwijzerpaginanummer op in PDF-bestand
second_title: Aspose.PDF voor .NET API-referentie
description: Haal eenvoudig het bladwijzerpaginanummer op in een PDF-bestand met Aspose.PDF voor .NET.
type: docs
weight: 60
url: /nl/net/programming-with-bookmarks/get-bookmark-page-number/
---
Het ophalen van paginanummers die zijn gekoppeld aan bladwijzers in een PDF-bestand kan handig zijn voor navigatie. Met Aspose.PDF voor .NET kunt u eenvoudig het paginanummer van bladwijzers opvragen door de volgende broncode te volgen:

## Stap 1: Importeer de vereiste bibliotheken

Voordat u begint, moet u de benodigde bibliotheken voor uw C#-project importeren. Hier is de noodzakelijke importrichtlijn:

```csharp
using Aspose.Pdf.Facades;
```

## Stap 2: Stel het pad naar de documentenmap in

 In deze stap moet u het pad opgeven naar de map met het PDF-bestand waaruit u de bladwijzerpaginanummers wilt extraheren. Vervangen`"YOUR DOCUMENT DIRECTORY"`in de volgende code met het daadwerkelijke pad naar uw documentenmap:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Stap 3: Maak de bladwijzereditor

 Nu gaan we een`PdfBookmarkEditor` object om de bladwijzers van het document te manipuleren. Gebruik de volgende code:

```csharp
PdfBookmarkEditor bookmarkEditor = new PdfBookmarkEditor();
```

## Stap 4: Open het PDF-bestand

 In deze stap openen we het PDF-bestand met behulp van de`BindPdf` methode van de bladwijzereditor. Hier is de bijbehorende code:

```csharp
bookmarkEditor.BindPdf(dataDir + "GetBookmarks.pdf");
```

## Stap 5: Bladwijzers extraheren

 Nu zullen we de bladwijzers uit het document extraheren met behulp van de`ExtractBookmarks` methode van de bladwijzereditor. Hier is de bijbehorende code:

```csharp
Bookmarks bookmarks = bookmarkEditor.ExtractBookmarks();
```

## Stap 6: Blader door bladwijzers en haal paginanummers op

 Ten slotte doorlopen we de geëxtraheerde bladwijzers en verkrijgen we de paginanummers die aan elke bladwijzer zijn gekoppeld met behulp van a`foreach` lus. Hier is de bijbehorende code:

```csharp
foreach (Bookmark bookmark in bookmarks)
{
     string strLevelSeprator = string.Empty;
     for (int i = 1; i < bookmark.Level; i++)
     {
         strLevelSeprator += "----";
     }
     Console.WriteLine("{0}Title: {1}", strLevelSeprator, bookmark.Title);
     Console.WriteLine("{0}Page number: {1}", strLevelSeprator, bookmark.PageNumber);
     Console.WriteLine("{0}Page Action: {1}", strLevelSeprator, bookmark.Action);
}
```

### Voorbeeldbroncode voor Get Bookmark Page Number met Aspose.PDF voor .NET 
```csharp
// Het pad naar de documentenmap.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Maak een PDFBookmarkEditor
PdfBookmarkEditor bookmarkEditor = new PdfBookmarkEditor();
// PDF-bestand openen
bookmarkEditor.BindPdf(dataDir + "GetBookmarks.pdf");
// Bladwijzers extraheren
Aspose.Pdf.Facades.Bookmarks bookmarks = bookmarkEditor.ExtractBookmarks();
foreach (Aspose.Pdf.Facades.Bookmark bookmark in bookmarks)
{
	string strLevelSeprator = string.Empty;
	for (int i = 1; i < bookmark.Level; i++)
	{
		strLevelSeprator += "----";
	}
	Console.WriteLine("{0}Title: {1}", strLevelSeprator, bookmark.Title);
	Console.WriteLine("{0}Page Number: {1}", strLevelSeprator, bookmark.PageNumber);
	Console.WriteLine("{0}Page Action: {1}", strLevelSeprator, bookmark.Action);
}
```

## Conclusie

Gefeliciteerd! Nu hebt u een stapsgewijze handleiding voor het verkrijgen van bladwijzerpaginanummers met Aspose.PDF voor .NET. U kunt deze code gebruiken om de navigatie-informatie op te halen die aan elke bladwijzer in uw PDF-documenten is gekoppeld.

Zorg ervoor dat u de officiële Aspose.PDF-documentatie bekijkt voor meer informatie over geavanceerde functies voor bladwijzermanipulatie.

### Veelgestelde vragen over het verkrijgen van bladwijzerpaginanummer in PDF-bestand

#### Vraag: Wat zijn bladwijzers in een PDF-bestand?

A: Bladwijzers in een PDF-bestand zijn navigatiehulpmiddelen waarmee gebruikers snel naar specifieke secties of pagina's in het document kunnen springen. Ze verbeteren de gebruikerservaring door snelkoppelingen naar relevante inhoud te bieden.

#### Vraag: Waarom zou ik paginanummers van bladwijzers uit een PDF-bestand willen ophalen?

A: Door bladwijzerpaginanummers op te halen, kunnen gebruikers effectiever door een document navigeren, waardoor een duidelijke indicatie wordt gegeven van waar elke bladwijzer naartoe leidt. Dit is vooral handig voor langere documenten met meerdere secties.

#### Vraag: Hoe importeer ik de benodigde bibliotheken voor mijn C#-project?

A: Om de vereiste bibliotheek voor uw C#-project te importeren, gebruikt u de volgende importinstructie:

```csharp
using Aspose.Pdf.Facades;
```

Met deze richtlijn kunt u de klassen en methoden van Aspose.PDF voor .NET gebruiken.

#### Vraag: Hoe geef ik het pad naar de documentenmap op?

 A: Vervang in de meegeleverde broncode`"YOUR DOCUMENT DIRECTORY"`met het daadwerkelijke pad naar de map met het PDF-bestand waaruit u bladwijzerpaginanummers wilt extraheren. Dit zorgt ervoor dat de code het doel-PDF-bestand kan lokaliseren.

#### Vraag: Hoe maak ik een bladwijzereditor?

A: Gebruik de volgende code om een bladwijzereditor te maken:

```csharp
PdfBookmarkEditor bookmarkEditor = new PdfBookmarkEditor();
```

#### Vraag: Hoe open ik een PDF-bestand voor bladwijzermanipulatie?

A: Om een PDF-bestand te openen en bladwijzerinformatie op te halen, gebruikt u de volgende code:

```csharp
bookmarkEditor.BindPdf(dataDir + "GetBookmarks.pdf");
```

 Vervangen`"GetBookmarks.pdf"` met de werkelijke bestandsnaam.

#### Vraag: Hoe extraheer ik bladwijzers uit het PDF-bestand?

 A: Om bladwijzers uit het PDF-bestand te extraheren, gebruikt u de`ExtractBookmarks` methode van de bladwijzereditor:

```csharp
Bookmarks bookmarks = bookmarkEditor.ExtractBookmarks();
```

#### Vraag: Hoe kan ik bladwijzerpaginanummers ophalen en weergeven?

 A: Loop door de geëxtraheerde bladwijzers met behulp van a`foreach` lus en toegang tot de`PageNumber` eigenschap van elke bladwijzer om het bijbehorende paginanummer op te halen en weer te geven:

```csharp
foreach (Bookmark bookmark in bookmarks)
{
    Console.WriteLine("Title: " + bookmark.Title);
    Console.WriteLine("Page Number: " + bookmark.PageNumber);
    Console.WriteLine("Page Action: " + bookmark.Action);
}
```

#### Vraag: Kan ik bladwijzereigenschappen wijzigen met deze aanpak?

 A: Hoewel deze tutorial zich richt op het ophalen van bladwijzerpaginanummers, kunt u andere bladwijzereigenschappen op dezelfde manier wijzigen`Bookmark`object en bijbehorende eigenschappen.

#### Vraag: Hoe bewaar ik het bijgewerkte PDF-bestand nadat ik de bladwijzergegevens heb geëxtraheerd?

A: Bladwijzerextractie wijzigt het originele PDF-bestand niet. Als u wijzigingen wilt opslaan, kunt u dit doen met behulp van andere methoden die worden aangeboden door Aspose.PDF voor .NET.