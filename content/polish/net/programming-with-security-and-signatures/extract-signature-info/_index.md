---
title: Wyodrębnij informacje o podpisie
linktitle: Wyodrębnij informacje o podpisie
second_title: Aspose.PDF dla .NET API Reference
description: Dowiedz się, jak wyodrębnić podpisy cyfrowe i informacje o certyfikacie z dokumentów PDF za pomocą Aspose.PDF dla .NET. Kompletny przewodnik krok po kroku dla programistów C#.
type: docs
weight: 80
url: /pl/net/programming-with-security-and-signatures/extract-signature-info/
---
## Wstęp

dzisiejszym cyfrowym świecie zapewnienie bezpieczeństwa i integralności dokumentów jest kluczowe. Jedną z powszechnych metod zabezpieczania plików PDF jest dodawanie podpisu cyfrowego. Jednak pobieranie i weryfikowanie szczegółów podpisu może czasami stanowić wyzwanie, szczególnie gdy masz do czynienia z różnymi certyfikatami. W tym przewodniku przeprowadzimy Cię przez proces wyodrębniania informacji o podpisie z dokumentów PDF przy użyciu Aspose.PDF dla .NET, dzięki czemu zadanie to stanie się proste. Dowiesz się, jak uzyskać dostęp do pól podpisu, wyodrębnić informacje o certyfikacie i zapisać je w pliku.

## Wymagania wstępne

Zanim zaczniemy, upewnijmy się, że masz wszystko gotowe do rozpoczęcia pracy.

-  Aspose.PDF dla biblioteki .NET: Jeśli jeszcze jej nie masz, możesz ją pobrać ze strony[Strona pobierania Aspose.PDF dla .NET](https://releases.aspose.com/pdf/net/). 
- Środowisko programistyczne .NET: Będziesz potrzebować środowiska IDE, np. Visual Studio.
- Podstawowa wiedza o języku C#: Znajomość języka C# będzie pomocna w zrozumieniu fragmentów kodu w tym samouczku.
- Dokument PDF z podpisem cyfrowym: W celach testowych upewnij się, że masz plik PDF zawierający co najmniej jeden podpis cyfrowy.

## Importowanie wymaganych przestrzeni nazw

Przed rozpoczęciem kodu ważne jest zaimportowanie niezbędnych przestrzeni nazw. Te przestrzenie nazw umożliwią Ci dostęp do funkcjonalności Aspose.PDF i pracę z dokumentami PDF.

```csharp
using System.IO;
using Aspose.Pdf.Forms;
using Aspose.Pdf;
using System;
```

Teraz, gdy skonfigurowałeś już podstawowe ustawienia, możemy przejść do właściwego procesu wyodrębniania informacji o podpisie z pliku PDF.

## Krok 1: Konfigurowanie katalogu dokumentów

 Przed rozpoczęciem pracy nad dokumentem PDF musisz określić lokalizację pliku, którego będziesz używać. Możesz zastąpić`"YOUR DOCUMENT DIRECTORY"` z rzeczywistą ścieżką do katalogu, w którym przechowywane są pliki PDF.

```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENT DIRECTORY";
string input = dataDir + "ExtractSignatureInfo.pdf";
```

Tutaj określamy katalog zawierający plik PDF i samą nazwę pliku. Upewnij się, że plik istnieje w tym katalogu!

## Krok 2: Ładowanie dokumentu PDF

 Teraz, gdy skonfigurowałeś już swój katalog, następnym krokiem jest załadowanie dokumentu PDF za pomocą`Document` klasa z Aspose.PDF.

```csharp
using (Document pdfDocument = new Document(input))
{
    // Przetwórz plik PDF tutaj.
}
```

 Ta linia kodu inicjuje`Document`obiekt, który reprezentuje plik PDF.`using` Oświadczenie to zapewnia oczyszczenie zasobów po przetworzeniu dokumentu.

## Krok 3: Dostęp do pól formularza

W tym kroku przejdziemy przez wszystkie pola formularza w dokumencie PDF. Ponieważ podpisy są zazwyczaj przechowywane jako pola formularza, ten krok pomoże nam zidentyfikować pola podpisu.

```csharp
foreach (Field field in pdfDocument.Form)
{
    // Tutaj zidentyfikuj pola podpisu.
}
```

 Poprzez iterację`Form` własność`Document` obiekt, możemy zbadać każde pole formularza, aby sprawdzić, czy jest ono polem podpisu.

## Krok 4: Identyfikacja pól podpisu

 Po uzyskaniu dostępu do pól formularza, następnym krokiem jest zidentyfikowanie pól podpisu. Możemy to zrobić, rzutując każde pole na`SignatureField` obiekt.

```csharp
SignatureField sf = field as SignatureField;
if (sf != null)
{
    // Wyodrębnij informacje o podpisie.
}
```

 Tutaj używamy`as` słowo kluczowe, aby spróbować rzutować każde pole formularza na`SignatureField`. Jeśli rzut się powiedzie, wiemy, że pole jest sygnaturą.

## Krok 5: Wyodrębnianie certyfikatu

Teraz, gdy zidentyfikowałeś pole podpisu, następnym zadaniem jest wyodrębnienie certyfikatu z podpisu. Certyfikaty zawierają kluczowe informacje o sygnatariuszu i ważności podpisu.

```csharp
Stream cerStream = sf.ExtractCertificate();
```

 Ten`ExtractCertificate` metoda zwraca`Stream` obiekt zawierający dane certyfikatu. Ten strumień może być użyty do zapisania certyfikatu do dalszej analizy lub przechowywania.

## Krok 6: Zapisywanie certyfikatu do pliku

 Po wyodrębnieniu certyfikatu ostatnim krokiem jest zapisanie go do pliku. W tym przypadku zapiszemy certyfikat jako`.cer` plik.

```csharp
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

W tym bloku kodu:

1. Sprawdź czy strumień certyfikatu nie jest pusty.
2. Odczytaj dane certyfikatu do tablicy bajtów.
3.  Zapisz tablicę bajtów w`.cer` plik w katalogu dokumentów.

## Wniosek

Wyodrębnianie podpisów cyfrowych i powiązanych z nimi informacji o certyfikacie z dokumentów PDF przy użyciu Aspose.PDF dla .NET jest dość proste, gdy rozłoży się je na proste kroki. Niezależnie od tego, czy audytujesz dokumenty, weryfikujesz podpisy, czy po prostu przechowujesz certyfikaty w celu bezpiecznego przechowywania, ten samouczek wyposaży Cię w wiedzę, aby zrobić to sprawnie. Pamiętaj, że zabezpieczanie i weryfikowanie dokumentów ma kluczowe znaczenie w dzisiejszym cyfrowym świecie, a korzystanie z narzędzi takich jak Aspose.PDF dla .NET znacznie ułatwia obsługę.

## Najczęściej zadawane pytania

### Czy mogę wyodrębnić wiele podpisów z pliku PDF korzystając z Aspose.PDF dla platformy .NET?
Tak, kod przechodzi przez wszystkie pola formularza w dokumencie, co pozwala na wyodrębnienie wielu podpisów, jeśli takowe istnieją.

### Co się stanie, jeśli w pliku PDF nie znajdzie się podpisu?
Jeśli nie ma żadnych pól podpisu, kod po prostu je pominie, nie zgłaszając błędu.

### Czy mogę użyć tego podejścia do weryfikacji ważności podpisu?
Chociaż można wyodrębnić certyfikat, sprawdzenie ważności podpisu wymaga dodatkowych czynności, takich jak sprawdzenie łańcucha zaufania certyfikatu.

### Czy można wyodrębnić dane z innych pól formularza za pomocą Aspose.PDF dla .NET?
Tak, Aspose.PDF umożliwia dostęp i modyfikowanie różnych typów pól formularzy w pliku PDF, nie tylko pól podpisu.

### Jak mogę wyświetlić szczegóły wyodrębnionego certyfikatu?
 Po zapisaniu certyfikatu jako`.cer` Plik można otworzyć za pomocą dowolnej przeglądarki certyfikatów lub zaimportować do systemowego magazynu certyfikatów w celu dalszej inspekcji.