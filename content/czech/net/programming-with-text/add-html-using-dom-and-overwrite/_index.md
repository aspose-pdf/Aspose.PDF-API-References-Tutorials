---
title: Přidejte HTML pomocí DOM a přepsání PDF
linktitle: Přidat HTML pomocí DOM a přepsat
second_title: Aspose.PDF pro .NET API Reference
description: Naučte se přidávat obsah HTML pomocí DOM a přepisování PDF v Aspose.PDF pro .NET.
type: docs
weight: 50
url: /cs/net/programming-with-text/add-html-using-dom-and-overwrite/
---
Tento tutoriál vás provede procesem přidávání obsahu HTML pomocí DOM (Document Object Model) v Aspose.PDF pro .NET. Navíc se naučíte, jak přepsat styly pro obsah HTML. Poskytnutý zdrojový kód C# ukazuje potřebné kroky.

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
using Aspose.Pdf.Text;
```

## Krok 3: Nastavte adresář dokumentu a cestu k výstupnímu souboru
 V kódu vyhledejte řádek, který říká`string dataDir = "YOUR DOCUMENT DIRECTORY";` a nahradit`"YOUR DOCUMENT DIRECTORY"` s cestou k adresáři, kde jsou uloženy vaše dokumenty.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Krok 4: Vytvořte nový objekt dokumentu
 Vytvořte nový`Document` objekt přidáním následujícího řádku kódu:

```csharp
Document doc = new Document();
```

## Krok 5: Přidejte do dokumentu stránku
 Přidejte do dokumentu novou stránku pomocí`Add` metoda`Pages` sbírka. V poskytnutém kódu je nová stránka přiřazena k proměnné`page`.

```csharp
Page page = doc.Pages.Add();
```

## Krok 6: Vytvořte HtmlFragment s obsahem HTML
 Instantovat an`HtmlFragment` objekt a poskytnout požadovaný obsah HTML. V poskytnutém kódu je obsah HTML přiřazen k proměnné`title`. Obsah HTML můžete upravit podle potřeby.

```csharp
HtmlFragment title = new HtmlFragment("<p style='font-family: Verdana'><b><i>Table contains text</i></b></p>");
```

## Krok 7: Přepište styly pro obsah HTML
 Chcete-li přepsat styly obsahu HTML, můžete upravit`TextState` vlastnosti`HtmlFragment` objekt. V poskytnutém kódu se rodina písem změní na "Arial" a velikost písma je nastavena na 20.

```csharp
title. TextState = new TextState("Arial");
title.TextState.FontSize = 20;
```

## Krok 8: Nastavte informace o okrajích
V případě potřeby upravte spodní a horní okraj fragmentu HTML. V poskytnutém kódu je spodní okraj nastaven na 10 a horní okraj na 400.

```csharp
title. Margin. Bottom = 10;
title. Margin. Top = 400;
```

## Krok 9: Přidejte na stránku HtmlFragment
 Přidejte`HtmlFragment` objekt proti kolekci odstavců na stránce.

```csharp
page.Paragraphs.Add(title);
```

## Krok 10: Uložte dokument PDF
 Uložte dokument PDF pomocí`Save` metoda`Document` objekt. Zadejte cestu k výstupnímu souboru, kterou jste nastavili v kroku 3.

```csharp
dataDir = dataDir + "AddHTMLUsingDOMAndOverwrite_out.pdf";
doc.Save(dataDir);
```

### Ukázkový zdrojový kód pro Add HTMLUsing DOMAnd Overwrite pomocí Aspose.PDF pro .NET 
```csharp
// Cesta k adresáři dokumentů.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Objekt okamžitého dokumentu
Document doc = new Document();
// Přidejte stránku do kolekce stránek souboru PDF
Page page = doc.Pages.Add();
// Instanciujte HtmlFragment s HTML contnets
HtmlFragment title = new HtmlFragment("<p style='font-family: Verdana'><b><i>Table contains text</i></b></p>");
//Rodina písem z „Verdana“ bude resetována na „Arial“
title.TextState = new TextState("Arial");
title.TextState.FontSize = 20;
// Nastavte informace o spodním okraji
title.Margin.Bottom = 10;
// Nastavte informace o horním okraji
title.Margin.Top = 400;
// Přidejte fragment HTML do kolekce odstavců stránky
page.Paragraphs.Add(title);
// Uložit soubor PDF
dataDir = dataDir + "AddHTMLUsingDOMAndOverwrite_out.pdf";
// Uložit soubor PDF
doc.Save(dataDir);
```

## Závěr
Úspěšně jste přidali obsah HTML pomocí DOM v Aspose.PDF pro .NET a přepsali styly pro obsah HTML. Výsledný soubor PDF lze nyní nalézt na zadané cestě k výstupnímu souboru.

### FAQ

#### Otázka: Na co je zaměřen tento tutoriál?

Odpověď: Tento tutoriál je navržen tak, aby vás provedl procesem přidávání obsahu HTML do dokumentu PDF pomocí Document Object Model (DOM) v Aspose.PDF pro .NET. Kromě toho se naučíte, jak přepsat styly pro obsah HTML, což vám umožní přizpůsobit jeho vzhled. Výukový program poskytuje úryvky zdrojového kódu C#, které demonstrují požadované kroky.

#### Otázka: Které jmenné prostory musím pro tento výukový program importovat?

Odpověď: Do souboru kódu, kam chcete přidat obsah HTML, importujte na začátek souboru následující jmenné prostory:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

#### Otázka: Jak určím adresář dokumentu a cestu k výstupnímu souboru?

 Odpověď: V kódu vyhledejte řádek`string dataDir = "YOUR DOCUMENT DIRECTORY";` a nahradit`"YOUR DOCUMENT DIRECTORY"` se skutečnou cestou k vašemu adresáři dokumentů.

#### Otázka: Jak vytvořím objekt dokumentu?

 Odpověď: V kroku 4 vytvoříte instanci nového`Document` objekt pomocí následujícího řádku kódu:

```csharp
Document doc = new Document();
```

#### Otázka: Jak přidám stránku do dokumentu?

 Odpověď: V kroku 5 přidáte do dokumentu novou stránku pomocí`Add` metoda`Pages` sbírka:

```csharp
Page page = doc.Pages.Add();
```

#### Otázka: Jak mohu nastavit obsah HTML pomocí DOM?

 Odpověď: V kroku 6 vytvoříte soubor`HtmlFragment` objekt a přiřaďte mu požadovaný obsah HTML. Obsah HTML je přiřazen k proměnné`title`:

```csharp
HtmlFragment title = new HtmlFragment("<p style='font-family: Verdana'><b><i>Table contains text</i></b></p>");
```

#### Otázka: Jak mohu přepsat styly obsahu HTML?

 Odpověď: V kroku 7 přepíšete styly obsahu HTML úpravou`TextState` vlastnosti`HtmlFragment`objekt. Můžete například změnit rodinu písem na „Arial“ a nastavit velikost písma na 20:

```csharp
title.TextState = new TextState("Arial");
title.TextState.FontSize = 20;
```

#### Otázka: Mohu upravit okraj obsahu HTML?

Odpověď: Ano, v kroku 8 můžete podle potřeby upravit spodní a horní okraj fragmentu HTML:

```csharp
title.Margin.Bottom = 10;
title.Margin.Top = 400;
```

#### Otázka: Jak přidám HtmlFragment do dokumentu PDF?

 Odpověď: V kroku 9 přidáte`HtmlFragment` objekt (`title`) do kolekce odstavců na stránce:

```csharp
page.Paragraphs.Add(title);
```

#### Otázka: Jak uložím výsledný dokument PDF?

 Odpověď: Po přidání obsahu HTML a přizpůsobení jeho stylů použijte soubor`Save` metoda`Document` objekt pro uložení dokumentu PDF:

```csharp
dataDir = dataDir + "AddHTMLUsingDOMAndOverwrite_out.pdf";
doc.Save(dataDir);
```

#### Otázka: Jaký je hlavní přínos tohoto tutoriálu?

Odpověď: Sledováním tohoto kurzu jste se úspěšně naučili, jak začlenit obsah HTML pomocí Document Object Model (DOM) v Aspose.PDF pro .NET. Navíc jste získali možnost přepisovat styly, abyste přizpůsobili vzhled obsahu HTML ve výsledném dokumentu PDF.