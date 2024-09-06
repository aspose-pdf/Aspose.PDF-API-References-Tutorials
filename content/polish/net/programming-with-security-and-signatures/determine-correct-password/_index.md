---
title: Określ prawidłowe hasło w pliku PDF
linktitle: Określ prawidłowe hasło w pliku PDF
second_title: Aspose.PDF dla .NET API Reference
description: Dowiedz się, jak ustalić prawidłowe hasło w pliku PDF za pomocą Aspose.PDF dla platformy .NET.
type: docs
weight: 30
url: /pl/net/programming-with-security-and-signatures/determine-correct-password/
---
W tym samouczku przeprowadzimy Cię przez proces określania prawidłowego hasła w pliku PDF przy użyciu Aspose.PDF dla .NET. Ta funkcja umożliwia sprawdzenie, czy plik PDF jest chroniony hasłem i znalezienie prawidłowego hasła z predefiniowanej listy.

## Krok 1: Wymagania wstępne

Zanim zaczniesz, upewnij się, że spełniasz następujące wymagania wstępne:

- Podstawowa znajomość języka programowania C#
- Instalowanie programu Visual Studio na komputerze
- Zainstalowano bibliotekę Aspose.PDF dla .NET

## Krok 2: Konfiguracja środowiska

Aby rozpocząć, wykonaj poniższe kroki, aby skonfigurować środowisko programistyczne:

1. Otwórz program Visual Studio i utwórz nowy projekt C#.
2. Zaimportuj wymagane przestrzenie nazw do pliku kodu:

```csharp
using Aspose.Pdf;
```

## Krok 3: Ładowanie pliku źródłowego PDF

Pierwszym krokiem jest przesłanie pliku PDF źródłowego, który chcesz zweryfikować. W tym przykładzie zakładamy, że masz plik PDF o nazwie „IsPasswordProtected.pdf” w określonym katalogu.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
PdfFileInfo info = new PdfFileInfo();
info.BindPdf(dataDir + "IsPasswordProtected.pdf");
```

Pamiętaj, aby zastąpić symbole zastępcze rzeczywistymi lokalizacjami pliku PDF.

## Krok 4: Określ szyfrowanie źródłowego pliku PDF

 Po przesłaniu pliku PDF źródłowego możesz sprawdzić, czy jest on zaszyfrowany, korzystając z`IsEncrypted` metoda`PdfFileInfo` obiekt.

```csharp
Console.WriteLine("The file is password protected: " + info.IsEncrypted);
```

To oświadczenie wyświetla informację, czy plik PDF jest chroniony hasłem, czy nie.

## Krok 5: Znalezienie prawidłowego hasła

Następnie wyszukamy poprawne hasło, używając wstępnie zdefiniowanej listy haseł. Przejdziemy przez każde hasło na liście i spróbujemy załadować dokument PDF z tym hasłem.

```csharp
String[] passwords = new String[5] { "test", "test1", "test2", "test3", "sample" };
for (int passwordcount = 0; passwordcount < passwords.Length; passwordcount++)
{
try
{
Document doc = new Document(dataDir + "IsPasswordProtected.pdf", passwords[passwordcount]);
if (doc.Pages.Count > 0)
Console.WriteLine("The document contains " + doc.Pages.Count + " pages.");
}
catch (InvalidPasswordException)
{
Console.WriteLine("The password " + passwords[passwordcount] + " is not correct.");
}
}
```

Ta pętla testuje każde słowo pass z listy. Jeśli hasło jest poprawne, wyświetlana jest liczba stron w dokumencie. W przeciwnym razie wyświetlana jest wiadomość wskazująca, że hasło jest nieprawidłowe.


### Przykładowy kod źródłowy dla funkcji Określ prawidłowe hasło za pomocą Aspose.PDF dla platformy .NET 
```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENTS DIRECTORY";            
// Załaduj plik źródłowy PDF
PdfFileInfo info = new PdfFileInfo();
info.BindPdf(dataDir + "IsPasswordProtected.pdf");
//Określ, czy źródłowy plik PDF jest zaszyfrowany
Console.WriteLine("File is password protected " + info.IsEncrypted);
String[] passwords = new String[5] { "test", "test1", "test2", "test3", "sample" };
for (int passwordcount = 0; passwordcount < passwords.Length; passwordcount++)
{
	try
	{
		Document doc = new Document(dataDir + "IsPasswordProtected.pdf", passwords[passwordcount]);
		if (doc.Pages.Count > 0)
			Console.WriteLine("Number of Page in document are = " + doc.Pages.Count);
	}
	catch (InvalidPasswordException)
	{
		Console.WriteLine("Password = " + passwords[passwordcount] + "  is not correct");
	}
}
```

## Wniosek

Gratulacje! Udało Ci się ustalić prawidłowe hasło do pliku PDF za pomocą Aspose.PDF dla .NET. Ten samouczek obejmuje proces krok po kroku, od weryfikacji szyfrowania pliku do znalezienia prawidłowego hasła z predefiniowanej listy. Teraz możesz użyć tej funkcji, aby sprawdzić i znaleźć prawidłowe hasło do swoich plików PDF.

### FAQ dotyczące ustalania prawidłowego hasła w pliku PDF

#### P: Jaki jest cel tego poradnika?

A: Ten samouczek ma na celu przeprowadzenie Cię przez proces określania prawidłowego hasła dla pliku PDF przy użyciu Aspose.PDF dla .NET. Ta funkcja umożliwia sprawdzenie, czy plik PDF jest chroniony hasłem i próbę znalezienia prawidłowego hasła z predefiniowanej listy.

#### P: Jakie warunki wstępne należy spełnić przed rozpoczęciem?

O: Zanim zaczniesz, upewnij się, że posiadasz podstawową wiedzę na temat języka programowania C#, że na Twoim komputerze jest zainstalowany program Visual Studio i że jest zainstalowana biblioteka Aspose.PDF dla platformy .NET.

#### P: Jak skonfigurować środowisko programistyczne?

A: Wykonaj podane kroki, aby skonfigurować środowisko programistyczne, m.in. utwórz nowy projekt C# w programie Visual Studio i zaimportuj wymagane przestrzenie nazw.

#### P: Jak sprawdzić, czy plik PDF jest zaszyfrowany?

 A: Użyj`PdfFileInfo` klasa do powiązania pliku PDF źródłowego. Następnie użyj`IsEncrypted`właściwość określająca, czy plik PDF jest chroniony hasłem.

#### P: Jak mogę znaleźć prawidłowe hasło do pliku PDF?

A: Po ustaleniu, że plik PDF jest zaszyfrowany, możesz spróbować znaleźć prawidłowe hasło, korzystając z predefiniowanej listy haseł. Dostarczony przykładowy kod pokazuje, jak przejść przez listę, wypróbować każde hasło i ustalić, czy hasło jest prawidłowe.

#### P: Co się stanie, jeśli uda się znaleźć prawidłowe hasło?

A: Jeśli znalezione zostanie prawidłowe hasło, przykładowy kod wyświetli liczbę stron w dokumencie PDF.

#### P: Co się stanie, jeśli hasło będzie nieprawidłowe?

 A: Jeśli hasło jest nieprawidłowe, przykładowy kod je wychwyci`InvalidPasswordException` i wyświetla komunikat informujący, że hasło jest nieprawidłowe.

#### P: Czy mogę użyć innej listy haseł?

 A: Tak, możesz modyfikować`passwords` w przykładowym kodzie umieść tablicę zawierającą hasła, które chcesz przetestować.

#### P: Skąd będę wiedzieć, że hasło zostało pomyślnie ustalone?

O: Jeśli przykładowy kod poprawnie wczytuje dokument PDF z hasłem i wyświetla liczbę stron, oznacza to, że hasło zostało ustalone prawidłowo.

#### P: Jak mogę zagwarantować bezpieczeństwo moich haseł podczas testów?

A: Zachowaj ostrożność podczas korzystania z predefiniowanej listy haseł i unikaj używania poufnych lub wrażliwych haseł do celów testowych. Ponadto usuń lub zmodyfikuj kod testowy przed wdrożeniem aplikacji.