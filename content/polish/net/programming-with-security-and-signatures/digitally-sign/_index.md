---
title: Cyfrowo podpisz plik PDF
linktitle: Cyfrowo podpisz plik PDF
second_title: Aspose.PDF dla .NET API Reference
description: Dowiedz się, jak cyfrowo podpisać plik PDF za pomocą Aspose.PDF dla platformy .NET.
type: docs
weight: 40
url: /pl/net/programming-with-security-and-signatures/digitally-sign/
---
W tym samouczku przeprowadzimy Cię przez proces cyfrowego podpisywania pliku PDF za pomocą Aspose.PDF dla .NET. Podpis cyfrowy gwarantuje autentyczność i integralność dokumentu, dodając unikalny elektroniczny odcisk palca.

## Krok 1: Wymagania wstępne

Zanim zaczniesz, upewnij się, że spełniasz następujące wymagania wstępne:

- Podstawowa znajomość języka programowania C#
- Instalowanie programu Visual Studio na komputerze
- Zainstalowano bibliotekę Aspose.PDF dla .NET

## Krok 2: Konfiguracja środowiska

Aby rozpocząć, wykonaj poniższe kroki, aby skonfigurować środowisko programistyczne:

1. Otwórz program Visual Studio i utwórz nowy projekt C#.
2. Zaimportuj wymagane przestrzenie nazw do pliku kodu:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Forms;
using System.Collections.Generic;
```

## Krok 3: Podpis cyfrowy

Pierwszym krokiem jest cyfrowe podpisanie pliku PDF. Dostarczony kod pokazuje, jak utworzyć podpis cyfrowy za pomocą Aspose.PDF dla .NET.

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

Po dodaniu podpisu cyfrowego możesz sprawdzić, czy plik PDF zawiera prawidłowy podpis.

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

Ten kod weryfikuje pierwszy podpis pliku PDF i wykonuje dodatkowe czynności, jeśli podpis jest certyfikowany i posiada określone uprawnienia.

### Przykładowy kod źródłowy dla funkcji Digitally Sign using Aspose.PDF for .NET 
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
			PKCS7 pkcs = new PKCS7(pbxFile, "WebSales"); // Użyj obiektów PKCS7/PKCS7Detached
			DocMDPSignature docMdpSignature = new DocMDPSignature(pkcs, DocMDPAccessPermissions.FillingInForms);
			System.Drawing.Rectangle rect = new System.Drawing.Rectangle(100, 100, 200, 100);
			// Ustaw wygląd podpisu
			signature.SignatureAppearance = dataDir + @"aspose-logo.jpg";
			// Utwórz dowolny z trzech typów podpisu
			signature.Certify(1, "Signature Reason", "Contact", "Location", true, rect, docMdpSignature);
			// Zapisz plik wyjściowy PDF
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
						if (signature.GetAccessPermissions() == DocMDPAccessPermissions.FillingInForms) // Uzyskaj uprawnienia dostępu
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

Gratulacje! Udało Ci się pomyślnie wykonać podpis cyfrowy na pliku PDF przy użyciu Aspose.PDF dla .NET. Ten samouczek obejmuje proces krok po kroku, od dodania podpisu cyfrowego do weryfikacji jego ważności. Teraz możesz użyć tej funkcji, aby zabezpieczyć pliki PDF za pomocą podpisów cyfrowych.

### Najczęściej zadawane pytania

#### P: Jaki jest cel tego poradnika?

A: Ten samouczek przeprowadzi Cię przez proces cyfrowego podpisywania pliku PDF za pomocą Aspose.PDF dla .NET. Podpisy cyfrowe dodają elektroniczny odcisk palca, aby zapewnić autentyczność i integralność dokumentu.

#### P: Jakie warunki wstępne należy spełnić przed rozpoczęciem?

O: Zanim zaczniesz, upewnij się, że posiadasz podstawową wiedzę na temat języka programowania C#, masz zainstalowany program Visual Studio i bibliotekę Aspose.PDF dla platformy .NET.

#### P: Jak skonfigurować środowisko programistyczne?

A: Wykonaj podane kroki, aby skonfigurować środowisko programistyczne, m.in. utwórz nowy projekt C# w programie Visual Studio i zaimportuj wymagane przestrzenie nazw.

#### P: Jak dodać podpis cyfrowy do pliku PDF?

 A: Dostarczony przykładowy kod pokazuje, jak załadować plik PDF, utworzyć podpis cyfrowy, określić wygląd i zapisać podpisany plik PDF. Podpis cyfrowy jest dodawany za pomocą`Certify` metoda`PdfFileSignature` obiekt.

#### P: Jak mogę sprawdzić ważność podpisu cyfrowego?

A: Po dodaniu podpisu cyfrowego możesz użyć przykładowego kodu, aby zweryfikować ważność podpisu. Sprawdza on, czy podpis jest certyfikowany i ma określone uprawnienia dostępu.

####  P: Co to jest`PKCS7` object represent?

 A: Ten`PKCS7` obiekt jest używany do zapewnienia kryptograficznej funkcjonalności dla podpisów cyfrowych. Jest używany do tworzenia podpisu cyfrowego w podanym przykładowym kodzie.

#### P: Czy mogę dostosować wygląd podpisu cyfrowego?

 O: Tak, możesz dostosować wygląd podpisu cyfrowego, określając ścieżkę do obrazu w`SignatureAppearance` własność`PdfFileSignature` obiekt.

#### P: Co się stanie, jeśli podpis będzie nieprawidłowy?

O: Jeśli podpis jest nieprawidłowy, proces weryfikacji zakończy się niepowodzeniem, a odpowiednie działania w bloku kodu weryfikacyjnego nie zostaną wykonane.

#### P: W jaki sposób mogę zagwarantować bezpieczeństwo moich podpisów cyfrowych?

A: Podpisy cyfrowe są bezpieczne z założenia i wykorzystują techniki kryptograficzne, aby zapewnić autentyczność i integralność. Upewnij się, że Twój klucz prywatny jest bezpieczny i postępuj zgodnie z najlepszymi praktykami obsługi podpisów cyfrowych.

#### P: Czy mogę dodać wiele podpisów cyfrowych do pliku PDF?

 O: Tak, możesz dodać wiele podpisów cyfrowych do pliku PDF za pomocą`PdfFileSignature` obiekt`Sign` Lub`Certify` metody. Każdy podpis będzie miał swój własny wygląd i konfigurację.