---
title: Získejte všechna písma v souboru PDF
linktitle: Získejte všechna písma v souboru PDF
second_title: Aspose.PDF pro .NET API Reference
description: Naučte se, jak používat Aspose.PDF pro .NET, abyste získali všechna písma použitá v souboru PDF programově, pomocí tohoto podrobného průvodce a příkladu kódu.
type: docs
weight: 160
url: /cs/net/programming-with-document/getallfonts/
---
Aspose.PDF for .NET je výkonná knihovna, která umožňuje vývojářům pracovat se souborem PDF programově. Jednou z funkcí, které poskytuje, je možnost získat všechna písma použitá v souboru PDF. To může být užitečné, pokud potřebujete programově analyzovat písma v souboru PDF nebo s nimi manipulovat.

V tomto tutoriálu probereme, jak používat Aspose.PDF pro .NET, abyste získali všechna písma použitá v dokumentu PDF. Poskytneme vám krok za krokem návod, jak to udělat, spolu s ukázkovým zdrojovým kódem.

## Krok 1: Vytvořte novou aplikaci C# Console
Chcete-li začít, vytvořte novou aplikaci C# Console v sadě Visual Studio. Můžete si to pojmenovat, jak chcete. Jakmile je projekt vytvořen, musíte přidat odkaz na knihovnu Aspose.PDF for .NET.

## Krok 2: Importujte jmenný prostor Aspose.PDF
Chcete-li importovat jmenný prostor Aspose.PDF, přidejte následující řádek kódu na začátek souboru C#:

```csharp
using Aspose.Pdf;
```

## Krok 3: Načtěte dokument PDF
Načtěte dokument PDF, ze kterého chcete získat písma:

```csharp
Document doc = new Document(dataDir + "input.pdf");
```

## Krok 4: Získejte všechna písma
Získejte všechna písma použitá v dokumentu PDF:

```csharp
Aspose.Pdf.Text.Font[] fonts = doc.FontUtilities.GetAllFonts();
```

## Krok 5: Vytiskněte všechna písma
Vytiskněte všechna písma použitá v dokumentu PDF:

```csharp
foreach (Aspose.Pdf.Text.Font font in fonts)
{
    Console.WriteLine(font.FontName);
}
```

### Příklad zdrojového kódu pro Get All Fonts using Aspose.PDF for .NET
```csharp
// Cesta k adresáři dokumentů.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "input.pdf");
Aspose.Pdf.Text.Font[] fonts = doc.FontUtilities.GetAllFonts();
foreach (Aspose.Pdf.Text.Font font in fonts)
{
    Console.WriteLine(font.FontName);
}
```

## Závěr
tomto tutoriálu jsme diskutovali o tom, jak získat všechna písma použitá v dokumentu PDF pomocí Aspose.PDF pro .NET. Získání všech písem použitých v dokumentu PDF může být užitečné, pokud potřebujete programově analyzovat písma v dokumentu PDF nebo s nimi manipulovat. Aspose.PDF for .NET poskytuje jednoduché a snadno použitelné rozhraní API pro práci s dokumenty PDF, včetně získání všech písem použitých v dokumentu PDF.

### FAQ

#### Otázka: Proč bych měl potřebovat všechna písma použitá v dokumentu PDF?

Odpověď: Použití všech písem v dokumentu PDF může být užitečné, pokud potřebujete písma programově analyzovat nebo s nimi manipulovat pro různé účely, jako je výměna písem nebo přizpůsobení písem.

#### Otázka: Jak mohu získat všechna písma použitá v dokumentu PDF pomocí Aspose.PDF pro .NET?

 Odpověď: Všechna písma použitá v dokumentu PDF můžete získat pomocí Aspose.PDF pro .NET voláním`GetAllFonts` metoda`FontUtilities` třída. Tato metoda vrací pole`Aspose.Pdf.Text.Font` objekty, které představují písma použitá v dokumentu PDF.

#### Otázka: Mohu filtrovat písma na základě určitých kritérií?

Odpověď: Ano, můžete filtrovat písma na základě určitých kritérií pomocí Aspose.PDF pro .NET. Po získání všech písem můžete programově analyzovat písma a podle potřeby použít logiku filtrování.

#### Otázka: Je Aspose.PDF for .NET kompatibilní s různými formáty písem?

Odpověď: Ano, Aspose.PDF for .NET je kompatibilní s různými formáty písem, včetně písem TrueType, OpenType a Type 1. Dokáže pracovat s různými formáty písem a manipulovat s nimi při manipulaci s PDF dokumenty.