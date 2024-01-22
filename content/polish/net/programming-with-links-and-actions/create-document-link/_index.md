---
title: Utwórz łącze do dokumentu
linktitle: Utwórz łącze do dokumentu
second_title: Aspose.PDF z dokumentacją API .NET
description: Z łatwością twórz łącza do innych dokumentów PDF za pomocą Aspose.PDF dla .NET.
type: docs
weight: 30
url: /pl/net/programming-with-links-and-actions/create-document-link/
---
Łączenie z innym dokumentem w pliku PDF umożliwia tworzenie klikalnych łączy przekierowujących użytkowników do innych dokumentów PDF. Dzięki Aspose.PDF dla .NET możesz łatwo utworzyć takie linki, postępując zgodnie z następującym kodem źródłowym:

## Krok 1: Zaimportuj wymagane biblioteki

Zanim zaczniesz, musisz zaimportować niezbędne biblioteki dla swojego projektu C#. Oto niezbędna dyrektywa importowa:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Annotations;
using Aspose.Pdf.InteractiveFeatures;
```

## Krok 2: Ustaw ścieżkę do folderu dokumentów

 tym kroku musisz określić ścieżkę do folderu zawierającego plik PDF, do którego chcesz dodać łącze do innego dokumentu. Zastępować`"YOUR DOCUMENT DIRECTORY"` następującym kodzie z rzeczywistą ścieżką do folderu dokumentów:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Krok 3: Otwórz dokument PDF

Teraz otworzymy dokument PDF, do którego chcemy dodać link do innego dokumentu, używając następującego kodu:

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

 Teraz zapiszmy zaktualizowany plik PDF za pomocą rozszerzenia`Save` metoda`document` obiekt. Oto odpowiedni kod:

```csharp
dataDir = dataDir + "CreateDocumentLink_out.pdf";
document. Save(dataDir);
```

### Przykładowy kod źródłowy narzędzia Utwórz łącze do dokumentu przy użyciu Aspose.PDF dla .NET 
```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Otwórz dokument
Document document = new Document(dataDir+ "CreateDocumentLink.pdf");
// Utwórz łącze
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

Gratulacje! Masz teraz przewodnik krok po kroku dotyczący łączenia z innymi dokumentami za pomocą Aspose.PDF dla .NET. Możesz użyć tego kodu, aby utworzyć klikalne linki w plikach PDF, przekierowując użytkowników do innych dokumentów.

Koniecznie zapoznaj się z oficjalną dokumentacją Aspose.PDF, aby uzyskać więcej informacji na temat zaawansowanych funkcji łączy interaktywnych.

### Często zadawane pytania dotyczące tworzenia łącza do dokumentu

#### P: Czym są łącza do dokumentów w plikach PDF?

Odp.: Łącza do dokumentów w plikach PDF to klikalne łącza, które kierują użytkowników do innych dokumentów PDF. Linki te usprawniają nawigację, zapewniając skuteczny sposób łączenia powiązanych treści i ułatwiają płynne czytanie.

#### P: Jakie korzyści mogę uzyskać z tworzenia łączy do dokumentów?

Odp.: Tworzenie łączy do dokumentów pozwala na ustanowienie połączeń pomiędzy różnymi sekcjami lub tematami w dokumentach PDF. Ta funkcja umożliwia użytkownikom łatwy dostęp do dodatkowych informacji lub powiązanych materiałów.

#### P: W jaki sposób Aspose.PDF dla .NET obsługuje tworzenie łączy do dokumentów?

Odp.: Aspose.PDF dla .NET upraszcza proces tworzenia łączy do dokumentów, udostępniając kompleksowy zestaw interfejsów API. Samouczek krok po kroku opisany w tym przewodniku pokazuje, jak dodawać łącza do dokumentów do plików PDF.

#### P: Czy mogę dostosować wygląd łączy do dokumentów?

Odp.: Absolutnie! Aspose.PDF dla .NET oferuje opcje dostosowywania wyglądu łącza do dokumentu, w tym kolor, styl i efekty najechania. Możesz dostosować wygląd tak, aby pasował do projektu dokumentu.

#### P: Czy możliwe jest utworzenie łącza do określonych sekcji lub stron w innym dokumencie?

O: Tak, możesz tworzyć łącza prowadzące użytkowników do określonych stron lub sekcji w innym dokumencie PDF. Aspose.PDF dla .NET zapewnia elastyczność definiowania lokalizacji docelowej w połączonym dokumencie.

#### P: Jak mogę się upewnić, że łącza do moich dokumentów działają?

Odp.: Postępując zgodnie z dostarczonym samouczkiem i przykładowym kodem, możesz z łatwością tworzyć funkcjonalne łącza do dokumentów. Możesz przetestować łącza, otwierając wygenerowany dokument PDF i klikając łącza.

#### P: Czy mogę utworzyć wiele łączy do dokumentów w jednym pliku PDF?

 Odp.: Oczywiście! Możesz utworzyć wiele łączy do dokumentów w jednym dokumencie PDF, korzystając z opcji`LinkAnnotation`adnotacja. Dzięki temu możesz zapewnić użytkownikom dostęp do różnych powiązanych dokumentów z różnych sekcji.

#### P: Czy istnieją jakieś ograniczenia w przypadku łączenia z dokumentami zewnętrznymi?

Odp.: Łącząc z dokumentami zewnętrznymi, upewnij się, że połączone dokumenty są dostępne i znajdują się w określonych ścieżkach. Ważne jest również rozważenie uprawnień użytkowników i zgodności połączonych dokumentów.

#### P: Czy mogę utworzyć łącze do dokumentów przechowywanych w Internecie lub w repozytoriach online?

Odp.: Chociaż ten samouczek skupia się na łączeniu do dokumentów lokalnych, Aspose.PDF dla .NET obsługuje także łącze do adresów URL lub repozytoriów online. Dostarczony kod można dostosować do tworzenia łączy do dokumentów w Internecie.