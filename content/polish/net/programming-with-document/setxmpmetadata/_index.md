---
title: Ustaw XMPmetadata w pliku PDF
linktitle: Ustaw XMPmetadata w pliku PDF
second_title: Aspose.PDF z dokumentacją API .NET
description: Dowiedz się, jak ustawić XMPMetadata w pliku PDF przy użyciu Aspose.PDF dla .NET. Postępuj zgodnie z tym przewodnikiem krok po kroku.
type: docs
weight: 330
url: /pl/net/programming-with-document/setxmpmetadata/
---
W tym artykule przedstawimy przewodnik krok po kroku, jak używać Aspose.PDF dla .NET do ustawiania metadanych XMP w pliku PDF. Pełny przykładowy kod źródłowy podamy na końcu artykułu.

## Krok 1: Ustaw ścieżkę do katalogu dokumentów

Zanim zaczniemy, musimy ustawić ścieżkę do katalogu, w którym znajduje się nasz dokument PDF. Będziemy przechowywać tę ścieżkę w zmiennej o nazwie „dataDir”.

```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Pamiętaj o wymianie`YOUR DOCUMENT DIRECTORY` z rzeczywistą ścieżką do pliku PDF.

## Krok 2: Otwórz plik PDF

 Pierwszym krokiem jest otwarcie pliku PDF, dla którego chcesz ustawić metadane XMP. Aby to zrobić, musisz utworzyć nowy`Document` obiekt i podaj ścieżkę do pliku PDF.

```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Otwórz dokument
Document pdfDocument = new Document(dataDir + "SetXMPMetadata.pdf");
```

## Krok 3: Ustaw właściwości metadanych XMP

Teraz, gdy masz już otwarty plik PDF, możesz rozpocząć ustawianie właściwości metadanych XMP. Ustawione właściwości będą zależeć od konkretnych potrzeb, ale oto kilka typowych właściwości, które warto ustawić:

- `xmp:CreateDate`: Data utworzenia pliku PDF.
- `xmp:Nickname`: pseudonim lub alias pliku PDF.
- `xmp:CustomProperty`: Właściwość niestandardowa z określoną wartością.

 Aby ustawić te właściwości, możesz użyć metody`Metadata` własność`Document` obiekt. Oto przykład:

```csharp
// Ustaw właściwości
pdfDocument.Metadata["xmp:CreateDate"] = DateTime.Now;
pdfDocument.Metadata["xmp:Nickname"] = "Nickname";
pdfDocument.Metadata["xmp:CustomProperty"] = "Custom Value";
```

tym samouczku ustawimy datę utworzenia na bieżącą datę i godzinę, pseudonim na „Pseudonim”, a właściwość niestandardową na „Wartość niestandardowa”. Możesz zastąpić te wartości własnymi.

## Krok 4: Zapisz plik PDF

 Po ustawieniu właściwości metadanych XMP należy zapisać plik PDF. Aby to zrobić, możesz użyć`Save` metoda`Document` obiekt i podaj ścieżkę do miejsca, w którym chcesz zapisać zaktualizowany plik PDF.

```csharp
dataDir = dataDir + "SetXMPMetadata_out.pdf";
// Zapisz dokument
pdfDocument.Save(dataDir);
```

### Przykładowy kod źródłowy dla zestawu XMPmetadata przy użyciu Aspose.PDF dla .NET

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

Aspose.PDF dla .NET oferuje prosty sposób ustawiania metadanych XMP w plikach PDF, umożliwiając dodawanie informacji opisowych i właściwości do dokumentów. Powyższy przewodnik krok po kroku pokazuje, jak ustawić różne właściwości metadanych XMP przy użyciu kodu źródłowego C#. Dodatkowo możesz dostosować metadane XMP do swoich konkretnych potrzeb i wymagań biznesowych. Dzięki Aspose.PDF dla .NET zarządzanie metadanymi PDF staje się wydajne i pozwala na lepszą organizację i możliwość wyszukiwania dokumentów PDF.

### Często zadawane pytania dotyczące zestawu XMPMetadata w pliku PDF

#### P: Czym są metadane XMP w pliku PDF i dlaczego są one ważne?

Odp.: XMP (Extensible Metadata Platform) to standard osadzania metadanych w różnych formatach plików, w tym w formacie PDF. Metadane XMP w pliku PDF umożliwiają dodanie do dokumentu informacji opisowych i właściwości, takich jak data utworzenia, autor, tytuł, słowa kluczowe i właściwości niestandardowe. Jest to niezbędne dla lepszej organizacji, możliwości wyszukiwania i archiwizacji dokumentów PDF.

#### P: Czy mogę ustawić inne właściwości metadanych XMP oprócz tych wymienionych w przykładzie?

 O: Tak, możesz ustawić szeroki zakres właściwości metadanych XMP w zależności od konkretnych wymagań. Niektóre typowe właściwości obejmują`dc:title` (tytuł dokumentu),`dc:creator` (twórca dokumentu),`dc:description` (opis dokumentu),`pdf:Keywords` (słowa kluczowe dokumentu) i nie tylko. Specyfikacja XMP oferuje różne standardowe przestrzenie nazw i niestandardowe przestrzenie nazw do ustawiania różnych typów metadanych.

#### P: Czy można odzyskać i odczytać metadane XMP z istniejącego pliku PDF?

 O: Tak, Aspose.PDF dla .NET umożliwia odczytywanie i pobieranie metadanych XMP z istniejącego pliku PDF. Możesz skorzystać z`Metadata` własność`Document` class, aby uzyskać dostęp do metadanych XMP i pobrać wartości określonych właściwości.