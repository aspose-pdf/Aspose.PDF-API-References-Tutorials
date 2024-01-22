---
title: Ustaw informacje o pliku w pliku PDF
linktitle: Ustaw informacje o pliku w pliku PDF
second_title: Aspose.PDF z dokumentacją API .NET
description: Dowiedz się, jak używać Aspose.PDF dla .NET do ustawiania informacji o pliku w pliku PDF, korzystając z tego przewodnika krok po kroku.
type: docs
weight: 310
url: /pl/net/programming-with-document/setfileinfo/
---
Jeśli pracujesz nad projektem, który wymaga zarządzania plikami PDF przy użyciu Aspose.PDF dla .NET, jedną z funkcji, z których możesz skorzystać, jest możliwość ustawienia informacji o pliku dla dokumentu PDF. Informacje o pliku obejmują różne szczegóły, takie jak autor, data utworzenia, słowa kluczowe, data modyfikacji, temat i tytuł. Ten przewodnik przeprowadzi Cię przez proces ustawiania informacji o pliku dla dokumentu PDF przy użyciu kodu źródłowego C# z Aspose.PDF dla .NET.

## Przewodnik krok po kroku dotyczący ustawiania informacji o pliku przy użyciu Aspose.PDF dla .NET

1. Utwórz nowy projekt C# w środowisku IDE programu Visual Studio.
2. Dodaj w swoim projekcie odwołanie do biblioteki Aspose.PDF for .NET.
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

Pomyślnie ustawiłeś informacje o pliku dla dokumentu PDF przy użyciu Aspose.PDF dla .NET.

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

Podsumowując, Aspose.PDF dla .NET zapewnia prosty i skuteczny sposób ustawiania informacji o plikach dla dokumentów PDF. Wykonując powyższe kroki, możesz łatwo ustawić żądane wartości informacji o plikach dla dokumentów PDF przy użyciu kodu źródłowego C#.

### Często zadawane pytania dotyczące ustawiania informacji o pliku w pliku PDF

#### P: Czy mogę ustawić dodatkowe właściwości informacji o pliku, które nie zostały wymienione w przykładzie?

 O: Tak, możesz ustawić dodatkowe właściwości informacji o pliku za pomocą opcji`DocumentInfo` obiekt w Aspose.PDF dla .NET. The`DocumentInfo`class udostępnia różne właściwości, które pozwalają ustawić dodatkowe informacje, takie jak producent, wersja i właściwości niestandardowe.

#### P: Czy można odzyskać informacje o pliku z istniejącego dokumentu PDF?

 Odp.: Tak, możesz pobrać informacje o pliku z istniejącego dokumentu PDF za pomocą Aspose.PDF dla .NET. Aby to zrobić, możesz użyć`DocumentInfo` obiekt, aby uzyskać dostęp do właściwości informacji o pliku i odczytać informacje zapisane w dokumencie PDF.

#### P: Czy ustawienie informacji o pliku modyfikuje oryginalny dokument PDF?

O: Nie, ustawienie informacji o pliku za pomocą Aspose.PDF dla .NET nie modyfikuje oryginalnego dokumentu PDF. Zamiast tego tworzy nowy dokument PDF ze zaktualizowanymi informacjami o pliku. Oryginalny dokument PDF pozostaje niezmieniony.