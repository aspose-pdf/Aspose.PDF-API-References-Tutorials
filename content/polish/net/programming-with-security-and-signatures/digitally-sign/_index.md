---
title: Zaloguj się cyfrowo w pliku PDF
linktitle: Zaloguj się cyfrowo w pliku PDF
second_title: Aspose.PDF z dokumentacją API .NET
description: Dowiedz się, jak cyfrowo podpisać plik PDF za pomocą Aspose.PDF dla .NET.
type: docs
weight: 40
url: /pl/net/programming-with-security-and-signatures/digitally-sign/
---
W tym samouczku przeprowadzimy Cię przez proces cyfrowego podpisywania pliku PDF przy użyciu Aspose.PDF dla .NET. Podpis cyfrowy gwarantuje autentyczność i integralność dokumentu poprzez dodanie unikalnego elektronicznego odcisku palca.

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
using System.Collections.Generic;
```

## Krok 3: Podpis cyfrowy

Pierwszym krokiem jest cyfrowe podpisanie pliku PDF. Dostarczony kod pokazuje, jak wykonać podpis cyfrowy za pomocą Aspose.PDF dla .NET.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
string pbxFile = "";
string inFile = dataDir + @"DigitallySign.pdf";
string outFile = dataDir + @"DigitallySign_out.pdf";
using (Document document = new Document(inFile))
{
     using (PdfFileSignature signature = new PdfFileSignature(document))
     {
         PKCS7 pkcs = new PKCS7(pbxFile, "WebSales");
         DocMDPSignature docMdpSignature = new DocMDPSignature(pkcs, DocMDPAccessPermissions.FillingInForms);
         System.Drawing.Rectangle rect = new System.Drawing.Rectangle(100, 100, 200, 100);
         signature.SignatureAppearance = dataDir + @"aspose-logo.jpg";
         signature.Certify(1, "Reason for signing", "Contact", "Location", true, rect, docMdpSignature);
         signature.Save(outFile);
     }
}
```

Ten kod ładuje plik PDF, tworzy podpis cyfrowy o określonym wyglądzie, a następnie zapisuje plik PDF z dodanym podpisem.

## Krok 4: Weryfikacja podpisu

Po dodaniu podpisu cyfrowego możesz sprawdzić, czy plik PDF zawiera ważny podpis.

```csharp
using(Document document = new Document(outFile))
{
     using (PdfFileSignature signature = new PdfFileSignature(document))
     {
         IList<string> sigNames = signature. GetSignNames();
         if (sigNames.Count > 0)
         {
             if (signature.VerifySigned(sigNames[0] as string))
             {
                 if (signature.IsCertified)
                 {
                     if (signature.GetAccessPermissions() == DocMDPAccessPermissions.FillingInForms)
                     {
                         // Zrób coś
                     }
                 }
             }
         }
     }
}
```

Kod ten weryfikuje pierwszy podpis pliku PDF i wykonuje dodatkowe akcje, jeśli podpis jest certyfikowany i ma określone uprawnienia.

### Przykładowy kod źródłowy dla Digitally Sign przy użyciu Aspose.PDF dla .NET 
```csharp
try
{
	// Ścieżka do katalogu dokumentów.
	string dataDir = "YOUR DOCUMENTS DIRECTORY";
	string pbxFile = "";
	string inFile = dataDir + @"DigitallySign.pdf";
	string outFile = dataDir + @"DigitallySign_out.pdf";
	using (Document document = new Document(inFile))
	{
		using (PdfFileSignature signature = new PdfFileSignature(document))
		{
			PKCS7 pkcs = new PKCS7(pbxFile, "WebSales"); // Użyj obiektów wolnostojących PKCS7/PKCS7
			DocMDPSignature docMdpSignature = new DocMDPSignature(pkcs, DocMDPAccessPermissions.FillingInForms);
			System.Drawing.Rectangle rect = new System.Drawing.Rectangle(100, 100, 200, 100);
			// Ustaw wygląd podpisu
			signature.SignatureAppearance = dataDir + @"aspose-logo.jpg";
			// Utwórz dowolny z trzech typów podpisów
			signature.Certify(1, "Signature Reason", "Contact", "Location", true, rect, docMdpSignature);
			// Zapisz wyjściowy plik PDF
			signature.Save(outFile);
		}
	}
	using (Document document = new Document(outFile))
	{
		using (PdfFileSignature signature = new PdfFileSignature(document))
		{
			IList<string> sigNames = signature.GetSignNames();
			if (sigNames.Count > 0) // Jakieś podpisy?
			{
				if (signature.VerifySigned(sigNames[0] as string)) // Zweryfikuj pierwszy
				{
					if (signature.IsCertified) // Atestowany?
					{
						if (signature.GetAccessPermissions() == DocMDPAccessPermissions.FillingInForms) // Uzyskaj pozwolenie na dostęp
						{
							// Zrób coś
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

Gratulacje! Pomyślnie wykonałeś podpis cyfrowy na pliku PDF przy użyciu Aspose.PDF dla .NET. W tym samouczku omówiono proces krok po kroku, od dodania podpisu cyfrowego po weryfikację jego ważności. Możesz teraz używać tej funkcji do zabezpieczania plików PDF podpisami cyfrowymi.

### Często zadawane pytania

#### P: Jaki jest cel tego samouczka?

Odp.: Ten samouczek poprowadzi Cię przez proces cyfrowego podpisywania pliku PDF przy użyciu Aspose.PDF dla .NET. Podpisy cyfrowe dodają elektroniczny odcisk palca, aby zapewnić autentyczność i integralność dokumentu.

#### P: Jakie wymagania wstępne są wymagane przed rozpoczęciem?

O: Zanim zaczniesz, upewnij się, że znasz podstawowy język programowania C#, masz zainstalowany program Visual Studio i bibliotekę Aspose.PDF dla .NET.

#### P: Jak skonfigurować środowisko programistyczne?

Odp.: Wykonaj podane kroki, aby skonfigurować środowisko programistyczne, w tym utworzyć nowy projekt C# w programie Visual Studio i zaimportować wymagane przestrzenie nazw.

#### P: Jak dodać podpis cyfrowy do pliku PDF?

 Odp.: Dostarczony przykładowy kod demonstruje, jak załadować plik PDF, utworzyć podpis cyfrowy, określić wygląd i zapisać podpisany plik PDF. Podpis cyfrowy jest dodawany za pomocą`Certify` metoda`PdfFileSignature` obiekt.

#### P: Jak sprawdzić ważność podpisu cyfrowego?

Odp.: Po dodaniu podpisu cyfrowego możesz użyć przykładowego kodu, aby zweryfikować ważność podpisu. Sprawdza, czy podpis jest certyfikowany i ma określone uprawnienia dostępu.

####  P: Co oznacza`PKCS7` object represent?

 O:`PKCS7` obiekt służy do zapewnienia funkcjonalności kryptograficznej podpisów cyfrowych. Służy do tworzenia podpisu cyfrowego w dostarczonym przykładowym kodzie.

#### P: Czy mogę dostosować wygląd podpisu cyfrowego?

 O: Tak, możesz dostosować wygląd podpisu cyfrowego, określając ścieżkę do obrazu w pliku`SignatureAppearance` własność`PdfFileSignature` obiekt.

#### P: Co się stanie, jeśli podpis będzie nieważny?

Odp.: Jeśli podpis jest nieprawidłowy, proces weryfikacji zakończy się niepowodzeniem i odpowiednie działania w bloku kodu weryfikacyjnego nie zostaną wykonane.

#### P: Jak mogę zapewnić bezpieczeństwo moich podpisów cyfrowych?

Odp.: Podpisy cyfrowe są bezpieczne z założenia i wykorzystują techniki kryptograficzne w celu zapewnienia autentyczności i integralności. Upewnij się, że Twój klucz prywatny jest bezpieczny i postępuj zgodnie z najlepszymi praktykami dotyczącymi obsługi podpisów cyfrowych.

#### P: Czy mogę dodać wiele podpisów cyfrowych do pliku PDF?

 Odp.: Tak, możesz dodać wiele podpisów cyfrowych do pliku PDF za pomocą`PdfFileSignature` obiekt`Sign` Lub`Certify` metody. Każdy podpis będzie miał swój własny wygląd i konfigurację.