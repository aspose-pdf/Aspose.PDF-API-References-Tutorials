---
title: Ustaw informacje o pliku w pliku PDF
linktitle: Ustaw informacje o pliku w pliku PDF
second_title: Aspose.PDF dla .NET API Reference
description: Dowiedz się, jak używać Aspose.PDF dla platformy .NET do ustawiania informacji o pliku w pliku PDF, korzystając z tego przewodnika krok po kroku.
type: docs
weight: 310
url: /pl/net/programming-with-document/setfileinfo/
---
Jeśli pracujesz nad projektem, który wymaga zarządzania plikami PDF przy użyciu Aspose.PDF dla .NET, jedną z funkcji, z których możesz chcieć skorzystać, jest możliwość ustawienia informacji o pliku dla dokumentu PDF. Informacje o pliku obejmują różne szczegóły, takie jak autor, data utworzenia, słowa kluczowe, data modyfikacji, temat i tytuł. Ten przewodnik przeprowadzi Cię przez proces ustawiania informacji o pliku dla dokumentu PDF przy użyciu kodu źródłowego C# z Aspose.PDF dla .NET.

## Instrukcja krok po kroku dotycząca ustawiania informacji o pliku za pomocą Aspose.PDF dla .NET

1. Utwórz nowy projekt C# w środowisku IDE programu Visual Studio.
2. Dodaj odwołanie do biblioteki Aspose.PDF dla .NET w swoim projekcie.
3. Utwórz nowy obiekt dokumentu PDF, podając ścieżkę do pliku PDF, w którym chcesz zmodyfikować informacje o pliku.

## Krok 1: Ustaw ścieżkę do katalogu dokumentów.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Krok 2: Otwórz dokument PDF

```csharp
// Otwórz dokument
Document pdfDocument = new Document(dataDir + "SetFileInfo.pdf");
```

## Krok 3: Użyj obiektu DocumentInfo, aby uzyskać dostęp do informacji o pliku dokumentu PDF.

```csharp
DocumentInfo docInfo = new DocumentInfo(pdfDocument);
```

## Krok 4: Ustaw żądane wartości informacji o pliku, korzystając z właściwości obiektu DocumentInfo.

```csharp
docInfo.Author = "Aspose";
docInfo.CreationDate = DateTime.Now;
docInfo.Keywords = "Aspose.Pdf, DOM, API";
docInfo.ModDate = DateTime.Now;
docInfo.Subject = "PDF Information";
docInfo.Title = "Setting PDF Document Information";
```

## Krok 5: Zapisz zaktualizowany dokument PDF w określonej lokalizacji.

```csharp
dataDir = dataDir + "SetFileInfo_out.pdf";
pdfDocument.Save(dataDir);
```

## Krok 6: Sprawdź, czy informacje o pliku zostały pomyślnie zaktualizowane.

```csharp
Console.WriteLine("\nFile informations setup successfully.\nFile saved at " + dataDir);
```

Pomyślnie ustawiono informacje o pliku dla dokumentu PDF przy użyciu Aspose.PDF dla .NET.

### Przykładowy kod źródłowy dla Ustaw informacje o pliku przy użyciu Aspose.PDF dla .NET


```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Otwórz dokument
Document pdfDocument = new Document(dataDir + "SetFileInfo.pdf");

// Określ informacje o dokumencie
DocumentInfo docInfo = new DocumentInfo(pdfDocument);

docInfo.Author = "Aspose";
docInfo.CreationDate = DateTime.Now;
docInfo.Keywords = "Aspose.Pdf, DOM, API";
docInfo.ModDate = DateTime.Now;
docInfo.Subject = "PDF Information";
docInfo.Title = "Setting PDF Document Information";

dataDir = dataDir + "SetFileInfo_out.pdf";
// Zapisz dokument wyjściowy
pdfDocument.Save(dataDir);

Console.WriteLine("\nFile informations setup successfully.\nFile saved at " + dataDir);
```

## Wniosek

Podsumowując, Aspose.PDF dla .NET zapewnia prosty i skuteczny sposób ustawiania informacji o pliku dla dokumentów PDF. Postępując zgodnie z powyższymi krokami, możesz łatwo ustawić żądane wartości informacji o pliku dla swoich dokumentów PDF, używając kodu źródłowego C#.

### Często zadawane pytania dotyczące informacji o pliku zestawu w pliku PDF

#### P: Czy mogę ustawić dodatkowe właściwości informacji o pliku, które nie zostały wymienione w przykładzie?

 O: Tak, możesz ustawić dodatkowe właściwości informacji o pliku za pomocą`DocumentInfo` obiekt w Aspose.PDF dla .NET.`DocumentInfo`Klasa udostępnia różne właściwości pozwalające na ustawienie dodatkowych informacji, takich jak producent, wersja i właściwości niestandardowe.

#### P: Czy można odzyskać informacje o pliku z istniejącego dokumentu PDF?

 A: Tak, możesz pobrać informacje o pliku z istniejącego dokumentu PDF za pomocą Aspose.PDF dla .NET. Aby to zrobić, możesz użyć`DocumentInfo` obiekt umożliwiający dostęp do właściwości informacji o pliku i odczytanie informacji zapisanych w dokumencie PDF.

#### P: Czy zmiana informacji o pliku powoduje modyfikację oryginalnego dokumentu PDF?

A: Nie, ustawienie informacji o pliku za pomocą Aspose.PDF dla .NET nie modyfikuje oryginalnego dokumentu PDF. Zamiast tego tworzy nowy dokument PDF z zaktualizowanymi informacjami o pliku. Oryginalny dokument PDF pozostaje niezmieniony.