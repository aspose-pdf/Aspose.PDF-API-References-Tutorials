---
title: Nahradit chybějící písma
linktitle: Nahradit chybějící písma
second_title: Aspose.PDF pro .NET API Reference
description: Podrobný průvodce nahrazením chybějících písem v souboru PDF pomocí Aspose.PDF pro .NET.
type: docs
weight: 260
url: /cs/net/document-conversion/replace-missing-fonts/
---
V tomto tutoriálu vás provedeme procesem nahrazení chybějících písem v souboru PDF pomocí Aspose.PDF for .NET. Když otevřete soubor PDF na počítači, kde chybí konkrétní písmo, mohou nastat problémy se zobrazením písma. V takových případech je možné nahradit chybějící písmo jiným písmem dostupným na stroji. Podle níže uvedených kroků budete moci nahradit chybějící písma v souboru PDF.

## Předpoklady
Než začnete, ujistěte se, že splňujete následující předpoklady:

- Základní znalost programovacího jazyka C#.
- Knihovna Aspose.PDF pro .NET nainstalovaná ve vašem systému.
- Vývojové prostředí, jako je Visual Studio.

## Krok 1: Nalezení chybějícího písma
Prvním krokem je najít chybějící písmo v souboru PDF. Použijte následující kód:

```csharp
// Cesta k adresáři dokumentů.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

Aspose.Pdf.Text.Font originalFont = null;
try
{
     // Najděte původní písmo
     originalFont = FontRepository.FindFont("AgencyFB");
}
catch(Exception)
{
     // Na cílovém počítači chybí písmo
     // Přidejte jednoduchou náhradu písma
     FontRepository.Substitutions.Add(new SimpleFontSubstitution("AgencyFB", "Arial"));
}
```

 Nezapomeňte vyměnit`"YOUR DOCUMENTS DIRECTORY"` se skutečným adresářem, kde se nachází váš soubor PDF.

## Krok 2: Nahraďte chybějící písmo
Dále chybějící písmo nahradíme jiným dostupným písmem. Použijte následující kód:

```csharp
var fileNew = new FileInfo(dataDir + "newfile_out.pdf");
var pdf = new Document(dataDir + "input.pdf");

// Převeďte soubor PDF do formátu PDF/A s odstraněním chyb
pdf.Convert(dataDir + "log.xml", PdfFormat.PDF_A_1B, ConvertErrorAction.Delete);

// Uložte výsledný soubor PDF
pdf.Save(fileNew.FullName);
```

 Nezapomeňte vyměnit`"input.pdf"` se skutečnou cestou k původnímu souboru PDF a`"newfile_out.pdf"` s požadovaným názvem výsledného souboru PDF.

## Krok 3: Uložení výsledného souboru PDF
Nakonec výsledný soubor PDF s nahrazeným písmem uložíme. Použijte následující kód:

```csharp
// Uložte výsledný soubor PDF
pdf.Save(fileNew.FullName);
```

Zajistí, že jste nastavili správnou cílovou cestu pro výsledný soubor PDF.

### Příklad zdrojového kódu pro Nahradit chybějící písma pomocí Aspose.PDF pro .NET

```csharp
// Cesta k adresáři dokumentů.
string dataDir = "YOUR DOCUMENT DIRECTORY";

Aspose.Pdf.Text.Font originalFont = null;
try
{
	originalFont = FontRepository.FindFont("AgencyFB");
}
catch (Exception)
{
	// Na cílovém počítači chybí písmo
	FontRepository.Substitutions.Add(new SimpleFontSubstitution("AgencyFB", "Arial"));
}
var fileNew = new FileInfo(dataDir + "newfile_out.pdf");
var pdf = new Document(dataDir + "input.pdf");
pdf.Convert( dataDir +  "log.xml", PdfFormat.PDF_A_1B, ConvertErrorAction.Delete);
pdf.Save(fileNew.FullName);
```

## Závěr
tomto tutoriálu jsme probrali krok za krokem proces nahrazování chybějících písem v souboru PDF pomocí Aspose.PDF pro .NET. Podle výše uvedených pokynů budete moci úspěšně nahradit chybějící písma v souboru PDF.

### FAQ

#### Otázka: Co je Aspose.PDF pro .NET?

A: Aspose.PDF for .NET je výkonná knihovna, která umožňuje vývojářům pracovat s dokumenty PDF v aplikacích C#. Nabízí různé funkce, včetně možnosti nahradit chybějící písma v souborech PDF.

#### Otázka: Proč bych v souboru PDF narazil na chybějící písma?

Odpověď: Chybějící písma v souboru PDF se mohou objevit, když je soubor otevřen na počítači, který nemá nainstalovaná potřebná písma. To může vést k nahrazení písem, což ovlivní vizuální vzhled dokumentu.

#### Otázka: Jak mohu najít a nahradit chybějící písma v souboru PDF pomocí Aspose.PDF pro .NET?

 Odpověď: Chcete-li najít a nahradit chybějící písma, můžete použít`FontRepository.FindFont` způsob kontroly přítomnosti požadovaného písma. Pokud písmo chybí, můžete přidat náhradu písma pomocí`FontRepository.Substitutions` vlastnictví.

#### Otázka: Mohu přizpůsobit proces nahrazování písem?

Odpověď: Ano, proces nahrazování písem můžete přizpůsobit zadáním jiného písma pro nahrazování. V poskytnutém kódu jsme použili Arial jako náhradu za chybějící font „AgencyFB“, ale můžete si vybrat jiný font podle svých preferencí.

#### Otázka: Jak mohu zajistit přesnost vykreslování písem po nahrazení?

Odpověď: Aspose.PDF for .NET poskytuje robustní možnosti manipulace s písmy a zajišťuje přesné vykreslování písem po nahrazení. Můžete si prohlédnout výsledný soubor PDF a ověřit nahrazení písma.