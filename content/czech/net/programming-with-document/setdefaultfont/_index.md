---
title: Nastavit výchozí písmo v souboru PDF
linktitle: Nastavit výchozí písmo v souboru PDF
second_title: Aspose.PDF pro .NET API Reference
description: Pomocí tohoto podrobného průvodce se dozvíte, jak nastavit výchozí písmo v souborech PDF pomocí Aspose.PDF for .NET. Ideální pro vývojáře, kteří chtějí vylepšit dokumenty PDF.
type: docs
weight: 280
url: /cs/net/programming-with-document/setdefaultfont/
---
## Zavedení

Stalo se vám někdy, že jste otevřeli dokument PDF, abyste zjistili, že písma chybí nebo se nezobrazují správně? Může to být frustrující, že? No, nebojte se! V tomto tutoriálu se ponoříme do toho, jak nastavit výchozí písmo v souboru PDF pomocí Aspose.PDF pro .NET. Tato výkonná knihovna vám umožňuje snadno manipulovat s dokumenty PDF a nastavení výchozího písma je pouze jednou z mnoha funkcí, které nabízí. Takže popadněte svůj kódovací klobouk a můžeme začít!

## Předpoklady

Než se pustíme do kódu, je třeba mít připraveno několik věcí:

1. Visual Studio: Ujistěte se, že máte na svém počítači nainstalované Visual Studio. Je to nejlepší IDE pro vývoj .NET.
2.  Aspose.PDF for .NET: Budete si muset stáhnout a nainstalovat knihovnu Aspose.PDF. Můžete to najít[zde](https://releases.aspose.com/pdf/net/).
3. Základní znalost C#: Trocha znalosti programování v C# vám pomůže porozumět příkladům, které probereme.

## Importujte balíčky

Chcete-li začít, budete muset importovat potřebné balíčky do svého projektu C#. Můžete to udělat takto:

1. Otevřete projekt sady Visual Studio.
2. Klikněte pravým tlačítkem na svůj projekt v Průzkumníku řešení a vyberte „Spravovat balíčky NuGet“.
3.  Hledat`Aspose.PDF` a nainstalujte nejnovější verzi.

Jakmile budete mít balíček nainstalován, jste připraveni začít kódovat!

## Krok 1: Nastavte svůj projekt

### Vytvořit nový projekt

Nejprve vytvořte nový projekt C# ve Visual Studiu:

- Otevřete Visual Studio a vyberte „Vytvořit nový projekt“.
- Vyberte „Console App (.NET Core)“ a klikněte na „Další“.
-  Pojmenujte svůj projekt (např.`AsposePdfExample`) a klikněte na „Vytvořit“.

### Přidat pomocí direktiv

 Nyní přidejte potřebné direktivy pomocí v horní části vašeho`Program.cs` soubor:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
using System.IO;
```

Tyto direktivy vám umožní přístup k třídám a metodám Aspose.PDF.

## Krok 2: Načtěte dokument PDF

### Zadejte cestu dokumentu

Dále budete muset zadat cestu k dokumentu PDF, se kterým chcete pracovat. Jak na to:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY"; // Nahraďte svým skutečným adresářem
string documentName = Path.Combine(dataDir, "input.pdf");
```

 Nezapomeňte vyměnit`"YOUR DOCUMENT DIRECTORY"` se skutečnou cestou, kde se nachází váš soubor PDF.

### Vložte dokument

Nyní načteme existující dokument PDF:

```csharp
using (FileStream fs = new FileStream(documentName, FileMode.Open))
{
    Document document = new Document(fs);
}
```

 Tento fragment kódu otevře soubor PDF a vytvoří a`Document` předmět, se kterým můžete manipulovat.

## Krok 3: Nastavte výchozí písmo

### Vytvořte možnosti PdfSaveOptions

 Nyní přichází ta vzrušující část! Budete muset vytvořit instanci`PdfSaveOptions` pro určení výchozího písma:

```csharp
PdfSaveOptions pdfSaveOptions = new PdfSaveOptions();
```

### Zadejte výchozí název písma

Dále nastavíte výchozí název písma. Pro tento příklad použijeme "Arial":

```csharp
pdfSaveOptions.DefaultFontName = "Arial";
```

Tento řádek říká Aspose.PDF, aby použil Arial jako výchozí písmo pro jakýkoli text, který nemá zadané písmo.

## Krok 4: Uložte dokument

Konečně je čas uložit upravený dokument PDF s novým výchozím písmem:

```csharp
document.Save(Path.Combine(dataDir, "output_out.pdf"), pdfSaveOptions);
```

 Tento řádek uloží dokument jako`output_out.pdf` v zadaném adresáři.

## Závěr

tady to máte! Úspěšně jste nastavili výchozí písmo v souboru PDF pomocí Aspose.PDF pro .NET. Tato jednoduchá, ale výkonná funkce může pomoci zajistit, aby vaše dokumenty vypadaly přesně tak, jak chcete, i když chybí písma. Takže až se příště setkáte s PDF s problémy s písmem, budete přesně vědět, co dělat!

## FAQ

### Co je Aspose.PDF pro .NET?
Aspose.PDF for .NET je knihovna, která umožňuje vývojářům vytvářet, manipulovat a převádět dokumenty PDF programově.

### Mohu použít jiná písma kromě Arialu?
Ano, můžete zadat libovolné písmo, které je nainstalováno ve vašem systému jako výchozí písmo.

### Je Aspose.PDF zdarma k použití?
Aspose.PDF nabízí bezplatnou zkušební verzi, ale pro plnou funkčnost si budete muset zakoupit licenci.

### Kde najdu další dokumentaci?
 Můžete najít komplexní dokumentaci[zde](https://reference.aspose.com/pdf/net/).

### Jak získám podporu pro Aspose.PDF?
 Podporu můžete získat prostřednictvím fóra Aspose[zde](https://forum.aspose.com/c/pdf/10).