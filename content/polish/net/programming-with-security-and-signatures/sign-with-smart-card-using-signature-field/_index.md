---
title: Podpisz za pomocą karty inteligentnej, korzystając z pola podpisu
linktitle: Podpisz za pomocą karty inteligentnej, korzystając z pola podpisu
second_title: Aspose.PDF z dokumentacją API .NET
description: Podpisuj bezpiecznie swoje pliki PDF za pomocą karty inteligentnej, korzystając z Aspose.PDF dla .NET.
type: docs
weight: 120
url: /pl/net/programming-with-security-and-signatures/sign-with-smart-card-using-signature-field/
---
Podpisywanie cyfrowe za pomocą karty inteligentnej to bezpieczny sposób podpisywania plików PDF. Dzięki Aspose.PDF dla .NET możesz łatwo podpisać plik PDF za pomocą pola podpisu i karty inteligentnej, postępując zgodnie z następującym kodem źródłowym:

## Krok 1: Zaimportuj wymagane biblioteki

Zanim zaczniesz, musisz zaimportować niezbędne biblioteki dla swojego projektu C#. Oto niezbędne dyrektywy importowe:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Forms;
using System.Security.Cryptography.X509Certificates;
```

## Krok 2: Ustaw ścieżkę do folderu dokumentów

 W tym kroku musisz określić ścieżkę do folderu zawierającego plik PDF, który chcesz podpisać. Zastępować`"YOUR DOCUMENTS DIRECTORY"` następującym kodzie z rzeczywistą ścieżką do folderu dokumentów:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Krok 3: Skopiuj i otwórz dokument PDF

Teraz skopiujemy i otworzymy dokument PDF do podpisu za pomocą następującego kodu:

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
        
         // Utwórz podpis zewnętrzny zawierający niezbędne informacje
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

 Na koniec weryfikujemy podpis podpisanego pliku PDF za pomocą`PdfFileSignature` klasa. Otrzymujemy nazwiska podpisów i sprawdzamy je jeden po drugim. Jeśli podpis nie przejdzie weryfikacji, zostanie zgłoszony wyjątek. Oto odpowiedni kod:

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

### Przykładowy kod źródłowy funkcji Podpisywanie za pomocą karty inteligentnej przy użyciu pola podpisu przy użyciu Aspose.PDF dla .NET 
```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
File.Copy(dataDir + "blank.pdf", dataDir + "externalSignature1.pdf", true);
using (FileStream fs = new FileStream(dataDir + "externalSignature1.pdf", FileMode.Open, FileAccess.ReadWrite))
{
	using (Document doc = new Document(fs))
	{
		SignatureField field1 = new SignatureField(doc.Pages[1], new Rectangle(100, 400, 10, 10));
		// Podpisz, wybierając certyfikat w magazynie certyfikatów systemu Windows
		System.Security.Cryptography.X509Certificates.X509Store store = new System.Security.Cryptography.X509Certificates.X509Store(System.Security.Cryptography.X509Certificates.StoreLocation.CurrentUser);
		store.Open(System.Security.Cryptography.X509Certificates.OpenFlags.ReadOnly);
		// Ręcznie wybrałem certyfikat w sklepie
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

Gratulacje! Masz teraz przewodnik krok po kroku dotyczący podpisywania pliku PDF za pomocą karty inteligentnej przy użyciu pola podpisu w Aspose.PDF dla .NET. Możesz użyć tego kodu, aby dodać bezpieczne podpisy cyfrowe do dokumentów PDF.

Koniecznie zapoznaj się z oficjalną dokumentacją Aspose.PDF, aby uzyskać więcej informacji na temat zaawansowanych funkcji podpisu cyfrowego i zarządzania certyfikatami.

### Często zadawane pytania

#### P: Jaka jest korzyść z używania pola podpisu do podpisu cyfrowego za pomocą karty inteligentnej?

Odp.: Użycie pola podpisu do podpisu cyfrowego za pomocą karty inteligentnej zapewnia wyznaczony obszar w pliku PDF, w którym umieszczany jest podpis. Zwiększa to przejrzystość dokumentu i zapewnia autentyczność podpisu.

#### P: W jaki sposób biblioteka Aspose.PDF dla .NET ułatwia cyfrowe podpisywanie przy użyciu kart inteligentnych z polem podpisu?

Odp.: Aspose.PDF dla .NET upraszcza proces tworzenia pola podpisu, wybierania certyfikatu karty inteligentnej i stosowania podpisu cyfrowego w określonym obszarze dokumentu PDF.

#### P: Dlaczego wybór konkretnego certyfikatu jest ważny w przypadku podpisywania za pomocą karty inteligentnej?

O: Wybranie konkretnego certyfikatu pozwala na jednoznaczną identyfikację osoby podpisującej i zapewnienie integralności podpisu. Pomaga to w budowaniu zaufania i zgodności ze standardami podpisu cyfrowego.

#### P: W jaki sposób dostarczony kod źródłowy obsługuje proces podpisywania przy użyciu karty inteligentnej z polem podpisu?

Odp.: Kod źródłowy pokazuje, jak utworzyć pole podpisu, wybrać certyfikat karty inteligentnej i zastosować podpis cyfrowy z określonymi informacjami podpisu. Pokazuje także, jak sprawdzić ważność podpisu.

#### P: Czy mogę dostosować wygląd pola podpisu?

O: Tak, możesz dostosować wygląd pola podpisu, np. jego rozmiar, położenie i reprezentację wizualną, aby dopasować je do układu dokumentu.

#### P: Co się stanie, jeśli podpis nie przejdzie weryfikacji na etapie weryfikacji?

Odp.: Jeśli podpis nie przejdzie weryfikacji, zostanie zgłoszony wyjątek wskazujący, że podpis jest nieprawidłowy. Dzięki temu akceptowane są tylko ważne i zaufane podpisy.

#### P: Czy mogę zastosować wiele pól podpisów i podpisów opartych na kartach inteligentnych w jednym dokumencie PDF?

Odp.: Oczywiście można zastosować wiele pól podpisów i podpisów opartych na kartach inteligentnych w różnych obszarach tego samego dokumentu PDF, zapewniając wiele warstw zabezpieczeń.

#### P: W jaki sposób użycie pola podpisu usprawnia cały proces podpisywania dokumentów?

Odp.: Korzystanie z pola podpisu usprawnia proces podpisywania dokumentu, ponieważ pomaga podpisującemu złożyć podpis w wyznaczonym miejscu, dzięki czemu proces podpisywania jest bardziej zorganizowany i przyjazny dla użytkownika.

#### P: Czy istnieją jakieś ograniczenia w korzystaniu z pól podpisu w przypadku podpisywania za pomocą karty inteligentnej?

Odp.: Nie ma żadnych nieodłącznych ograniczeń w korzystaniu z pól podpisu w przypadku podpisywania za pomocą karty inteligentnej. Należy jednak upewnić się, że wybrana lokalizacja pola podpisu nie przesłania ważnej treści dokumentu.

#### P: Gdzie mogę znaleźć dalszą pomoc lub wsparcie dotyczące wdrażania podpisywania przy użyciu karty inteligentnej z polem podpisu?

Odp.: Aby uzyskać dodatkowe wskazówki i wsparcie, możesz zapoznać się z oficjalną dokumentacją Aspose.PDF i forami społeczności, które oferują cenne spostrzeżenia i rozwiązania dotyczące wdrażania bezpiecznych podpisów cyfrowych.