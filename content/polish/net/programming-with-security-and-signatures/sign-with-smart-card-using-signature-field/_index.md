---
title: Podpisz kartą inteligentną, korzystając z pola podpisu
linktitle: Podpisz kartą inteligentną, korzystając z pola podpisu
second_title: Aspose.PDF dla .NET API Reference
description: Dowiedz się, jak bezpiecznie podpisywać pliki PDF za pomocą karty inteligentnej za pomocą Aspose.PDF dla .NET. Postępuj zgodnie z naszym przewodnikiem krok po kroku, aby ułatwić wdrożenie.
type: docs
weight: 120
url: /pl/net/programming-with-security-and-signatures/sign-with-smart-card-using-signature-field/
---
## Wstęp

dzisiejszym cyfrowym świecie zabezpieczanie dokumentów jest ważniejsze niż kiedykolwiek. Niezależnie od tego, czy jesteś deweloperem, właścicielem firmy, czy po prostu osobą, która obsługuje poufne informacje, wiedza, jak podpisywać pliki PDF elektronicznie, może zaoszczędzić Ci czasu i zapewnić uwierzytelnienie dokumentów. W tym przewodniku przeprowadzimy Cię przez proces podpisywania pliku PDF za pomocą karty inteligentnej i pola podpisu za pomocą Aspose.PDF dla .NET. 

## Wymagania wstępne

Zanim zagłębimy się w szczegóły procesu podpisywania, upewnijmy się, że masz wszystko, czego potrzebujesz, aby zacząć. Oto lista kontrolna wymagań wstępnych:

1. Aspose.PDF dla .NET: Upewnij się, że biblioteka Aspose.PDF jest zainstalowana w środowisku .NET. Możesz ją pobrać ze strony[strona](https://releases.aspose.com/pdf/net/).

2. Visual Studio: Będziesz potrzebować IDE, aby pisać i uruchamiać kod .NET. Visual Studio Community Edition to świetna darmowa opcja.

3. Karta inteligentna: Jest niezbędna do podpisania pliku PDF. Upewnij się, że masz czytnik kart inteligentnych i niezbędne certyfikaty zainstalowane na swoim komputerze.

4. Podstawowa wiedza o języku C#: Znajomość programowania w języku C# pomoże Ci zrozumieć fragmenty kodu, z których będziemy korzystać.

5. Przykładowy dokument PDF: Przygotuj przykładowy dokument PDF do testowania. Możesz utworzyć pusty plik PDF lub użyć istniejącego.

## Importuj pakiety

Zanim zaczniemy kodować, zaimportujmy niezbędne pakiety. Musisz uwzględnić następujące przestrzenie nazw w pliku C#:

```csharp
using Aspose.Pdf.Facades;
using Aspose.Pdf.Forms;
using System;
using System.Collections.Generic;
using System.IO;
using System.Linq;
using System.Text;
```

Te przestrzenie nazw dadzą ci dostęp do klas i metod wymaganych do pracy z plikami PDF i obsługi podpisów cyfrowych.

## Instrukcja krok po kroku dotycząca podpisywania pliku PDF za pomocą karty inteligentnej

Teraz, gdy mamy już uporządkowane nasze wymagania wstępne, podzielmy proces podpisywania na łatwe do opanowania kroki. Przejdziemy przez każdy krok szczegółowo, upewniając się, że rozumiesz, co dzieje się pod maską.

### Krok 1: Skonfiguruj katalog dokumentów

Co zrobić: Określ ścieżkę do katalogu dokumentów.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

 Wyjaśnienie: Zamień`"YOUR DOCUMENTS DIRECTORY"` z rzeczywistą ścieżką, gdzie znajdują się Twoje pliki PDF. To tutaj odczytamy pusty plik PDF i zapiszemy podpisany dokument.

### Krok 2: Skopiuj pusty plik PDF

Co zrobić: Utwórz kopię pustego pliku PDF, aby z nią pracować.

```csharp
File.Copy(dataDir + "blank.pdf", dataDir + "externalSignature1.pdf", true);
```

 Wyjaśnienie: Ten wiersz kopiuje`blank.pdf`plik do nowego pliku o nazwie`externalSignature1.pdf` . Ten`true` Parametr pozwala na nadpisanie pliku, jeśli plik już istnieje.

### Krok 3: Otwórz dokument PDF

Co należy zrobić: Otwórz skopiowany plik PDF w celu odczytania i zapisania.

```csharp
using (FileStream fs = new FileStream(dataDir + "externalSignature1.pdf", FileMode.Open, FileAccess.ReadWrite))
{
    using (Document doc = new Document(fs))
    {
        // Dalsze kroki będą tutaj
    }
}
```

 Wyjaśnienie: Używamy`FileStream` aby otworzyć nasz plik PDF.`Document` Klasa Aspose.PDF umożliwia nam manipulowanie zawartością PDF.

### Krok 4: Utwórz pole podpisu

Co należy zrobić: Zdefiniuj pole podpisu w pliku PDF, w którym zostanie umieszczony podpis.

```csharp
SignatureField field1 = new SignatureField(doc.Pages[1], new Rectangle(100, 400, 10, 10));
```

 Wyjaśnienie: Tutaj tworzymy`SignatureField` na drugiej stronie (indeks stron zaczyna się od 1) pliku PDF.`Rectangle` definiuje pozycję i rozmiar pola podpisu.

### Krok 5: Uzyskaj dostęp do magazynu certyfikatów kart inteligentnych

Co zrobić: Otwórz magazyn certyfikatów i wybierz certyfikat swojej karty inteligentnej.

```csharp
X509Store store = new X509Store(StoreLocation.CurrentUser);
store.Open(OpenFlags.ReadOnly);
```

Wyjaśnienie: Uzyskujemy dostęp do magazynu certyfikatów dla bieżącego użytkownika. Tutaj przechowywane są certyfikaty Twoich kart inteligentnych.

### Krok 6: Wybierz certyfikat

Co należy zrobić: Wyświetl monit o wybranie certyfikatu ze sklepu.

```csharp
X509Certificate2Collection sel = X509Certificate2UI.SelectFromCollection(store.Certificates, null, null, X509SelectionFlag.SingleSelection);
```

Wyjaśnienie: Ten wiersz otwiera okno dialogowe, w którym możesz wybrać certyfikat. Możesz wybrać certyfikat powiązany z Twoją kartą inteligentną.

### Krok 7: Utwórz podpis zewnętrzny

 Co zrobić: Utwórz instancję`ExternalSignature` używając wybranego certyfikatu.

```csharp
Aspose.Pdf.Forms.ExternalSignature externalSignature = new Aspose.Pdf.Forms.ExternalSignature(sel[0])
{
    Authority = "Me",
    Reason = "Reason",
    ContactInfo = "Contact"
};
```

 Wyjaśnienie: Inicjujemy`ExternalSignature` z wybranym certyfikatem. Możesz również ustawić autorytet, powód podpisania i dane kontaktowe.

### Krok 8: Dodaj pole podpisu do dokumentu

Co zrobić: Dodaj pole podpisu do dokumentu.

```csharp
field1.PartialName = "sig1";
doc.Form.Add(field1, 1);
```

Wyjaśnienie: Nadajemy polu podpisu nazwę i dodajemy ją do pierwszej strony dokumentu. To przygotowuje plik PDF do podpisania.

### Krok 9: Podpisz dokument

Co należy zrobić: Podpisz plik PDF za pomocą podpisu zewnętrznego.

```csharp
field1.Sign(externalSignature);
doc.Save();
```

Wyjaśnienie: Ten wiersz podpisuje dokument za pomocą zewnętrznego podpisu i zapisuje zmiany w pliku PDF. Twój dokument jest teraz podpisany!

### Krok 10: Zweryfikuj podpis

Co zrobić: Sprawdź czy podpis jest ważny.

```csharp
using (PdfFileSignature pdfSign = new PdfFileSignature(new Document(dataDir + "externalSignature1.pdf")))
{
    IList<string> sigNames = pdfSign.GetSignNames();
    for (int index = 0; index <= sigNames.Count - 1; index++)
    {
        if (!pdfSign.VerifySigned(sigNames[index]) || !pdfSign.VerifySignature(sigNames[index]))
        {
            throw new ApplicationException("Not verified");
        }
    }
}
```

Wyjaśnienie: Tworzymy instancję`PdfFileSignature` aby zweryfikować podpisy w dokumencie. Jeśli podpis nie jest prawidłowy, zgłaszany jest wyjątek.

## Wniosek

Gratulacje! Właśnie nauczyłeś się podpisywać dokument PDF za pomocą karty inteligentnej i pola podpisu za pomocą Aspose.PDF dla .NET. Ten proces nie tylko zabezpiecza Twoje dokumenty, ale także zapewnia ich autentyczność, co czyni go niezbędną umiejętnością w dzisiejszym cyfrowym krajobrazie. Niezależnie od tego, czy podpisujesz umowy, faktury czy inne ważne dokumenty, wiedza o tym, jak wdrożyć podpisy cyfrowe, może zaoszczędzić Ci czasu i zapewnić spokój ducha.

## Najczęściej zadawane pytania

### Czym jest Aspose.PDF dla .NET?
Aspose.PDF dla platformy .NET to zaawansowana biblioteka umożliwiająca programistom tworzenie, edytowanie i konwertowanie dokumentów PDF w aplikacjach .NET.

### Czy potrzebuję karty inteligentnej, aby podpisywać pliki PDF?
Tak, do bezpiecznego podpisywania plików PDF za pomocą certyfikatu cyfrowego wymagana jest karta inteligentna.

### Czy mogę używać Aspose.PDF bezpłatnie?
 Aspose.PDF oferuje bezpłatną wersję próbną, którą możesz pobrać[Tutaj](https://releases.aspose.com/).

### Jak mogę zweryfikować podpisany plik PDF?
 Możesz użyć`PdfFileSignature` klasę w Aspose.PDF w celu weryfikacji podpisów w dokumencie PDF.

### Gdzie mogę znaleźć więcej dokumentacji na temat Aspose.PDF?
 Możesz sprawdzić[Dokumentacja Aspose.PDF](https://reference.aspose.com/pdf/net/) po więcej szczegółów i przykładów.