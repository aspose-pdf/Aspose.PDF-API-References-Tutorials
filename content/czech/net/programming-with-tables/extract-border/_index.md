---
title: Extrahovat ohraničení v souboru PDF
linktitle: Extrahovat ohraničení v souboru PDF
second_title: Aspose.PDF pro .NET API Reference
description: Naučte se extrahovat okraje ze souboru PDF a uložit je jako obrázek pomocí Aspose.PDF for .NET. Podrobný průvodce s ukázkami kódu a tipy pro úspěch.
type: docs
weight: 80
url: /cs/net/programming-with-tables/extract-border/
---
## Zavedení

Při práci s PDF se může extrakce konkrétních prvků, jako jsou okraje nebo grafické cesty, zdát skličujícím úkolem. Ale s Aspose.PDF pro .NET můžete snadno extrahovat okraje nebo tvary ze souboru PDF a uložit je jako obrázek. V tomto tutoriálu se ponoříme do procesu extrahování ohraničení z PDF a jeho uložení jako obrázku PNG. Připravte se převzít kontrolu nad grafickým obsahem vašeho PDF!

## Předpoklady

Než se ponoříme do kódu, ujistěte se, že máte vše nastaveno:

1.  Aspose.PDF pro .NET: Pokud jste ještě nenainstalovali knihovnu Aspose.PDF, můžete[stáhněte si jej zde](https://releases.aspose.com/pdf/net/). Budete také muset použít licenci, buď prostřednictvím bezplatné zkušební verze, nebo zakoupené licence.
2. Nastavení IDE: Nastavte projekt C# v sadě Visual Studio nebo v jakémkoli jiném .NET IDE. Ujistěte se, že jste přidali potřebné odkazy do knihovny Aspose.PDF.
3. Vstupní soubor PDF: Připravte si soubor PDF, ze kterého vyjmete okraje. Tento tutoriál bude odkazovat na soubor s názvem`input.pdf`.

## Import požadovaných balíčků

Začněme importem požadovaných jmenných prostorů. Tyto balíčky poskytují nástroje potřebné pro manipulaci s obsahem PDF.

```csharp
using System.IO;
using System;
using System.Drawing.Drawing2D;
using System.Drawing.Imaging;
using System.Collections;
using Aspose.Pdf;
using Aspose.Pdf.Annotations;
```

Nyní, když jsme probrali základy, přejděme k podrobnému průvodci, kde rozebereme jednotlivé části kódu a podrobně je vysvětlíme.


## Krok 1: Načtení dokumentu PDF

Prvním krokem je načtení dokumentu PDF, který obsahuje okraj, který chcete extrahovat. Představte si to jako otevření knihy, než začnete číst – potřebujete přístup k obsahu!

 Začneme zadáním adresáře, kde je uložen váš soubor PDF, a načtením dokumentu pomocí`Aspose.Pdf.Document` třída.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "input.pdf");
```

 Tento kód načte`input.pdf` soubor z vašeho zadaného adresáře. Ujistěte se, že cesta k souboru je správná, jinak se může zobrazit chyba soubor nenalezen.

## Krok 2: Nastavení grafiky a bitmapy

Než začneme vytahovat, musíme si vytvořit plátno, na které budeme kreslit. Ve světě .NET to znamená nastavení objektů Bitmap a Graphics. Bitmapa představuje obrázek a objekt Graphics nám umožní kreslit tvary, jako jsou okraje, extrahované z PDF.

```csharp
System.Drawing.Bitmap bitmap = new System.Drawing.Bitmap((int)doc.Pages[1].PageInfo.Width, (int)doc.Pages[1].PageInfo.Height);
System.Drawing.Drawing2D.GraphicsPath graphicsPath = new System.Drawing.Drawing2D.GraphicsPath();
System.Drawing.Drawing2D.Matrix lastCTM = new System.Drawing.Drawing2D.Matrix(1, 0, 0, -1, 0, 0);
System.Drawing.Drawing2D.Matrix inversionMatrix = new System.Drawing.Drawing2D.Matrix(1, 0, 0, -1, 0, (float)doc.Pages[1].PageInfo.Height);
System.Drawing.PointF lastPoint = new System.Drawing.PointF(0, 0);
System.Drawing.Color fillColor = System.Drawing.Color.FromArgb(0, 0, 0);
System.Drawing.Color strokeColor = System.Drawing.Color.FromArgb(0, 0, 0);
```

Zde je rozpis:
- Vytvoříme bitmapový obrázek o velikosti první stránky PDF.
- GraphicsPath se používá k definování tvarů (v tomto případě ohraničení).
- Matrix definuje, jak bude grafika transformována; potřebujeme inverzní matici, protože PDF a .NET mají různé souřadnicové systémy.

## Krok 3: Zpracování obsahu PDF


Soubor PDF je řada kreslicích příkazů a každý z těchto příkazů potřebujeme zpracovat, abychom identifikovali a extrahovali informace o ohraničení.

```csharp
foreach (Operator op in doc.Pages[1].Contents)
{
    // Zpracování příkazů, jako je uložení/obnovení stavu, kreslení čar, vyplňování tvarů atd.
}
```

Kód prochází každým operátorem výkresu v toku obsahu PDF. Každý operátor může představovat čáru, obdélník nebo jinou grafickou instrukci.

## Krok 4: Práce s operátory PDF

Každý operátor v souboru PDF řídí akci. Chcete-li extrahovat ohraničení, potřebujeme identifikovat příkazy jako "přesunout do", "čára do" a "nakreslit obdélník". O tyto akce se starají následující operátoři:

- MoveTo: Přesune kurzor na počáteční bod.
- LineTo: Nakreslí čáru z aktuálního bodu do nového bodu.
- Re: Nakreslí obdélník (může být součástí ohraničení).

```csharp
Aspose.Pdf.Operators.MoveTo opMoveTo = op as Aspose.Pdf.Operators.MoveTo;
Aspose.Pdf.Operators.LineTo opLineTo = op as Aspose.Pdf.Operators.LineTo;
Aspose.Pdf.Operators.Re opRe = op as Aspose.Pdf.Operators.Re;

if (opMoveTo != null)
{
    lastPoint = new System.Drawing.PointF((float)opMoveTo.X, (float)opMoveTo.Y);
}
else if (opLineTo != null)
{
    System.Drawing.PointF linePoint = new System.Drawing.PointF((float)opLineTo.X, (float)opLineTo.Y);
    graphicsPath.AddLine(lastPoint, linePoint);
    lastPoint = linePoint;
}
else if (opRe != null)
{
    System.Drawing.RectangleF re = new System.Drawing.RectangleF((float)opRe.X, (float)opRe.Y, (float)opRe.Width, (float)opRe.Height);
    graphicsPath.AddRectangle(re);
}
```

V tomto kroku:
- Zachycujeme body pro každou nakreslenou čáru nebo tvar.
- Pro obdélníky (`opRe` ), přidáme je přímo do`graphicsPath`, který později použijeme k nakreslení hranice.

## Krok 5: Nakreslení hranice

Jakmile identifikujeme čáry a obdélníky, které tvoří hranici, musíme je skutečně nakreslit na objekt Bitmap. Zde přichází na řadu grafický objekt.

```csharp
using (System.Drawing.Graphics gr = System.Drawing.Graphics.FromImage(bitmap))
{
    gr.SmoothingMode = SmoothingMode.HighQuality;
    gr.DrawPath(new System.Drawing.Pen(strokeColor), graphicsPath);
}
```

- Na základě bitmapy vytvoříme objekt Graphics.
- SmoothingMode.HighQuality zajišťuje, že získáme pěkně hladký obraz.
- Nakonec použijeme DrawPath k nakreslení ohraničení.

## Krok 6: Uložení extrahovaného okraje

Nyní, když jsme extrahovali ohraničení, je čas jej uložit jako soubor obrázku. Tím se ohraničení uloží jako PNG.

```csharp
dataDir = dataDir + "ExtractBorder_out.png";
bitmap.Save(dataDir, ImageFormat.Png);
```

- Bitmapa se uloží jako obrázek PNG.
- Nyní můžete tento obrázek otevřít a zobrazit extrahovaný okraj.

## Závěr

Extrahování hranic ze souboru PDF pomocí Aspose.PDF for .NET se může na první pohled zdát složité, ale jakmile to rozeberete, bude to jednoduché. Pochopením operátorů kreslení v PDF a využitím výkonných knihoven .NET můžete efektivně manipulovat a extrahovat grafický obsah. Tato příručka vám poskytuje robustní základ, abyste mohli začít s manipulací s PDF!

## FAQ

### Jak zpracuji více stránek v PDF?  
 Každou stránku v dokumentu můžete procházet opakováním`doc.Pages` místo pevného kódování`doc.Pages[1]`.

### Mohu pomocí stejného přístupu extrahovat další prvky, například text?  
Ano, Aspose.PDF poskytuje bohaté rozhraní API pro extrahování textu, obrázků a dalšího obsahu ze souborů PDF.

### Jak uplatním licenci, abych se vyhnul omezením?  
 Můžete[uplatnit licenci](https://purchase.aspose.com/temporary-license/) jeho načtením přes`License` třídy, kterou poskytuje Aspose.

### Co když moje PDF nemá žádné okraje?  
Pokud váš PDF neobsahuje žádné viditelné okraje, nemusí proces extrakce grafiky přinést žádný výsledek. Ujistěte se, že obsah PDF obsahuje vykreslitelné okraje.

### Mohu uložit výstup v jiných formátech než PNG?  
 Ano, stačí změnit`ImageFormat.Png` do jiného podporovaného formátu, např`ImageFormat.Jpeg`.