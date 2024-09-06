---
title: Podpisz cyfrowo z znacznikiem czasu w pliku PDF
linktitle: Podpisz cyfrowo z znacznikiem czasu w pliku PDF
second_title: Aspose.PDF dla .NET API Reference
description: Dowiedz się, jak dodać podpis cyfrowy ze znacznikiem czasu do pliku PDF przy użyciu Aspose.PDF dla platformy .NET.
type: docs
weight: 50
url: /pl/net/programming-with-security-and-signatures/digitally-sign-with-time-stamp/
---
W tym samouczku przeprowadzimy Cię przez proces cyfrowego podpisywania pliku PDF ze znacznikiem czasu przy użyciu Aspose.PDF dla .NET. Cyfrowy podpis ze znacznikiem czasu gwarantuje autentyczność i integralność dokumentu, poprzez dodanie elektronicznego odcisku palca ze znacznikiem czasu.

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
using Aspose.Pdf.Forms;
```

## Krok 3: Podpis cyfrowy ze znacznikiem czasu

Pierwszym krokiem jest wykonanie podpisu cyfrowego ze znacznikiem czasu na pliku PDF. Dostarczony kod pokazuje, jak uzyskać ten podpis za pomocą Aspose.PDF dla .NET.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
string pfxFile = "";
using (Document document = new Document(dataDir + @"DigitallySign.pdf"))
{
     using (PdfFileSignature signature = new PdfFileSignature(document))
     {
         PKCS7 pkcs = new PKCS7(pfxFile, "pfx_password");
         TimestampSettings timestampSettings = new TimestampSettings("https:\\your_timestamp_settings", "user:password");
         pkcs. TimestampSettings = timestampSettings;
         System.Drawing.Rectangle rect = new System.Drawing.Rectangle(100, 100, 200, 100);
         signature.Sign(1, "Reason for signing", "Contact", "Location", true, rect, pkcs);
         signature.Save(dataDir + "DigitallySignWithTimeStamp_out.pdf");
     }
}
```

Ten kod ładuje plik PDF, tworzy podpis cyfrowy ze znacznikiem czasu przy użyciu pliku PFX (klucz prywatny) i określonych parametrów znacznika czasu. Następnie podpis jest dodawany do pliku PDF i zapisywany z sufiksem „_na zewnątrz".

### Przykładowy kod źródłowy dla funkcji Digitally Sign With Time Stamp przy użyciu Aspose.PDF dla platformy .NET 
```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
string pfxFile = "";
using (Document document = new Document(dataDir + @"DigitallySign.pdf"))
{
	using (PdfFileSignature signature = new PdfFileSignature(document))
	{
		PKCS7 pkcs = new PKCS7(pfxFile, "pfx_password");
		TimestampSettings timestampSettings = new TimestampSettings("https:\\your_timestamp_settings", "user:password"); // Użytkownik/Hasło można pominąć
		pkcs.TimestampSettings = timestampSettings;
		System.Drawing.Rectangle rect = new System.Drawing.Rectangle(100, 100, 200, 100);
		// Utwórz dowolny z trzech typów podpisu
		signature.Sign(1, "Signature Reason", "Contact", "Location", true, rect, pkcs);
		// Zapisz plik wyjściowy PDF
		signature.Save(dataDir + "DigitallySignWithTimeStamp_out.pdf");
	}
}
```

## Wniosek

Gratulacje! Udało Ci się pomyślnie wykonać podpis cyfrowy ze znacznikiem czasu w pliku PDF przy użyciu Aspose.PDF dla .NET. Ten samouczek obejmuje proces krok po kroku od utworzenia podpisu do zapisania zaktualizowanego pliku PDF. Teraz możesz użyć tej funkcji, aby dodać podpisy cyfrowe ze znacznikiem czasu do swoich plików PDF.

### Często zadawane pytania dotyczące cyfrowego podpisywania plików PDF znacznikiem czasu

#### P: Jaki jest cel składania podpisu cyfrowego za pomocą znacznika czasu?

A: Podpisanie cyfrowe ze znacznikiem czasu dodaje do pliku PDF elektroniczny odcisk palca ze znacznikiem czasu, gwarantując autentyczność i integralność dokumentu w określonym momencie.

#### P: Jakie warunki wstępne są konieczne, aby rozpocząć korzystanie z tego samouczka?

O: Zanim zaczniesz, upewnij się, że posiadasz podstawową wiedzę na temat języka programowania C#, masz zainstalowany program Visual Studio i bibliotekę Aspose.PDF dla platformy .NET.

#### P: Jak mogę skonfigurować środowisko programistyczne?

A: Wykonaj podane kroki, aby skonfigurować środowisko programistyczne, m.in. utwórz nowy projekt C# w programie Visual Studio i zaimportuj niezbędne przestrzenie nazw.

#### P: Jak dodać podpis cyfrowy ze znacznikiem czasu do pliku PDF?

A: Dostarczony przykładowy kod pokazuje, jak załadować plik PDF, utworzyć podpis cyfrowy ze znacznikiem czasu za pomocą pliku PFX (klucz prywatny) i określonych ustawień znacznika czasu, dodać podpis do pliku PDF i zapisać zaktualizowany plik.

#### P: Czym jest plik PFX i dlaczego został użyty w przykładzie?

A: Plik PFX (Personal Exchange Format) zawiera klucz prywatny i certyfikat. Jest on tutaj używany do zapewnienia kryptograficznej funkcjonalności dla podpisów cyfrowych. Upewnij się, że zastępujesz symbol zastępczy swoim plikiem PFX i hasłem.

#### P: Czym są ustawienia znacznika czasu?

A: TimestampSettings definiuje ustawienia serwera znaczników czasu używanego do dodawania elektronicznego znacznika czasu do podpisu. Obejmuje adres URL serwera znaczników czasu i opcjonalne dane uwierzytelniające użytkownika.

#### P: Czy mogę użyć innego serwera znaczników czasu niż ten w przykładzie?
 A: Tak, możesz użyć dowolnego zgodnego serwera znaczników czasu. Zastąp adres URL i, jeśli to konieczne, podaj odpowiednie dane uwierzytelniające użytkownika w`TimestampSettings` obiekt.

#### P: Jaki jest cel określenia prostokąta podpisu?

A: Prostokąt podpisu definiuje pozycję i wymiary wyglądu podpisu cyfrowego na stronie PDF. Dostosuj te wartości, aby umieścić podpis zgodnie z oczekiwaniami.

#### P: Co się stanie, jeśli podczas podpisywania serwer znaczników czasu będzie niedostępny?

A: Jeśli serwer znaczników czasu jest niedostępny podczas podpisywania, proces może się nie powieść lub potrwać dłużej. Upewnij się, że serwer znaczników czasu jest niezawodny i dostępny.

#### P: Jak mogę sprawdzić obecność znacznika czasu w podpisanym pliku PDF?

 A: Możesz sprawdzić podpisany plik PDF, korzystając z przykładowego kodu.`TimestampSettings` którego użyłeś podczas podpisywania, powinien być dostępny w szczegółach podpisu.

#### P: Czy podpisy cyfrowe ze znacznikami czasu są prawnie wiążące?

A: Podpisy cyfrowe ze znacznikami czasu mają wartość prawną w wielu jurysdykcjach i są często uważane za bardziej niezawodne niż proste podpisy cyfrowe. Skonsultuj się z ekspertami prawnymi w swojej jurysdykcji, aby uzyskać szczegółowe przepisy.

#### P: Czy mogę dodać do pliku PDF wiele podpisów cyfrowych ze znacznikami czasu?

A: Tak, możesz dodać wiele podpisów cyfrowych ze znacznikami czasu do pliku PDF, wywołując proces tworzenia podpisu wiele razy. Każdy podpis będzie miał swój własny znacznik czasu.