---
title: Rozdělit na stránky
linktitle: Rozdělit na stránky
second_title: Aspose.PDF pro .NET API Reference
description: Podrobný průvodce rozdělením dokumentu PDF na jednotlivé stránky pomocí Aspose.PDF pro .NET.
type: docs
weight: 140
url: /cs/net/programming-with-pdf-pages/split-to-pages/
---
V tomto tutoriálu vás provedeme krok za krokem procesem rozdělení dokumentu PDF na jednotlivé stránky pomocí Aspose.PDF for .NET. Vysvětlíme vám přibalený zdrojový kód C# a poskytneme vám komplexního průvodce, který vám pomůže pochopit a implementovat tuto funkci ve vašich vlastních projektech. Na konci tohoto tutoriálu budete vědět, jak rozdělit dokument PDF do více souborů PDF, z nichž každý obsahuje jednu stránku.

## Předpoklady
Než začnete, ujistěte se, že máte následující:

- Základní znalost programovacího jazyka C#
- Aspose.PDF for .NET nainstalovaný ve vašem vývojovém prostředí

## Krok 1: Definujte adresář dokumentů
Nejprve musíte nastavit cestu k adresáři dokumentů. Zde se nachází dokument PDF, který chcete rozdělit. Nahraďte "VAŠE ADRESÁŘ DOKUMENTŮ" příslušnou cestou.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Krok 2: Otevřete dokument PDF
 Poté můžete otevřít dokument PDF a rozdělit jej pomocí`Document` třída Aspose.PDF. Ujistěte se, že jste zadali správnou cestu dokumentu.

```csharp
Document pdfDocument = new Document(dataDir + "SplitToPages.pdf");
```

## Krok 3: Projděte stránky a rozdělte je
Nyní můžete procházet všemi stránkami dokumentu PDF pomocí smyčky. Pro každou stránku vytvořte nový dokument a přidejte tuto stránku do tohoto nového dokumentu. Poté uložte nový dokument s jedinečným názvem souboru pro každou stránku.

```csharp
int pageCount = 1;
foreach(Page pdfPage in pdfDocument.Pages)
{
Document newDocument = newDocument();
newDocument.Pages.Add(pdfPage);
newDocument.Save(dataDir + "page_" + pageCount + "_out" + ".pdf");
pageCount++;
}
```

### Ukázkový zdrojový kód pro Split To Pages pomocí Aspose.PDF pro .NET 

```csharp

// Cesta k adresáři dokumentů.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Otevřete dokument
Document pdfDocument = new Document(dataDir + "SplitToPages.pdf");
int pageCount = 1;
// Projděte všechny stránky
foreach (Page pdfPage in pdfDocument.Pages)
{
	Document newDocument = new Document();
	newDocument.Pages.Add(pdfPage);
	newDocument.Save(dataDir + "page_" + pageCount + "_out" + ".pdf");
	pageCount++;
}

```

## Závěr
V tomto tutoriálu jsme se naučili, jak rozdělit dokument PDF na jednotlivé stránky pomocí Aspose.PDF pro .NET. Podle tohoto podrobného průvodce můžete snadno rozdělit dokument PDF do více souborů PDF, z nichž každý obsahuje jednu stránku. Aspose.PDF nabízí výkonné a flexibilní API pro práci s dokumenty PDF ve vašich projektech. Nyní můžete tuto funkci použít k provádění operací rozdělení dokumentu PDF podle vašich specifických potřeb.

### FAQ

#### Otázka: Jak mohu rozdělit dokument PDF na jednotlivé stránky pomocí Aspose.PDF for .NET?

Odpověď: Chcete-li rozdělit dokument PDF na jednotlivé stránky pomocí Aspose.PDF for .NET, můžete postupovat takto:

1. Nastavte adresář dokumentu zadáním cesty, kde se nachází váš původní soubor PDF a kam chcete uložit rozdělené soubory PDF. Nahraďte "VAŠE ADRESÁŘ DOKUMENTŮ" příslušnou cestou.
2.  Otevřete dokument PDF, který chcete rozdělit pomocí`Document` třída Aspose.PDF. Ujistěte se, že jste zadali správnou cestu k původnímu dokumentu PDF.
3. Procházejte všechny stránky dokumentu PDF pomocí smyčky.
4.  Pro každou stránku vytvořte nový dokument pomocí`Document` třídy a přidejte tuto stránku do tohoto nového dokumentu pomocí`Add()` metoda`Pages` vlastnictví.
5.  Uložte nový dokument s jedinečným názvem souboru pro každou stránku pomocí`Save()` metoda`Document` třída.

#### Otázka: Ovlivní rozdělení dokumentu PDF původní soubor PDF?

Odpověď: Ne, rozdělení dokumentu PDF neovlivní původní soubor PDF. Každá stránka se zkopíruje do nového dokumentu a nové dokumenty se uloží samostatně, přičemž původní soubor PDF zůstane nedotčen.

#### Otázka: Mohu určit jiný formát souboru pro rozdělené stránky, jako jsou obrázky nebo textové soubory?

Odpověď: Poskytnutý zdrojový kód C# ukazuje, jak rozdělit dokument PDF do samostatných souborů PDF pro každou stránku. Můžete však upravit kód tak, aby byly rozdělené stránky uloženy v jiných formátech, jako jsou obrázky nebo textové soubory, v závislosti na vašich konkrétních požadavcích.

#### Otázka: Existuje nějaký limit na počet stránek, které lze rozdělit pomocí Aspose.PDF pro .NET?

Odpověď: Aspose.PDF pro .NET nestanoví žádný konkrétní limit na počet stránek, které lze rozdělit. Množství paměti a prostředků dostupných ve vašem systému však může ovlivnit výkon při práci s velkým počtem stránek.

#### Otázka: Mohu rozdělit určitý rozsah stránek z dokumentu PDF?

Odpověď: Ano, poskytnutý zdrojový kód můžete upravit tak, aby byl z dokumentu PDF rozdělen určitý rozsah stránek. Namísto procházení všemi stránkami můžete implementovat logiku pro výběr konkrétního rozsahu stránek a vytvářet nové dokumenty pouze pro tyto stránky.