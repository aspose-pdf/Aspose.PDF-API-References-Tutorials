---
title: Określ prawidłowe hasło w pliku PDF
linktitle: Określ prawidłowe hasło w pliku PDF
second_title: Aspose.PDF z dokumentacją API .NET
description: Dowiedz się, jak ustalić prawidłowe hasło w pliku PDF za pomocą Aspose.PDF dla .NET.
type: docs
weight: 30
url: /pl/net/programming-with-security-and-signatures/determine-correct-password/
---
W tym samouczku przeprowadzimy Cię przez proces ustalania prawidłowego hasła w pliku PDF przy użyciu Aspose.PDF dla .NET. Ta funkcja pozwala sprawdzić, czy plik PDF jest chroniony hasłem i znaleźć prawidłowe hasło ze wstępnie zdefiniowanej listy.

## Krok 1: Warunki wstępne

Zanim zaczniesz, upewnij się, że masz następujące wymagania wstępne:

- Podstawowa znajomość języka programowania C#
- Instalowanie programu Visual Studio na komputerze
- Zainstalowana biblioteka Aspose.PDF dla .NET

## Krok 2: Konfiguracja środowiska

Aby rozpocząć, wykonaj następujące kroki, aby skonfigurować środowisko programistyczne:

1. Otwórz program Visual Studio i utwórz nowy projekt C#.
2. Zaimportuj wymagane przestrzenie nazw do pliku kodu:

```csharp
using Aspose.Pdf;
```

## Krok 3: Ładowanie źródłowego pliku PDF

Pierwszym krokiem jest przesłanie źródłowego pliku PDF, który chcesz zweryfikować. W tym przykładzie zakładamy, że masz plik PDF o nazwie „IsPasswordProtected.pdf” w określonym katalogu.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
PdfFileInfo info = new PdfFileInfo();
info.BindPdf(dataDir + "IsPasswordProtected.pdf");
```

Pamiętaj, aby zastąpić symbole zastępcze rzeczywistymi lokalizacjami pliku PDF.

## Krok 4: Określ szyfrowanie źródłowego pliku PDF

Po przesłaniu źródłowego pliku PDF możesz określić, czy jest on zaszyfrowany za pomocą`IsEncrypted` metoda`PdfFileInfo` obiekt.

```csharp
Console.WriteLine("The file is password protected: " + info.IsEncrypted);
```

To oświadczenie wyświetla, czy plik PDF jest chroniony hasłem, czy nie.

## Krok 5: Znalezienie prawidłowego hasła

Następnie wyszukamy prawidłowe hasło korzystając z predefiniowanej listy haseł. Przeglądamy każde hasło na liście i próbujemy załadować dokument PDF z tym hasłem.

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

Ta pętla sprawdza każde słowo pass z listy. Jeżeli hasło jest prawidłowe, wyświetlona zostanie liczba stron dokumentu. W przeciwnym razie wyświetli się komunikat informujący, że hasło jest nieprawidłowe.


### Przykładowy kod źródłowy dla określenia prawidłowego hasła przy użyciu Aspose.PDF dla .NET 
```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENTS DIRECTORY";            
// Załaduj źródłowy plik PDF
PdfFileInfo info = new PdfFileInfo();
info.BindPdf(dataDir + "IsPasswordProtected.pdf");
// Sprawdź, czy źródłowy plik PDF jest zaszyfrowany
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

Gratulacje! Pomyślnie ustaliłeś prawidłowe hasło do pliku PDF przy użyciu Aspose.PDF dla .NET. W tym samouczku omówiono proces krok po kroku, od weryfikacji szyfrowania plików po znalezienie prawidłowego hasła z predefiniowanej listy. Teraz możesz użyć tej funkcji, aby sprawdzić i znaleźć prawidłowe hasło do swoich plików PDF.

### Często zadawane pytania dotyczące ustalenia prawidłowego hasła w pliku PDF

#### P: Jaki jest cel tego samouczka?

Odp.: Ten samouczek ma na celu poprowadzić Cię przez proces ustalania prawidłowego hasła do pliku PDF przy użyciu Aspose.PDF dla .NET. Ta funkcja pozwala sprawdzić, czy plik PDF jest chroniony hasłem i spróbować znaleźć prawidłowe hasło ze wstępnie zdefiniowanej listy.

#### P: Jakie wymagania wstępne są wymagane przed rozpoczęciem?

O: Zanim zaczniesz, upewnij się, że masz podstawową wiedzę na temat języka programowania C#, masz zainstalowany program Visual Studio na swoim komputerze i masz zainstalowaną bibliotekę Aspose.PDF dla .NET.

#### P: Jak skonfigurować środowisko programistyczne?

Odp.: Wykonaj podane kroki, aby skonfigurować środowisko programistyczne, w tym utworzyć nowy projekt C# w programie Visual Studio i zaimportować wymagane przestrzenie nazw.

#### P: Jak sprawdzić, czy plik PDF jest zaszyfrowany?

 O: Skorzystaj z`PdfFileInfo` class, aby powiązać źródłowy plik PDF. Następnie skorzystaj z`IsEncrypted` właściwość, aby określić, czy plik PDF jest chroniony hasłem.

#### P: Jak znaleźć prawidłowe hasło do pliku PDF?

O: Po ustaleniu, że plik PDF jest zaszyfrowany, możesz spróbować znaleźć prawidłowe hasło, korzystając ze wstępnie zdefiniowanej listy haseł. Dostarczony przykładowy kod demonstruje, jak przeglądać listę, wypróbowywać każde hasło i sprawdzać, czy jest ono poprawne.

#### P: Co się stanie, jeśli zostanie znalezione prawidłowe hasło?

Odp.: Jeśli zostanie znalezione prawidłowe hasło, przykładowy kod wyświetli liczbę stron w dokumencie PDF.

#### P: Co się stanie, jeśli hasło nie będzie poprawne?

 Odp.: Jeśli hasło jest nieprawidłowe, przykładowy kod przechwyci błąd`InvalidPasswordException` i wyświetlić komunikat informujący, że hasło jest nieprawidłowe.

#### P: Czy mogę użyć innej listy haseł?

 Odp.: Tak, możesz modyfikować plik`passwords` array w przykładowym kodzie, aby uwzględnić hasła, które chcesz przetestować.

#### P: Skąd mam wiedzieć, że hasło zostało pomyślnie ustalone?

Odp.: Jeśli przykładowy kod pomyślnie załaduje dokument PDF z hasłem i wyświetli liczbę stron, oznacza to, że ustalono prawidłowe hasło.

#### P: Jak mogę zapewnić bezpieczeństwo moich haseł podczas testowania?

O: Zachowaj ostrożność podczas korzystania z predefiniowanej listy haseł i unikaj używania wrażliwych lub poufnych haseł do celów testowych. Ponadto przed wdrożeniem aplikacji usuń lub zmodyfikuj kod testowy.