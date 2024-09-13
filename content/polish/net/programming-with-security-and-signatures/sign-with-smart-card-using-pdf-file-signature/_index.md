---
title: Podpisz za pomocą karty inteligentnej, używając podpisu pliku PDF
linktitle: Podpisz za pomocą karty inteligentnej, używając podpisu pliku PDF
second_title: Aspose.PDF dla .NET API Reference
description: Dowiedz się, jak podpisywać pliki PDF za pomocą karty inteligentnej za pomocą Aspose.PDF dla .NET. Postępuj zgodnie z tym przewodnikiem krok po kroku, aby uzyskać bezpieczne podpisy cyfrowe.
type: docs
weight: 110
url: /pl/net/programming-with-security-and-signatures/sign-with-smart-card-using-pdf-file-signature/
---
## Wstęp

erze cyfrowej zabezpieczanie dokumentów jest ważniejsze niż kiedykolwiek. Niezależnie od tego, czy jest to kontrakt, umowa czy jakiekolwiek poufne informacje, najważniejsze jest zapewnienie, że dokument jest autentyczny i nie został zmodyfikowany. Wprowadź podpisy cyfrowe! Dzisiaj zagłębimy się w to, jak podpisać plik PDF za pomocą karty inteligentnej z Aspose.PDF dla .NET. Ta potężna biblioteka umożliwia programistom wydajne manipulowanie i tworzenie dokumentów PDF, w tym dodawanie bezpiecznych podpisów cyfrowych. Więc weź swoją kartę inteligentną i zaczynajmy!

## Wymagania wstępne

Zanim przejdziemy do szczegółów podpisywania pliku PDF, upewnijmy się, że masz wszystko, czego potrzebujesz. Oto lista kontrolna, która pomoże Ci się przygotować:

1.  Aspose.PDF dla .NET: Upewnij się, że masz zainstalowaną bibliotekę Aspose.PDF. Możesz ją pobrać ze strony[strona](https://releases.aspose.com/pdf/net/).
2. Visual Studio: środowisko programistyczne, w którym można pisać i uruchamiać kod .NET.
3. Karta inteligentna: Będziesz potrzebować karty inteligentnej z zainstalowanym ważnym certyfikatem cyfrowym.
4. Podstawowa znajomość języka C#: Znajomość programowania w języku C# będzie pomocna, ponieważ będziemy pisać fragmenty kodu w tym języku.
5. Dokument PDF: przykładowy plik PDF (np.`blank.pdf`) aby przetestować nasz proces podpisywania.

Mając te wymagania wstępne za sobą, możesz zagłębić się w kod!

## Importuj pakiety

Najpierw zaimportujmy niezbędne pakiety. Musisz dodać odwołania do biblioteki Aspose.PDF w swoim projekcie. Oto, jak możesz to zrobić:

1. Otwórz program Visual Studio.
2. Utwórz nowy projekt lub otwórz istniejący.
3.  Kliknij prawym przyciskiem myszy swój projekt w Eksploratorze rozwiązań i wybierz`Manage NuGet Packages`.
4.  Szukaj`Aspose.PDF` i zainstaluj najnowszą wersję.

```csharp
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

Teraz, gdy zaimportowaliśmy już niezbędne pakiety, możemy przeanalizować kod krok po kroku.

## Krok 1: Skonfiguruj swój dokument

Pierwszym krokiem w naszym procesie jest skonfigurowanie dokumentu PDF, który chcemy podpisać. Oto, jak możesz to zrobić:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "blank.pdf");
```
 W tym fragmencie kodu definiujemy ścieżkę do naszego katalogu dokumentów i tworzymy wystąpienie`Document` klasa korzystająca z przykładowego pliku PDF o nazwie`blank.pdf` . Upewnij się, że wymienisz`"YOUR DOCUMENTS DIRECTORY"` z rzeczywistą ścieżką, gdzie znajduje się Twój plik PDF.

## Krok 2: Zainicjuj PdfFileSignature

 Następnie zainicjujemy`PdfFileSignature` Klasa, która odpowiada za obsługę procesu podpisywania.

```csharp
using (Facades.PdfFileSignature pdfSign = new Facades.PdfFileSignature())
{
    pdfSign.BindPdf(doc);
```
Tutaj tworzymy instancję`PdfFileSignature` powiąż go z naszym dokumentem PDF. To przygotowuje dokument do podpisania.

## Krok 3: Uzyskaj dostęp do certyfikatu karty inteligentnej

Teraz nadchodzi kluczowa część — dostęp do cyfrowego certyfikatu zapisanego na karcie inteligentnej. Oto jak możemy to zrobić:

### Otwórz magazyn certyfikatów

```csharp
System.Security.Cryptography.X509Certificates.X509Store store = new System.Security.Cryptography.X509Certificates.X509Store(System.Security.Cryptography.X509Certificates.StoreLocation.CurrentUser);
store.Open(System.Security.Cryptography.X509Certificates.OpenFlags.ReadOnly);
```
Otwieramy magazyn certyfikatów znajdujący się w profilu bieżącego użytkownika. Umożliwia nam to dostęp do certyfikatów zainstalowanych na Twoim komputerze, w tym tych na Twojej karcie inteligentnej.

### Wybierz certyfikat

```csharp
System.Security.Cryptography.X509Certificates.X509Certificate2Collection sel =
    System.Security.Cryptography.X509Certificates.X509Certificate2UI.SelectFromCollection(
        store.Certificates, null, null, System.Security.Cryptography.X509Certificates.X509SelectionFlag.SingleSelection);
```
Ten kod prosi użytkownika o wybranie certyfikatu z kolekcji. Interfejs użytkownika wyświetli wszystkie dostępne certyfikaty, umożliwiając wybór certyfikatu powiązanego z kartą inteligentną.

## Krok 4: Utwórz podpis zewnętrzny

Po wybraniu certyfikatu następnym krokiem jest utworzenie podpisu zewnętrznego przy użyciu wybranego certyfikatu.

```csharp
Aspose.Pdf.Forms.ExternalSignature externalSignature = new Aspose.Pdf.Forms.ExternalSignature(sel[0]);
```
Tutaj tworzymy instancję`ExternalSignature` używając wybranego certyfikatu. Ten obiekt będzie używany do podpisania dokumentu PDF.

## Krok 5: Ustaw wygląd podpisu

Teraz ustawmy wygląd naszego podpisu. Tutaj możesz dostosować wygląd swojego podpisu w dokumencie.

```csharp
pdfSign.SignatureAppearance = dataDir + "demo.png";
```
 W tym fragmencie kodu określamy wygląd podpisu, podając ścieżkę do pliku obrazu (np. logo lub grafikę podpisu). Pamiętaj o zastąpieniu`"demo.png"` z rzeczywistym obrazem, którego chcesz użyć.

## Krok 6: Podpisz plik PDF

Gdy wszystko jest już skonfigurowane, czas podpisać dokument PDF!

```csharp
pdfSign.Sign(1, "Reason", "Contact", "Location", true, new System.Drawing.Rectangle(100, 100, 200, 200), externalSignature);
pdfSign.Save(dataDir + "externalSignature2.pdf");
```
 tym kroku wywołujemy`Sign` metoda na naszej`pdfSign` obiekt. Oto co oznacza każdy parametr:
- `1`:Numer strony, na której pojawi się podpis.
- `"Reason"`:Powód podpisania dokumentu.
- `"Contact"`: Dane kontaktowe osoby podpisującej.
- `"Location"`:Lokalizacja osoby podpisującej.
- `true`: Wskazuje, czy utworzyć widoczny podpis.
- `new System.Drawing.Rectangle(100, 100, 200, 200)`:Pozycja i rozmiar podpisu w pliku PDF.
- `externalSignature`:Obiekt podpisu, który utworzyliśmy wcześniej.

 Na koniec zapisujemy podpisany dokument jako`externalSignature2.pdf`.

## Krok 7: Zweryfikuj podpis

Po podpisaniu dokumentu, konieczne jest sprawdzenie, czy podpis jest ważny. Oto jak to zrobić:

### Zainicjuj proces weryfikacji

```csharp
using (Facades.PdfFileSignature pdfSign = new Facades.PdfFileSignature(new Document(dataDir + "externalSignature2.pdf")))
{
    IList<string> sigNames = pdfSign.GetSignNames();
```
 Tworzymy nową instancję`PdfFileSignature` dla podpisanego dokumentu. Następnie pobieramy nazwiska wszystkich podpisów obecnych w dokumencie.

### Sprawdź ważność podpisu

```csharp
for (int index = 0; index <= sigNames.Count - 1; index++)
{
    if (!pdfSign.VerifySigned(sigNames[index]) || !pdfSign.VerifySignature(sigNames[index]))
    {
        throw new ApplicationException("Not verified");
    }
}
```
Przechodzimy przez każdą nazwę podpisu i weryfikujemy jego ważność. Jeśli jakikolwiek podpis nie przejdzie weryfikacji, zgłaszany jest wyjątek, wskazujący, że podpis nie jest prawidłowy.

## Wniosek

I masz to! Udało Ci się podpisać dokument PDF za pomocą karty inteligentnej za pomocą Aspose.PDF dla .NET. Ten proces nie tylko zabezpiecza Twój dokument, ale także dodaje warstwę autentyczności, która jest kluczowa w dzisiejszym cyfrowym świecie. Niezależnie od tego, czy masz do czynienia z umowami, dokumentami prawnymi czy jakimikolwiek poufnymi informacjami, wiedza, jak wdrożyć podpisy cyfrowe, jest cenną umiejętnością. 

## Najczęściej zadawane pytania

### Czym jest Aspose.PDF dla .NET?
Aspose.PDF dla platformy .NET to zaawansowana biblioteka umożliwiająca programistom tworzenie, edytowanie i konwertowanie dokumentów PDF w aplikacjach .NET.

### Czy do podpisywania plików PDF potrzebuję karty inteligentnej?
Choć korzystanie z karty inteligentnej nie jest obowiązkowe, jest ona zdecydowanie zalecana w przypadku bezpiecznych podpisów cyfrowych, gdyż zapewnia dodatkową warstwę bezpieczeństwa.

### Czy mogę podpisać się przy użyciu dowolnego pliku PDF?
Tak, możesz użyć dowolnego pliku PDF, ale upewnij się, że nie jest on chroniony hasłem. Jeśli jest, musisz go najpierw odblokować.

### A co jeśli nie mam certyfikatu cyfrowego?
Możesz uzyskać certyfikat cyfrowy od zaufanego urzędu certyfikacji (CA) lub użyć certyfikatu podpisanego samodzielnie w celach testowych.

### Czy jest dostępna wersja próbna Aspose.PDF?
 Tak, możesz pobrać bezpłatną wersję próbną ze strony[Strona internetowa Aspose](https://releases.aspose.com/).