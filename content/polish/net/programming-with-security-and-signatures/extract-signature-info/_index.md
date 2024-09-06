---
title: Wyodrębnij informacje o podpisie
linktitle: Wyodrębnij informacje o podpisie
second_title: Aspose.PDF dla .NET API Reference
description: Wyodrębnianie informacji o podpisie przy użyciu Aspose.PDF dla .NET.
type: docs
weight: 80
url: /pl/net/programming-with-security-and-signatures/extract-signature-info/
---
Proces wyodrębniania informacji o podpisie z dokumentu PDF może być bardzo przydatny w różnych scenariuszach. Niezależnie od tego, czy musisz zweryfikować autentyczność podpisanego dokumentu, czy przeanalizować certyfikat użyty do podpisu, biblioteka Aspose.PDF dla .NET zapewnia wygodne rozwiązanie. W tym samouczku przeprowadzimy Cię przez proces krok po kroku wyodrębniania informacji o podpisie przy użyciu dostarczonego kodu źródłowego C#.

## Wymagania

Zanim zaczniemy, upewnij się, że spełnione są następujące wymagania wstępne:

1. Podstawowa znajomość języka programowania C#.
2. Biblioteka Aspose.PDF dla platformy .NET zainstalowana w systemie.
3. Prawidłowy dokument PDF z jednym lub większą liczbą pól podpisu.

Przyjrzyjmy się teraz szczegółom implementacji.

## Krok 1: Importowanie wymaganych bibliotek

 Aby rozpocząć, musisz zaimportować niezbędne biblioteki do swojego projektu C#. W tym przypadku musimy zaimportować`Aspose.Pdf` I`System.IO` przestrzenie nazw. Można to zrobić, dodając następujący kod na początku pliku C#:

```csharp
using Aspose.Pdf;
using System.IO;
```

## Krok 2: Ustawianie ścieżki dokumentu

Następnie musisz ustawić ścieżkę do dokumentu PDF, z którego chcesz wyodrębnić informacje o podpisie. Zastąp`"YOUR DOCUMENTS DIRECTORY"` w poniższym fragmencie kodu podaj rzeczywistą ścieżkę do swojego dokumentu:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
string input = dataDir + "ExtractSignatureInfo.pdf";
```

## Krok 3: Wyodrębnianie informacji o podpisie

Przejdźmy teraz do głównej części kodu, w której wyodrębniamy informacje o podpisie z dokumentu PDF. Przechodzimy przez każde pole w formularzu dokumentu i sprawdzamy, czy jest to pole podpisu. Jeśli pole podpisu zostanie znalezione, kontynuujemy wyodrębnianie certyfikatu. Dodaj następujący fragment kodu:

```csharp
using (Document pdfDocument = new Document(input))
{
     foreach(Field field in pdfDocument.Form)
     {
         SignatureField sf = field as SignatureField;
         if (sf != null)
         {
             // Wyodrębnij certyfikat
             Stream cerStream = sf.ExtractCertificate();
             if (cerStream != null)
             {
                 using (cerStream)
                 {
                     byte[] bytes = new byte[cerStream.Length];
                     using (FileStream fs = new FileStream(dataDir + @"input.cer", FileMode.CreateNew))
                     {
                         cerStream.Read(bytes, 0, bytes.Length);
                         fs.Write(bytes, 0, bytes.Length);
                     }
                 }
             }
         }
     }
}
```

## Krok 4: Wyodrębnianie certyfikatu

W tym kroku wyodrębniamy certyfikat z pola podpisu i zapisujemy go jako plik. Wyodrębniony certyfikat można dalej analizować lub wykorzystać do celów walidacji. Poniższy fragment kodu demonstruje proces wyodrębniania i zapisywania:

```csharp
Stream cerStream = sf.ExtractCertificate();
if (cerStream != null)
{
     using (cerStream)
     {
         byte[] bytes = new byte[cerStream.Length];
         using (FileStream fs = new FileStream(dataDir + @"input.cer", FileMode.CreateNew))
         {
             cerStream.Read(bytes, 0, bytes.Length);
             fs.Write(bytes, 0, bytes.Length);
         }
     }
}
```

## Krok 5

:Zapisywanie certyfikatu

Na koniec zapisujemy wyodrębniony certyfikat jako plik. W tym przykładzie certyfikat jest zapisywany pod nazwą „input.cer” w określonym katalogu. Możesz zmodyfikować kod, aby dostosować go do swoich wymagań. Oto fragment kodu do zapisania certyfikatu:

```csharp
using (FileStream fs = new FileStream(dataDir + @"input.cer", FileMode.CreateNew))
{
     fs.Write(bytes, 0, bytes.Length);
}
```

To wszystko! Udało Ci się wyodrębnić informacje o podpisie za pomocą Aspose.PDF dla .NET. Możesz zintegrować ten kod ze swoimi aplikacjami lub zmodyfikować go zgodnie ze swoimi potrzebami.

### Przykładowy kod źródłowy do wyodrębniania informacji o podpisie przy użyciu Aspose.PDF dla .NET 
```csharp
try
{
	// Ścieżka do katalogu dokumentów.
	string dataDir = "YOUR DOCUMENTS DIRECTORY";
	string input = dataDir + "ExtractSignatureInfo.pdf";
	using (Document pdfDocument = new Document(input))
	{
		foreach (Field field in pdfDocument.Form)
		{
			SignatureField sf = field as SignatureField;
			if (sf != null)
			{
				Stream cerStream = sf.ExtractCertificate();
				if (cerStream != null)
				{
					using (cerStream)
					{
						byte[] bytes = new byte[cerStream.Length];
						using (FileStream fs = new FileStream(dataDir + @"input.cer", FileMode.CreateNew))
						{
							cerStream.Read(bytes, 0, bytes.Length);
							fs.Write(bytes, 0, bytes.Length);
						}
					}
				}
			}
		}
	}
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## Wniosek

W tym samouczku przeprowadziliśmy przewodnik krok po kroku, jak wyodrębnić informacje o podpisie z dokumentu PDF przy użyciu biblioteki Aspose.PDF dla .NET. Omówiliśmy proces importowania wymaganych bibliotek, ustawiania ścieżki dokumentu, wyodrębniania informacji o podpisie, wyodrębniania certyfikatu i zapisywania go w pliku. Postępując zgodnie z tymi krokami, możesz łatwo pobrać szczegóły podpisu i pracować z nimi w razie potrzeby.

### Najczęściej zadawane pytania

#### P: Dlaczego miałbym wyodrębniać informacje o podpisie z dokumentu PDF?

A: Wyodrębnianie informacji o podpisie z dokumentu PDF jest przydatne do sprawdzania autentyczności podpisanego dokumentu i analizowania certyfikatu użytego do podpisu. Ten proces pomaga zapewnić integralność podpisanej treści i może być niezbędny do celów prawnych i bezpieczeństwa.

#### P: Czym jest Aspose.PDF dla platformy .NET?

A: Aspose.PDF dla .NET to biblioteka, która umożliwia programistom pracę z dokumentami PDF w aplikacjach .NET. Zapewnia szeroki zakres funkcji do tworzenia, modyfikowania i interakcji z plikami PDF programowo.

#### P: Jakie są wymagania wstępne dotyczące wyodrębniania informacji o podpisie za pomocą Aspose.PDF dla platformy .NET?

O: Aby wyodrębnić informacje o podpisie, potrzebna jest podstawowa znajomość języka programowania C#, biblioteka Aspose.PDF for .NET zainstalowana w systemie oraz prawidłowy dokument PDF zawierający co najmniej jedno pole podpisu.

#### P: Jak zaimportować biblioteki wymagane do procesu ekstrakcji?

A: Możesz zaimportować niezbędne biblioteki, dodając`using` dyrektywy dla`Aspose.Pdf` I`System.IO` na początku pliku C#. Te dyrektywy umożliwiają użycie klas i metod wymaganych do wyodrębnienia informacji o podpisie.

#### P: Jak wskazać dokument PDF, z którego zostaną wyodrębnione informacje o podpisie?

 A: Możesz ustawić ścieżkę do dokumentu PDF, zastępując`"YOUR DOCUMENTS DIRECTORY"` z rzeczywistą ścieżką do dokumentu w podanym fragmencie kodu. Ta ścieżka jest używana do załadowania dokumentu PDF, z którego chcesz wyodrębnić informacje o podpisie.

#### P: Jak wygląda proces wyodrębniania informacji o podpisie z dokumentu PDF?

A: Proces ekstrakcji obejmuje iterację przez pola formularza dokumentu PDF, sprawdzanie, czy każde pole jest polem podpisu, a jeśli tak, wyodrębnianie powiązanego certyfikatu. Wyodrębniony certyfikat można zapisać jako plik w celu dalszej analizy lub walidacji.

#### P: W jaki sposób certyfikat jest wyodrębniany z pola podpisu?

A: Certyfikat jest wyodrębniany z pola podpisu za pomocą`ExtractCertificate()` metoda dostarczona przez`SignatureField` Klasa w Aspose.PDF dla .NET. Ta metoda zwraca strumień zawierający dane certyfikatu.

#### P: Jak zapisać wyodrębniony certyfikat jako plik?

 A: Możesz zapisać wyodrębniony certyfikat jako plik, odczytując strumień certyfikatów i zapisując jego zawartość do pliku za pomocą`FileStream` Klasa. Kod podany w samouczku demonstruje ten proces.

#### P: Czy mogę użyć tego wyodrębnionego certyfikatu do weryfikacji podpisu?

A: Tak, wyodrębniony certyfikat może być użyty do walidacji podpisu. Możesz przeanalizować szczegóły certyfikatu i zweryfikować jego autentyczność, aby zapewnić integralność podpisanego dokumentu.

#### P: W jaki sposób mogę zintegrować ten kod z moimi własnymi aplikacjami?

A: Możesz zintegrować dostarczony kod z własnymi aplikacjami C#, postępując zgodnie z przewodnikiem krok po kroku. Zmodyfikuj ścieżki i nazwy plików w razie potrzeby i włącz kod do istniejących projektów.

#### P: Czy Aspose.PDF dla platformy .NET zawiera inne funkcje związane z zarządzaniem podpisami?

A: Tak, Aspose.PDF dla .NET oferuje szereg funkcji do pracy z podpisami cyfrowymi, w tym podpisywanie dokumentów, weryfikację podpisów i dodawanie informacji o znaczniku czasu. Więcej szczegółów na temat tych funkcji można znaleźć w oficjalnej dokumentacji.

#### P: Gdzie mogę znaleźć dodatkowe materiały dotyczące korzystania z pliku Aspose.PDF na platformie .NET?

 A: Aby uzyskać więcej informacji, samouczków i zasobów dotyczących korzystania z Aspose.PDF dla .NET,[Aspose.PDF dla .NET](https://reference.aspose.com/pdf/net/).

#### P: Czy można wyodrębnić podpisy z zaszyfrowanych dokumentów PDF?

A: Możliwość wyodrębniania podpisów z zaszyfrowanych dokumentów PDF może zależeć od ustawień szyfrowania i uprawnień dokumentu. Może być konieczne upewnienie się, że masz niezbędne uprawnienia do dostępu i wyodrębniania informacji o podpisie.

#### P: Czy mogę wyodrębnić wiele podpisów z jednego dokumentu PDF?

A: Tak, możesz zmodyfikować dostarczony kod, aby przejść przez wszystkie pola podpisu w dokumencie PDF i wyodrębnić informacje o podpisie z każdego z nich. Pozwala to wyodrębnić informacje o wielu podpisach obecnych w dokumencie.

#### P: Jakie są praktyczne przypadki wykorzystania informacji o podpisie?

A: Przykłady praktycznego wykorzystania informacji o podpisie obejmują weryfikację autentyczności dokumentów podpisanych cyfrowo, analizę szczegółów certyfikatów pod kątem zgodności z przepisami oraz prowadzenie rejestru podpisów i sygnatariuszy na potrzeby audytu.

#### P: Czy istnieją jakieś kwestie prawne związane z pozyskiwaniem informacji o podpisie?

A: Wyodrębnienie informacji o podpisie może mieć konsekwencje prawne, zwłaszcza w przypadku obsługi prawnie wiążących dokumentów. Upewnij się, że przestrzegasz odpowiednich przepisów i praw dotyczących podpisów elektronicznych i autentyczności dokumentów w swojej jurysdykcji.