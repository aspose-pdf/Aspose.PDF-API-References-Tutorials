---
title: Podepište Chytrou Kartou Pomocí Pole Podpisu
linktitle: Podepište Chytrou Kartou Pomocí Pole Podpisu
second_title: Aspose.PDF pro .NET API Reference
description: Podepište své soubory PDF bezpečně pomocí čipové karty pomocí Aspose.PDF for .NET.
type: docs
weight: 120
url: /cs/net/programming-with-security-and-signatures/sign-with-smart-card-using-signature-field/
---
Digitální podepisování pomocí čipové karty je bezpečný způsob podepisování souborů PDF. S Aspose.PDF pro .NET můžete snadno podepsat soubor PDF pomocí pole podpisu a čipové karty podle následujícího zdrojového kódu:

## Krok 1: Importujte požadované knihovny

Než začnete, musíte importovat potřebné knihovny pro váš projekt C#. Zde jsou nezbytné importní směrnice:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Forms;
using System.Security.Cryptography.X509Certificates;
```

## Krok 2: Nastavte cestu ke složce dokumentů

 V tomto kroku musíte zadat cestu ke složce obsahující soubor PDF, který chcete podepsat. Nahradit`"YOUR DOCUMENTS DIRECTORY"` následujícím kódu se skutečnou cestou ke složce dokumentů:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Krok 3: Zkopírujte a otevřete dokument PDF

Nyní zkopírujeme a otevřeme dokument PDF k podpisu pomocí následujícího kódu:

```csharp
File.Copy(dataDir + "blank.pdf", dataDir + "externalSignature1.pdf", true);

using (FileStream fs = new FileStream(dataDir + "externalSignature1.pdf", FileMode.Open, FileAccess.ReadWrite))
{
     using (Document doc = new Document(fs))
     {
         // Vytvořte pole pro podpis
         SignatureField field1 = new SignatureField(doc.Pages[1], new Rectangle(100, 400, 10, 10));

         // Vyberte certifikát v obchodě
         X509Store store = new X509Store(StoreLocation.CurrentUser);
         store.Open(OpenFlags.ReadOnly);
         X509Certificate2Collection sel = X509Certificate2UI.SelectFromCollection(store.Certificates, null, null, X509SelectionFlag.SingleSelection);
        
         // Vytvořte externí podpis s potřebnými informacemi
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

## Krok 4: Ověřte podpis

 Nakonec ověříme podpis podepsaného souboru PDF pomocí`PdfFileSignature` třída. Získáme jména podpisů a zkontrolujeme je jeden po druhém. Pokud se podpis nepodaří ověřit, je vyvolána výjimka. Zde je odpovídající kód:

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

### Ukázkový zdrojový kód pro Podepsat pomocí čipové karty pomocí pole podpisu pomocí Aspose.PDF pro .NET 
```csharp
// Cesta k adresáři dokumentů.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
File.Copy(dataDir + "blank.pdf", dataDir + "externalSignature1.pdf", true);
using (FileStream fs = new FileStream(dataDir + "externalSignature1.pdf", FileMode.Open, FileAccess.ReadWrite))
{
	using (Document doc = new Document(fs))
	{
		SignatureField field1 = new SignatureField(doc.Pages[1], new Rectangle(100, 400, 10, 10));
		// Podepište se výběrem certifikátu v úložišti certifikátů systému Windows
		System.Security.Cryptography.X509Certificates.X509Store store = new System.Security.Cryptography.X509Certificates.X509Store(System.Security.Cryptography.X509Certificates.StoreLocation.CurrentUser);
		store.Open(System.Security.Cryptography.X509Certificates.OpenFlags.ReadOnly);
		// Manuálně vyberte certifikát v obchodě
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

## Závěr

gratuluji! Nyní máte krok za krokem průvodce podepsáním souboru PDF pomocí čipové karty pomocí pole pro podpis pomocí Aspose.PDF pro .NET. Tento kód můžete použít k přidání bezpečných digitálních podpisů do dokumentů PDF.

Nezapomeňte se podívat na oficiální dokumentaci Aspose.PDF, kde najdete další informace o pokročilém digitálním podpisu a funkcích správy certifikátů.

### FAQ

#### Otázka: Jaká je výhoda použití pole pro podpis pro digitální podepisování pomocí čipové karty?

Odpověď: Použití pole podpisu pro digitální podepisování pomocí čipové karty poskytuje v PDF určenou oblast, kde je podpis aplikován. To zvyšuje srozumitelnost dokumentu a zajišťuje pravost podpisu.

#### Otázka: Jak knihovna Aspose.PDF for .NET usnadňuje digitální podepisování založené na čipových kartách s polem pro podpis?

Odpověď: Aspose.PDF for .NET zjednodušuje proces vytváření pole pro podpis, výběr certifikátu čipové karty a použití digitálního podpisu na určitou oblast v dokumentu PDF.

#### Otázka: Proč je výběr konkrétního certifikátu důležitý pro podepisování pomocí čipových karet?

Odpověď: Výběr konkrétního certifikátu vám umožní jednoznačně identifikovat podepisujícího a zajistit integritu podpisu. To pomáhá vytvořit důvěru a shodu se standardy digitálního podepisování.

#### Otázka: Jak poskytnutý zdrojový kód zpracovává proces podepisování založený na čipové kartě s polem pro podpis?

Odpověď: Zdrojový kód ukazuje, jak vytvořit pole pro podpis, vybrat certifikát čipové karty a použít digitální podpis se specifickými informacemi pro podpis. Ukazuje také, jak ověřit platnost podpisu.

#### Otázka: Mohu upravit vzhled pole podpisu?

Odpověď: Ano, vzhled pole podpisu, jako je jeho velikost, poloha a vizuální reprezentace, můžete přizpůsobit tak, aby odpovídal rozvržení vašeho dokumentu.

#### Otázka: Co se stane, když podpis během kroku ověření selže?

Odpověď: Pokud se ověření podpisu nezdaří, je vyvolána výjimka označující, že podpis není platný. To zajišťuje, že jsou přijímány pouze platné a důvěryhodné podpisy.

#### Otázka: Mohu použít více podpisových polí a podpisů založených na čipových kartách na jeden dokument PDF?

Odpověď: Rozhodně můžete použít více podpisových polí a podpisů založených na čipových kartách na různé oblasti stejného dokumentu PDF, což poskytuje více vrstev zabezpečení.

#### Otázka: Jak použití pole pro podpis zlepšuje celkový proces podepisování dokumentů?

Odpověď: Použití pole pro podpis zjednodušuje proces podepisování dokumentů, protože vede podepisujícího k umístění podpisu do určené oblasti, díky čemuž je proces podepisování organizovanější a uživatelsky přívětivější.

#### Otázka: Existují nějaká omezení pro používání podpisových polí při podepisování pomocí čipových karet?

Odpověď: Neexistují žádná přirozená omezení pro používání podpisových polí s podepisováním pomocí čipových karet. Je však důležité zajistit, aby zvolené umístění pole podpisu nezakrývalo důležitý obsah dokumentu.

#### Otázka: Kde najdu další pomoc nebo podporu pro implementaci podepisování pomocí čipových karet s polem pro podpis?

Odpověď: Další pokyny a podporu naleznete v oficiální dokumentaci Aspose.PDF a komunitních fórech, které nabízejí cenné poznatky a řešení pro implementaci bezpečných digitálních podpisů.