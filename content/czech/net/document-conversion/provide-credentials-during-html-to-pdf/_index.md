---
title: Poskytněte přihlašovací údaje během HTML do PDF
linktitle: Poskytněte přihlašovací údaje během HTML do PDF
second_title: Aspose.PDF pro .NET API Reference
description: Naučte se, jak převést HTML do PDF pomocí Aspose.PDF for .NET pomocí tohoto podrobného průvodce. Ideální pro vývojáře, kteří chtějí zefektivnit generování dokumentů.
type: docs
weight: 240
url: /cs/net/document-conversion/provide-credentials-during-html-to-pdf/
---
## Zavedení

Ve světě vývoje softwaru je převod HTML do PDF běžným požadavkem. Ať už generujete sestavy, faktury nebo jakýkoli jiný dokument, mít spolehlivou knihovnu, která tento úkol zvládne, vám může ušetřit spoustu času a úsilí. Vstupte do Aspose.PDF for .NET, výkonné knihovny, která umožňuje vývojářům snadno vytvářet, manipulovat a převádět dokumenty PDF. V tomto tutoriálu vás provedeme procesem používání Aspose.PDF k převodu HTML do PDF a zároveň poskytujeme přihlašovací údaje pro zabezpečený přístup. Takže popadněte svůj kódovací klobouk a pojďme se ponořit!

## Předpoklady

Než začneme, je třeba mít připraveno několik věcí:

1. Visual Studio: Ujistěte se, že máte na svém počítači nainstalované Visual Studio. Toto bude naše vývojové prostředí.
2.  Aspose.PDF pro .NET: Knihovnu si můžete stáhnout z[webové stránky](https://releases.aspose.com/pdf/net/) . Pokud si to chcete nejprve vyzkoušet, můžete také získat a[zkušební verze zdarma](https://releases.aspose.com/).
3. Základní znalost C#: Znalost programování v C# vám pomůže lépe porozumět příkladům.
4. Přístup k internetu: Protože budeme načítat obsah HTML z adresy URL, ujistěte se, že máte aktivní připojení k internetu.

## Importujte balíčky

Chcete-li začít s Aspose.PDF, musíte do projektu importovat potřebné balíčky. Můžete to udělat takto:

1. Otevřete projekt sady Visual Studio.
2. Klikněte pravým tlačítkem na svůj projekt v Průzkumníku řešení a vyberte „Spravovat balíčky NuGet“.
3. Vyhledejte „Aspose.PDF“ a nainstalujte nejnovější verzi.

```csharp
using System.IO;
using Aspose.Pdf;
using System;
using System.Net;
```
Nyní, když máme vše nastaveno, pojďme si rozdělit proces převodu HTML do PDF s přihlašovacími údaji na zvládnutelné kroky.

## Krok 1: Nastavte adresář dokumentů

Než budeme moci převést HTML do PDF, musíme určit, kam bude naše výstupní PDF uloženo. To se provádí definováním cesty k adresáři dokumentů.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Nahradit`"YOUR DOCUMENT DIRECTORY"` se skutečnou cestou, kam chcete soubor PDF uložit. Může to být složka na ploše nebo jakékoli jiné umístění ve vašem systému.

## Krok 2: Vytvořte webovou žádost

 Dále musíme vytvořit požadavek na načtení obsahu HTML z konkrétní adresy URL. Toto je místo, kde použijeme`WebRequest` třída.

```csharp
WebRequest request = WebRequest.Create("http://My.signchart.com/Report/PrintBook.asp?ProjectGuid=6FB9DBB0-");
```

Zde vytváříme požadavek na adresu URL, která obsahuje kód HTML, který chceme převést. Nezapomeňte nahradit adresu URL adresou, kterou chcete použít.

## Krok 3: Nastavte přihlašovací údaje (pokud jsou vyžadovány)

Pokud server vyžaduje přihlašovací údaje pro přístup k obsahu, musíme je nastavit. To se provádí pomocí`CredentialCache.DefaultCredentials`.

```csharp
request.Credentials = CredentialCache.DefaultCredentials;
```

 Tento řádek zajišťuje, že požadavek používá výchozí přihlašovací údaje aktuálního uživatele. Pokud potřebujete zadat konkrétní přihlašovací údaje, můžete vytvořit nové`NetworkCredential` objekt.

## Krok 4: Získejte odpověď

Nyní, když máme požadavek nastaven, je čas získat odpověď ze serveru.

```csharp
HttpWebResponse response = (HttpWebResponse)request.GetResponse();
```

Tento řádek odešle požadavek a čeká na odpověď serveru. Pokud vše půjde dobře, obdržíme obsah HTML, který potřebujeme.

## Krok 5: Přečtěte si tok odpovědí

 Jakmile máme odpověď, musíme si přečíst obsah vrácený serverem. To se provádí pomocí a`StreamReader`.

```csharp
Stream dataStream = response.GetResponseStream();
StreamReader reader = new StreamReader(dataStream);
string responseFromServer = reader.ReadToEnd();
reader.Close();
dataStream.Close();
response.Close();
```

 Zde čteme celý obsah toku odpovědí do řetězcové proměnné nazvané`responseFromServer`. Nezapomeňte zavřít čtečku a stream, abyste uvolnili zdroje.

## Krok 6: Převeďte HTML do PDF

Nyní přichází ta vzrušující část! Obsah HTML převedeme do dokumentu PDF pomocí Aspose.PDF.

```csharp
MemoryStream stream = new MemoryStream(System.Text.Encoding.UTF8.GetBytes(responseFromServer));
HtmlLoadOptions options = new HtmlLoadOptions("http://My.signchart.com/");
options.ExternalResourcesCredentials = CredentialCache.DefaultCredentials;

Document pdfDocument = new Document(stream, options);
```

 tomto kroku vytváříme a`MemoryStream` z obsahu HTML a nastavení`HtmlLoadOptions`. To nám umožňuje určit základní adresu URL pro jakékoli externí zdroje (jako jsou obrázky nebo šablony stylů), na které může HTML odkazovat.

## Krok 7: Uložte dokument PDF

Nakonec musíme vygenerovaný PDF dokument uložit do zadaného adresáře.

```csharp
pdfDocument.Save(dataDir + "ProvideCredentialsDuringHTMLToPDF_out.pdf");
```

 Tento řádek uloží soubor PDF s názvem`ProvideCredentialsDuringHTMLToPDF_out.pdf` v adresáři, který jsme uvedli dříve.

## Závěr

A tady to máte! Úspěšně jste převedli HTML do PDF pomocí Aspose.PDF for .NET a zároveň jste poskytli přihlašovací údaje pro bezpečný přístup. Tato výkonná knihovna usnadňuje práci s dokumenty PDF a pomocí pouhých několika řádků kódu můžete z obsahu HTML generovat profesionálně vypadající soubory PDF. 

## FAQ

### Co je Aspose.PDF pro .NET?
Aspose.PDF for .NET je knihovna, která umožňuje vývojářům vytvářet, manipulovat a převádět dokumenty PDF v aplikacích .NET.

### Jak nainstaluji Aspose.PDF?
 Aspose.PDF můžete nainstalovat přes NuGet Package Manager ve Visual Studiu nebo si jej stáhnout z[webové stránky](https://releases.aspose.com/pdf/net/).

### Mohu používat Aspose.PDF zdarma?
Ano, Aspose nabízí bezplatnou zkušební verzi, kterou můžete použít k vyhodnocení knihovny před jejím zakoupením.

### Jaké typy dokumentů mohu vytvořit pomocí Aspose.PDF?
Pomocí Aspose.PDF můžete vytvořit širokou škálu dokumentů, včetně zpráv, faktur a formulářů.

### Kde najdu podporu pro Aspose.PDF?
 Podporu a dotazy můžete najít na[Aspose fórum podpory](https://forum.aspose.com/c/pdf/10).