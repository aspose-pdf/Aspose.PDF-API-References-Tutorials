---
title: Dodaj skrypt Java do pliku PDF
linktitle: Dodaj plik PDF ze skryptem Java
second_title: Aspose.PDF z dokumentacją API .NET
description: Dowiedz się, jak dodać JavaScript do pliku PDF przy użyciu Aspose.PDF dla .NET. Przewodnik krok po kroku z samouczkami dotyczącymi kodu umożliwiającymi tworzenie skryptów na poziomie dokumentu i strony.
type: docs
weight: 10
url: /pl/net/programming-with-document/addjavascripttopage/
---
Aby dodać JavaScript do pliku PDF, użyjemy Aspose.PDF dla .NET. Ta biblioteka zapewnia prosty i wydajny sposób pracy z plikami PDF w aplikacjach .NET. Poniższe kroki poprowadzą Cię przez proces dodawania JavaScript do pliku PDF przy użyciu Aspose.PDF dla .NET.

## Krok 1: Załaduj plik PDF

 Pierwszym krokiem jest załadowanie pliku PDF, do którego chcesz dodać JavaScript. Można to zrobić za pomocą`Document` klasa dostarczona przez Aspose.PDF dla .NET. The`Document` klasa udostępnia metody ładowania, zapisywania i manipulowania plikami PDF.

```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Załaduj istniejące pliki PDF
Document doc = new Document(dataDir + "input.pdf");
```

## Krok 2: Dodaj JavaScript na poziomie dokumentu

Aby dodać JavaScript na poziomie dokumentu, użyjemy metody`JavascriptAction` klasa dostarczona przez Aspose.PDF dla .NET. Ta klasa umożliwia określenie instrukcji JavaScript, którą chcesz dodać do pliku PDF.

```csharp
// Dodawanie JavaScriptu na poziomie dokumentu
// Utwórz instancję JavaScriptAction z żądaną instrukcją JavaScript
JavascriptAction javaScript = new JavascriptAction("this.print({bUI:true,bSilent:false,bShrinkToFit:true});");

// Przypisz obiekt JavascriptAction do żądanej akcji dokumentu
doc.OpenAction = javaScript;
```

W tym samouczku dodamy instrukcję JavaScript, która po otwarciu dokumentu wydrukuje plik PDF z określonymi opcjami.

## Krok 3: Dodaj JavaScript na poziomie strony

 Aby dodać JavaScript na poziomie strony, użyjemy metody`JavascriptAction` klasa i`Actions` właściwość udostępniona przez Aspose.PDF dla .NET. Ta właściwość pozwala określić instrukcje JavaScript, które zostaną wykonane po otwarciu lub zamknięciu strony.

```csharp
// Dodanie JavaScriptu na poziomie strony
doc.Pages[2].Actions.OnOpen = new JavascriptAction("app.alert('page 1 opened')");
doc.Pages[2].Actions.OnClose = new JavascriptAction("app.alert('page 1 closed')");
```

W tym samouczku dodajemy instrukcje JavaScript, które będą wyświetlać komunikat ostrzegawczy po otwarciu lub zamknięciu strony.

## Krok 4: Zapisz plik PDF

Po dodaniu kodu JavaScript do pliku PDF należy zapisać zmodyfikowany plik. Można to zrobić za pomocą`Save` metoda podana przez`Document` klasa.

```csharp
dataDir = dataDir + "JavaScript-Added_out.pdf";
// Zapisz dokument PDF
doc.Save(dataDir);

Console.WriteLine("\nJavascript added successfully to a page.\nFile saved at " + dataDir);
```

Ten kod zapisze zmodyfikowany plik PDF w określonym katalogu.

### Przykładowy kod źródłowy dla opcji Dodaj skrypt Java do strony przy użyciu Aspose.PDF dla .NET

```csharp
            
// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Załaduj istniejące pliki PDF
Document doc = new Document(dataDir + "input.pdf");

// Dodawanie JavaScriptu na poziomie dokumentu
// Utwórz instancję JavaScriptAction z żądaną instrukcją JavaScript
JavascriptAction javaScript = new JavascriptAction("this.print({bUI:true,bSilent:false,bShrinkToFit:true});");

// Przypisz obiekt JavascriptAction do żądanej akcji dokumentu
doc.OpenAction = javaScript;

// Dodanie JavaScriptu na poziomie strony
doc.Pages[2].Actions.OnOpen = new JavascriptAction("app.alert('page 1 opened')");
doc.Pages[2].Actions.OnClose = new JavascriptAction("app.alert('page 1 closed')");

dataDir = dataDir + "JavaScript-Added_out.pdf";
// Zapisz dokument PDF
doc.Save(dataDir);

Console.WriteLine("\nJavascript added successfully to a page.\nFile saved at " + dataDir);     
```

## Wniosek

W tym artykule wyjaśniliśmy, jak dodać JavaScript do pliku PDF zarówno na poziomie dokumentu, jak i na poziomie strony, używając Aspose.PDF dla .NET. Do każdego przykładu dołączyliśmy instrukcje krok po kroku i pełny kod źródłowy. Dzięki tej wiedzy możesz dodać JavaScript do swoich plików PDF i dostosować ich zachowanie do swoich potrzeb.


### Często zadawane pytania dotyczące dodawania skryptu Java do pliku PDF

#### P: Co to jest Aspose.PDF dla .NET?

O: Aspose.PDF dla .NET to potężna biblioteka, która umożliwia programistom pracę z plikami PDF w aplikacjach .NET. Zapewnia szeroką gamę funkcji do tworzenia, modyfikowania i manipulowania dokumentami PDF.

#### P: Czy mogę dodać JavaScript do dokumentu PDF przy użyciu Aspose.PDF dla .NET?

Odp.: Tak, Aspose.PDF dla .NET umożliwia dodanie JavaScript zarówno na poziomie dokumentu, jak i na poziomie strony pliku PDF, umożliwiając tworzenie dynamicznych i interaktywnych dokumentów PDF.

#### P: Jak załadować istniejący plik PDF przy użyciu Aspose.PDF dla .NET?

 Odp.: Możesz załadować istniejący plik PDF za pomocą`Document` class i jej metody, jak pokazano w przewodniku krok po kroku.

#### P: Jakie typy akcji JavaScript mogę dodać do dokumentu PDF?

Odp.: Dzięki Aspose.PDF dla .NET możesz dodać szeroką gamę akcji JavaScript, takich jak drukowanie, komunikaty ostrzegawcze, manipulowanie polami formularzy i inne.

#### P: Czy Aspose.PDF dla .NET nadaje się do projektów komercyjnych?

O: Tak, Aspose.PDF dla .NET to niezawodna i solidna biblioteka, która jest powszechnie używana w projektach komercyjnych do zadań związanych z manipulacją i generowaniem plików PDF.

