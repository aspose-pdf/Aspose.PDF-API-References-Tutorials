---
title: Digitálně podepsat s časovým razítkem v souboru PDF
linktitle: Digitálně podepsat s časovým razítkem v souboru PDF
second_title: Aspose.PDF pro .NET API Reference
description: Naučte se provádět digitální podpis s časovým razítkem v souboru PDF pomocí Aspose.PDF pro .NET.
type: docs
weight: 50
url: /cs/net/programming-with-security-and-signatures/digitally-sign-with-time-stamp/
---
V tomto tutoriálu vás provedeme procesem digitálního podepisování v souboru PDF s časovým razítkem pomocí Aspose.PDF pro .NET. Digitální podpis s časovým razítkem zaručuje pravost a integritu dokumentu přidáním elektronického otisku prstu s časovým razítkem.

## Krok 1: Předpoklady

Než začnete, ujistěte se, že máte následující předpoklady:

- Základní znalost programovacího jazyka C#
- Instalace sady Visual Studio na váš počítač
- Nainstalovaná knihovna Aspose.PDF pro .NET

## Krok 2: Nastavení prostředí

Chcete-li začít, postupujte podle následujících kroků a nastavte vývojové prostředí:

1. Otevřete Visual Studio a vytvořte nový projekt C#.
2. Importujte požadované jmenné prostory do souboru kódu:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Forms;
```

## Krok 3: Digitální podpis s časovým razítkem

Prvním krokem je provedení digitálního podpisu s časovým razítkem na souboru PDF. Poskytnutý kód ukazuje, jak dosáhnout tohoto podpisu pomocí Aspose.PDF pro .NET.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
string pfxFile = "";
using (Document document = new Document(dataDir + @"DigitallySign.pdf"))
{
     using (PdfFileSignature signature = new PdfFileSignature(document))
     {
         PKCS7 pkcs = new PKCS7(pfxFile, "pfx_password");
         TimestampSettings timestampSettings = new TimestampSettings("https:\\your_timestamp_settings", "user:password");
         pkcs. TimestampSettings = timestampSettings;
         System.Drawing.Rectangle rect = new System.Drawing.Rectangle(100, 100, 200, 100);
         signature.Sign(1, "Reason for signing", "Contact", "Location", true, rect, pkcs);
         signature.Save(dataDir + "DigitallySignWithTimeStamp_out.pdf");
     }
}
```

Tento kód načte soubor PDF, vytvoří digitální podpis s časovým razítkem pomocí souboru PFX (soukromý klíč) a zadaných parametrů časového razítka. Podpis je poté přidán do souboru PDF a uložen s příponou "_ven".

### Ukázka zdrojového kódu pro Digitally Sign With Time Stamp pomocí Aspose.PDF pro .NET 
```csharp
// Cesta k adresáři dokumentů.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
string pfxFile = "";
using (Document document = new Document(dataDir + @"DigitallySign.pdf"))
{
	using (PdfFileSignature signature = new PdfFileSignature(document))
	{
		PKCS7 pkcs = new PKCS7(pfxFile, "pfx_password");
		TimestampSettings timestampSettings = new TimestampSettings("https:\\your_timestamp_settings", "user:password"); // Uživatel/Heslo lze vynechat
		pkcs.TimestampSettings = timestampSettings;
		System.Drawing.Rectangle rect = new System.Drawing.Rectangle(100, 100, 200, 100);
		// Vytvořte libovolný ze tří typů podpisu
		signature.Sign(1, "Signature Reason", "Contact", "Location", true, rect, pkcs);
		// Uložit výstupní soubor PDF
		signature.Save(dataDir + "DigitallySignWithTimeStamp_out.pdf");
	}
}
```

## Závěr

gratuluji! Úspěšně jste provedli digitální podpis s časovým razítkem na souboru PDF pomocí Aspose.PDF pro .NET. Tento výukový program popsal proces krok za krokem od vytvoření podpisu po uložení aktualizovaného souboru PDF. Tuto funkci nyní můžete použít k přidávání digitálních podpisů s časovým razítkem do souborů PDF.

### Časté dotazy pro digitální podpis s časovým razítkem v souboru PDF

#### Otázka: Jaký je účel digitálního podepisování s časovým razítkem?

Odpověď: Digitální podpis s časovým razítkem přidá do souboru PDF elektronický otisk s časovým razítkem, čímž zajistí autentičnost a integritu dokumentu v konkrétním okamžiku.

#### Otázka: Jaké předpoklady jsou potřeba ke spuštění tohoto kurzu?

Odpověď: Než začnete, ujistěte se, že máte základní znalosti programovacího jazyka C#, máte nainstalované Visual Studio a máte nainstalovanou knihovnu Aspose.PDF pro .NET.

#### Otázka: Jak mohu nastavit své vývojové prostředí?

Odpověď: Podle uvedených kroků nastavte vývojové prostředí, včetně vytvoření nového projektu C# v sadě Visual Studio a importu potřebných oborů názvů.

#### Otázka: Jak přidám digitální podpis s časovým razítkem do PDF?

Odpověď: Poskytnutý ukázkový kód ukazuje, jak načíst soubor PDF, vytvořit digitální podpis s časovým razítkem pomocí souboru PFX (soukromý klíč) a zadaných nastavení časového razítka, přidat podpis do souboru PDF a uložit aktualizovaný soubor.

#### Otázka: Co je soubor PFX a proč je použit v příkladu?

Odpověď: Soubor PFX (Personal Exchange Format) obsahuje soukromý klíč a certifikát. Zde se používá k poskytování kryptografických funkcí pro digitální podpisy. Ujistěte se, že jste zástupný symbol nahradili vaším souborem PFX a heslem.

#### Otázka: Co jsou TimestampSettings?

A: TimestampSettings definují nastavení pro server časového razítka, který se používá k přidání elektronického časového razítka k podpisu. Zahrnuje adresu URL serveru časového razítka a volitelné přihlašovací údaje uživatele.

#### Otázka: Mohu použít jiný server časových razítek než ten v příkladu?
 Odpověď: Ano, můžete použít jakýkoli kompatibilní server časových razítek. Nahraďte adresu URL a v případě potřeby zadejte příslušné přihlašovací údaje uživatele`TimestampSettings` objekt.

#### Otázka: Jaký je účel určení obdélníku podpisu?

Odpověď: Podpisový obdélník definuje polohu a rozměry vzhledu digitálního podpisu na stránce PDF. Upravte tyto hodnoty pro umístění podpisu podle potřeby.

#### Otázka: Co se stane, když je server časového razítka během podepisování nedostupný?

Odpověď: Pokud je server časových razítek během podepisování nedostupný, proces může selhat nebo trvat déle. Ujistěte se, že váš server časových razítek je spolehlivý a dostupný.

#### Otázka: Jak mohu ověřit přítomnost časového razítka v podepsaném PDF?

 Odpověď: Podepsané PDF si můžete prohlédnout pomocí poskytnutého ukázkového kódu. The`TimestampSettings` použitý při podepisování by měl být k dispozici v podrobnostech podpisu.

#### Otázka: Jsou digitální podpisy s časovými razítky právně závazné?

Odpověď: Digitální podpisy s časovými razítky mají právní hodnotu v mnoha jurisdikcích a jsou často považovány za spolehlivější než jednoduché digitální podpisy. Konkrétní předpisy konzultujte s právními odborníky ve vaší jurisdikci.

#### Otázka: Mohu do PDF přidat více digitálních podpisů s časovými razítky?

Odpověď: Ano, do souboru PDF můžete přidat více digitálních podpisů s časovými razítky opakovaným voláním procesu vytváření podpisu. Každý podpis bude mít své vlastní časové razítko.