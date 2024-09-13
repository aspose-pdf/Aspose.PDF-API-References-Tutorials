---
title: Změnit orientaci
linktitle: Změnit orientaci
second_title: Aspose.PDF pro .NET API Reference
description: Podrobný průvodce změnou orientace stránky PDF pomocí Aspose.PDF pro .NET. Snadné sledování a implementace do vašich projektů.
type: docs
weight: 10
url: /cs/net/programming-with-pdf-pages/change-orientation/
---
## Zavedení

Už se vám někdy stalo, že jste se potýkali se souborem PDF, kde je orientace stránky prostě... vypnutá? Možná máte co do činění s dokumentem, který byl naskenován nebo vytvořen nesprávně a stránky je třeba otočit, aby dávaly smysl. Máme štěstí, že Aspose.PDF for .NET poskytuje snadný a výkonný způsob, jak manipulovat se soubory PDF téměř jakýmkoliv představitelným způsobem – včetně změny orientace vašich stránek. Ať už chcete přejít z portrétu na šířku nebo naopak, tento průvodce vás provede procesem krok za krokem.

Takže, pokud jste připraveni se ponořit a snadno otočit tyto stránky PDF, začněme!

## Předpoklady

Než se pustíme do podrobností o změně orientace stránky ve vašem PDF, pojďme si rychle probrat, co budete muset mít na svém místě:

-  Aspose.PDF pro .NET: Ujistěte se, že jste nainstalovali knihovnu Aspose.PDF pro .NET. Pokud ne, můžete[stáhněte si jej zde](https://releases.aspose.com/pdf/net/).
- Vývojové prostředí .NET: Pro práci s .NET můžete použít Visual Studio, JetBrains Rider nebo jakékoli preferované IDE.
- Základní znalost C#: I když je tato příručka přímočará, některé základní znalosti C# usnadní její sledování.
- Soubor PDF: Níže uvedený příklad předpokládá, že máte soubor PDF s více stránkami. Pokud nemáte žádný po ruce, vytvořte nebo stáhněte si vzorový soubor PDF, se kterým budete pracovat.

 Také, pokud právě začínáte, můžete zkusit Aspose.PDF s a[dočasná licence zdarma](https://purchase.aspose.com/temporary-license/) než se rozhodnout[koupit plnou verzi](https://purchase.aspose.com/buy).

## Importovat jmenné prostory

Než budete moci manipulovat s orientací stránek ve vašem PDF, budete muset do projektu C# importovat potřebné jmenné prostory. Ujistěte se, že máte následující:

```csharp
using System.IO;
using Aspose.Pdf;
```

S tímto importem se vrhneme do hlavní části tutoriálu.

## Krok 1: Načtěte dokument PDF

 První věc, kterou musíme udělat, je načíst soubor PDF, který chcete upravit. Můžete použít`Document` třídy z oboru názvů Aspose.PDF a otevřete soubor PDF.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "input.pdf");
```

 Tento řádek načte PDF z vašeho zadaného adresáře. Nezapomeňte vyměnit`"YOUR DOCUMENT DIRECTORY"` se skutečnou cestou k vašemu souboru. The`"input.pdf"` je PDF, jehož orientaci chcete změnit.

## Krok 2: Projděte každou stránku

 Nyní, když máme načtený dokument, projdeme každou stránku v PDF. Použijeme a`foreach` smyčkou procházet každou stránku, což nám umožňuje aplikovat změnu orientace na všechny z nich.

```csharp
foreach (Page page in doc.Pages)
{
    // Manipulujte s každou stránkou
}
```

Tato smyčka bude procházet všemi stránkami v dokumentu.

## Krok 3: Získejte MediaBox stránky

 Každá stránka v PDF má a`MediaBox` který určuje hranice stránky. K tomu potřebujeme přistupovat, abychom mohli určit aktuální orientaci a upravit ji.

```csharp
Aspose.Pdf.Rectangle r = page.MediaBox;
```

 The`MediaBox` nám udává rozměry stránky, jako je její šířka, výška a umístění.

## Krok 4: Vyměňte šířku a výšku

Chcete-li změnit orientaci stránky z orientace na výšku na šířku nebo na šířku na výšku, jednoduše prohodíme hodnoty šířky a výšky. Tento krok upraví rozměry stránky.

```csharp
double newHeight = r.Width;
double newWidth = r.Height;
double newLLX = r.LLX;
double newLLY = r.LLY + (r.Height - newHeight);
```

Tento kód zamění výšku a šířku a přemístí levý dolní roh (`LLY`), aby se obsah po otočení úhledně vešel.

## Krok 5: Aktualizujte MediaBox a CropBox

Nyní, když máme novou výšku a šířku, aplikujme změny na stránku`MediaBox` a`CropBox` . The`CropBox` je zásadní, pokud měl původní dokument jednu sadu, aby se zajistilo správné zobrazení celé stránky.

```csharp
page.MediaBox = new Aspose.Pdf.Rectangle(newLLX, newLLY, newLLX + newWidth, newLLY + newHeight);
page.CropBox = new Aspose.Pdf.Rectangle(newLLX, newLLY, newLLX + newWidth, newLLY + newHeight);
```

Tento krok změní velikost stránky na základě nových dimenzí, které jsme právě vypočítali.

## Krok 6: Otočte stránku

Nakonec nastavíme úhel natočení stránky. Aspose.PDF to velmi zjednodušuje. Stránku můžeme otočit o 90 stupňů a posunout se z portrétu na šířku nebo naopak.

```csharp
page.Rotate = Rotation.on90;
```

Tento kód otočí stránku o 90 stupňů a převrátí ji do požadované orientace.

## Krok 7: Uložte výstupní PDF

Po aplikování změn orientace na všechny stránky uložíme upravený dokument do nového souboru. 

```csharp
dataDir = dataDir + "ChangeOrientation_out.pdf";
doc.Save(dataDir);
System.Console.WriteLine("\nPage orientation changed successfully.\nFile saved at " + dataDir);
```

 Ujistěte se, že zadáváte nový název souboru (v tomto případě`ChangeOrientation_out.pdf`) pro uložení výstupu. Tímto způsobem nepřepíšete svůj původní soubor.

### Závěr

tady to máte! Změna orientace stránky souboru PDF pomocí Aspose.PDF for .NET je stejně jednoduchá jako načtení dokumentu, procházení stránek, úprava MediaBoxu a uložení aktualizovaného souboru. Ať už máte co do činění se špatně naskenovaným dokumentem nebo potřebujete otočit stránky tak, aby odpovídaly vašim potřebám formátování, tento podrobný průvodce by vám měl pomoci.

## FAQ

### Mohu otočit konkrétní stránky namísto všech stránek v PDF?  
Ano, smyčku můžete upravit tak, aby cílila na konkrétní stránky pomocí jejich indexu namísto procházení všemi stránkami.

###  Co je`MediaBox`?  
 The`MediaBox` definuje velikost a tvar stránky v souboru PDF. Je to místo, kde je umístěn obsah stránky.

### Funguje Aspose.PDF for .NET s jinými formáty souborů?  
Ano, Aspose.PDF si poradí s řadou formátů souborů, jako je HTML, XML, XPS a další.

### Existuje bezplatná verze Aspose.PDF pro .NET?  
 Ano, můžete začít s a[zkušební verze zdarma](https://releases.aspose.com/) nebo požádat a[dočasná licence](https://purchase.aspose.com/temporary-license/).

### Mohu po uložení změny vrátit zpět?  
Jakmile dokument uložíte, změny jsou trvalé. Ujistěte se, že pracujete na kopii nebo si ponechte zálohu původního souboru.