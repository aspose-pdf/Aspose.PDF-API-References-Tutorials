---
title: Vytvořte místní hypertextový odkaz v souboru PDF
linktitle: Vytvořte místní hypertextový odkaz v souboru PDF
second_title: Aspose.PDF pro .NET API Reference
description: Naučte se, jak vytvořit místní hypertextové odkazy v souborech PDF pomocí Aspose.PDF for .NET bez námahy s naším průvodcem krok za krokem.
type: docs
weight: 40
url: /cs/net/programming-with-links-and-actions/create-local-hyperlink/
---
## Zavedení

této příručce vás provedeme procesem vytváření místních hypertextových odkazů v souboru PDF pomocí Aspose.PDF for .NET. Každý krok jasně rozebereme a zajistíme, že i když jste ve světě manipulace s PDF nováčky, budete je moci bez námahy sledovat.

## Předpoklady

Než se ponoříte do kódu po hlavě, ujistěte se, že máte vše, co potřebujete:

1.  Visual Studio: Toto budete potřebovat k vývoji aplikací .NET. Stáhněte si jej z[webové stránky](https://visualstudio.microsoft.com/).
2.  Aspose.PDF pro .NET: Tuto knihovnu si můžete stáhnout prostřednictvím[odkaz ke stažení zde](https://releases.aspose.com/pdf/net/). Dodává se s bohatou sadou funkcí pro manipulaci s PDF.
3. Základní znalost C#: Malá znalost programování C# pomůže, ale nebojte se; projdeme kód řádek po řádku.
4.  .NET Framework: Ujistěte se, že máte na svém počítači nainstalovaný .NET Framework. Požadavky si můžete zkontrolovat na Aspose.PDF[dokumentace](https://reference.aspose.com/pdf/net/).

S těmito předpoklady jste připraveni naučit se vytvářet místní hypertextové odkazy v dokumentech PDF!

## Importujte balíčky

Nyní, když jste vše připraveni, je čas naimportovat potřebné balíčky do vašeho projektu C#. Knihovna Aspose.PDF obsahuje všechny třídy, které potřebujeme. Jak na to:

### Otevřete svůj projekt

Otevřete svůj stávající projekt .NET nebo vytvořte nový v aplikaci Visual Studio. Pokud začínáte znovu, vyberte na úvodní obrazovce možnost „Vytvořit nový projekt“.

### Přidejte odkaz do Aspose.PDF

 Klikněte pravým tlačítkem myši na "Dependencies" ve složce projektu v Průzkumníku řešení. Vyberte „Spravovat balíčky NuGet“ a poté vyhledejte`Aspose.PDF`. Nainstalujte nejnovější dostupnou verzi. To přinese všechny nástroje, které potřebujete pro vytváření a manipulaci s PDF.

### Importovat jmenné prostory

V horní části souboru .cs přidejte pomocí direktiv pro knihovnu Aspose.PDF takto:

```csharp
using System;
using System.IO;
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

Tímto způsobem budete mít přístup k funkcím knihovny.

Pojďme si proces vytváření lokálních hypertextových odkazů rozdělit do jednoduchých kroků. Každý krok bude podrobně vysvětlen, aby vám pomohl pochopit logiku za ním.

## Krok 1: Nastavte instanci dokumentu

tomto kroku vytvoříte novou instanci třídy Document, která představuje soubor PDF, se kterým budete pracovat.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY"; // Nastavte adresář dokumentů
Document doc = new Document(); // Vytvořit instanci dokumentu
```
 The`dataDir` proměnná je místo, kde bude umístěn váš nově vytvořený soubor PDF. Budete muset vyměnit`"YOUR DOCUMENT DIRECTORY"` se skutečnou cestou ve vašem systému. The`Document` třída vytvoří nový dokument PDF, do kterého můžeme přidat stránky a odkazy.

## Krok 2: Přidejte stránku do dokumentu

Dále přidáte stránku do dokumentu PDF. 

```csharp
Page page = doc.Pages.Add(); // Přidat stránku do kolekce stránek
```
 The`Pages.Add()` metoda přidá do dokumentu novou stránku. Zde bude žít veškerý váš obsah.

## Krok 3: Vytvořte textový fragment

Nyní vytvoříme text, který bude fungovat jako odkaz, na který lze kliknout.

```csharp
Aspose.Pdf.Text.TextFragment text = new Aspose.Pdf.Text.TextFragment("link page number test to page 7");
```
 The`TextFragment` představuje část textu v PDF. Zde vytváříme odkaz, který uživatelům řekne, že je přesměruje na stránku 7.

## Krok 4: Vytvořte místní hypertextový odkaz

Tady se děje kouzlo! Musíte vytvořit místní hypertextový odkaz, který fragmentu textu řekne, kam má ukazovat.

```csharp
Aspose.Pdf.LocalHyperlink link = new Aspose.Pdf.LocalHyperlink(); // Vytvořte místní hypertextový odkaz
link.TargetPageNumber = 7; //Nastavit cílovou stránku pro instanci odkazu
text.Hyperlink = link; // Nastavit hypertextový odkaz TextFragment
```
 The`LocalHyperlink` class je to, co nám umožňuje ukázat na jiné stránky ve stejném dokumentu. Nastavením`TargetPageNumber` až 7, řeknete hypertextovému odkazu, aby po kliknutí přešel na tuto konkrétní stránku.

## Krok 5: Přidejte textový fragment na stránku

Po nastavení hypertextového odkazu je čas přidat náš textový fragment na stránku, kterou jsme vytvořili.

```csharp
page.Paragraphs.Add(text); // Přidejte text do kolekce odstavců stránky
```
Tento řádek přidá váš text, na který lze kliknout, do kolekce odstavců na stránce.

## Krok 6: Vytvořte další textový fragment (volitelné)

Pojďme přidat další hypertextový odkaz pro přechod zpět na stránku 1.

```csharp
text = new TextFragment("link page number test to page 1"); // Vytvořte nový TextFragment
text.IsInNewPage = true; // Přidejte jej na novou stránku
```
 Vytvoření nového`TextFragment` pro druhý odkaz jsme nastavili`IsInNewPage` na true, což znamená, že se tento text přesune na novou stránku.

## Krok 7: Nastavte druhý místní hypertextový odkaz

Stejně jako předtím vytvoříte další místní hypertextový odkaz pro stránku 1.

```csharp
link = new LocalHyperlink(); // Vytvořte další místní instanci hypertextového odkazu
link.TargetPageNumber = 1; //Nastavte cílovou stránku pro druhý hypertextový odkaz
text.Hyperlink = link; // Nastavit odkaz pro druhý TextFragment
```
Tento hypertextový odkaz cílí na stránku 1 a umožňuje uživatelům přejít zpět, když se dostanou na druhou stránku.

## Krok 8: Přidejte druhý textový fragment na novou stránku

Nyní přidáme tento text na jeho stránku.

```csharp
page.Paragraphs.Add(text); // Přidejte text do kolekce odstavců objektu stránky
```
Podobně jako v kroku 5 tento řádek přidá nový text hypertextového odkazu na nově vytvořenou stránku.

## Krok 9: Uložte dokument

Konečně je čas ušetřit si tvrdou práci! 

```csharp
dataDir = dataDir + "CreateLocalHyperlink_out.pdf"; // Zadejte název výstupního souboru
doc.Save(dataDir); // Uložit aktualizovaný dokument
Console.WriteLine("\nLocal hyperlink created successfully.\nFile saved at " + dataDir);
```
 To kombinuje cestu k adresáři s názvem souboru. The`Save()` metoda uloží váš dokument a potvrzovací zpráva vám dá vědět, že vše proběhlo hladce!

## Závěr

Vytváření lokálních hypertextových odkazů v souborech PDF pomocí Aspose.PDF for .NET není jen skvělý trik; je to praktická funkce, která zlepšuje navigaci a uživatelský zážitek. Nyní jste vybaveni znalostmi, abyste své čtenáře nasměrovali přímo na informace, které potřebují. Jen si vzpomeňte na naši původní analogii – už žádné ztracené duše putující nekonečnými stránkami.

## FAQ

### Co je Aspose.PDF pro .NET?
Aspose.PDF for .NET je knihovna, která umožňuje vývojářům vytvářet, manipulovat a převádět dokumenty PDF programově pomocí rozhraní .NET.

### Mohu vytvořit hypertextové odkazy na externí webové stránky?
Ano, Aspose.PDF také podporuje vytváření hypertextových odkazů na externí URL kromě lokálních hypertextových odkazů v PDF.

### Existuje bezplatná zkušební verze pro Aspose.PDF?
 Absolutně! K bezplatné zkušební verzi můžete přistupovat z[místo](https://releases.aspose.com/).

### Jaké programovací jazyky Aspose podporuje?
Aspose nabízí knihovny pro různé programovací jazyky, včetně Javy, C++, a Python, mimo jiné.

### Jak získám podporu pro produkty Aspose?
 Podporu můžete hledat prostřednictvím[Fórum Aspose](https://forum.aspose.com/c/pdf/10).