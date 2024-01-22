---
title: Podpisuj za pomocą karty inteligentnej, korzystając z podpisu pliku PDF
linktitle: Podpisuj za pomocą karty inteligentnej, korzystając z podpisu pliku PDF
second_title: Aspose.PDF z dokumentacją API .NET
description: Podpisuj bezpiecznie swoje pliki PDF za pomocą karty inteligentnej, korzystając z Aspose.PDF dla .NET.
type: docs
weight: 110
url: /pl/net/programming-with-security-and-signatures/sign-with-smart-card-using-pdf-file-signature/
---
Podpisywanie cyfrowe za pomocą karty inteligentnej to bezpieczny sposób podpisywania plików PDF. Dzięki Aspose.PDF dla .NET możesz łatwo podpisać plik PDF za pomocą karty inteligentnej, postępując zgodnie z następującym kodem źródłowym:

## Krok 1: Zaimportuj wymagane biblioteki

Zanim zaczniesz, musisz zaimportować niezbędne biblioteki dla swojego projektu C#. Oto niezbędne dyrektywy importowe:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Facades;
using Aspose.Pdf.Forms;
using System.Security.Cryptography.X509Certificates;
```

## Krok 2: Ustaw ścieżkę do folderu dokumentów

 W tym kroku musisz określić ścieżkę do folderu zawierającego plik PDF, który chcesz podpisać. Zastępować`"YOUR DOCUMENTS DIRECTORY"` następującym kodzie z rzeczywistą ścieżką do folderu dokumentów:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Krok 3: Załaduj dokument PDF

Teraz załadujemy dokument PDF do podpisu za pomocą następującego kodu:

```csharp
Document doc = new Document(dataDir + "blank.pdf");
```

## Krok 4: Wykonaj podpis za pomocą karty inteligentnej

 W tym kroku wykonamy podpis kartą inteligentną za pomocą`PdfFileSignature` klasa z`Facades`biblioteka. Wybieramy certyfikat karty inteligentnej z magazynu certyfikatów systemu Windows i określamy niezbędne informacje do podpisu. Oto odpowiedni kod:

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

 Na koniec weryfikujemy podpis podpisanego pliku PDF za pomocą`PdfFileSignature` klasa. Otrzymujemy nazwiska podpisów i sprawdzamy je jeden po drugim. Jeśli podpis nie przejdzie weryfikacji, zostanie zgłoszony wyjątek. Oto odpowiedni kod:

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

### Przykładowy kod źródłowy funkcji Podpisywanie za pomocą karty inteligentnej przy użyciu podpisu pliku PDF przy użyciu Aspose.PDF dla .NET 
```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "blank.pdf");
using (Facades.PdfFileSignature pdfSign = new Facades.PdfFileSignature())
{
	pdfSign.BindPdf(doc);
	// Podpisz, wybierając certyfikat w magazynie certyfikatów systemu Windows
	System.Security.Cryptography.X509Certificates.X509Store store = new System.Security.Cryptography.X509Certificates.X509Store(System.Security.Cryptography.X509Certificates.StoreLocation.CurrentUser);
	store.Open(System.Security.Cryptography.X509Certificates.OpenFlags.ReadOnly);
	// Ręcznie wybrałem certyfikat w sklepie
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

Gratulacje! Masz teraz przewodnik krok po kroku dotyczący podpisywania pliku PDF za pomocą karty inteligentnej przy użyciu Aspose.PDF dla .NET. Możesz użyć tego kodu, aby dodać bezpieczne podpisy cyfrowe do dokumentów PDF.

Koniecznie zapoznaj się z oficjalną dokumentacją Aspose.PDF, aby uzyskać więcej informacji na temat zaawansowanych funkcji podpisu cyfrowego i zarządzania certyfikatami.

### Często zadawane pytania

#### P: Dlaczego powinienem rozważyć podpisywanie plików PDF za pomocą karty inteligentnej?

Odp.: Podpisywanie plików PDF za pomocą karty inteligentnej zwiększa bezpieczeństwo, zapewniając autentyczność i integralność dokumentu. Podpisy oparte na kartach inteligentnych zapewniają wyższy poziom zaufania i zgodności.

#### P: Jak działa podpisywanie cyfrowe oparte na kartach inteligentnych?

Odp.: Podpisywanie cyfrowe za pomocą karty inteligentnej polega na użyciu klucza kryptograficznego przechowywanego na karcie inteligentnej w celu utworzenia unikalnego podpisu cyfrowego. Podpis ten jest dołączany do pliku PDF, umożliwiając odbiorcom weryfikację pochodzenia i integralności dokumentu.

#### P: Jaka jest rola Aspose.PDF dla .NET w podpisywaniu opartym na kartach inteligentnych?

O: Aspose.PDF dla .NET zapewnia kompleksowy zestaw narzędzi i bibliotek ułatwiających cyfrowe podpisywanie plików PDF przy użyciu kart inteligentnych. Upraszcza to proces i zapewnia bezpieczne podpisywanie dokumentów.

#### P: Czy mogę wybrać konkretny certyfikat karty inteligentnej do podpisania?

O: Tak, możesz wybrać do podpisania określony certyfikat karty inteligentnej z magazynu certyfikatów systemu Windows. Aspose.PDF dla .NET umożliwia bezproblemową integrację wyboru certyfikatów z aplikacją.

#### P: W jaki sposób dostarczony kod źródłowy obsługuje podpisywanie za pomocą karty inteligentnej?

Odp.: Kod źródłowy pokazuje, jak oprawić dokument PDF, wybrać certyfikat karty inteligentnej, określić informacje o podpisie i utworzyć podpis cyfrowy. Pokazuje także, jak sprawdzić ważność podpisu.

#### P: Czy mogę zastosować wiele podpisów przy użyciu kart inteligentnych w jednym pliku PDF?

Odp.: Oczywiście w jednym pliku PDF można zastosować wiele podpisów opartych na kartach inteligentnych. Każdy podpis jest niepowtarzalny i przyczynia się do ogólnego bezpieczeństwa dokumentu.

#### P: Co się stanie, jeśli podpis nie przejdzie weryfikacji na etapie weryfikacji?

Odp.: Jeśli podpis nie przejdzie weryfikacji, zostanie zgłoszony wyjątek wskazujący, że podpis jest nieprawidłowy. Dzięki temu akceptowane są tylko ważne i zaufane podpisy.

#### P: Czy podpisywanie za pomocą karty inteligentnej jest zgodne ze wszystkimi typami dokumentów PDF?

Odp.: Tak, podpisywanie za pomocą karty inteligentnej jest kompatybilne ze wszystkimi typami dokumentów PDF. Podpisy cyfrowe można stosować do różnych typów plików PDF, w tym formularzy, raportów i innych.

#### P: Jak mogę dowiedzieć się więcej o zaawansowanym zarządzaniu podpisem cyfrowym i certyfikatami?

O: Zapoznaj się z oficjalną dokumentacją Aspose.PDF, aby uzyskać szczegółowy wgląd w zaawansowane funkcje podpisu cyfrowego, zarządzanie certyfikatami i najlepsze praktyki zapewniające bezpieczeństwo dokumentów.

#### P: Gdzie mogę znaleźć dalszą pomoc lub wsparcie dotyczące wdrażania podpisywania za pomocą kart inteligentnych?

Odp.: Aby uzyskać dodatkowe wskazówki i wsparcie, skontaktuj się z forami społeczności Aspose.PDF lub zapoznaj się z dokumentacją zawierającą wyczerpujące informacje na temat podpisywania w oparciu o karty inteligentne.