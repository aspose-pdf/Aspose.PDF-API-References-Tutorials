---
title: Číslo Stránky V Zápatí Záhlaví Pomocí Plovoucí Krabice
linktitle: Číslo Stránky V Zápatí Záhlaví Pomocí Plovoucí Krabice
second_title: Aspose.PDF pro .NET API Reference
description: Naučte se, jak přidat číslo stránky do záhlaví a zápatí dokumentu PDF pomocí Aspose.PDF pro .NET.
type: docs
weight: 150
url: /cs/net/programming-with-stamps-and-watermarks/page-number-in-header-footer-using-floating-box/
---
V tomto tutoriálu vás krok za krokem provedeme, jak přidat číslo stránky do záhlaví a zápatí dokumentu PDF pomocí FloatingBox s Aspose.PDF pro .NET. Dodaný zdrojový kód C# použijeme k vytvoření dokumentu PDF, přidání stránky, vytvoření FloatingBoxu, nastavení jeho pozice a přidání čísla stránky k němu a poté uložení upraveného PDF dokumentu.

## Krok 1: Nastavení prostředí

Než začnete, ujistěte se, že máte následující:

- Nainstalované vývojové prostředí .NET.
- Knihovna Aspose.PDF pro .NET stažená a odkazovaná ve vašem projektu.

## Krok 2: Vytvoření dokumentu PDF a přidání stránky

Prvním krokem je vytvořit instanci dokumentu PDF a přidat do něj stránku. Zde je postup:

```csharp
// Cesta k adresáři dokumentů.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Vytvořte instanci dokumentu PDF
Aspose.Pdf.Document pdf = new Aspose.Pdf.Document();

// Přidejte stránku do dokumentu PDF
Aspose.Pdf.Page page = pdf.Pages.Add();
```

Nezapomeňte nahradit "VAŠE ADRESÁŘ DOKUMENTŮ" skutečnou cestou k adresáři, kam chcete uložit dokument PDF.

## Krok 3: Vytvoření FloatingBoxu a přidání čísla stránky

Nyní, když je stránka přidána do dokumentu PDF, můžeme vytvořit FloatingBox, nastavit jeho pozici a přidat k němu číslo stránky. Zde je postup:

```csharp
// Vytvořte FloatingBox o šířce 140 a výšce 80
Aspose.Pdf.FloatingBox box1 = new Aspose.Pdf.FloatingBox(140, 80);

// Nastavte levou pozici odstavce
box1. Left = 2;

// Nastavte horní pozici odstavce
box1. Top = 10;

// Přidejte číslo stránky do FloatingBox
box1.Paragraphs.Add(new Aspose.Pdf.Text.TextFragment("Page: ($p/ $P )"));

// Přidejte FloatingBox na stránku
page.Paragraphs.Add(box1);
```

Výše uvedený kód vytvoří FloatingBox o šířce 140 a výšce 80. Dále nastavíme jeho pozici zadáním hodnoty vlevo a nahoře. Nakonec do FloatingBoxu přidáme číslo stránky pomocí TextFragmentu obsahujícího syntaxi "($p/ $P )", která bude nahrazena aktuálním číslem stránky a celkovým počtem stránek.

## Krok 4: Uložení upraveného dokumentu PDF

Jakmile je číslo stránky přidáno do záhlaví nebo zápatí pomocí FloatingBoxu, můžeme upravený dokument PDF uložit. Zde je postup:

```csharp
// Uložte upravený dokument PDF
pdf.Save(dataDir + "PageNumberinHeaderFooterUsingFloatingBox_out.pdf");
```

Výše uvedený kód uloží upravený dokument PDF do určeného adresáře.

### Ukázkový zdrojový kód pro číslo stránky v záhlaví zápatí pomocí plovoucího rámečku pomocí Aspose.PDF pro .NET 
```csharp

// Cesta k adresáři dokumentů.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Instancia dokumentu instance
Aspose.Pdf.Document pdf = new Aspose.Pdf.Document();

// Přidejte stránku do dokumentu pdf
Aspose.Pdf.Page page = pdf.Pages.Add();

// Inicializuje novou instanci třídy FloatingBox
Aspose.Pdf.FloatingBox box1 = new Aspose.Pdf.FloatingBox(140, 80);

// Plovoucí hodnota, která označuje levou pozici odstavce
box1.Left = 2;

// Plovoucí hodnota, která označuje horní pozici odstavce
box1.Top = 10;

// Přidejte makra do kolekce odstavců FloatingBox
box1.Paragraphs.Add(new Aspose.Pdf.Text.TextFragment("Page: ($p/ $P )"));

// Přidejte na stránku plovoucí rámeček
page.Paragraphs.Add(box1);

// Uložte dokument
pdf.Save(dataDir + "PageNumberinHeaderFooterUsingFloatingBox_out.pdf");

```

## Závěr

gratuluji! Naučili jste se, jak přidat číslo stránky do záhlaví a zápatí dokumentu PDF pomocí FloatingBox s Aspose.PDF pro .NET. Nyní můžete upravit záhlaví a zápatí přidáním dynamických informací, jako je číslo stránky.

### FAQ

#### Otázka: Co je to FloatingBox a jak se používá k přidávání čísel stránek do záhlaví nebo zápatí dokumentu PDF?

A: FloatingBox je všestranný prvek rozvržení v Aspose.PDF, který pojme různý obsah, včetně textu a obrázků. V tomto tutoriálu se používá k vytvoření kontejneru pro číslo stránky, což vám umožňuje dynamicky vkládat aktuální číslo stránky a celkový počet stránek do záhlaví nebo zápatí.

#### Otázka: Jak dodaný zdrojový kód C# dosáhne přidání čísel stránek pomocí FloatingBox?

Odpověď: Fragment kódu ukazuje, jak vytvořit dokument PDF, přidat stránku, vytvořit FloatingBox, nastavit jeho pozici na stránce a vložit číslo stránky pomocí TextFragmentu. Syntaxe "($p/ $P )" v TextFragment je nahrazena aktuálním číslem stránky a celkovým počtem stránek.

#### Otázka: Mohu upravit vzhled a formátování čísla stránky přidaného pomocí FloatingBox?

Odpověď: Ano, vzhled čísla stránky můžete přizpůsobit úpravou vlastností TextFragmentu v rámci FloatingBox. Můžete změnit velikost písma, barvu, styl, zarovnání a další možnosti formátování.

#### Otázka: Je možné přidat různé dynamické prvky, jako je datum a čas, do záhlaví nebo zápatí pomocí podobného přístupu?

Odpověď: Samozřejmě můžete přidávat různé dynamické prvky, jako je datum, čas, metadata dokumentu nebo vlastní text, úpravou obsahu TextFragment v rámci FloatingBox. Můžete použít makra jako "($p/ $P )" pro čísla stránek nebo "($date)" pro aktuální datum.

#### Otázka: Jak určím pozici FloatingBoxu v sekci záhlaví nebo zápatí?
 Odpověď: Poskytnutý kód nastavuje polohu FloatingBoxu pomocí`Left` a`Top` vlastnosti. Tyto hodnoty můžete upravit tak, aby se FloatingBox umístil podle potřeby v sekci záhlaví nebo zápatí.

#### Otázka: Mohu použít jiné písmo nebo styl pro číslo stránky v záhlaví nebo zápatí?

Odpověď: Ano, můžete upravit písmo, styl a další vlastnosti formátování textu čísla stránky úpravou vlastností TextFragment v rámci FloatingBox.

#### Otázka: Co se stane, když obsah ve FloatingBox přesáhne své rozměry?

Odpověď: Pokud obsah ve FloatingBox přesáhne své rozměry, může být oříznut nebo mohou nastat problémy s rozložením. Ujistěte se, že rozměry FloatingBoxu jsou vhodné pro umístění obsahu, a v případě potřeby zvažte úpravu rozvržení stránky.

#### Otázka: Je možné přidat více FloatingBoxů s různým obsahem do záhlaví nebo zápatí stejné stránky?

Odpověď: Ano, můžete přidat více FloatingBoxů s různým obsahem do záhlaví nebo zápatí stejné stránky vytvořením samostatných instancí FloatingBox a jejich přidáním do kolekce odstavců stránky.

#### Otázka: Mohu použít přístup FloatingBox k přidání obsahu do jiných částí dokumentu PDF, jako je tělo nebo okraje?

Odpověď: I když se plovoucí rámečky běžně používají pro záhlaví a zápatí, můžete je také použít k přidání obsahu do jiných částí dokumentu PDF, jako je tělo nebo okraje, jejich umístěním na stránce.