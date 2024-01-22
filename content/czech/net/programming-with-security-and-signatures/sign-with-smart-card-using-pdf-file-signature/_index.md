---
title: Podepište se pomocí čipové karty pomocí podpisu souboru PDF
linktitle: Podepište se pomocí čipové karty pomocí podpisu souboru PDF
second_title: Aspose.PDF pro .NET API Reference
description: Podepište své soubory PDF bezpečně pomocí čipové karty pomocí Aspose.PDF for .NET.
type: docs
weight: 110
url: /cs/net/programming-with-security-and-signatures/sign-with-smart-card-using-pdf-file-signature/
---
Digitální podepisování pomocí čipové karty je bezpečný způsob podepisování souborů PDF. S Aspose.PDF for .NET můžete snadno podepsat soubor PDF pomocí čipové karty podle následujícího zdrojového kódu:

## Krok 1: Importujte požadované knihovny

Než začnete, musíte importovat potřebné knihovny pro váš projekt C#. Zde jsou nezbytné importní směrnice:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Facades;
using Aspose.Pdf.Forms;
using System.Security.Cryptography.X509Certificates;
```

## Krok 2: Nastavte cestu ke složce dokumentů

 V tomto kroku musíte zadat cestu ke složce obsahující soubor PDF, který chcete podepsat. Nahradit`"YOUR DOCUMENTS DIRECTORY"` následujícím kódu se skutečnou cestou ke složce dokumentů:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Krok 3: Načtěte dokument PDF

Nyní načteme dokument PDF k podpisu pomocí následujícího kódu:

```csharp
Document doc = new Document(dataDir + "blank.pdf");
```

## Krok 4: Proveďte podpis pomocí čipové karty

 V tomto kroku provedeme podpis pomocí čipové karty pomocí`PdfFileSignature` třídy z`Facades`knihovna. Vybereme certifikát čipové karty z úložiště certifikátů Windows a zadáme potřebné informace k podpisu. Zde je odpovídající kód:

```csharp
using (PdfFileSignature pdfSign = new PdfFileSignature())
{
     pdfSign.BindPdf(doc);

     // Vyberte certifikát v obchodě
     X509Store store = new X509Store(StoreLocation.CurrentUser);
     store.Open(OpenFlags.ReadOnly);
     X509Certificate2Collection sel = X509Certificate2UI.SelectFromCollection(store.Certificates, null, null, X509SelectionFlag.SingleSelection);
     ExternalSignature externalSignature = new ExternalSignature(sel[0]);

     pdfSign.SignatureAppearance = dataDir + "demo.png";
     pdfSign.Sign(1, "Reason", "Contact", "Location", true, new System.Drawing.Rectangle(100, 100, 200, 200), externalSignature);
     pdfSign.Save(dataDir + "externalSignature2.pdf");
}
```

## Krok 5: Ověřte podpis

 Nakonec ověříme podpis podepsaného souboru PDF pomocí`PdfFileSignature` třída. Získáme jména podpisů a zkontrolujeme je jeden po druhém. Pokud se podpis nepodaří ověřit, je vyvolána výjimka. Zde je odpovídající kód:

```csharp
using (PdfFileSignature pdfSign = new PdfFileSignature(new Document(dataDir + "externalSignature2.pdf")))
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

### Ukázka zdrojového kódu pro podepisování pomocí čipové karty pomocí podpisu souboru PDF pomocí Aspose.PDF pro .NET 
```csharp
// Cesta k adresáři dokumentů.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "blank.pdf");
using (Facades.PdfFileSignature pdfSign = new Facades.PdfFileSignature())
{
	pdfSign.BindPdf(doc);
	// Podepište se výběrem certifikátu v úložišti certifikátů systému Windows
	System.Security.Cryptography.X509Certificates.X509Store store = new System.Security.Cryptography.X509Certificates.X509Store(System.Security.Cryptography.X509Certificates.StoreLocation.CurrentUser);
	store.Open(System.Security.Cryptography.X509Certificates.OpenFlags.ReadOnly);
	// Manuálně vyberte certifikát v obchodě
	System.Security.Cryptography.X509Certificates.X509Certificate2Collection sel = System.Security.Cryptography.X509Certificates.X509Certificate2UI.SelectFromCollection(store.Certificates, null, null, System.Security.Cryptography.X509Certificates.X509SelectionFlag.SingleSelection);
	Aspose.Pdf.Forms.ExternalSignature externalSignature = new Aspose.Pdf.Forms.ExternalSignature(sel[0]);
	pdfSign.SignatureAppearance = dataDir + "demo.png";
	pdfSign.Sign(1, "Reason", "Contact", "Location", true, new System.Drawing.Rectangle(100, 100, 200, 200), externalSignature);
	pdfSign.Save(dataDir + "externalSignature2.pdf");
}
using (Facades.PdfFileSignature pdfSign = new Facades.PdfFileSignature(new Document(dataDir + "externalSignature2.pdf")))
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

## Závěr

gratuluji! Nyní máte k dispozici podrobného průvodce podepsáním souboru PDF pomocí čipové karty pomocí Aspose.PDF pro .NET. Tento kód můžete použít k přidání bezpečných digitálních podpisů do dokumentů PDF.

Nezapomeňte se podívat na oficiální dokumentaci Aspose.PDF, kde najdete další informace o pokročilém digitálním podpisu a funkcích správy certifikátů.

### FAQ

#### Otázka: Proč bych měl uvažovat o podepisování souborů PDF pomocí čipové karty?

Odpověď: Podepisování souborů PDF pomocí čipové karty zvyšuje zabezpečení zajištěním pravosti a integrity dokumentu. Podpisy založené na čipových kartách poskytují vyšší úroveň důvěry a souladu.

#### Otázka: Jak funguje digitální podepisování založené na čipových kartách?

Odpověď: Digitální podepisování založené na čipové kartě zahrnuje použití kryptografického klíče uloženého na čipové kartě k vytvoření jedinečného digitálního podpisu. Tento podpis je připojen k souboru PDF a umožňuje příjemcům ověřit původ a integritu dokumentu.

#### Otázka: Jaká je role Aspose.PDF pro .NET v podepisování založeném na čipových kartách?

Odpověď: Aspose.PDF for .NET poskytuje komplexní sadu nástrojů a knihoven pro usnadnění digitálního podepisování souborů PDF pomocí čipových karet. Zjednodušuje proces a zajišťuje bezpečné podepisování dokumentů.

#### Otázka: Mohu si pro podpis vybrat konkrétní certifikát čipové karty?

Odpověď: Ano, k podpisu můžete vybrat konkrétní certifikát čipové karty z úložiště certifikátů Windows. Aspose.PDF for .NET vám umožňuje bezproblémově integrovat výběr certifikátů do vaší aplikace.

#### Otázka: Jak poskytnutý zdrojový kód zpracovává podepisování založené na čipové kartě?

Odpověď: Zdrojový kód ukazuje, jak svázat dokument PDF, vybrat certifikát čipové karty, zadat informace pro podpis a vytvořit digitální podpis. Ukazuje také, jak ověřit platnost podpisu.

#### Otázka: Mohu použít více podpisů pomocí čipových karet v jednom souboru PDF?

Odpověď: Na jeden soubor PDF můžete samozřejmě použít více podpisů založených na čipových kartách. Každý podpis je jedinečný a přispívá k celkové bezpečnosti dokumentu.

#### Otázka: Co když podpis během kroku ověření selže?

Odpověď: Pokud se ověření podpisu nezdaří, je vyvolána výjimka označující, že podpis není platný. To zajišťuje, že jsou přijímány pouze platné a důvěryhodné podpisy.

#### Otázka: Je podepisování pomocí čipových karet kompatibilní se všemi typy dokumentů PDF?

Odpověď: Ano, podepisování pomocí čipových karet je kompatibilní se všemi typy dokumentů PDF. Digitální podpisy můžete použít na různé typy souborů PDF, včetně formulářů, sestav a dalších.

#### Otázka: Jak se mohu dozvědět více o pokročilém digitálním podpisu a správě certifikátů?

Odpověď: Prozkoumejte oficiální dokumentaci Aspose.PDF, kde najdete podrobné informace o pokročilých funkcích digitálního podpisu, správě certifikátů a osvědčených postupech pro zajištění bezpečnosti dokumentů.

#### Otázka: Kde najdu další pomoc nebo podporu pro implementaci podepisování pomocí čipových karet?

Odpověď: Další pokyny a podporu získáte na fórech komunity Aspose.PDF nebo v dokumentaci, kde najdete komplexní informace o podepisování pomocí čipových karet.