---
title: Digitálně se přihlásit do souboru PDF
linktitle: Digitálně se přihlásit do souboru PDF
second_title: Aspose.PDF pro .NET API Reference
description: Naučte se, jak digitálně přihlásit soubor PDF pomocí Aspose.PDF pro .NET.
type: docs
weight: 40
url: /cs/net/programming-with-security-and-signatures/digitally-sign/
---
V tomto tutoriálu vás provedeme procesem digitálního podepisování v souboru PDF pomocí Aspose.PDF pro .NET. Digitální podpis zaručuje pravost a integritu dokumentu přidáním jedinečného elektronického otisku prstu.

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
using System.Collections.Generic;
```

## Krok 3: Digitální podpis

Prvním krokem je digitální podpis souboru PDF. Poskytnutý kód ukazuje, jak vytvořit digitální podpis pomocí Aspose.PDF pro .NET.

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

Tento kód načte soubor PDF, vytvoří digitální podpis se zadaným vzhledem a poté uloží soubor PDF s přidaným podpisem.

## Krok 4: Ověření podpisu

Po přidání digitálního podpisu můžete zkontrolovat, zda soubor PDF obsahuje platný podpis.

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
                         // Dělej něco
                     }
                 }
             }
         }
     }
}
```

Tento kód ověří první podpis souboru PDF a provede další akce, pokud je podpis certifikovaný a má specifická oprávnění.

### Ukázka zdrojového kódu pro Digitally Sign pomocí Aspose.PDF pro .NET 
```csharp
try
{
	// Cesta k adresáři dokumentů.
	string dataDir = "YOUR DOCUMENTS DIRECTORY";
	string pbxFile = "";
	string inFile = dataDir + @"DigitallySign.pdf";
	string outFile = dataDir + @"DigitallySign_out.pdf";
	using (Document document = new Document(inFile))
	{
		using (PdfFileSignature signature = new PdfFileSignature(document))
		{
			PKCS7 pkcs = new PKCS7(pbxFile, "WebSales"); // Použijte objekty PKCS7/PKCS7Detached
			DocMDPSignature docMdpSignature = new DocMDPSignature(pkcs, DocMDPAccessPermissions.FillingInForms);
			System.Drawing.Rectangle rect = new System.Drawing.Rectangle(100, 100, 200, 100);
			// Nastavení vzhledu podpisu
			signature.SignatureAppearance = dataDir + @"aspose-logo.jpg";
			// Vytvořte libovolný ze tří typů podpisu
			signature.Certify(1, "Signature Reason", "Contact", "Location", true, rect, docMdpSignature);
			// Uložit výstupní soubor PDF
			signature.Save(outFile);
		}
	}
	using (Document document = new Document(outFile))
	{
		using (PdfFileSignature signature = new PdfFileSignature(document))
		{
			IList<string> sigNames = signature.GetSignNames();
			if (sigNames.Count > 0) // Nějaké podpisy?
			{
				if (signature.VerifySigned(sigNames[0] as string)) // Ověřte první
				{
					if (signature.IsCertified) // Certifikovaný?
					{
						if (signature.GetAccessPermissions() == DocMDPAccessPermissions.FillingInForms) // Získejte oprávnění k přístupu
						{
							// Dělej něco
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

## Závěr

gratuluji! Úspěšně jste provedli digitální podpis na souboru PDF pomocí Aspose.PDF pro .NET. Tento výukový program popsal proces krok za krokem, od přidání digitálního podpisu po ověření jeho platnosti. Tuto funkci nyní můžete použít k zabezpečení souborů PDF digitálními podpisy.

### FAQ

#### Otázka: Jaký je účel tohoto tutoriálu?

Odpověď: Tento tutoriál vás provede procesem digitálního podepisování souboru PDF pomocí Aspose.PDF for .NET. Digitální podpisy přidávají elektronický otisk prstu pro zajištění pravosti a integrity dokumentu.

#### Otázka: Jaké předpoklady jsou vyžadovány před zahájením?

Odpověď: Než začnete, ujistěte se, že máte základní znalosti programovacího jazyka C#, máte nainstalované Visual Studio a máte nainstalovanou knihovnu Aspose.PDF pro .NET.

#### Otázka: Jak nastavím vývojové prostředí?

Odpověď: Podle poskytnutých kroků nastavte vývojové prostředí, včetně vytvoření nového projektu C# v sadě Visual Studio a importu požadovaných oborů názvů.

#### Otázka: Jak přidám digitální podpis do souboru PDF?

 Odpověď: Poskytnutý ukázkový kód ukazuje, jak načíst soubor PDF, vytvořit digitální podpis, určit vzhled a uložit podepsaný soubor PDF. Digitální podpis se přidá pomocí`Certify` metoda`PdfFileSignature` objekt.

#### Otázka: Jak ověřím platnost digitálního podpisu?

Odpověď: Po přidání digitálního podpisu můžete použít ukázkový kód k ověření platnosti podpisu. Kontroluje, zda je podpis ověřený a zda má konkrétní přístupová oprávnění.

####  Q: Co dělá`PKCS7` object represent?

 A:`PKCS7` Objekt se používá k poskytování kryptografických funkcí pro digitální podpisy. Používá se k vytvoření digitálního podpisu v poskytnutém vzorovém kódu.

#### Otázka: Mohu upravit vzhled digitálního podpisu?

 Odpověď: Ano, vzhled digitálního podpisu můžete přizpůsobit zadáním cesty k obrázku v`SignatureAppearance` vlastnictvím`PdfFileSignature` objekt.

#### Otázka: Co se stane, když podpis není platný?

Odpověď: Pokud podpis není platný, ověřovací proces selže a odpovídající akce v bloku ověřovacího kódu nebudou provedeny.

#### Otázka: Jak mohu zajistit bezpečnost svých digitálních podpisů?

Odpověď: Digitální podpisy jsou svou konstrukcí bezpečné a používají šifrovací techniky k zajištění pravosti a integrity. Ujistěte se, že máte svůj soukromý klíč v bezpečí a dodržujte osvědčené postupy pro manipulaci s digitálními podpisy.

#### Otázka: Mohu do PDF přidat více digitálních podpisů?

 Odpověď: Ano, do souboru PDF můžete přidat více digitálních podpisů pomocí`PdfFileSignature` objektu`Sign` nebo`Certify` metody. Každý podpis bude mít svůj vlastní vzhled a konfiguraci.