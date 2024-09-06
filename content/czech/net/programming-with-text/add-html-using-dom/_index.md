---
title: Přidejte HTML pomocí DOM
linktitle: Přidejte HTML pomocí DOM
second_title: Aspose.PDF pro .NET API Reference
description: Naučte se přidávat obsah HTML pomocí DOM v Aspose.PDF pro .NET.
type: docs
weight: 40
url: /cs/net/programming-with-text/add-html-using-dom/
---
Tento tutoriál vás provede procesem přidávání obsahu HTML pomocí DOM (Document Object Model) v Aspose.PDF pro .NET. Poskytnutý zdrojový kód C# ukazuje potřebné kroky.

## Požadavky
Než začnete, ujistěte se, že máte následující:

- Visual Studio nebo jakýkoli jiný kompilátor C# nainstalovaný na vašem počítači.
- Aspose.PDF pro knihovnu .NET. Můžete si jej stáhnout z oficiálního webu Aspose nebo jej nainstalovat pomocí správce balíčků, jako je NuGet.

## Krok 1: Nastavte projekt
1. Vytvořte nový projekt C# ve vámi preferovaném vývojovém prostředí.
2. Přidejte odkaz na knihovnu Aspose.PDF for .NET.

## Krok 2: Importujte požadované jmenné prostory
Do souboru kódu, kam chcete přidat obsah HTML, přidejte následující pomocí direktiv v horní části souboru:

```csharp
using Aspose.Pdf;
```

## Krok 3: Nastavte adresář dokumentu a cestu k výstupnímu souboru
 V kódu vyhledejte řádek, který říká`string dataDir = "YOUR DOCUMENT DIRECTORY";` a nahradit`"YOUR DOCUMENT DIRECTORY"` s cestou k adresáři, kde jsou uloženy vaše dokumenty.

## Krok 4: Vytvořte nový objekt dokumentu
 Vytvořte nový`Document` objekt přidáním následujícího řádku kódu:

```csharp
Document doc = new Document();
```

## Krok 5: Přidejte do dokumentu stránku
 Přidejte do dokumentu novou stránku pomocí`Add` metoda`Pages`sbírka. V poskytnutém kódu je nová stránka přiřazena k proměnné`page`.

```csharp
Page page = doc.Pages.Add();
```

## Krok 6: Vytvořte HtmlFragment s obsahem HTML
 Instantovat an`HtmlFragment` objekt a poskytnout požadovaný obsah HTML. V poskytnutém kódu je obsah HTML přiřazen k proměnné`titel`. Obsah HTML můžete upravit podle potřeby.

```csharp
HtmlFragment titel = new HtmlFragment("<fontsize=10><b><i>Table</i></b></fontsize>");
```

## Krok 7: Nastavte informace o okrajích
V případě potřeby upravte spodní a horní okraj fragmentu HTML. V poskytnutém kódu je spodní okraj nastaven na 10 a horní okraj na 200.

```csharp
title. Margin. Bottom = 10;
title. Margin. Top = 200;
```

## Krok 8: Přidejte na stránku HtmlFragment
 Přidejte`HtmlFragment` objekt proti kolekci odstavců na stránce.

```csharp
page.Paragraphs.Add(title);
dataDir = dataDir + "AddHTMLUsingDOM_out.pdf";
```

## Krok 9: Uložte dokument PDF
 Uložte dokument PDF pomocí`Save` metoda`Document` objekt. Zadejte cestu k výstupnímu souboru, kterou jste nastavili v kroku 3.

```csharp
doc.Save(dataDir);
```

## Krok 10: Zobrazte zprávu o úspěchu
Zobrazte zprávu o úspěchu spolu s cestou, kam byl soubor PDF uložen.

```csharp
Console.WriteLine("\nHTML using DOM added successfully.\nFile saved at " + dataDir);
```

### Ukázkový zdrojový kód pro Add HTMLUsing DOM pomocí Aspose.PDF pro .NET 
```csharp
// Cesta k adresáři dokumentů.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Objekt okamžitého dokumentu
Document doc = new Document();
// Přidejte stránku do kolekce stránek souboru PDF
Page page = doc.Pages.Add();
// Instanciujte HtmlFragment s HTML contnets
HtmlFragment titel = new HtmlFragment("<fontsize=10><b><i>Table</i></b></fontsize>");
// Nastavte informace o spodním okraji
titel.Margin.Bottom = 10;
// Nastavte informace o horním okraji
titel.Margin.Top = 200;
// Přidejte fragment HTML do kolekce odstavců stránky
page.Paragraphs.Add(titel);
dataDir = dataDir + "AddHTMLUsingDOM_out.pdf";
// Uložit soubor PDF
doc.Save(dataDir);
Console.WriteLine("\nHTML using DOM added successfully.\nFile saved at " + dataDir);
```

## Závěr
Úspěšně jste přidali obsah HTML pomocí DOM v Aspose.PDF pro .NET. Výsledný soubor PDF lze nyní nalézt na zadané cestě k výstupnímu souboru.

### FAQ

#### Otázka: Co je cílem tohoto tutoriálu?

Odpověď: Tento tutoriál si klade za cíl poskytnout podrobného průvodce, jak přidat obsah HTML do dokumentu PDF pomocí Document Object Model (DOM) v Aspose.PDF pro .NET. Zahrnuje úryvky zdrojového kódu C#, které vám pomohou pochopit a implementovat proces.

#### Otázka: Které jmenné prostory musím pro tento výukový program importovat?

Odpověď: Do souboru kódu, kam plánujete přidat obsah HTML, importujte na začátek souboru následující jmenný prostor:

```csharp
using Aspose.Pdf;
```

#### Otázka: Jak určím adresář dokumentu a cestu k výstupnímu souboru?

 A: V kódu najděte řádek`string dataDir = "YOUR DOCUMENT DIRECTORY";` a nahradit`"YOUR DOCUMENT DIRECTORY"` se skutečnou cestou k vašemu adresáři dokumentů.

#### Otázka: Jak vytvořím objekt dokumentu?

 Odpověď: V kroku 4 vytvořte instanci nového`Document` objekt přidáním následujícího řádku kódu:

```csharp
Document doc = new Document();
```

#### Otázka: Jak přidám stránku do dokumentu?

 Odpověď: V kroku 5 přidáte do dokumentu novou stránku pomocí`Add` metoda`Pages` sbírka:

```csharp
Page page = doc.Pages.Add();
```

#### Otázka: Jak mohu nastavit obsah HTML pomocí DOM?

 Odpověď: V kroku 6 vytvoříte soubor`HtmlFragment` objekt a přiřaďte mu požadovaný obsah HTML. Obsah HTML je přiřazen k proměnné`titel`:

```csharp
HtmlFragment titel = new HtmlFragment("<fontsize=10><b><i>Table</i></b></fontsize>");
```

#### Otázka: Mohu upravit okraj obsahu HTML?

Odpověď: Ano, v kroku 7 můžete upravit spodní a horní okraj fragmentu HTML podle potřeby:

```csharp
titel.Margin.Bottom = 10;
titel.Margin.Top = 200;
```

#### Otázka: Jak přidám HTMLFragment do dokumentu PDF?

 Odpověď: V kroku 8 přidáte`HtmlFragment` objekt (`titel`) do kolekce odstavců na stránce:

```csharp
page.Paragraphs.Add(titel);
dataDir = dataDir + "AddHTMLUsingDOM_out.pdf";
```

#### Otázka: Jak uložím výsledný dokument PDF?

 Odpověď: Po přidání obsahu HTML a úpravě okrajů použijte`Save` metoda`Document` objekt pro uložení dokumentu PDF:

```csharp
doc.Save(dataDir);
```

#### Otázka: Existuje způsob, jak ověřit, zda byl proces úspěšný?

Odpověď: Určitě se v kroku 10 zobrazí zpráva o úspěchu spolu s cestou, kam byl soubor PDF uložen:

```csharp
Console.WriteLine("\nHTML using DOM added successfully.\nFile saved at " + dataDir);
```

#### Otázka: Jaký je hlavní přínos tohoto tutoriálu?

Odpověď: Sledováním tohoto kurzu jste se úspěšně naučili používat objektový model dokumentu (DOM) v Aspose.PDF pro .NET k přidání obsahu HTML do dokumentu PDF. Tyto znalosti vám umožňují vylepšit možnosti generování PDF.