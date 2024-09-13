---
title: Přidat průhledný text do souboru PDF
linktitle: Přidat průhledný text do souboru PDF
second_title: Aspose.PDF pro .NET API Reference
description: Naučte se, jak přidat průhledný text do souboru PDF pomocí Aspose.PDF pro .NET.
type: docs
weight: 100
url: /cs/net/programming-with-text/add-transparent-text/
---
Tento tutoriál vás provede procesem přidávání průhledného textu do dokumentu PDF pomocí Aspose.PDF pro .NET. Poskytnutý zdrojový kód C# ukazuje potřebné kroky.

## Požadavky
Než začnete, ujistěte se, že máte následující:

- Visual Studio nebo jakýkoli jiný kompilátor C# nainstalovaný na vašem počítači.
- Aspose.PDF pro knihovnu .NET. Můžete si jej stáhnout z oficiálního webu Aspose nebo jej nainstalovat pomocí správce balíčků, jako je NuGet.

## Krok 1: Nastavte projekt
1. Vytvořte nový projekt C# ve vámi preferovaném vývojovém prostředí.
2. Přidejte odkaz na knihovnu Aspose.PDF for .NET.

## Krok 2: Importujte požadované jmenné prostory
Do souboru kódu, kam chcete přidat průhledný text, přidejte následující pomocí direktiv v horní části souboru:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Drawing;
```

## Krok 3: Nastavte adresář dokumentů
 V kódu vyhledejte řádek, který říká`string dataDir = "YOUR DOCUMENT DIRECTORY";` a nahradit`"YOUR DOCUMENT DIRECTORY"` s cestou k adresáři, kde jsou uloženy vaše dokumenty.

## Krok 4: Vytvořte novou instanci dokumentu
 Vytvořte nový`Document` objekt přidáním následujícího řádku kódu:

```csharp
Document doc = new Document();
```

## Krok 5: Přidejte do dokumentu stránku
 Přidejte do dokumentu novou stránku pomocí`Add` metoda`Pages` sbírka. V poskytnutém kódu je nová stránka přiřazena k proměnné`page`.

```csharp
Aspose.Pdf.Page page = doc.Pages.Add();
```

## Krok 6: Vytvořte objekt Graph
 Vytvořte nový`Graph` objekt s určitou šířkou a výškou.

```csharp
Aspose.Pdf.Drawing.Graph canvas = new Aspose.Pdf.Drawing.Graph(100, 400);
```

## Krok 7: Vytvořte obdélník s průhledností
 Vytvořte obdélník se specifickými rozměry a nastavte jeho barvu výplně na průhlednou pomocí`Color.FromRgb` metoda.

```csharp
Aspose.Pdf.Drawing.Rectangle rect = new Aspose.Pdf.Drawing.Rectangle(100, 100, 400, 400);
rect.GraphInfo.FillColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.FromArgb(128, System.Drawing.Color.FromArgb(12957183)));
canvas.Shapes.Add(rect);
```

## Krok 8: Přidejte na stránku objekt Graph
 Přidejte`Graph` objekt proti kolekci odstavců na stránce.

```csharp
page.Paragraphs.Add(canvas);
```

## Krok 9: Nastavte pozici pro objekt Graph
 Nastavte`IsChangePosition` vlastnictví`Graph` namítat proti`false` aby nedošlo ke změně polohy.

```csharp
canvas. IsChangePosition = false;
```

## Krok 10: Vytvořte TextFragment s průhledností
 Vytvořte a`TextFragment` objekt a nastavte jeho obsah na požadovaný text. Nastavte`ForegroundColor` vlastnictví`TextState` na barvu s průhledností pomocí`Color.FromArgb` metoda.

```csharp
TextFragment text = new TextFragment("transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text ");
Aspose.Pdf.Color color = Aspose.Pdf.Color.FromArgb(30, 0, 255, 0);
text.TextState.ForegroundColor = color;
page.Paragraphs.Add(text);
```

## Krok 11: Uložte dokument PDF
 Uložte dokument PDF pomocí`Save` metoda`Document` objekt.

```csharp
doc.Save(dataDir + "AddTransparentText_out.pdf");
doc.Save(dataDir);
Console.WriteLine("\nTransparent text added successfully.\nFile saved at " + dataDir);
```

### Ukázkový zdrojový kód pro Add Transparent Text pomocí Aspose.PDF for .NET 
```csharp
// Cesta k adresáři dokumentů.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Vytvořit instanci dokumentu
Document doc = new Document();
// Vytvořte kolekci stránek ve formátu PDF
Aspose.Pdf.Page page = doc.Pages.Add();
// Vytvořit objekt Graph
Aspose.Pdf.Drawing.Graph canvas = new Aspose.Pdf.Drawing.Graph(100, 400);
// Vytvořte instanci obdélníku s určitými rozměry
Aspose.Pdf.Drawing.Rectangle rect = new Aspose.Pdf.Drawing.Rectangle(100, 100, 400, 400);
// Vytvořte barevný objekt z barevného kanálu Alpha
rect.GraphInfo.FillColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.FromArgb(128, System.Drawing.Color.FromArgb(12957183)));
// Přidejte obdélník do kolekce tvarů objektu Graph
canvas.Shapes.Add(rect);
// Přidejte objekt grafu do kolekce odstavců objektu stránky
page.Paragraphs.Add(canvas);
// Nastavte hodnotu tak, aby neměnila polohu objektu grafu
canvas.IsChangePosition = false;
// Vytvořte instanci TextFragment s ukázkovou hodnotou
TextFragment text = new TextFragment("transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text ");
// Vytvořte barevný objekt z alfa kanálu
Aspose.Pdf.Color color = Aspose.Pdf.Color.FromArgb(30, 0, 255, 0);
// Nastavte informace o barvě pro instanci textu
text.TextState.ForegroundColor = color;
// Přidejte text do kolekce odstavců instance stránky
page.Paragraphs.Add(text);
dataDir = dataDir + "AddTransparentText_out.pdf";
doc.Save(dataDir);
Console.WriteLine("\nTransparent text added successfully.\nFile saved at " + dataDir);
```


## Závěr
Úspěšně jste přidali průhledný text do svého dokumentu PDF pomocí Aspose.PDF pro .NET. Výsledný soubor PDF lze nyní nalézt na zadané cestě k výstupnímu souboru.

### FAQ

#### Otázka: Na co je zaměřen tento tutoriál?

Odpověď: Tento tutoriál se zaměřuje na přidávání průhledného textu do dokumentu PDF pomocí knihovny Aspose.PDF for .NET. Poskytnutý zdrojový kód C# demonstruje nezbytné kroky k dosažení tohoto efektu.

#### Otázka: Které jmenné prostory je třeba pro tento výukový program importovat?

Odpověď: Do souboru kódu, kam chcete přidat průhledný text, importujte na začátek souboru následující jmenné prostory:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Drawing;
```

#### Otázka: Jak určím adresář dokumentů?

 A: V kódu najděte řádek`string dataDir = "YOUR DOCUMENT DIRECTORY";` a nahradit`"YOUR DOCUMENT DIRECTORY"` se skutečnou cestou k vašemu adresáři dokumentů.

#### Otázka: Jak vytvořím novou instanci dokumentu?

 Odpověď: V kroku 4 vytvoříte instanci nového`Document` objekt pomocí poskytnutého kódu.

#### Otázka: Jak přidám stránku do dokumentu?

 Odpověď: V kroku 5 přidáte do dokumentu novou stránku pomocí`Add` metoda`Pages` sbírka.

#### Otázka: Jak vytvořím objekt Graph?

 Odpověď: V kroku 6 vytvoříte nový`Graph` objekt s určitou šířkou a výškou.

#### Otázka: Jak vytvořím obdélník s průhledností?

 Odpověď: V kroku 7 vytvoříte obdélník se specifickými rozměry a nastavíte jeho barvu výplně na průhlednou pomocí`Color.FromRgb` metoda.

#### Otázka: Jak přidám objekt Graph na stránku?

 Odpověď: V kroku 8 přidáte`Graph` objekt proti kolekci odstavců na stránce.

#### Otázka: Jak nastavím pozici pro objekt Graph?

 A: V kroku 9 nastavíte`IsChangePosition` vlastnictví`Graph` namítat proti`false` aby nedošlo ke změně polohy.

#### Otázka: Jak vytvořím TextFragment s průhledností?

Odpověď: V kroku 10 vytvoříte a`TextFragment` objekt a nastavit jeho obsah a`ForegroundColor` vlastnost k dosažení průhledného textu.

#### Otázka: Jak uložím dokument PDF?

 Odpověď: V kroku 11 uložíte dokument PDF pomocí`Save` metoda`Document` objekt.

#### Otázka: Jaký je hlavní poznatek z tohoto tutoriálu?

Odpověď: Podle tohoto kurzu jste se naučili, jak přidat průhledný text do dokumentu PDF pomocí Aspose.PDF for .NET. To může být užitečné pro vytváření vizuálně přitažlivých a kreativních dokumentů PDF.