---
title: Utwórz lokalne hiperłącze w pliku PDF
linktitle: Utwórz lokalne hiperłącze w pliku PDF
second_title: Aspose.PDF dla .NET API Reference
description: Łatwe tworzenie lokalnych hiperłączy w plikach PDF za pomocą Aspose.PDF dla platformy .NET.
type: docs
weight: 40
url: /pl/net/programming-with-links-and-actions/create-local-hyperlink/
---
Tworzenie lokalnych hiperłączy w pliku PDF pozwala tworzyć klikalne łącza, które przenoszą użytkowników do innych stron w tym samym dokumencie PDF. Dzięki Aspose.PDF dla .NET możesz łatwo tworzyć takie łącza, postępując zgodnie z następującym kodem źródłowym:

## Krok 1: Importuj wymagane biblioteki

Zanim zaczniesz, musisz zaimportować niezbędne biblioteki dla swojego projektu C#. Oto niezbędna dyrektywa importu:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
using Aspose.Pdf.InteractiveFeatures;
```

## Krok 2: Ustaw ścieżkę do folderu dokumentów

 W tym kroku musisz określić ścieżkę do folderu, w którym chcesz zapisać wynikowy plik PDF. Zastąp`"YOUR DOCUMENT DIRECTORY"` w poniższym kodzie podaj rzeczywistą ścieżkę do folderu z dokumentami:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Krok 3: Utwórz wystąpienie dokumentu

 Utworzymy instancję`Document` klasa do reprezentowania naszego dokumentu PDF. Oto odpowiadający kod:

```csharp
Document doc = new Document();
```

## Krok 4: Dodaj stronę i tekst z hiperłączami

tym kroku dodamy stronę do naszego dokumentu PDF i dodamy tekst zawierający lokalne hiperłącza. Zdefiniujemy strony docelowe dla każdego łącza. Oto odpowiedni kod:

```csharp
Page page = doc.Pages.Add();

TextFragment text = new TextFragment("Link to page 7");
LocalHyperlink link = new LocalHyperlink();
link.TargetPageNumber = 7;
text. Hyperlink = link;
page.Paragraphs.Add(text);

text = new TextFragment("Link to page 1");
text. IsInNewPage = true;
link = new LocalHyperlink();
link.TargetPageNumber = 1;
text. Hyperlink = link;
page.Paragraphs.Add(text);
```

## Krok 5: Zapisz zaktualizowany dokument

Teraz zapiszmy zaktualizowany plik PDF za pomocą`Save` metoda`doc` obiekt. Oto odpowiadający kod:

```csharp
dataDir = dataDir + "CreateLocalHyperlink_out.pdf";
doc.Save(dataDir);
```

### Przykładowy kod źródłowy dla funkcji Utwórz lokalne hiperłącze przy użyciu Aspose.PDF dla .NET 
```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Utwórz instancję dokumentu
Document doc = new Document();
// Dodaj stronę do zbioru stron pliku PDF
Page page = doc.Pages.Add();
// Utwórz instancję fragmentu tekstu
Aspose.Pdf.Text.TextFragment text = new Aspose.Pdf.Text.TextFragment("link page number test to page 7");
// Utwórz lokalną instancję hiperłącza
Aspose.Pdf.LocalHyperlink link = new Aspose.Pdf.LocalHyperlink();
// Ustaw stronę docelową dla wystąpienia łącza
link.TargetPageNumber = 7;
// Ustaw hiperłącze TextFragment
text.Hyperlink = link;
// Dodaj tekst do zbioru akapitów strony
page.Paragraphs.Add(text);
// Utwórz nową instancję TextFragment
text = new TextFragment("link page number test to page 1");
// Fragment tekstu należy dodać na nowej stronie
text.IsInNewPage = true;
// Utwórz kolejną lokalną instancję hiperłącza
link = new LocalHyperlink();
// Ustaw stronę docelową dla drugiego hiperłącza
link.TargetPageNumber = 1;
// Ustaw link dla drugiego fragmentu tekstu
text.Hyperlink = link;
// Dodaj tekst do zbioru akapitów obiektu strony
page.Paragraphs.Add(text);    
dataDir = dataDir + "CreateLocalHyperlink_out.pdf";
// Zapisz zaktualizowany dokument
doc.Save(dataDir);
Console.WriteLine("\nLocal hyperlink created successfully.\nFile saved at " + dataDir);            
```

## Wniosek

Gratulacje! Teraz masz przewodnik krok po kroku, jak tworzyć lokalne hiperłącza w pliku PDF przy użyciu Aspose.PDF dla .NET. Możesz użyć tego kodu, aby tworzyć klikalne łącza, które przenoszą użytkowników do innych stron w tym samym dokumencie.

Koniecznie zapoznaj się z oficjalną dokumentacją Aspose.PDF, aby uzyskać więcej informacji na temat zaawansowanych funkcji hiperłączy.

### FAQ dotyczące tworzenia lokalnego hiperłącza w pliku PDF

#### P: Czym są lokalne hiperłącza w pliku PDF?

A: Lokalne hiperłącza w pliku PDF to klikalne łącza, które kierują użytkowników do różnych stron w tym samym dokumencie. Te łącza usprawniają nawigację i pozwalają czytelnikom na szybki dostęp do odpowiednich sekcji.

#### P: Jaką korzyść mogą przynieść lokalne hiperłącza w moim dokumencie PDF?

A: Lokalne hiperłącza zapewniają wydajny sposób łączenia powiązanych treści w tym samym dokumencie PDF. Poprawiają one doświadczenie użytkownika, umożliwiając czytelnikom szybkie przechodzenie do określonych sekcji bez przewijania całego dokumentu.

#### P: W jaki sposób Aspose.PDF dla platformy .NET obsługuje tworzenie lokalnych hiperłączy?
A: Aspose.PDF dla .NET oferuje kompleksowe wsparcie dla tworzenia lokalnych hiperłączy. Samouczek krok po kroku zawarty w tym przewodniku pokazuje, jak dodawać lokalne hiperłącza do dokumentu PDF za pomocą języka C#.

#### P: Czy mogę dostosować wygląd lokalnych hiperłączy?

O: Tak, możesz dostosować wygląd lokalnych hiperłączy, w tym kolor i styl tekstu, aby mieć pewność, że będą one pasować do projektu Twojego dokumentu i zapewnią spójne wrażenia wizualne.

#### P: Czy można utworzyć wiele lokalnych hiperłączy w ramach jednej strony pliku PDF?

A: Oczywiście! Możesz utworzyć wiele lokalnych hiperłączy w ramach jednej strony PDF, umożliwiając czytelnikom przeskakiwanie do różnych sekcji lub stron w razie potrzeby. Każde lokalne hiperłącze można dostosować do jego celu.

#### P: Czy mogę linkować do konkretnych sekcji strony za pomocą lokalnych hiperłączy?

A: Podczas gdy lokalne hiperłącza zazwyczaj prowadzą do całych stron, możesz tworzyć kotwice lub zakładki w dokumencie PDF, aby uzyskać ukierunkowane łączenie. Aspose.PDF dla .NET obsługuje różne opcje hiperłączy.

#### P: Jak mogę sprawdzić, czy moje lokalne hiperłącza działają prawidłowo?

A: Postępując zgodnie z samouczkiem i przykładowym kodem, możesz pewnie tworzyć funkcjonalne lokalne hiperłącza. Możesz przetestować łącza, otwierając wygenerowany dokument PDF i klikając na tekst hiperłącza.

#### P: Czy istnieją jakieś ograniczenia przy korzystaniu z lokalnych hiperłączy?

A: Lokalne hiperłącza są skutecznym sposobem na ulepszenie nawigacji w dokumencie, ale ważne jest, aby struktura dokumentu pozostała przejrzysta i intuicyjna. Prawidłowo oznaczone hiperłącza i kotwice przyczyniają się do pozytywnych doświadczeń użytkownika.

#### P: Czy mogę tworzyć lokalne hiperłącza w tabelach i obrazach?

A: Tak, możesz tworzyć lokalne hiperłącza w różnych elementach dokumentu PDF, w tym tabelach, obrazach i tekście. Aspose.PDF dla .NET oferuje elastyczność w dodawaniu hiperłączy do różnych typów treści.