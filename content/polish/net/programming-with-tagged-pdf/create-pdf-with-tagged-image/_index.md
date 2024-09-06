---
title: Utwórz plik PDF z tagowanym obrazem
linktitle: Utwórz plik PDF z tagowanym obrazem
second_title: Aspose.PDF dla .NET API Reference
description: Instrukcja krok po kroku dotycząca tworzenia pliku PDF z tagowanym obrazem przy użyciu Aspose.PDF dla platformy .NET.
type: docs
weight: 40
url: /pl/net/programming-with-tagged-pdf/create-pdf-with-tagged-image/
---
W tym samouczku przedstawimy Ci przewodnik krok po kroku, jak utworzyć dokument PDF z tagowanym obrazem przy użyciu Aspose.PDF dla .NET. Aspose.PDF to potężna biblioteka, która umożliwia programowe tworzenie, manipulowanie i konwertowanie dokumentów PDF. Korzystając z funkcji tagowanej struktury treści Aspose.PDF, możesz dodawać tagowane obrazy do swojego dokumentu PDF.

## Wymagania wstępne

Zanim zaczniesz, upewnij się, że spełnione są następujące wymagania wstępne:

1. Zainstalowano program Visual Studio z platformą .NET Framework.
2. Biblioteka Aspose.PDF dla .NET.

## Krok 1: Konfiguracja projektu

Aby rozpocząć, utwórz nowy projekt w Visual Studio i dodaj odwołanie do biblioteki Aspose.PDF dla .NET. Możesz pobrać bibliotekę z oficjalnej strony internetowej Aspose i zainstalować ją na swoim komputerze.

## Krok 2: Zaimportuj niezbędne przestrzenie nazw

W pliku kodu C# zaimportuj przestrzenie nazw wymagane do uzyskania dostępu do klas i metod udostępnianych przez Aspose.PDF:

```csharp
using System;
using Aspose.Pdf;
using Aspose.Pdf.Tagged;
```

## Krok 3: Tworzenie dokumentu PDF z tagowanym obrazem

Użyj poniższego kodu, aby utworzyć dokument PDF z oznaczonym obrazem:

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

Ten kod tworzy pusty dokument PDF i dodaje oznaczony obraz za pomocą metod dostarczonych przez Aspose.PDF. Obraz jest określony za pomocą tekstu alternatywnego, tytułu i tagu.

## Krok 4: Zapisywanie dokumentu PDF

Użyj poniższego kodu, aby zapisać dokument PDF:

```csharp
document.Save(dataDir + "PDFwithTaggedImage.pdf");
```

Ten kod zapisuje dokument PDF z oznaczonym obrazem do określonego pliku.

### Przykładowy kod źródłowy dla funkcji Create PDFwith Tagged Image przy użyciu Aspose.PDF dla .NET 
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
// Dodaj obraz o rozdzielczości 300 DPI (domyślnie)
figure1.SetImage(dataDir + @"aspose-logo.jpg");
// Zapisz dokument PDF
document.Save(dataDir + "PDFwithTaggedImage.pdf");

```

## Wniosek

W tym samouczku dowiedziałeś się, jak utworzyć dokument PDF z oznaczonym obrazem za pomocą Aspose.PDF dla .NET. Oznaczone obrazy dodają dodatkowe, ustrukturyzowane informacje do dokumentu PDF.

### Najczęściej zadawane pytania

#### P: Jaki jest cel tworzenia dokumentu PDF z tagowanym obrazem za pomocą Aspose.PDF dla platformy .NET?

A: Tworzenie dokumentu PDF z tagowanym obrazem przy użyciu Aspose.PDF dla .NET umożliwia dodawanie tagowanych obrazów do zawartości dokumentu. Tagowane obrazy zapewniają ustrukturyzowane informacje, takie jak tekst alternatywny i tytuły, zwiększając dostępność i organizację.

#### P: W jaki sposób biblioteka Aspose.PDF pomaga w tworzeniu dokumentu PDF z tagowanym obrazem?

A: Aspose.PDF dla .NET to solidna biblioteka, która zapewnia funkcjonalności do tworzenia, manipulowania i konwertowania dokumentów PDF programowo. W tym samouczku funkcje struktury treści tagowanej biblioteki są używane do dodawania tagowanego obrazu do dokumentu PDF.

#### P: Jakie wymagania należy spełnić, aby utworzyć dokument PDF z tagowanym obrazem przy użyciu Aspose.PDF dla platformy .NET?

O: Zanim zaczniesz, upewnij się, że masz zainstalowany program Visual Studio z platformą .NET Framework i że w projekcie znajduje się odwołanie do biblioteki Aspose.PDF dla platformy .NET.

#### P: W jaki sposób dostarczony kod C# tworzy dokument PDF z oznaczonym obrazem?

A: Kod pokazuje, jak utworzyć dokument PDF, zdefiniować oznaczony element obrazu i dodać go do zawartości dokumentu. Oznaczony obraz zawiera tekst alternatywny, tytuł i tag przy użyciu metod dostarczonych przez Aspose.PDF.

#### P: Czy mogę używać różnych formatów obrazu dla oznaczonego obrazu?

O: Tak, możesz użyć różnych formatów obrazu dla oznaczonego obrazu, takich jak JPEG, PNG, GIF itd. Przykład kodu podany w samouczku wykorzystuje obraz JPEG, ale możesz go zastąpić ścieżką do pliku obrazu w preferowanym formacie.

#### P: W jaki sposób tekst alternatywny (alt text) jest używany w oznaczonych obrazach?

 A: Tekst alternatywny zapewnia tekstowy opis obrazu, który jest odczytywany na głos przez czytniki ekranowe dla użytkowników z dysfunkcją wzroku. W podanym kodzie tekst alternatywny jest ustawiany za pomocą`AlternativeText` własność`IllustrationElement` reprezentujący oznaczony obraz.

####  P: Jak to działa?`SetTitle` method contribute to the PDF document's tagged image?

 A: Ten`SetTitle` Metoda ustawia tytuł oznaczonej zawartości dokumentu PDF, zapewniając dodatkowy kontekst dla oznaczonego obrazu. Ten tytuł może pomóc zidentyfikować cel lub temat oznaczonej zawartości.

#### P: Czy mogę dostosować tag i tytuł tagowanego obrazu?

 O: Tak, możesz dostosować tag i tytuł oznaczonego obrazu, korzystając z`SetTag` I`Title` metody`IllustrationElement`Przykład kodu pokazuje, jak ustawić tag na „Fig” i tytuł na „Picture 1”.

#### P: Jak mogę mieć pewność, że oznaczony obraz jest dostępny i zgodny ze standardami dostępności?

A: Korzystając z funkcji struktury treści oznaczonych w Aspose.PDF i podając tekst alternatywny oraz inne istotne informacje, przyczyniasz się do dostępności oznaczonego obrazu. Zapewnienie zgodności ze standardami dostępności obejmuje przestrzeganie najlepszych praktyk dotyczących tekstu alternatywnego i struktury dokumentu.

#### P: Czy można dodać wiele oznaczonych obrazów do tego samego dokumentu PDF, stosując podobne techniki?

 A: Tak, możesz dodać wiele oznaczonych obrazów do tego samego dokumentu PDF, używając podobnych technik. Utworzyłbyś dodatkowe`IllustrationElement` wystąpienia dla każdego oznaczonego obrazu i dostosować ich właściwości według potrzeb.