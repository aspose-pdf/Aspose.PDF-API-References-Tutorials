---
title: Niewidoczna adnotacja w pliku PDF
linktitle: Niewidoczna adnotacja w pliku PDF
second_title: Aspose.PDF z dokumentacją API .NET
description: Dowiedz się, jak niewidoczną adnotację w pliku PDF przy użyciu kodu źródłowego C# z Aspose.PDF dla .NET. Przewodnik krok po kroku.
type: docs
weight: 100
url: /pl/net/annotations/invisibleannotation/
---
Adnotacje w pliku PDF to zaawansowana funkcja, która pozwala dodawać dodatkowe informacje lub notatki do dokumentu bez zmiany rzeczywistej zawartości. Można ich używać do wyróżniania tekstu, zwracania uwagi na określone obszary dokumentu lub dodawania komentarzy lub opinii.

Istnieje wiele różnych typów adnotacji, których można używać w dokumentach PDF, w tym:

- Adnotacje tekstowe
- Adnotacje linków
- Adnotacje stemplowe
- Adnotacje dźwiękowe
- Adnotacje do załączników plików
- i wiele więcej

## Krok 1: Tworzenie niewidocznej adnotacji w dokumencie PDF przy użyciu Aspose.PDF dla .NET

 Aby utworzyć niewidoczną adnotację w dokumencie PDF przy użyciu Aspose.PDF dla .NET, musimy najpierw utworzyć`FreeTextAnnotation` obiektu i określ lokalizację i rozmiar adnotacji.

```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Otwórz dokument
Document doc = new Document(dataDir + "input.pdf");

FreeTextAnnotation annotation = new FreeTextAnnotation(doc.Pages[1], new Aspose.Pdf.Rectangle(50, 600, 250, 650), new DefaultAppearance("Helvetica", 16, System.Drawing.Color.Red));
```

 W powyższym kodzie tworzymy plik`FreeTextAnnotation`obiektu i określ lokalizację adnotacji na stronie 2 dokumentu PDF. Określamy także rodzaj, rozmiar i kolor czcionki, która będzie wyświetlana w adnotacji.

## Krok 2: Dodawanie cech do niewidocznej adnotacji

Następnie możemy dodać do adnotacji pewne cechy, takie jak kolor obramowania, kolor tła lub krycie.

```csharp
annotation.Characteristics.Border = System.Drawing.Color.Red;
```

W powyższym kodzie kolor obramowania adnotacji ustawiamy na czerwony.

## Krok 3: Ustawianie flag adnotacji

Po utworzeniu adnotacji i ustaleniu jej charakterystyki możemy określić flagi adnotacji. W tym samouczku chcemy, aby adnotację można było wydrukować, ale nie można jej oglądać.

```csharp
annotation.Flags = AnnotationFlags.Print | AnnotationFlags.NoView;
doc.Pages[1].Annotations.Add(annotation);
```

## Krok 4: Zapisywanie zmodyfikowanego dokumentu PDF

Wreszcie możemy zapisać zmodyfikowany dokument PDF z nową niewidoczną adnotacją.

```csharp
dataDir = dataDir + "InvisibleAnnotation_out.pdf";
doc.Save(dataDir);
```

## Przykładowy kod źródłowy sposobu niewidocznej adnotacji przy użyciu Aspose.PDF dla .NET

```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Otwórz dokument
Document doc = new Document(dataDir + "input.pdf");

FreeTextAnnotation annotation = new FreeTextAnnotation(doc.Pages[1], new Aspose.Pdf.Rectangle(50, 600, 250, 650), new DefaultAppearance("Helvetica", 16, System.Drawing.Color.Red));
annotation.Contents = "ABCDEFG";
annotation.Characteristics.Border = System.Drawing.Color.Red;
annotation.Flags = AnnotationFlags.Print | AnnotationFlags.NoView;
doc.Pages[1].Annotations.Add(annotation);

dataDir = dataDir + "InvisibleAnnotation_out.pdf";
// Zapisz plik wyjściowy
doc.Save(dataDir);
// ExEnd:InvisibleAdnotation
Console.WriteLine("\nAnnotation nvisible successfully.\nFile saved at " + dataDir);
```

## Wniosek

tym samouczku nauczyliśmy się, jak utworzyć niewidoczną adnotację w dokumencie PDF przy użyciu Aspose.PDF dla .NET. Niewidoczne adnotacje są przydatną funkcją, gdy chcesz dodać dodatkowe informacje lub notatki do dokumentu bez wyświetlania ich czytelnikowi. Postępując zgodnie ze szczegółowym przewodnikiem i korzystając z dostarczonego kodu źródłowego C#, programiści mogą łatwo tworzyć i dostosowywać niewidoczne adnotacje w swoich dokumentach PDF. Aspose.PDF dla .NET zapewnia kompleksowy zestaw narzędzi do pracy z adnotacjami, pozwalający zwiększyć interaktywność i użyteczność plików PDF.

### Często zadawane pytania

#### P: Co to jest niewidoczna adnotacja w dokumencie PDF?

Odp.: Niewidoczna adnotacja w dokumencie PDF to adnotacja, która nie jest widoczna na stronie, ale zawiera dodatkowe informacje lub notatki. Umożliwia dodawanie komentarzy lub opinii bez konieczności wyświetlania ich czytelnikowi.

#### P: Jakiego rodzaju cechy można dodać do niewidocznej adnotacji?

Odp.: Do niewidocznej adnotacji można dodać różne cechy, takie jak kolor obramowania, kolor tła, przezroczystość, typ czcionki, rozmiar i kolor wyświetlanego tekstu.

#### P: Czy mogę ustawić różne flagi adnotacji dla niewidocznej adnotacji?

O: Tak, możesz ustawić różne flagi adnotacji dla niewidocznej adnotacji, w zależności od wymagań. Na przykład możesz sprawić, że adnotacja będzie drukowana, ale nie będzie widoczna.

#### P: Jak mogę dodać niewidoczną adnotację do określonej strony dokumentu PDF?

 Odp.: Aby dodać niewidoczną adnotację do określonej strony dokumentu PDF, musisz utworzyć plik`FreeTextAnnotation` obiektu i określ lokalizację i rozmiar adnotacji na tej stronie.

#### P: Czy mogę modyfikować właściwości istniejącej niewidocznej adnotacji w pliku PDF?

Odp.: Tak, możesz modyfikować charakterystykę istniejącej niewidocznej adnotacji w pliku PDF przy użyciu Aspose.PDF dla .NET. Możesz zmienić typ czcionki, rozmiar, kolor, kolor obramowania, kolor tła, przezroczystość i inne właściwości adnotacji.