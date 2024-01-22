---
title: Podpisz cyfrowo znacznikiem czasu w pliku PDF
linktitle: Podpisz cyfrowo znacznikiem czasu w pliku PDF
second_title: Aspose.PDF z dokumentacją API .NET
description: Dowiedz się, jak wykonać podpis cyfrowy ze znacznikiem czasu w pliku PDF przy użyciu Aspose.PDF dla .NET.
type: docs
weight: 50
url: /pl/net/programming-with-security-and-signatures/digitally-sign-with-time-stamp/
---
W tym samouczku przeprowadzimy Cię przez proces cyfrowego podpisywania pliku PDF ze znacznikiem czasu przy użyciu Aspose.PDF dla .NET. Podpis cyfrowy ze znacznikiem czasu gwarantuje autentyczność i integralność dokumentu, poprzez dodanie elektronicznego odcisku palca ze znacznikiem czasu.

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
using Aspose.Pdf.Forms;
```

## Krok 3: Podpis cyfrowy ze znacznikiem czasu

Pierwszym krokiem jest złożenie podpisu cyfrowego wraz ze znacznikiem czasu na pliku PDF. Dostarczony kod pokazuje, jak uzyskać ten podpis za pomocą Aspose.PDF dla .NET.

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

Ten kod ładuje plik PDF, tworzy podpis cyfrowy ze znacznikiem czasu przy użyciu pliku PFX (klucz prywatny) i określonych parametrów znacznika czasu. Podpis jest następnie dodawany do pliku PDF i zapisywany z przyrostkiem „_na zewnątrz".

### Przykładowy kod źródłowy funkcji Podpisz cyfrowo ze znacznikiem czasu przy użyciu Aspose.PDF dla .NET 
```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
string pfxFile = "";
using (Document document = new Document(dataDir + @"DigitallySign.pdf"))
{
	using (PdfFileSignature signature = new PdfFileSignature(document))
	{
		PKCS7 pkcs = new PKCS7(pfxFile, "pfx_password");
		TimestampSettings timestampSettings = new TimestampSettings("https:\\your_timestamp_settings", "user:password"); // Użytkownik/hasło można pominąć
		pkcs.TimestampSettings = timestampSettings;
		System.Drawing.Rectangle rect = new System.Drawing.Rectangle(100, 100, 200, 100);
		// Utwórz dowolny z trzech typów podpisów
		signature.Sign(1, "Signature Reason", "Contact", "Location", true, rect, pkcs);
		// Zapisz wyjściowy plik PDF
		signature.Save(dataDir + "DigitallySignWithTimeStamp_out.pdf");
	}
}
```

## Wniosek

Gratulacje! Pomyślnie wykonałeś podpis cyfrowy ze znacznikiem czasu na pliku PDF przy użyciu Aspose.PDF dla .NET. W tym samouczku omówiono krok po kroku proces od utworzenia podpisu do zapisania zaktualizowanego pliku PDF. Możesz teraz używać tej funkcji, aby dodawać podpisy cyfrowe ze znacznikiem czasu do plików PDF.

### Często zadawane pytania dotyczące podpisu cyfrowego ze znacznikiem czasu w pliku PDF

#### P: Jaki jest cel cyfrowego podpisywania za pomocą znacznika czasu?

Odp.: Podpisywanie cyfrowe za pomocą znacznika czasu dodaje elektroniczny odcisk palca ze znacznikiem czasu do pliku PDF, zapewniając autentyczność i integralność dokumentu w określonym momencie.

#### P: Jakie wymagania wstępne są potrzebne, aby rozpocząć ten samouczek?

O: Zanim zaczniesz, upewnij się, że znasz podstawowy język programowania C#, masz zainstalowany program Visual Studio i bibliotekę Aspose.PDF dla .NET.

#### P: Jak mogę skonfigurować środowisko programistyczne?

Odp.: Wykonaj podane kroki, aby skonfigurować środowisko programistyczne, w tym utworzyć nowy projekt C# w programie Visual Studio i zaimportować niezbędne przestrzenie nazw.

#### P: Jak dodać podpis cyfrowy ze znacznikiem czasu do pliku PDF?

Odp.: Dostarczony przykładowy kod demonstruje, jak załadować plik PDF, utworzyć podpis cyfrowy ze znacznikiem czasu przy użyciu pliku PFX (klucz prywatny) i określonych ustawień znacznika czasu, dodać podpis do pliku PDF i zapisać zaktualizowany plik.

#### P: Co to jest plik PFX i dlaczego został użyty w przykładzie?

Odp.: Plik PFX (Personal Exchange Format) zawiera klucz prywatny i certyfikat. Służy tutaj do zapewnienia funkcjonalności kryptograficznej podpisów cyfrowych. Upewnij się, że zastąpiłeś symbol zastępczy plikiem PFX i hasłem.

#### P: Czym są ustawienia znacznika czasu?

Odp.: Ustawienia znacznika czasu definiują ustawienia serwera znacznika czasu używanego do dodawania elektronicznego znacznika czasu do podpisu. Zawiera adres URL serwera sygnatury czasowej i opcjonalne poświadczenia użytkownika.

#### P: Czy mogę użyć serwera znaczników czasu innego niż ten w przykładzie?
 Odp.: Tak, możesz użyć dowolnego kompatybilnego serwera znaczników czasu. Zamień adres URL i, jeśli to konieczne, podaj odpowiednie poświadczenia użytkownika w pliku`TimestampSettings` obiekt.

#### P: Jaki jest cel określenia prostokąta podpisu?

Odpowiedź: Prostokąt podpisu określa położenie i wymiary wyglądu podpisu cyfrowego na stronie PDF. Dostosuj te wartości, aby ustawić żądane położenie podpisu.

#### P: Co się stanie, jeśli serwer znaczników czasu będzie niedostępny podczas podpisywania?

Odp.: Jeśli serwer znaczników czasu będzie niedostępny podczas podpisywania, proces może się nie powieść lub potrwać dłużej. Upewnij się, że Twój serwer znaczników czasu jest niezawodny i dostępny.

#### P: Jak mogę sprawdzić obecność znacznika czasu w podpisanym pliku PDF?

 Odp.: Możesz sprawdzić podpisany plik PDF, korzystając z dostarczonego przykładowego kodu. The`TimestampSettings` Hasło użyte podczas podpisywania powinno być dostępne w szczegółach podpisu.

#### P: Czy podpisy cyfrowe ze znacznikami czasu są prawnie wiążące?

Odp.: Podpisy cyfrowe ze znacznikami czasu mają wartość prawną w wielu jurysdykcjach i często są uważane za bardziej niezawodne niż zwykłe podpisy cyfrowe. Aby poznać szczegółowe przepisy, skonsultuj się z ekspertami prawnymi w swojej jurysdykcji.

#### P: Czy mogę dodać wiele podpisów cyfrowych ze znacznikami czasu do pliku PDF?

Odp.: Tak, możesz dodać wiele podpisów cyfrowych ze znacznikami czasu do pliku PDF, wielokrotnie wywołując proces tworzenia podpisu. Każdy podpis będzie miał swój własny znacznik czasu.