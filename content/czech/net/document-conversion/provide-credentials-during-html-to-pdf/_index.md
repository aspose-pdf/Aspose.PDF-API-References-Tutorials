---
title: Poskytněte přihlašovací údaje během HTML do PDF
linktitle: Poskytněte přihlašovací údaje během HTML do PDF
second_title: Aspose.PDF pro .NET API Reference
description: Krok za krokem průvodce převodem HTML do PDF poskytnutím přihlašovacích údajů Aspose.PDF pro .NET.
type: docs
weight: 240
url: /cs/net/document-conversion/provide-credentials-during-html-to-pdf/
---
tomto tutoriálu vás provedeme procesem převodu souboru HTML do PDF a zároveň poskytneme přihlašovací údaje při přístupu k zabezpečené adrese URL pomocí Aspose.PDF for .NET. Podle níže uvedených kroků budete moci převést obsah HTML do PDF pomocí příslušných přihlašovacích údajů.

## Předpoklady
Než začnete, ujistěte se, že splňujete následující předpoklady:

- Základní znalost programovacího jazyka C#.
- Knihovna Aspose.PDF pro .NET nainstalovaná ve vašem systému.
- Vývojové prostředí, jako je Visual Studio.

## Krok 1: Načtěte zabezpečený obsah HTML
V tomto kroku načteme zabezpečený obsah HTML z adresy URL pomocí příslušných přihlašovacích údajů. Použijte následující kód:

```csharp
// Cesta k adresáři dokumentů.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Vytvořte požadavek na adresu URL.
WebRequest request = WebRequest.Create("http://My.signchart.com/Report/PrintBook.asp?ProjectGuid=6FB9DBB0-");
// Pokud je to nutné pro server, nastavte přihlašovací údaje.
request.Credentials = CredentialCache.DefaultCredentials;
// Získejte odpověď.
HttpWebResponse response = (HttpWebResponse)request.GetResponse();

// Získejte stream obsahující obsah vrácený serverem.
Stream dataStream = response. GetResponseStream();
// Pro snadný přístup otevřete stream pomocí aplikace StreamReader.
StreamReader reader = new StreamReader(dataStream);
// Přečtěte si obsah.
string responseFromServer = reader.ReadToEnd();
reader. Close();
dataStream.Close();
response. Close();
```

 Nezapomeňte vyměnit`"YOUR DOCUMENTS DIRECTORY"` se skutečným adresářem, kam chcete uložit výsledný soubor PDF.

## Krok 2: Převeďte HTML do PDF poskytnutím přihlašovacích údajů
Nyní načteme načtený obsah HTML a převedeme jej do formátu PDF, přičemž poskytneme příslušné přihlašovací údaje. Použijte následující kód:

```csharp
MemoryStream stream = new MemoryStream(System.Text.Encoding.UTF8.GetBytes(responseFromServer));

HtmlLoadOptions options = new HtmlLoadOptions("http://My.signchart.com/");
options.ExternalResourcesCredentials = CredentialCache.DefaultCredentials;

// Načtěte soubor HTML
Document pdfDocument = new Document(stream, options);
```

## Krok 3: Uložení výsledného souboru PDF
Nakonec výsledný soubor PDF uložíme. Použijte následující kód:

```csharp
// Uložte výsledný soubor PDF
pdfDocument.Save(dataDir + "ProvideCredentialsDuringHTMLToPDF_out.pdf");
```

 Výše uvedený kód uloží výsledný soubor PDF s názvem souboru`"ProvideCredentialsDuringHTMLToPDF_out.pdf"`.

### Příklad zdrojového kódu pro Poskytnutí pověření během HTML do PDF pomocí Aspose.PDF pro .NET

```csharp
try
{
	
	// Cesta k adresáři dokumentů.
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	// Vytvořte požadavek na adresu URL.
	WebRequest request = WebRequest.Create("http:// My.signchart.com/Report/PrintBook.asp?ProjectGuid=6FB9DBB0-");
	// Pokud to server vyžaduje, nastavte přihlašovací údaje.
	request.Credentials = CredentialCache.DefaultCredentials;
	// Získejte odpověď.
	HttpWebResponse response = (HttpWebResponse)request.GetResponse();

	// Získejte stream obsahující obsah vrácený serverem.
	Stream dataStream = response.GetResponseStream();
	// Pro snadný přístup otevřete stream pomocí aplikace StreamReader.
	StreamReader reader = new StreamReader(dataStream);
	// Přečtěte si obsah.
	string responseFromServer = reader.ReadToEnd();
	reader.Close();
	dataStream.Close();
	response.Close();

	MemoryStream stream = new MemoryStream(System.Text.Encoding.UTF8.GetBytes(responseFromServer));

	HtmlLoadOptions options = new HtmlLoadOptions("http:// My.signchart.com/");
	options.ExternalResourcesCredentials = CredentialCache.DefaultCredentials;

	// Načíst soubor HTML
	Document pdfDocument = new Document(stream, options);
	// Uložte výsledný soubor
	pdfDocument.Save("ProvideCredentialsDuringHTMLToPDF_out.pdf");
	
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## Závěr
tomto tutoriálu jsme se zabývali procesem převodu souboru HTML do formátu PDF krok za krokem a zároveň poskytnutím přihlašovacích údajů při přístupu k zabezpečené adrese URL pomocí Aspose.PDF for .NET. Podle výše uvedených pokynů budete schopni úspěšně převést obsah HTML do PDF a zároveň poskytnout správné přihlašovací údaje.

### FAQ

#### Otázka: Co je Aspose.PDF pro .NET?

Odpověď: Aspose.PDF for .NET je robustní knihovna, která umožňuje vývojářům pracovat s dokumenty PDF v aplikacích C#. Nabízí širokou škálu funkcí, včetně převodu HTML do PDF.

#### Otázka: Jak mohu načíst zabezpečený obsah HTML z adresy URL?

 Odpověď: Chcete-li načíst zabezpečený obsah HTML z adresy URL, můžete použít`WebRequest` třídy v C#. Ujistěte se, že jste nastavili příslušná pověření pomocí`Credentials` vlastnictví.

#### Otázka: Jaké jsou předpoklady pro tento tutoriál?

Odpověď: Než budete pokračovat s výukovým programem, ujistěte se, že máte následující předpoklady:

- Základní znalost programovacího jazyka C#.
- Knihovna Aspose.PDF pro .NET nainstalovaná ve vašem systému.
- Vývojové prostředí, jako je Visual Studio.

#### Otázka: Jak Aspose.PDF for .NET zpracovává externí zdroje při převodu HTML do PDF?

 A: Aspose.PDF pro .NET poskytuje`HtmlLoadOptions`třídy pro zpracování externích zdrojů během převodu HTML do PDF. Přihlašovací údaje k externímu prostředku můžete nastavit pomocí`ExternalResourcesCredentials` vlastnictví.

#### Otázka: Mohu upravit název souboru pro výsledný soubor PDF?

 Odpověď: Ano, můžete upravit název souboru pro výsledný soubor PDF úpravou kódu, který uloží dokument PDF. Jednoduše změňte požadovaný název souboru v`pdfDocument.Save()` metoda.