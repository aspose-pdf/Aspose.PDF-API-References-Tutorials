---
title: Dodaj Usuń Javascript Do Dokumentu PDF
linktitle: Dodaj Usuń Javascript Do Dokumentu
second_title: Aspose.PDF dla .NET API Reference
description: Dowiedz się, jak dodawać i usuwać JavaScript do dokumentu PDF za pomocą Aspose.PDF dla .NET. Przewodnik krok po kroku z samouczkami kodu dla skryptów na poziomie dokumentu.
type: docs
weight: 30
url: /pl/net/programming-with-document/addremovejavascripttodoc/
---
## Wstęp

W tym przewodniku pokażemy, jak używać Aspose.PDF dla .NET, aby wstawiać JavaScript do pliku PDF i jak go usuwać, gdy jest to konieczne. Do końca tego samouczka będziesz mieć jasne zrozumienie, jak bez wysiłku manipulować JavaScript w plikach PDF.

## Wymagania wstępne

Zanim zagłębimy się w kod, jest kilka rzeczy, które musisz skonfigurować:

1.  Aspose.PDF dla .NET: Będziesz potrzebować biblioteki Aspose.PDF dla .NET zainstalowanej w swoim projekcie. Jeśli jeszcze jej nie masz, pobierz bibliotekę z[Strona pobierania Aspose.PDF dla .NET](https://releases.aspose.com/pdf/net/).
2. IDE lub edytor tekstu: Możesz użyć dowolnego środowiska IDE zgodnego z platformą .NET, np. Visual Studio.
3. Podstawowa wiedza o języku C#: W tym samouczku założono, że znasz język C# i potrafisz manipulować plikami PDF.
4. Licencja: Upewnij się, że stosujesz ważną licencję, aby uniknąć ograniczeń. Możesz uzyskać tymczasową licencję od[Tutaj](https://purchase.aspose.com/temporary-license/).

## Importuj pakiety

Aby rozpocząć korzystanie z Aspose.PDF dla .NET, musisz zaimportować niezbędne przestrzenie nazw do swojego projektu. Oto jak to zrobić:

```csharp
using System.IO;
using System;
using Aspose.Pdf;
using Aspose.Pdf.Annotations;
using Aspose.Pdf.Text;
using System.Collections;
```

 Te dwie przestrzenie nazw są niezbędne.`Aspose.Pdf` umożliwia pracę z dokumentami PDF, podczas gdy`System.Collections` będzie używany do obsługi kluczy JavaScript.

Przedstawimy cały proces dodawania i usuwania kodu JavaScript z pliku PDF w kilku łatwych do wykonania krokach.

## Krok 1: Zainicjuj nowy dokument PDF

Pierwszą rzeczą, którą musisz zrobić, jest utworzenie nowego dokumentu PDF. Ten dokument będzie służył jako nasze puste płótno do dodawania JavaScript.

```csharp
Document doc = new Document();
doc.Pages.Add();
```

 Tutaj inicjujemy nowy`Document` obiekt i dodanie do niego pustej strony. Pomyśl o tym jako o fundamencie swojego PDF-a.

## Krok 2: Dodaj JavaScript do pliku PDF

Teraz, gdy mamy dokument, czas dodać do niego trochę JavaScript. JavaScript w plikach PDF może być używany do dodawania niestandardowych zachowań, takich jak alerty lub walidacja formularza.

```csharp
doc.JavaScript["func1"] = "function func1() { hello(); }";
doc.JavaScript["func2"] = "function func2() { hello(); }";
```

tym fragmencie kodu dodajemy dwie funkcje JavaScript (`func1` I`func2` ) do pliku PDF. Funkcje te mogą wykonywać różne zadania, w zależności od potrzeb. Tutaj po prostu wywołujemy funkcję zastępczą o nazwie`hello()`.

## Krok 3: Zapisz plik PDF za pomocą JavaScript

Po dodaniu żądanego kodu JavaScript czas zapisać plik PDF.

```csharp
doc.Save(dataDir + "AddJavascript.pdf");
```

 Spowoduje to zapisanie dokumentu z JavaScript pod nazwą`AddJavascript.pdf` w określonym katalogu (`dataDir`).

## Krok 4: Załaduj i wyświetl JavaScript w istniejącym pliku PDF

Załóżmy, że musisz sprawdzić lub zmodyfikować funkcje JavaScript w istniejącym pliku PDF. Pierwszym krokiem jest załadowanie pliku PDF i dostęp do kluczy JavaScript.

```csharp
Document doc1 = new Document(dataDir + "AddJavascript.pdf");
IList keys = (System.Collections.IList)doc1.JavaScript.Keys;
```

 Ładujemy istniejące`AddJavascript.pdf` i przechowywanie kluczy JavaScript na liście.`Keys` Właściwość zwraca nazwy wszystkich funkcji JavaScript dołączonych do dokumentu.

## Krok 5: Wyświetl funkcje JavaScript

Następnie możemy przejść przez funkcje JavaScript, aby zobaczyć, co jest dostępne w dokumencie.

```csharp
Console.WriteLine("=============================== ");
foreach (string key in keys)
{
    Console.WriteLine(key + " ==> " + doc1.JavaScript[key]);
}
```

Spowoduje to wydrukowanie każdej nazwy funkcji JavaScript i odpowiadającego jej kodu na konsoli. Jest to przydatne, jeśli chcesz sprawdzić, jakie funkcje są obecnie w dokumencie.

## Krok 6: Usuń JavaScript z pliku PDF

 Załóżmy teraz, że chcesz usunąć określoną funkcję JavaScript, taką jak`func1`Oto jak możesz to zrobić:

```csharp
doc1.JavaScript.Remove("func1");
Console.WriteLine("Key 'func1' removed ");
```

 Ten`Remove` Metoda przyjmuje nazwę funkcji JavaScript jako argument i usuwa ją z dokumentu.

## Krok 7: Zweryfikuj usunięcie JavaScript

 Po usunięciu JavaScript możesz wydrukować ponownie pozostałe funkcje, aby to potwierdzić`func1` został pomyślnie usunięty.

```csharp
Console.WriteLine("=============================== ");
foreach (string key in keys)
{
    Console.WriteLine(key + " ==> " + doc1.JavaScript[key]);
}
Console.WriteLine("Javascript added/removed successfully.");
```

Ta ostatnia część kodu zapewnia, że wszystko jest na swoim miejscu i funkcje JavaScript są poprawnie aktualizowane.

## Wniosek

Gratulacje! Właśnie nauczyłeś się, jak dodawać i usuwać JavaScript z dokumentu PDF za pomocą Aspose.PDF dla .NET. Ta potężna funkcja może być wykorzystywana do różnych zadań, od dodawania dynamicznych wiadomości po wykonywanie niestandardowych obliczeń lub walidacji. Manipulując JavaScript w pliku PDF, możesz znacznie poprawić wrażenia użytkownika.

## Najczęściej zadawane pytania

### Czy mogę dodać wiele funkcji JavaScript do jednego pliku PDF?
 Oczywiście! Możesz dodać tyle funkcji JavaScript, ile potrzebujesz, używając`doc.JavaScript` kolekcja.

### Co się stanie, jeśli spróbuję usunąć nieistniejącą funkcję JavaScript?
 Jeżeli funkcja nie istnieje,`Remove` Metoda nie zgłosi błędu, ale też niczego nie usunie.

### Czy można uruchomić JavaScript od razu po otwarciu pliku PDF?
Tak! Możesz skonfigurować JavaScript, aby działał na określonych wyzwalaczach, takich jak otwieranie dokumentu lub klikanie przycisku.

### Czy mogę edytować JavaScript po dodaniu go do pliku PDF?
Tak, możesz załadować istniejący plik PDF, uzyskać dostęp do jego kodu JavaScript, zmodyfikować kod i ponownie zapisać dokument.

### Czy usunięcie JavaScriptu ma wpływ na pozostałą zawartość pliku PDF?
Nie, usunięcie JavaScript wpływa tylko na skrypt. Zawartość pliku PDF pozostaje niezmieniona.