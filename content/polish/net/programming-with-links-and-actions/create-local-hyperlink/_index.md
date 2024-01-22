---
title: Utwórz lokalne hiperłącze w pliku PDF
linktitle: Utwórz lokalne hiperłącze w pliku PDF
second_title: Aspose.PDF z dokumentacją API .NET
description: Z łatwością twórz lokalne hiperłącza w pliku PDF za pomocą Aspose.PDF dla .NET.
type: docs
weight: 40
url: /pl/net/programming-with-links-and-actions/create-local-hyperlink/
---
Tworzenie lokalnych hiperłączy w pliku PDF umożliwia tworzenie klikalnych łączy przenoszących użytkowników do innych stron tego samego dokumentu PDF. Dzięki Aspose.PDF dla .NET możesz łatwo utworzyć takie linki, postępując zgodnie z następującym kodem źródłowym:

## Krok 1: Zaimportuj wymagane biblioteki

Zanim zaczniesz, musisz zaimportować niezbędne biblioteki dla swojego projektu C#. Oto niezbędna dyrektywa importowa:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
using Aspose.Pdf.InteractiveFeatures;
```

## Krok 2: Ustaw ścieżkę do folderu dokumentów

 W tym kroku musisz określić ścieżkę do folderu, w którym chcesz zapisać wynikowy plik PDF. Zastępować`"YOUR DOCUMENT DIRECTORY"` następującym kodzie z rzeczywistą ścieżką do folderu dokumentów:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Krok 3: Utwórz instancję dokumentu

 Stworzymy instancję`Document` class reprezentująca nasz dokument PDF. Oto odpowiedni kod:

```csharp
Document doc = new Document();
```

## Krok 4: Dodaj stronę i tekst za pomocą hiperłączy

W tym kroku dodamy stronę do naszego dokumentu PDF i dodamy tekst zawierający lokalne hiperłącza. Zdefiniujemy strony docelowe dla każdego linku. Oto odpowiedni kod:

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

 Teraz zapiszmy zaktualizowany plik PDF za pomocą rozszerzenia`Save` metoda`doc` obiekt. Oto odpowiedni kod:

```csharp
dataDir = dataDir + "CreateLocalHyperlink_out.pdf";
doc.Save(dataDir);
```

### Przykładowy kod źródłowy narzędzia Utwórz lokalne hiperłącze przy użyciu Aspose.PDF dla .NET 
```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Utwórz instancję dokumentu
Document doc = new Document();
// Dodaj stronę do kolekcji stron pliku PDF
Page page = doc.Pages.Add();
// Utwórz instancję fragmentu tekstu
Aspose.Pdf.Text.TextFragment text = new Aspose.Pdf.Text.TextFragment("link page number test to page 7");
// Utwórz lokalną instancję hiperłącza
Aspose.Pdf.LocalHyperlink link = new Aspose.Pdf.LocalHyperlink();
// Ustaw stronę docelową dla instancji łącza
link.TargetPageNumber = 7;
// Ustaw hiperłącze TextFragment
text.Hyperlink = link;
//Dodaj tekst do kolekcji akapitów Page
page.Paragraphs.Add(text);
// Utwórz nową instancję TextFragment
text = new TextFragment("link page number test to page 1");
// TextFragment należy dodać na nowej stronie
text.IsInNewPage = true;
// Utwórz kolejną lokalną instancję hiperłącza
link = new LocalHyperlink();
// Ustaw stronę docelową dla drugiego hiperłącza
link.TargetPageNumber = 1;
// Ustaw łącze dla drugiego fragmentu tekstu
text.Hyperlink = link;
// Dodaj tekst do kolekcji akapitów obiektu strony
page.Paragraphs.Add(text);    
dataDir = dataDir + "CreateLocalHyperlink_out.pdf";
// Zapisz zaktualizowany dokument
doc.Save(dataDir);
Console.WriteLine("\nLocal hyperlink created successfully.\nFile saved at " + dataDir);            
```

## Wniosek

Gratulacje! Teraz masz przewodnik krok po kroku dotyczący tworzenia lokalnych hiperłączy w pliku PDF przy użyciu Aspose.PDF dla .NET. Możesz użyć tego kodu, aby utworzyć klikalne linki przenoszące użytkowników do innych stron w tym samym dokumencie.

Koniecznie zapoznaj się z oficjalną dokumentacją Aspose.PDF, aby uzyskać więcej informacji na temat zaawansowanych funkcji hiperłączy.

### Często zadawane pytania dotyczące tworzenia lokalnego hiperłącza w pliku PDF

#### P: Czym są lokalne hiperłącza w pliku PDF?

Odp.: Lokalne hiperłącza w pliku PDF to klikalne łącza, które przenoszą użytkowników do różnych stron w tym samym dokumencie. Linki te usprawniają nawigację i umożliwiają czytelnikom szybki dostęp do odpowiednich sekcji.

#### P: W jaki sposób lokalne hiperłącza mogą pomóc mojemu dokumentowi PDF?

Odp.: Lokalne hiperłącza stanowią skuteczny sposób łączenia powiązanych treści w tym samym dokumencie PDF. Poprawiają wygodę użytkownika, umożliwiając czytelnikom szybkie przechodzenie do określonych sekcji bez konieczności przewijania całego dokumentu.

#### P: W jaki sposób Aspose.PDF dla .NET obsługuje tworzenie lokalnych hiperłączy?
Odp.: Aspose.PDF dla .NET oferuje kompleksową obsługę tworzenia lokalnych hiperłączy. Samouczek krok po kroku zawarty w tym przewodniku pokazuje, jak dodać lokalne hiperłącza do dokumentu PDF przy użyciu języka C#.

#### P: Czy mogę dostosować wygląd lokalnych hiperłączy?

O: Tak, możesz dostosować wygląd lokalnych hiperłączy, w tym kolor i styl tekstu, aby mieć pewność, że pasują one do projektu dokumentu i zapewniają spójne wrażenia wizualne.

#### P: Czy można utworzyć wiele lokalnych hiperłączy na jednej stronie pliku PDF?

Odp.: Absolutnie! Na jednej stronie pliku PDF można utworzyć wiele lokalnych hiperłączy, umożliwiając czytelnikom przechodzenie do różnych sekcji lub stron w razie potrzeby. Każde lokalne hiperłącze można dostosować do odpowiedniego celu.

#### P: Czy mogę utworzyć łącze do określonych sekcji strony za pomocą lokalnych hiperłączy?

Odp.: Chociaż lokalne hiperłącza zazwyczaj prowadzą do całych stron, w dokumencie PDF można tworzyć kotwice lub zakładki, aby uzyskać ukierunkowane linki. Aspose.PDF dla .NET obsługuje różne opcje hiperłączy.

#### P: Jak mogę sprawdzić, czy moje lokalne hiperłącza działają poprawnie?

Odp.: Postępując zgodnie z dostarczonym samouczkiem i przykładowym kodem, możesz z łatwością tworzyć funkcjonalne hiperłącza lokalne. Możesz przetestować łącza, otwierając wygenerowany dokument PDF i klikając tekst hiperłącza.

#### P: Czy istnieją jakieś ograniczenia podczas korzystania z lokalnych hiperłączy?

O: Lokalne hiperłącza to skuteczny sposób na usprawnienie nawigacji w dokumencie, ale ważne jest, aby struktura dokumentu pozostała przejrzysta i intuicyjna. Odpowiednio oznaczone hiperłącza i kotwice przyczyniają się do pozytywnego doświadczenia użytkownika.

#### P: Czy mogę tworzyć lokalne hiperłącza w tabelach lub obrazach?

O: Tak, możesz tworzyć lokalne hiperłącza w różnych elementach dokumentu PDF, w tym w tabelach, obrazach i tekście. Aspose.PDF dla .NET oferuje elastyczność w dodawaniu hiperłączy do różnych typów treści.