---
title: Utwórz łącze do dokumentu
linktitle: Utwórz łącze do dokumentu
second_title: Aspose.PDF dla .NET API Reference
description: Łatwe tworzenie linków do innych dokumentów PDF za pomocą Aspose.PDF dla .NET.
type: docs
weight: 30
url: /pl/net/programming-with-links-and-actions/create-document-link/
---
Łączenie z innym dokumentem w pliku PDF umożliwia tworzenie klikalnych linków, które przekierowują użytkowników do innych dokumentów PDF. Dzięki Aspose.PDF dla .NET możesz łatwo tworzyć takie linki, postępując zgodnie z następującym kodem źródłowym:

## Krok 1: Importuj wymagane biblioteki

Zanim zaczniesz, musisz zaimportować niezbędne biblioteki dla swojego projektu C#. Oto niezbędna dyrektywa importu:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Annotations;
using Aspose.Pdf.InteractiveFeatures;
```

## Krok 2: Ustaw ścieżkę do folderu dokumentów

 W tym kroku musisz określić ścieżkę do folderu zawierającego plik PDF, do którego chcesz dodać łącze do innego dokumentu. Zastąp`"YOUR DOCUMENT DIRECTORY"` w poniższym kodzie podaj rzeczywistą ścieżkę do folderu z dokumentami:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Krok 3: Otwórz dokument PDF

Teraz otworzymy dokument PDF, do którego chcemy dodać link do innego dokumentu, korzystając z następującego kodu:

```csharp
Document document = new Document(dataDir + "CreateDocumentLink.pdf");
```

## Krok 4: Utwórz łącze do innego dokumentu

 W tym kroku utworzymy łącze do innego dokumentu za pomocą`LinkAnnotation` adnotacja. Określimy współrzędne i obszar łącza, a także akcję nawigacyjną do dokumentu zewnętrznego. Oto odpowiedni kod:

```csharp
Page page = document.Pages[1];
LinkAnnotation link = new LinkAnnotation(page, new Aspose.Pdf.Rectangle(100, 100, 300, 300));
link.Color = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Green);
link. Action = new GoToRemoteAction(dataDir + "RemoveOpenAction.pdf", 1);
page.Annotations.Add(link);
```

## Krok 5: Zapisz zaktualizowany plik

Teraz zapiszmy zaktualizowany plik PDF za pomocą`Save` metoda`document` obiekt. Oto odpowiadający kod:

```csharp
dataDir = dataDir + "CreateDocumentLink_out.pdf";
document. Save(dataDir);
```

### Przykładowy kod źródłowy dla funkcji Create Document Link using Aspose.PDF for .NET 
```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Otwórz dokument
Document document = new Document(dataDir+ "CreateDocumentLink.pdf");
// Utwórz link
Page page = document.Pages[1];
LinkAnnotation link = new LinkAnnotation(page, new Aspose.Pdf.Rectangle(100, 100, 300, 300));
link.Color = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Green);
link.Action = new GoToRemoteAction(dataDir + "RemoveOpenAction.pdf", 1);
page.Annotations.Add(link);
dataDir = dataDir + "CreateDocumentLink_out.pdf";
// Zapisz zaktualizowany dokument
document.Save(dataDir);
Console.WriteLine("\nDocument link created successfully.\nFile saved at " + dataDir);            
```

## Wniosek

Gratulacje! Masz teraz przewodnik krok po kroku, jak łączyć się z innymi dokumentami za pomocą Aspose.PDF dla .NET. Możesz użyć tego kodu, aby tworzyć klikalne linki w plikach PDF, przekierowując użytkowników do innych dokumentów.

Koniecznie zapoznaj się z oficjalną dokumentacją Aspose.PDF, aby uzyskać więcej informacji na temat zaawansowanych funkcji interaktywnych łączy.

### Często zadawane pytania dotyczące tworzenia łącza do dokumentu

#### P: Czym są linki do dokumentów w plikach PDF?

A: Linki do dokumentów w plikach PDF to klikalne linki, które kierują użytkowników do innych dokumentów PDF. Te linki usprawniają nawigację, zapewniając wydajny sposób łączenia powiązanych treści i ułatwiając bezproblemowe czytanie.

#### P: Jakie korzyści mogę odnieść dzięki tworzeniu linków do dokumentów?

A: Tworzenie linków do dokumentów umożliwia nawiązywanie połączeń między różnymi sekcjami lub tematami w dokumentach PDF. Ta funkcja umożliwia użytkownikom łatwy dostęp do informacji uzupełniających lub powiązanych materiałów.

#### P: W jaki sposób Aspose.PDF dla platformy .NET obsługuje tworzenie łączy do dokumentów?

A: Aspose.PDF dla .NET upraszcza proces tworzenia linków do dokumentów, zapewniając kompleksowy zestaw interfejsów API. Samouczek krok po kroku opisany w tym przewodniku pokazuje, jak dodawać linki do dokumentów do plików PDF.

#### P: Czy mogę dostosować wygląd linków do dokumentów?

A: Oczywiście! Aspose.PDF dla .NET oferuje opcje dostosowywania wyglądu linku dokumentu, w tym kolor, styl i efekty najechania kursorem. Możesz dostosować wygląd do projektu dokumentu.

#### P: Czy można tworzyć linki do konkretnych sekcji lub stron w innym dokumencie?

A: Tak, możesz tworzyć linki, które kierują użytkowników do określonych stron lub sekcji w innym dokumencie PDF. Aspose.PDF dla .NET zapewnia elastyczność definiowania lokalizacji docelowej w połączonym dokumencie.

#### P: Jak mogę mieć pewność, że linki do moich dokumentów będą działać?

A: Postępując zgodnie z dostarczonym samouczkiem i przykładowym kodem, możesz pewnie tworzyć funkcjonalne linki do dokumentów. Możesz przetestować linki, otwierając wygenerowany dokument PDF i klikając na linki.

#### P: Czy mogę utworzyć wiele linków do dokumentów w jednym pliku PDF?

 A: Oczywiście! Możesz utworzyć wiele linków do dokumentów w jednym dokumencie PDF, używając`LinkAnnotation` adnotacja. Pozwala to zapewnić użytkownikom dostęp do różnych powiązanych dokumentów z różnych sekcji.

#### P: Czy istnieją jakieś ograniczenia przy linkowaniu do dokumentów zewnętrznych?

A: Podczas linkowania do dokumentów zewnętrznych upewnij się, że powiązane dokumenty są dostępne i znajdują się w określonych ścieżkach. Ważne jest również uwzględnienie uprawnień użytkownika i zgodności powiązanych dokumentów.

#### P: Czy mogę linkować do dokumentów przechowywanych w sieci lub repozytoriach online?

A: Podczas gdy ten samouczek koncentruje się na linkowaniu do lokalnych dokumentów, Aspose.PDF dla .NET obsługuje również linkowanie do adresów URL w sieci lub repozytoriów online. Możesz dostosować dostarczony kod, aby tworzyć linki do dokumentów w sieci.