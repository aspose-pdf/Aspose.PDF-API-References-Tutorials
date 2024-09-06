---
title: Podpisz za pomocą karty inteligentnej, używając podpisu pliku PDF
linktitle: Podpisz za pomocą karty inteligentnej, używając podpisu pliku PDF
second_title: Aspose.PDF dla .NET API Reference
description: Bezpiecznie podpisuj pliki PDF za pomocą karty inteligentnej, korzystając z Aspose.PDF dla .NET.
type: docs
weight: 110
url: /pl/net/programming-with-security-and-signatures/sign-with-smart-card-using-pdf-file-signature/
---
Cyfrowe podpisywanie za pomocą karty inteligentnej to bezpieczny sposób podpisywania plików PDF. Dzięki Aspose.PDF dla .NET możesz łatwo podpisać plik PDF za pomocą karty inteligentnej, postępując zgodnie z następującym kodem źródłowym:

## Krok 1: Importuj wymagane biblioteki

Zanim zaczniesz, musisz zaimportować niezbędne biblioteki dla swojego projektu C#. Oto niezbędne dyrektywy importu:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Facades;
using Aspose.Pdf.Forms;
using System.Security.Cryptography.X509Certificates;
```

## Krok 2: Ustaw ścieżkę do folderu dokumentów

 W tym kroku musisz określić ścieżkę do folderu zawierającego plik PDF, który chcesz podpisać. Zastąp`"YOUR DOCUMENTS DIRECTORY"` w poniższym kodzie podaj rzeczywistą ścieżkę do folderu z dokumentami:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Krok 3: Załaduj dokument PDF

Teraz załadujemy dokument PDF do podpisania, korzystając z następującego kodu:

```csharp
Document doc = new Document(dataDir + "blank.pdf");
```

## Krok 4: Wykonaj podpis za pomocą karty inteligentnej

 W tym kroku wykonamy podpis za pomocą karty inteligentnej, używając`PdfFileSignature` klasa z`Facades`library. Wybieramy certyfikat karty inteligentnej z magazynu certyfikatów Windows i określamy niezbędne informacje o podpisie. Oto odpowiedni kod:

```csharp
using (PdfFileSignature pdfSign = new PdfFileSignature())
{
     pdfSign.BindPdf(doc);

     // Wybierz certyfikat w sklepie
     X509Store store = new X509Store(StoreLocation.CurrentUser);
     store.Open(OpenFlags.ReadOnly);
     X509Certificate2Collection sel = X509Certificate2UI.SelectFromCollection(store.Certificates, null, null, X509SelectionFlag.SingleSelection);
     ExternalSignature externalSignature = new ExternalSignature(sel[0]);

     pdfSign.SignatureAppearance = dataDir + "demo.png";
     pdfSign.Sign(1, "Reason", "Contact", "Location", true, new System.Drawing.Rectangle(100, 100, 200, 200), externalSignature);
     pdfSign.Save(dataDir + "externalSignature2.pdf");
}
```

## Krok 5: Zweryfikuj podpis

 Na koniec weryfikujemy podpis podpisanego pliku PDF za pomocą`PdfFileSignature` klasa. Pobieramy nazwy podpisów i sprawdzamy je po kolei. Jeśli podpis nie przejdzie weryfikacji, zgłaszany jest wyjątek. Oto odpowiedni kod:

```csharp
using (PdfFileSignature pdfSign = new PdfFileSignature(new Document(dataDir + "externalSignature2.pdf")))
{
     IList<string> sigNames = pdfSign. GetSignNames();
     for (int index = 0; index <= sigNames.Count - 1; index++)
     {
         if (!pdfSign.VerifySigned(sigNames[index]) || !pdfSign.VerifySignature(sigNames[index]))
         {
             throw new ApplicationException("Unverified");
         }
     }
}
```

### Przykładowy kod źródłowy dla podpisu za pomocą karty inteligentnej przy użyciu pliku PDF z wykorzystaniem Aspose.PDF dla .NET 
```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "blank.pdf");
using (Facades.PdfFileSignature pdfSign = new Facades.PdfFileSignature())
{
	pdfSign.BindPdf(doc);
	// Podpisz za pomocą wybranego certyfikatu w magazynie certyfikatów systemu Windows
	System.Security.Cryptography.X509Certificates.X509Store store = new System.Security.Cryptography.X509Certificates.X509Store(System.Security.Cryptography.X509Certificates.StoreLocation.CurrentUser);
	store.Open(System.Security.Cryptography.X509Certificates.OpenFlags.ReadOnly);
	// Ręcznie wybrano certyfikat w sklepie
	System.Security.Cryptography.X509Certificates.X509Certificate2Collection sel = System.Security.Cryptography.X509Certificates.X509Certificate2UI.SelectFromCollection(store.Certificates, null, null, System.Security.Cryptography.X509Certificates.X509SelectionFlag.SingleSelection);
	Aspose.Pdf.Forms.ExternalSignature externalSignature = new Aspose.Pdf.Forms.ExternalSignature(sel[0]);
	pdfSign.SignatureAppearance = dataDir + "demo.png";
	pdfSign.Sign(1, "Reason", "Contact", "Location", true, new System.Drawing.Rectangle(100, 100, 200, 200), externalSignature);
	pdfSign.Save(dataDir + "externalSignature2.pdf");
}
using (Facades.PdfFileSignature pdfSign = new Facades.PdfFileSignature(new Document(dataDir + "externalSignature2.pdf")))
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

## Wniosek

Gratulacje! Masz teraz przewodnik krok po kroku, jak podpisać plik PDF kartą inteligentną za pomocą Aspose.PDF dla .NET. Możesz użyć tego kodu, aby dodać bezpieczne podpisy cyfrowe do swoich dokumentów PDF.

Zapoznaj się z oficjalną dokumentacją Aspose.PDF, aby uzyskać więcej informacji na temat zaawansowanych funkcji podpisu cyfrowego i zarządzania certyfikatami.

### Najczęściej zadawane pytania

#### P: Dlaczego warto rozważyć podpisywanie plików PDF za pomocą karty inteligentnej?

A: Podpisywanie plików PDF za pomocą karty inteligentnej zwiększa bezpieczeństwo, zapewniając autentyczność i integralność dokumentu. Podpisy oparte na karcie inteligentnej zapewniają wyższy poziom zaufania i zgodności.

#### P: Jak działa podpis cyfrowy oparty na karcie inteligentnej?

A: Podpis cyfrowy oparty na karcie inteligentnej polega na użyciu klucza kryptograficznego zapisanego na karcie inteligentnej w celu utworzenia unikalnego podpisu cyfrowego. Ten podpis jest dołączany do pliku PDF, umożliwiając odbiorcom weryfikację pochodzenia i integralności dokumentu.

#### P: Jaką rolę pełni Aspose.PDF dla platformy .NET w podpisach opartych na kartach inteligentnych?

A: Aspose.PDF dla .NET zapewnia kompleksowy zestaw narzędzi i bibliotek, które ułatwiają cyfrowe podpisywanie plików PDF za pomocą kart inteligentnych. Upraszcza proces i zapewnia bezpieczne podpisywanie dokumentów.

#### P: Czy mogę wybrać konkretny certyfikat karty inteligentnej do podpisania?

A: Tak, możesz wybrać konkretny certyfikat karty inteligentnej z magazynu certyfikatów Windows do podpisania. Aspose.PDF dla .NET umożliwia bezproblemową integrację wyboru certyfikatu z aplikacją.

#### P: W jaki sposób udostępniony kod źródłowy obsługuje podpisywanie za pomocą kart inteligentnych?

A: Kod źródłowy pokazuje, jak powiązać dokument PDF, wybrać certyfikat karty inteligentnej, określić informacje o podpisie i utworzyć podpis cyfrowy. Pokazuje również, jak zweryfikować ważność podpisu.

#### P: Czy mogę złożyć wiele podpisów za pomocą kart inteligentnych w jednym pliku PDF?

A: Oczywiście, możesz zastosować wiele podpisów opartych na kartach inteligentnych do jednego pliku PDF. Każdy podpis jest unikalny i przyczynia się do ogólnego bezpieczeństwa dokumentu.

#### P: Co się stanie, jeśli podpis nie przejdzie weryfikacji na etapie weryfikacji?

A: Jeśli podpis nie przejdzie weryfikacji, zgłaszany jest wyjątek, wskazujący, że podpis nie jest prawidłowy. Zapewnia to, że akceptowane są tylko prawidłowe i zaufane podpisy.

#### P: Czy podpisywanie przy użyciu karty inteligentnej jest kompatybilne ze wszystkimi typami dokumentów PDF?

A: Tak, podpisywanie oparte na karcie inteligentnej jest zgodne ze wszystkimi typami dokumentów PDF. Możesz stosować podpisy cyfrowe do różnych typów plików PDF, w tym formularzy, raportów i innych.

#### P: Gdzie mogę dowiedzieć się więcej o zaawansowanym zarządzaniu podpisami cyfrowymi i certyfikatami?

A: Zapoznaj się z oficjalną dokumentacją Aspose.PDF, aby uzyskać szczegółowe informacje na temat zaawansowanych funkcji podpisu cyfrowego, zarządzania certyfikatami i najlepszych praktyk zapewniających bezpieczeństwo dokumentów.

#### P: Gdzie mogę znaleźć dalszą pomoc lub wsparcie w zakresie wdrażania podpisów opartych na kartach inteligentnych?

A: Aby uzyskać dodatkowe wskazówki i pomoc, skontaktuj się z forami społeczności Aspose.PDF lub zapoznaj się z dokumentacją, w której znajdują się kompleksowe informacje na temat podpisów opartych na kartach inteligentnych.