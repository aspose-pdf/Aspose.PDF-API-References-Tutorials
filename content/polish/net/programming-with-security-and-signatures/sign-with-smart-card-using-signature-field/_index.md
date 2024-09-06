---
title: Podpisz kartą inteligentną, korzystając z pola podpisu
linktitle: Podpisz kartą inteligentną, korzystając z pola podpisu
second_title: Aspose.PDF dla .NET API Reference
description: Bezpiecznie podpisuj pliki PDF za pomocą karty inteligentnej, korzystając z Aspose.PDF dla .NET.
type: docs
weight: 120
url: /pl/net/programming-with-security-and-signatures/sign-with-smart-card-using-signature-field/
---
Cyfrowe podpisywanie za pomocą karty inteligentnej to bezpieczny sposób podpisywania plików PDF. Dzięki Aspose.PDF dla .NET możesz łatwo podpisać plik PDF za pomocą pola podpisu i karty inteligentnej, postępując zgodnie z następującym kodem źródłowym:

## Krok 1: Importuj wymagane biblioteki

Zanim zaczniesz, musisz zaimportować niezbędne biblioteki dla swojego projektu C#. Oto niezbędne dyrektywy importu:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Forms;
using System.Security.Cryptography.X509Certificates;
```

## Krok 2: Ustaw ścieżkę do folderu dokumentów

 W tym kroku musisz określić ścieżkę do folderu zawierającego plik PDF, który chcesz podpisać. Zastąp`"YOUR DOCUMENTS DIRECTORY"` w poniższym kodzie podaj rzeczywistą ścieżkę do folderu z dokumentami:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Krok 3: Skopiuj i otwórz dokument PDF

Teraz skopiujemy i otworzymy dokument PDF, który ma zostać podpisany, korzystając z następującego kodu:

```csharp
File.Copy(dataDir + "blank.pdf", dataDir + "externalSignature1.pdf", true);

using (FileStream fs = new FileStream(dataDir + "externalSignature1.pdf", FileMode.Open, FileAccess.ReadWrite))
{
     using (Document doc = new Document(fs))
     {
         // Utwórz pole podpisu
         SignatureField field1 = new SignatureField(doc.Pages[1], new Rectangle(100, 400, 10, 10));

         // Wybierz certyfikat w sklepie
         X509Store store = new X509Store(StoreLocation.CurrentUser);
         store.Open(OpenFlags.ReadOnly);
         X509Certificate2Collection sel = X509Certificate2UI.SelectFromCollection(store.Certificates, null, null, X509SelectionFlag.SingleSelection);
        
         // Utwórz zewnętrzny podpis z niezbędnymi informacjami
         ExternalSignature externalSignature = new ExternalSignature(sel[0])
         {
             Authority = "Me",
             Reason = "Reason",
             ContactInfo = "Contact"
         };

         field1.PartialName = "sig1";
         doc.Form.Add(field1, 1);
         field1.Sign(externalSignature);
         doc.Save();
     }
}
```

## Krok 4: Zweryfikuj podpis

 Na koniec weryfikujemy podpis podpisanego pliku PDF za pomocą`PdfFileSignature` klasa. Pobieramy nazwy podpisów i sprawdzamy je po kolei. Jeśli podpis nie przejdzie weryfikacji, zgłaszany jest wyjątek. Oto odpowiedni kod:

```csharp
using (PdfFileSignature pdfSign = new PdfFileSignature(new Document(dataDir + "externalSignature1.pdf")))
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

### Przykładowy kod źródłowy dla Podpisu za pomocą karty inteligentnej przy użyciu pola podpisu przy użyciu Aspose.PDF dla .NET 
```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
File.Copy(dataDir + "blank.pdf", dataDir + "externalSignature1.pdf", true);
using (FileStream fs = new FileStream(dataDir + "externalSignature1.pdf", FileMode.Open, FileAccess.ReadWrite))
{
	using (Document doc = new Document(fs))
	{
		SignatureField field1 = new SignatureField(doc.Pages[1], new Rectangle(100, 400, 10, 10));
		// Podpisz za pomocą wybranego certyfikatu w magazynie certyfikatów systemu Windows
		System.Security.Cryptography.X509Certificates.X509Store store = new System.Security.Cryptography.X509Certificates.X509Store(System.Security.Cryptography.X509Certificates.StoreLocation.CurrentUser);
		store.Open(System.Security.Cryptography.X509Certificates.OpenFlags.ReadOnly);
		// Ręcznie wybrano certyfikat w sklepie
		System.Security.Cryptography.X509Certificates.X509Certificate2Collection sel = System.Security.Cryptography.X509Certificates.X509Certificate2UI.SelectFromCollection(store.Certificates, null, null, System.Security.Cryptography.X509Certificates.X509SelectionFlag.SingleSelection);
		Aspose.Pdf.Forms.ExternalSignature externalSignature = new Aspose.Pdf.Forms.ExternalSignature(sel[0])
		{
			Authority = "Me",
			Reason = "Reason",
			ContactInfo = "Contact"
		};
		field1.PartialName = "sig1";
		doc.Form.Add(field1, 1);
		field1.Sign(externalSignature);
		doc.Save();
	}
}
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

## Wniosek

Gratulacje! Masz teraz przewodnik krok po kroku, jak podpisać plik PDF kartą inteligentną, używając pola podpisu z Aspose.PDF dla .NET. Możesz użyć tego kodu, aby dodać bezpieczne podpisy cyfrowe do swoich dokumentów PDF.

Zapoznaj się z oficjalną dokumentacją Aspose.PDF, aby uzyskać więcej informacji na temat zaawansowanych funkcji podpisu cyfrowego i zarządzania certyfikatami.

### Najczęściej zadawane pytania

#### P: Jakie są korzyści z używania pola podpisu do składania podpisu cyfrowego za pomocą karty inteligentnej?

A: Użycie pola podpisu do cyfrowego podpisywania kartą inteligentną zapewnia wyznaczony obszar w pliku PDF, w którym podpis jest stosowany. Zwiększa to przejrzystość dokumentu i zapewnia autentyczność podpisu.

#### P: W jaki sposób biblioteka Aspose.PDF dla platformy .NET ułatwia składanie podpisów cyfrowych przy użyciu kart inteligentnych z polem podpisu?

A: Aspose.PDF dla platformy .NET upraszcza proces tworzenia pola podpisu, wybierania certyfikatu karty inteligentnej i stosowania podpisu cyfrowego do określonego obszaru dokumentu PDF.

#### P: Dlaczego wybór konkretnego certyfikatu jest istotny w przypadku podpisywania przy użyciu karty inteligentnej?

A: Wybór konkretnego certyfikatu pozwala na jednoznaczną identyfikację osoby podpisującej i zapewnienie integralności podpisu. Pomaga to w budowaniu zaufania i zgodności ze standardami podpisu cyfrowego.

#### P: W jaki sposób udostępniony kod źródłowy obsługuje proces podpisywania przy użyciu karty inteligentnej z polem podpisu?

A: Kod źródłowy pokazuje, jak utworzyć pole podpisu, wybrać certyfikat karty inteligentnej i zastosować podpis cyfrowy ze szczegółowymi informacjami o podpisie. Pokazuje również, jak zweryfikować ważność podpisu.

#### P: Czy mogę dostosować wygląd pola podpisu?

O: Tak, możesz dostosować wygląd pola podpisu, na przykład jego rozmiar, pozycję i reprezentację wizualną, aby dopasować je do układu dokumentu.

#### P: Co się stanie, jeśli podpis nie przejdzie weryfikacji na etapie weryfikacji?

A: Jeśli podpis nie przejdzie weryfikacji, zgłaszany jest wyjątek, wskazujący, że podpis nie jest prawidłowy. Zapewnia to, że akceptowane są tylko prawidłowe i zaufane podpisy.

#### P: Czy mogę zastosować wiele pól podpisu i podpisów na kartach inteligentnych w jednym dokumencie PDF?

O: Oczywiście. Możesz zastosować wiele pól podpisu i podpisów opartych na kartach inteligentnych w różnych obszarach tego samego dokumentu PDF, zapewniając w ten sposób wiele warstw zabezpieczeń.

#### P: W jaki sposób użycie pola podpisu usprawnia cały proces podpisywania dokumentu?

A: Użycie pola podpisu usprawnia proces podpisywania dokumentu, ponieważ wskazuje sygnatariuszowi miejsce, w którym należy złożyć podpis. Dzięki temu proces podpisywania staje się bardziej uporządkowany i przyjazny dla użytkownika.

#### P: Czy istnieją jakieś ograniczenia w korzystaniu z pól podpisu w przypadku podpisów opartych na kartach inteligentnych?

A: Nie ma żadnych wewnętrznych ograniczeń w korzystaniu z pól podpisu z podpisem opartym na karcie inteligentnej. Ważne jest jednak, aby upewnić się, że wybrana lokalizacja pola podpisu nie przesłania ważnej treści dokumentu.

#### P: Gdzie mogę znaleźć dalszą pomoc lub wsparcie w zakresie wdrażania podpisów opartych na kartach inteligentnych z polem podpisu?

A: Dodatkowe wskazówki i pomoc można znaleźć w oficjalnej dokumentacji Aspose.PDF oraz na forach społecznościowych. Można tam znaleźć cenne informacje i rozwiązania ułatwiające wdrażanie bezpiecznych podpisów cyfrowych.