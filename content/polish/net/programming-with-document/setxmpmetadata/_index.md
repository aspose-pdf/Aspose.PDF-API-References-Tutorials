---
title: Ustaw XMPMetadata w pliku PDF
linktitle: Ustaw XMPMetadata w pliku PDF
second_title: Aspose.PDF dla .NET API Reference
description: Dowiedz się, jak ustawić XMPMetadata w pliku PDF za pomocą Aspose.PDF dla .NET. Postępuj zgodnie z tym przewodnikiem krok po kroku.
type: docs
weight: 330
url: /pl/net/programming-with-document/setxmpmetadata/
---
W tym artykule przedstawimy przewodnik krok po kroku, jak używać Aspose.PDF dla .NET do ustawiania metadanych XMP w pliku PDF. Na końcu artykułu podamy pełny przykładowy kod źródłowy.

## Krok 1: Ustaw ścieżkę do katalogu dokumentu

Zanim zaczniemy, musimy ustawić ścieżkę do katalogu, w którym znajduje się nasz dokument PDF. Zapiszemy tę ścieżkę w zmiennej o nazwie „dataDir”.

```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Pamiętaj o wymianie`YOUR DOCUMENT DIRECTORY` z rzeczywistą ścieżką do pliku PDF.

## Krok 2: Otwórz plik PDF

 Pierwszym krokiem jest otwarcie pliku PDF, dla którego chcesz ustawić metadane XMP. Aby to zrobić, musisz utworzyć nowy`Document` obiekt i przekaż ścieżkę do pliku PDF.

```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Otwórz dokument
Document pdfDocument = new Document(dataDir + "SetXMPMetadata.pdf");
```

## Krok 3: Ustaw właściwości metadanych XMP

Teraz, gdy masz otwarty plik PDF, możesz zacząć ustawiać właściwości metadanych XMP. Właściwości, które ustawisz, będą zależeć od Twoich konkretnych potrzeb, ale oto kilka typowych właściwości, które możesz chcieć ustawić:

- `xmp:CreateDate`:Data utworzenia pliku PDF.
- `xmp:Nickname`: Pseudonim lub alias pliku PDF.
- `xmp:CustomProperty`: Właściwość niestandardowa o określonej przez Ciebie wartości.

 Aby ustawić te właściwości, możesz użyć`Metadata` własność`Document` obiekt. Oto przykład:

```csharp
// Ustaw właściwości
pdfDocument.Metadata["xmp:CreateDate"] = DateTime.Now;
pdfDocument.Metadata["xmp:Nickname"] = "Nickname";
pdfDocument.Metadata["xmp:CustomProperty"] = "Custom Value";
```

tym samouczku ustawiamy datę utworzenia na bieżącą datę i godzinę, pseudonim na „Nickname”, a niestandardową właściwość na „Custom Value”. Możesz zastąpić te wartości swoimi własnymi.

## Krok 4: Zapisz plik PDF

 Po ustawieniu właściwości metadanych XMP należy zapisać plik PDF. Aby to zrobić, można użyć`Save` metoda`Document` obiekt i podaj ścieżkę do miejsca, w którym chcesz zapisać zaktualizowany plik PDF.

```csharp
dataDir = dataDir + "SetXMPMetadata_out.pdf";
// Zapisz dokument
pdfDocument.Save(dataDir);
```

### Przykładowy kod źródłowy dla Set XMPMetadata przy użyciu Aspose.PDF dla .NET

Oto kompletny przykładowy kod źródłowy do ustawiania XMPMetadata przy użyciu Aspose.PDF dla .NET:

```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Otwórz dokument
Document pdfDocument = new Document(dataDir + "SetXMPMetadata.pdf");

// Ustaw właściwości
pdfDocument.Metadata["xmp:CreateDate"] = DateTime.Now;
pdfDocument.Metadata["xmp:Nickname"] = "Nickname";
pdfDocument.Metadata["xmp:CustomProperty"] = "Custom Value";

dataDir = dataDir + "SetXMPMetadata_out.pdf";
// Zapisz dokument
pdfDocument.Save(dataDir);

Console.WriteLine("\nXMP metadata in a pdf file setup successfully.\nFile saved at " + dataDir);
```

## Wniosek

Aspose.PDF dla .NET oferuje prosty sposób ustawiania metadanych XMP w plikach PDF, umożliwiając dodawanie informacji opisowych i właściwości do dokumentów. Powyższy przewodnik krok po kroku pokazuje, jak ustawić różne właściwości metadanych XMP przy użyciu kodu źródłowego C#. Ponadto możesz dostosować metadane XMP do swoich konkretnych potrzeb i wymagań biznesowych. Dzięki Aspose.PDF dla .NET zarządzanie metadanymi PDF staje się wydajne i pozwala na lepszą organizację i możliwość wyszukiwania dokumentów PDF.

### Często zadawane pytania dotyczące zestawu XMPMetadata w pliku PDF

#### P: Czym są metadane XMP w pliku PDF i dlaczego są ważne?

A: XMP (Extensible Metadata Platform) to standard osadzania metadanych w różnych formatach plików, w tym PDF. Metadane XMP w pliku PDF umożliwiają dodawanie opisowych informacji i właściwości do dokumentu, takich jak data utworzenia, autor, tytuł, słowa kluczowe i właściwości niestandardowe. Jest to niezbędne do lepszej organizacji, możliwości wyszukiwania i archiwizacji dokumentów PDF.

#### P: Czy mogę ustawić inne właściwości metadanych XMP oprócz tych wymienionych w przykładzie?

 A: Tak, możesz ustawić szeroki zakres właściwości metadanych XMP w zależności od swoich konkretnych wymagań. Niektóre typowe właściwości obejmują:`dc:title` (tytuł dokumentu),`dc:creator` (twórca dokumentu),`dc:description` (opis dokumentu),`pdf:Keywords` (słowa kluczowe dokumentu) i więcej. Specyfikacja XMP oferuje różne standardowe przestrzenie nazw i niestandardowe przestrzenie nazw do ustawiania różnych typów metadanych.

#### P: Czy można pobrać i odczytać metadane XMP z istniejącego pliku PDF?

 A: Tak, Aspose.PDF dla .NET umożliwia odczytywanie i pobieranie metadanych XMP z istniejącego pliku PDF. Możesz użyć`Metadata` własność`Document` Klasa umożliwiająca dostęp do metadanych XMP i pobieranie wartości określonych właściwości.