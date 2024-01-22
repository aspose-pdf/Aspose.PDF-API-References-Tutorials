---
title: Osadzaj czcionki w pliku PDF ze strategią podzbioru
linktitle: Osadzaj czcionki ze strategią podzbioru
second_title: Aspose.PDF z dokumentacją API .NET
description: Dowiedz się, jak osadzać czcionki w pliku PDF za pomocą strategii podzbiorów przy użyciu Aspose.PDF dla .NET. Zoptymalizuj rozmiar pliku PDF, osadzając tylko niezbędne znaki.
type: docs
weight: 130
url: /pl/net/programming-with-document/embedfontsusingsubsetstrategy/
---
W tym samouczku omówimy, jak osadzać czcionki w pliku PDF ze strategią podzbioru przy użyciu Aspose.PDF dla .NET. Aspose.PDF dla .NET to potężna biblioteka, która pozwala programistom programowo tworzyć, edytować i manipulować dokumentami PDF. Osadzanie czcionek w pliku PDF to ważny krok zapewniający prawidłowe wyświetlanie dokumentu na różnych urządzeniach, niezależnie od tego, czy wymagane czcionki są na tych urządzeniach zainstalowane, czy nie.

## Krok 1: Utwórz nową aplikację konsolową C#
Aby rozpocząć, utwórz nową aplikację konsolową C# w programie Visual Studio. Możesz nazwać to jak chcesz. Po utworzeniu projektu należy dodać odwołanie do biblioteki Aspose.PDF dla .NET.

## Krok 2: Zaimportuj przestrzeń nazw Aspose.PDF
Dodaj następujący wiersz kodu na górze pliku C#, aby zaimportować przestrzeń nazw Aspose.PDF:

```csharp
using Aspose.Pdf;
```

## Krok 3: Załaduj istniejący plik PDF
Aby osadzić czcionki w istniejącym pliku PDF, należy załadować ten plik za pomocą klasy Dokument. Poniższy kod demonstruje, jak załadować istniejący plik PDF:

```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Załaduj istniejący plik PDF
Document doc = new Document(dataDir + "input.pdf");
```

## Krok 4: Osadź czcionki za pomocą strategii podzbioru
Aspose.PDF dla .NET udostępnia dwie strategie osadzania czcionek: SubsetAllFonts i SubsetEmbeddedFontsOnly.

Strategia SubsetAllFonts osadzi wszystkie czcionki w dokumencie jako podzbiór. Podzbiór to część czcionki zawierająca tylko znaki używane w dokumencie. Strategia ta jest przydatna do zmniejszania rozmiaru pliku dokumentu PDF.

Strategia SubsetEmbeddedFontsOnly osadzi tylko podzbiór czcionek, które są już osadzone w dokumencie. Jeśli czcionka nie jest osadzona, ta strategia nie będzie miała na nią wpływu.

Poniższy kod ilustruje sposób osadzania czcionek w pliku PDF przy użyciu strategii podzbioru:

```csharp
// W przypadku SubsetAllFonts wszystkie czcionki zostaną osadzone jako podzbiór w dokumencie.
doc.FontUtilities.SubsetFonts(FontSubsetStrategy.SubsetAllFonts);

// Podzbiór czcionek zostanie osadzony w przypadku czcionek całkowicie osadzonych, ale nie będzie to miało wpływu na czcionki, które nie są osadzone w dokumencie.
doc.FontUtilities.SubsetFonts(FontSubsetStrategy.SubsetEmbeddedFontsOnly);
```

## Krok 5: Zapisz dokument PDF
Po osadzeniu wszystkich czcionek w pliku PDF przy użyciu strategii podzbioru należy zapisać dokument. Poniższy kod demonstruje, jak zapisać plik PDF:

```csharp
doc.Save(dataDir + "Output_out.pdf");
```

### Przykładowy kod źródłowy do osadzania czcionek ze strategią podzbioru przy użyciu Aspose.PDF dla .NET. 

```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "input.pdf");
// W przypadku SubsetAllFonts wszystkie czcionki zostaną osadzone jako podzbiór w dokumencie.
doc.FontUtilities.SubsetFonts(FontSubsetStrategy.SubsetAllFonts);
// Podzbiór czcionek zostanie osadzony w przypadku czcionek całkowicie osadzonych, ale nie będzie to miało wpływu na czcionki, które nie są osadzone w dokumencie.
doc.FontUtilities.SubsetFonts(FontSubsetStrategy.SubsetEmbeddedFontsOnly);
doc.Save(dataDir + "Output_out.pdf");
```

## Wniosek
tym artykule omówiliśmy, jak osadzać czcionki w pliku PDF ze strategią podzbioru przy użyciu Aspose.PDF dla .NET. Aspose.PDF dla .NET zapewnia prosty i łatwy w użyciu interfejs API do pracy z dokumentami PDF, w tym dodawania i osadzania czcionek przy użyciu różnych strategii. Osadzanie czcionek w pliku PDF to ważny krok zapewniający prawidłowe wyświetlanie dokumentu na różnych urządzeniach, a strategia podzbioru to przydatna funkcja umożliwiająca zmniejszenie rozmiaru pliku dokumentu PDF.

### Często zadawane pytania dotyczące osadzania czcionek w pliku PDF przy użyciu strategii podzbioru

#### P: Jaka jest strategia podzbioru osadzania czcionek w pliku PDF?

Odp.: Strategia podzbioru czcionek osadzanych w pliku PDF oznacza, że osadzona zostanie tylko część czcionki zawierająca znaki użyte w dokumencie. Pomaga to zmniejszyć rozmiar pliku dokumentu PDF, eliminując niepotrzebne dane dotyczące czcionek.

#### P: Jaka jest różnica między strategiami SubsetAllFonts i SubsetEmbeddedFontsOnly?

 O:`SubsetAllFonts`strategia osadzi wszystkie czcionki w dokumencie jako podzbiór, podczas gdy plik`SubsetEmbeddedFontsOnly` strategia osadzi tylko podzbiór czcionek, które są już osadzone w dokumencie. Ta ostatnia strategia nie będzie miała wpływu na czcionki, które nie są jeszcze osadzone.

#### P: Dlaczego osadzanie czcionek przy użyciu strategii podzbioru jest ważne?

O: Osadzanie czcionek przy użyciu strategii podzbioru jest ważne, aby mieć pewność, że plik PDF zawiera dane czcionki niezbędne do prawidłowego wyświetlania tekstu, a jednocześnie zachować mniejszy rozmiar pliku poprzez uwzględnienie tylko znaków używanych w dokumencie.

#### P: Czy mogę używać Aspose.PDF dla .NET do osadzania czcionek z różnymi strategiami?

 Odp.: Tak, Aspose.PDF dla .NET zapewnia różne strategie osadzania czcionek, w tym`SubsetAllFonts` I`SubsetEmbeddedFontsOnly`. Możesz wybrać odpowiednią strategię w oparciu o swoje wymagania.

#### P: Czy Aspose.PDF dla .NET jest niezawodną biblioteką do pracy z dokumentami PDF?

O: Tak, Aspose.PDF dla .NET to niezawodna i wydajna biblioteka do pracy z dokumentami PDF. Zapewnia rozbudowane funkcje tworzenia, edytowania i manipulowania plikami PDF w aplikacjach .NET.