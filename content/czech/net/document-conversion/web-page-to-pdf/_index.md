---
title: Webová stránka do PDF
linktitle: Webová stránka do PDF
second_title: Aspose.PDF pro .NET API Reference
description: Krok za krokem průvodce převodem webové stránky do PDF pomocí Aspose.PDF pro .NET.
type: docs
weight: 320
url: /cs/net/document-conversion/web-page-to-pdf/
---
V tomto tutoriálu vás krok za krokem provedeme, jak převést webovou stránku do PDF pomocí knihovny Aspose.PDF for .NET. Vysvětlíme vám poskytnutý zdrojový kód C# a ukážeme vám, jak jej implementovat do vašich vlastních projektů. Na konci tohoto tutoriálu budete schopni bez námahy převádět webové stránky na dokumenty PDF.

## Úvod
Převod webových stránek do formátu PDF je běžným požadavkem mnoha aplikací. Převedením webového obsahu do PDF můžete snadno zachovat rozvržení, formátování a obrázky původní webové stránky. Aspose.PDF for .NET je výkonná knihovna, která vám umožňuje provádět tento převod efektivně a přesně.

## Požadavky
Než začneme, ujistěte se, že máte splněny následující předpoklady:
- Visual Studio nainstalované na vašem počítači
- Aspose.PDF pro knihovnu .NET (můžete si ji stáhnout z oficiálních stránek Aspose)
- Základní znalost programování v C#


## Krok 1: Definujte adresář dokumentů
```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```
 Nahradit`"YOUR DOCUMENT DIRECTORY"` s cestou, kam chcete uložit vygenerovaný soubor PDF.

## Krok 2: Vytvořte webovou žádost
```csharp
WebRequest request = WebRequest.Create("https://en.wikipedia.org/wiki/Main_Page");
request.Credentials = CredentialCache.DefaultCredentials;
```
Vytvořte objekt webového požadavku a zadejte adresu URL webové stránky, kterou chcete převést. Adresu URL můžete nahradit jakoukoli požadovanou webovou stránkou.

## Krok 3: Získejte odezvu webu
```csharp
HttpWebResponse response = (HttpWebResponse)request.GetResponse();
```
Odešlete webový požadavek a získejte odpověď ze serveru.

## Krok 4: Přečtěte si obsah webu
```csharp
Stream dataStream = response. GetResponseStream();
StreamReader reader = new StreamReader(dataStream);
string responseFromServer = reader.ReadToEnd();
reader. Close();
dataStream.Close();
response. Close();
```
 Přečtěte si obsah webové stránky pomocí a`StreamReader` uložte jej do`responseFromServer` variabilní.

## Krok 5: Převeďte HTML do PDF
```csharp
MemoryStream stream = new MemoryStream(System.Text.Encoding.UTF8.GetBytes(responseFromServer));
HtmlLoadOptions options = new HtmlLoadOptions("https://en.wikipedia.org/wiki/");
Document pdfDocument = new Document(stream, options);
options.PageInfo.IsLandscape = true;
pdfDocument.Save(dataDir + "WebPageToPDF_out.pdf");
```
 Vytvořit`MemoryStream` objekt pro načtení obsahu webové stránky. Poté vytvořte instanci`HtmlLoadOptions` a předat základní adresu URL webové stránky. Dále vytvořte a`Document` objekt pomocí načteného proudu a možností načtení HTML. Nastav`IsLandscape` majetek do`true` pokud chcete, aby byl PDF v orientaci na šířku. Nakonec uložte dokument PDF do určeného adresáře

.

## Krok 6: Ošetřete výjimky
```csharp
catch (Exception ex)
{
Console.WriteLine(ex.Message);
}
```
Zachyťte všechny výjimky, které mohou nastat během procesu převodu, a zobrazte chybovou zprávu.

### Příklad zdrojového kódu pro webovou stránku do PDF pomocí Aspose.PDF pro .NET

```csharp
try
{
	
	// Cesta k adresáři dokumentů.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// Vytvořte požadavek na adresu URL.
	WebRequest request = WebRequest.Create("https:// En.wikipedia.org/wiki/Main_Page");
	// Pokud to server vyžaduje, nastavte přihlašovací údaje.
	request.Credentials = CredentialCache.DefaultCredentials;
	// Časový limit v milisekundách před vypršením časového limitu požadavku
	// Časový limit požadavku = 100;

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
	HtmlLoadOptions options = new HtmlLoadOptions("https:// En.wikipedia.org/wiki/");


	// Načíst soubor HTML
	Document pdfDocument = new Document(stream, options);

	options.PageInfo.IsLandscape = true;

	// Uložit výstup ve formátu PDF
	pdfDocument.Save(dataDir + "WebPageToPDF_out.pdf");
	
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## Závěr
tomto tutoriálu jsme se naučili, jak převést webovou stránku do PDF pomocí knihovny Aspose.PDF for .NET. Prošli jsme si podrobného průvodce vysvětlujícího poskytnutý zdrojový kód C#. Podle těchto pokynů můžete snadno integrovat funkci převodu webové stránky do formátu PDF do svých vlastních aplikací .NET.

### FAQ

#### Otázka: Co je Aspose.PDF pro .NET?

A: Aspose.PDF for .NET je výkonná knihovna, která umožňuje vývojářům pracovat s dokumenty PDF v aplikacích C#. Poskytuje různé funkce, včetně převodu webových stránek do PDF.

#### Otázka: Proč bych měl chtít převést webovou stránku do PDF?

Odpověď: Převod webových stránek do PDF je užitečný pro zachování rozvržení, formátování a obrázků původního webového obsahu. Umožňuje vám vytvořit snímek webové stránky pro offline prohlížení nebo sdílení s ostatními.

#### Otázka: Jaké jsou předpoklady pro tento tutoriál?

A: Abyste mohli postupovat podle tohoto návodu, musíte mít na svém počítači nainstalované Visual Studio, knihovnu Aspose.PDF for .NET a základní znalosti programování v C#.

#### Otázka: Mohu převést jakoukoli webovou stránku do PDF?

Odpověď: Ano, můžete libovolnou webovou stránku převést do PDF zadáním adresy URL webové stránky v kódu. Aspose.PDF for .NET načte webový obsah a převede jej do formátu PDF.

#### Otázka: Jak mohu přizpůsobit výstup PDF, například orientaci stránky?

 Odpověď: Výstup PDF můžete přizpůsobit pomocí možností jako`IsLandscape` pro nastavení orientace stránky. V poskytnutém kódu`options.PageInfo.IsLandscape = true` se používá k vytvoření PDF v orientaci na šířku.