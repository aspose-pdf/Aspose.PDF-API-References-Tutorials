---
title: Digitálně podepsat s časovým razítkem v souboru PDF
linktitle: Digitálně podepsat s časovým razítkem v souboru PDF
second_title: Aspose.PDF pro .NET API Reference
description: Naučte se, jak digitálně podepsat PDF s časovým razítkem pomocí Aspose.PDF pro .NET. Tento podrobný průvodce pokrývá předpoklady, nastavení certifikátu, časové razítko a další.
type: docs
weight: 50
url: /cs/net/programming-with-security-and-signatures/digitally-sign-with-time-stamp/
---
## Zavedení

Potřebovali jste někdy digitálně podepsat PDF a přidat časové razítko pro větší zabezpečení? Ať už pracujete na právních dokumentech, smlouvách nebo na čemkoli, co vyžaduje bezpečné ověření, digitální podpis s časovým razítkem přidává další vrstvu důvěryhodnosti. V tomto tutoriálu rozebereme, jak můžete použít Aspose.PDF pro .NET k přidání digitálního podpisu spolu s časovým razítkem do vašich dokumentů PDF. Nebojte se, půjdeme na to krok za krokem!

## Předpoklady

Než se ponoříme do kódu, je potřeba nastavit několik věcí, abyste je mohli sledovat. Zde je rychlý kontrolní seznam nezbytných předpokladů, abyste mohli začít:

-  Knihovna Aspose.PDF for .NET: Ve svém projektu budete potřebovat nainstalovanou knihovnu Aspose.PDF for .NET. Můžete[stáhněte si nejnovější verzi zde](https://releases.aspose.com/pdf/net/) nebo jej přidejte do svého projektu prostřednictvím NuGet.
- Dokument PDF: K práci budete potřebovat vzorový soubor PDF. Ujistěte se, že máte v adresáři projektu soubor, který chcete podepsat.
-  Digitální certifikát (soubor PFX): Ujistěte se, že máte digitální certifikát (a`.pfx` soubor) k digitálnímu podepsání dokumentu.
- Adresa URL časového razítka: Toto je online služba časového razítka, která bude použita k připojení časového razítka k digitálnímu podpisu. 
- Základní znalost C#: Nemusíte být expert, ale znalost základů C# vám pomůže porozumět a přizpůsobit kód.

Jakmile zaškrtnete všechna tato políčka, jste připraveni začít kódovat!

## Importujte balíčky

Chcete-li začít, budete muset do svého projektu C# importovat následující jmenné prostory. To zajišťuje, že máte přístup k příslušným třídám a funkcím Aspose.PDF.

```csharp
using System.IO;
using System;
using Aspose.Pdf;
using Aspose.Pdf.Facades;
using Aspose.Pdf.Forms;
using System.Collections;
```

## Krok 1: Načtěte dokument PDF

První věc, kterou musíme udělat, je načíst dokument PDF, který chceme podepsat. Postupujte takto:

```csharp
// Definujte cestu k adresáři dokumentů
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Načtěte dokument PDF
Document document = new Document(dataDir + @"DigitallySign.pdf");
```

 Tento krok je docela přímočarý. Jednoduše definujeme cestu k dokumentu, který chceme podepsat. The`Document` class z Aspose.PDF zpracovává načítání souboru.

## Krok 2: Nastavte digitální podpis

Dále vytvoříme digitální podpis pomocí třídy PKCS7 a načteme soubor PFX. Tento soubor PFX obsahuje váš certifikát a soukromý klíč, které jsou nezbytné pro podepsání dokumentu.

```csharp
// Cesta k vašemu souboru .pfx
string pfxFile = "YOUR DOCUMENTS DIRECTORY\\certificate.pfx";

// Inicializujte objekt podpisu
PdfFileSignature signature = new PdfFileSignature(document);

// Načtěte soubor PFX s heslem
PKCS7 pkcs = new PKCS7(pfxFile, "pfx_password");
```

 V tomto okamžiku říkáte Aspose, aby použil váš digitální certifikát k podepsání dokumentu. The`PKCS7`objekt za vás zařídí veškerou kryptografickou práci, takže se nemusíte starat o ty nejhrubší detaily.

## Krok 3: Přidejte nastavení časového razítka

Jednou z klíčových součástí robustního digitálního podpisu je časové razítko. Tím je zajištěno, že podpis dokumentu lze ověřit i po vypršení platnosti certifikátu. Pojďme nastavit časové razítko pomocí online autority pro časové razítko.

```csharp
// Definujte nastavení časového razítka
TimestampSettings timestampSettings = new TimestampSettings("https://your_timestamp_url", "user:password");

// Přidejte nastavení časového razítka do objektu PKCS7
pkcs.TimestampSettings = timestampSettings;
```

Zde zadáváte URL pro službu časového razítka, která automaticky poskytne čas a datum vašemu podpisu. To lze provést s ověřením nebo bez něj.

## Krok 4: Definujte umístění a vzhled podpisu

Nyní definujeme, kde se podpis v PDF objeví a jeho rozměry. Pozici pole pro podpis na stránce si můžete přizpůsobit, stejně jako jeho velikost.

```csharp
//Definujte vzhled a umístění podpisu (strana 1, se zadaným obdélníkem)
System.Drawing.Rectangle rect = new System.Drawing.Rectangle(100, 100, 200, 100);
```

Zde definujeme obdélník, který umístí podpis na souřadnice (100, 100) na první stránce PDF, o šířce 200 a výšce 100. Tyto hodnoty můžete změnit, aby odpovídaly vašemu návrhu.

## Krok 5: Podepište dokument PDF

Když je vše nastaveno, je čas skutečně použít digitální podpis na PDF. Tento krok kombinuje certifikát, časové razítko a umístění do jednoho jednoduchého příkazu.

```csharp
// Podepište dokument na první stránce
signature.Sign(1, "Signature Reason", "Contact", "Location", true, rect, pkcs);
```

Zde je to, co se děje:
- 1: Označuje, že podpis by měl být aplikován na první stránku.
- "Důvod podpisu": Zde můžete určit, proč dokument podepisujete.
- "Kontakt": Zadejte kontaktní informace podepisujícího.
- "Umístění": Zadejte umístění podepisujícího.
- true: Tato logická hodnota označuje, zda je podpis v dokumentu viditelný.
- rect: Obdélník, který jsme definovali dříve, určuje velikost a polohu podpisu.
- pkcs: Objekt PKCS7 obsahuje nastavení digitálního certifikátu a časového razítka.

## Krok 6: Uložte podepsaný PDF

Jakmile je dokument podepsán, zbývá jej pouze uložit. Chcete-li zachovat původní i podepsanou verzi, můžete zvolit nový název souboru.

```csharp
// Uložte podepsaný dokument PDF
signature.Save(dataDir + "DigitallySignWithTimeStamp_out.pdf");
```

Váš nově podepsaný a časově označený PDF je nyní uložen do určeného adresáře!

## Závěr

A tady to máte! Úspěšně jste digitálně podepsali PDF s časovým razítkem pomocí Aspose.PDF pro .NET. Tento proces zajišťuje pravost a integritu vašich dokumentů, což vám i příjemci poskytne klid. Digitální podpisy jsou v dnešním digitálním světě stále důležitější, takže zvládnutí tohoto procesu rozhodně stojí za to.

## FAQ

### Mohu pro certifikát použít jiný formát souboru?  
Ano, ale tutoriál se zaměřuje na použití souboru PFX, což je nejběžnější formát pro digitální certifikáty.

### Potřebuji k použití časového razítka internetové připojení?  
Ano, protože časové razítko je získáváno od online úřadu pro časové razítko, budete potřebovat přístup k internetu.

### Mohu podepsat více stránek v PDF?  
 Absolutně! Můžete upravit`signature.Sign()` způsob cílení na více stránek nebo procházení všech stránek.

### Co se stane, když je heslo souboru PFX nesprávné?  
Pokud je heslo nesprávné, obdržíte výjimku, takže se ujistěte, že je zadáno správně.

### Mohu učinit podpis neviditelným?  
 Ano, můžete projít`false` k`Sign` parametr viditelnosti metody, aby byl podpis neviditelný.