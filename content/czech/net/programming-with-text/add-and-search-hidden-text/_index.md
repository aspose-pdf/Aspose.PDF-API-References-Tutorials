---
title: Přidat a hledat skrytý text v souboru PDF
linktitle: Přidat a hledat skrytý text v souboru PDF
second_title: Aspose.PDF pro .NET API Reference
description: Podrobný průvodce přidáváním a vyhledáváním skrytého textu v souboru PDF pomocí Aspose.PDF pro .NET.
type: docs
weight: 20
url: /cs/net/programming-with-text/add-and-search-hidden-text/
---
V tomto tutoriálu vás provedeme přidáváním a vyhledáváním skrytého textu v souboru PDF pomocí Aspose.PDF for .NET. Chcete-li tuto operaci snadno provést, postupujte podle následujících kroků.

## 1. Předpoklady

Než začnete, ujistěte se, že máte následující:

- Visual Studio nebo jakékoli jiné vývojové prostředí nainstalované a nakonfigurované.
- Základní znalost programovacího jazyka C#.
- Nainstalovaná knihovna Aspose.PDF pro .NET. Můžete si jej stáhnout z oficiálních stránek Aspose.

## 2. Vytvoření dokumentu PDF se skrytým textem

Chcete-li začít, použijte následující kód k vytvoření nového dokumentu PDF obsahujícího skrytý text:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
// Vytvořte dokument
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
Page page = doc.Pages.Add();
TextFragment frag1 = new TextFragment("This is common text.");
TextFragment frag2 = new TextFragment("This is invisible text.");
// Nastavit vlastnost textu - neviditelný
frag2.TextState.Invisible = true;
page.Paragraphs.Add(frag1);
page.Paragraphs.Add(frag2);
doc.Save(dataDir + "39400_out.pdf");
doc.Dispose();
```

Nezapomeňte zadat požadovanou cestu a název souboru pro dokument PDF.

## 3. Vyhledejte text v dokumentu

Dále prohledáme skrytý text v dokumentu PDF. Použijte následující kód:

```csharp
doc = new Aspose.Pdf.Document(dataDir + "39400_out.pdf");
TextFragmentAbsorber absorb = new TextFragmentAbsorber();
absorb.Visit(doc.Pages[1]);
foreach(TextFragment fragment in absorber.TextFragments)
{
//Udělejte něco s úlomky
Console.WriteLine("Text '{0}' at position {1}, invisibility: {2} ",
fragment.Text, fragment.Position.ToString(), fragment.TextState.Invisible);
}
doc.Dispose();
```

To prohledá skrytý text na druhé stránce dokumentu PDF a zobrazí příslušné informace.

### Ukázka zdrojového kódu pro Add And Search Hidden Text pomocí Aspose.PDF for .NET 
```csharp
// Cesta k adresáři dokumentů.
string dataDir = "YOUR DOCUMENT DIRECTORY";
//Vytvořte dokument se skrytým textem
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
Page page = doc.Pages.Add();
TextFragment frag1 = new TextFragment("This is common text.");
TextFragment frag2 = new TextFragment("This is invisible text.");
//Nastavit vlastnost textu - neviditelný
frag2.TextState.Invisible = true;
page.Paragraphs.Add(frag1);
page.Paragraphs.Add(frag2);
doc.Save(dataDir + "39400_out.pdf");
doc.Dispose();
//Vyhledejte text v dokumentu
doc = new Aspose.Pdf.Document(dataDir + "39400_out.pdf");
TextFragmentAbsorber absorber = new TextFragmentAbsorber();
absorber.Visit(doc.Pages[1]);
foreach (TextFragment fragment in absorber.TextFragments)
{
	//Udělejte něco s fragmenty
	Console.WriteLine("Text '{0}' on pos {1} invisibility: {2} ",
	fragment.Text, fragment.Position.ToString(), fragment.TextState.Invisible);
}
doc.Dispose();
```

## Závěr

gratuluji! Úspěšně jste přidali a našli skrytý text v dokumentu PDF pomocí Aspose.PDF pro .NET. Nyní můžete tuto metodu použít na své vlastní projekty a manipulovat a prohledávat skrytý text v souborech PDF.

### FAQ

#### Otázka: Co je Aspose.PDF pro .NET?

Odpověď: Aspose.PDF for .NET je robustní knihovna, která umožňuje vývojářům vytvářet, manipulovat a transformovat dokumenty PDF v rámci aplikací .NET.

#### Otázka: Lze skrytý text použít pro účely vodoznaku?

A: Rozhodně! Skrytý text může sloužit jako účinný prostředek k vodoznaku dokumentů PDF a přidává další vrstvu zabezpečení.

#### Otázka: Je možné odhalit skrytý text v dokumentu PDF?

Odpověď: Ano, proces vyhledávání a odhalování skrytého textu v dokumentu PDF lze provést pomocí technik popsaných v tomto návodu.

#### Otázka: Jaké další funkce nabízí Aspose.PDF pro .NET?

Odpověď: Kromě manipulace se skrytým textem poskytuje Aspose.PDF for .NET širokou škálu funkcí, včetně generování PDF, převodu, šifrování a dalších.