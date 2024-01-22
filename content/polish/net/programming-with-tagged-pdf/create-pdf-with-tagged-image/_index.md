---
title: Utwórz plik PDF z oznaczonym obrazem
linktitle: Utwórz plik PDF z oznaczonym obrazem
second_title: Aspose.PDF z dokumentacją API .NET
description: Przewodnik krok po kroku dotyczący tworzenia pliku PDF ze znacznikiem obrazu przy użyciu Aspose.PDF dla .NET.
type: docs
weight: 40
url: /pl/net/programming-with-tagged-pdf/create-pdf-with-tagged-image/
---
W tym samouczku przedstawimy krok po kroku, jak utworzyć dokument PDF ze znacznikiem obrazu przy użyciu Aspose.PDF dla .NET. Aspose.PDF to potężna biblioteka, która umożliwia programowe tworzenie, manipulowanie i konwertowanie dokumentów PDF. Korzystając z funkcji struktury oznaczonej zawartości Aspose.PDF, możesz dodać oznaczone obrazy do swojego dokumentu PDF.

## Warunki wstępne

Zanim zaczniesz, upewnij się, że spełnione są następujące wymagania wstępne:

1. Visual Studio zainstalowany z platformą .NET.
2. Biblioteka Aspose.PDF dla .NET.

## Krok 1: Konfiguracja projektu

Aby rozpocząć, utwórz nowy projekt w Visual Studio i dodaj odwołanie do biblioteki Aspose.PDF dla .NET. Możesz pobrać bibliotekę z oficjalnej strony Aspose i zainstalować ją na swoim komputerze.

## Krok 2: Zaimportuj niezbędne przestrzenie nazw

W pliku kodu C# zaimportuj przestrzenie nazw wymagane do uzyskania dostępu do klas i metod dostarczonych przez Aspose.PDF:

```csharp
using System;
using Aspose.Pdf;
using Aspose.Pdf.Tagged;
```

## Krok 3: Tworzenie dokumentu PDF ze znacznikiem obrazu

Użyj poniższego kodu, aby utworzyć dokument PDF ze znacznikiem obrazu:

```csharp
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";
Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Creating a PDF with a tagged image");
taggedContent.SetLanguage("fr-FR");

IllustrationElement figure1 = taggedContent.CreateFigureElement();
taggedContent.RootElement.AppendChild(figure1);
figure1.AlternativeText = "Aspose Logo";
figure1.Title = "Picture 1";
figure1.SetTag("Fig");
figure1.SetImage(dataDir + @"aspose-logo.jpg");
```

Ten kod tworzy pusty dokument PDF i dodaje oznaczony obraz przy użyciu metod dostarczonych przez Aspose.PDF. Obraz jest określony za pomocą tekstu alternatywnego, tytułu i tagu.

## Krok 4: Zapisywanie dokumentu PDF

Użyj poniższego kodu, aby zapisać dokument PDF:

```csharp
document.Save(dataDir + "PDFwithTaggedImage.pdf");
```

Ten kod zapisuje dokument PDF ze znacznikiem obrazu w określonym pliku.

### Przykładowy kod źródłowy narzędzia Utwórz plik PDF ze znacznikiem obrazu przy użyciu Aspose.PDF dla .NET 
```csharp

// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("CreatePDFwithTaggedImage");
taggedContent.SetLanguage("en-US");
IllustrationElement figure1 = taggedContent.CreateFigureElement();
taggedContent.RootElement.AppendChild(figure1);
figure1.AlternativeText = "Aspose Logo";
figure1.Title = "Image 1";
figure1.SetTag("Fig");
// Dodaj obraz w rozdzielczości 300 DPI (domyślnie)
figure1.SetImage(dataDir + @"aspose-logo.jpg");
// Zapisz dokument PDF
document.Save(dataDir + "PDFwithTaggedImage.pdf");

```

## Wniosek

W tym samouczku nauczyłeś się tworzyć dokument PDF ze znacznikiem obrazu przy użyciu Aspose.PDF dla .NET. Oznaczone obrazy dodają dodatkowe, uporządkowane informacje do dokumentu PDF.

### Często zadawane pytania

#### P: Jaki jest cel tworzenia dokumentu PDF ze znacznikiem obrazu przy użyciu Aspose.PDF dla .NET?

Odp.: Tworzenie dokumentu PDF ze znacznikami obrazu przy użyciu Aspose.PDF dla .NET umożliwia dodawanie oznakowanych obrazów do zawartości dokumentu. Oznaczone obrazy zapewniają uporządkowane informacje, takie jak tekst alternatywny i tytuły, zwiększając dostępność i organizację.

#### P: W jaki sposób biblioteka Aspose.PDF pomaga w tworzeniu dokumentu PDF ze znacznikiem obrazu?

Odp.: Aspose.PDF dla .NET to solidna biblioteka zapewniająca funkcje do programowego tworzenia, manipulowania i konwertowania dokumentów PDF. W tym samouczku funkcje struktury oznaczonej zawartości biblioteki służą do dodawania oznaczonego obrazu do dokumentu PDF.

#### P: Jakie są wymagania wstępne dotyczące tworzenia dokumentu PDF ze znacznikiem obrazu przy użyciu Aspose.PDF dla .NET?

O: Zanim zaczniesz, upewnij się, że masz zainstalowany program Visual Studio ze środowiskiem .NET i że w projekcie znajduje się odwołanie do biblioteki Aspose.PDF dla .NET.

#### P: W jaki sposób dostarczony kod C# tworzy dokument PDF ze znacznikiem obrazu?

Odp.: Kod demonstruje, jak utworzyć dokument PDF, zdefiniować oznaczony element obrazu i dodać go do zawartości dokumentu. Oznaczony obraz zawiera tekst alternatywny, tytuł i znacznik przy użyciu metod dostarczonych przez Aspose.PDF.

#### P: Czy mogę użyć różnych formatów obrazu dla oznaczonego obrazu?

Odp.: Tak, możesz użyć różnych formatów obrazu z tagiem, takich jak JPEG, PNG, GIF itp. Przykładowy kod podany w samouczku wykorzystuje obraz JPEG, ale możesz go zastąpić ścieżką do pliku obrazu w preferowany format.

#### P: W jaki sposób tekst alternatywny (tekst alternatywny) jest używany w oznaczonych obrazach?

 O: Tekst alternatywny zawiera tekstowy opis obrazu, który jest odczytywany na głos przez czytniki ekranu dla użytkowników niedowidzących. W dostarczonym kodzie tekst alternatywny jest ustawiany za pomocą`AlternativeText` własność`IllustrationElement` reprezentujący oznaczony obraz.

####  P: W jaki sposób`SetTitle` method contribute to the PDF document's tagged image?

 O:`SetTitle` Metoda ustawia tytuł oznaczonej zawartości dokumentu PDF, zapewniając dodatkowy kontekst dla oznaczonego obrazu. Tytuł ten może pomóc w określeniu celu lub tematu otagowanej treści.

#### P: Czy mogę dostosować tag i tytuł oznaczonego obrazu?

 O: Tak, możesz dostosować tag i tytuł oznaczonego obrazu za pomocą`SetTag` I`Title` metody`IllustrationElement`. Przykład kodu demonstruje, jak ustawić tag na „Fig”, a tytuł na „Obraz 1”.

#### P: Jak mogę upewnić się, że oznaczony tagiem obraz jest dostępny i zgodny ze standardami dostępności?

O: Korzystając z funkcji struktury oznaczonej treści w Aspose.PDF i dostarczając tekst alternatywny oraz inne istotne informacje, przyczyniasz się do dostępności oznaczonego obrazu. Zapewnienie zgodności ze standardami dostępności polega na przestrzeganiu najlepszych praktyk dotyczących tekstu alternatywnego i struktury dokumentu.

#### P: Czy można dodać wiele oznaczonych obrazów do tego samego dokumentu PDF przy użyciu podobnych technik?

 Odp.: Tak, możesz dodać wiele oznaczonych obrazów do tego samego dokumentu PDF, korzystając z podobnych technik. Utworzyłbyś dodatkowe`IllustrationElement` instancje dla każdego oznaczonego obrazu i dostosuj ich właściwości zgodnie z potrzebami.