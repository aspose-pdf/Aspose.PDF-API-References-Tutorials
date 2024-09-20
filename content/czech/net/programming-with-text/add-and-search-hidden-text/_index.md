---
title: Přidat a hledat skrytý text v souboru PDF
linktitle: Přidat a hledat skrytý text v souboru PDF
second_title: Aspose.PDF pro .NET API Reference
description: Naučte se přidávat a vyhledávat skrytý text v dokumentech PDF pomocí Aspose.PDF for .NET. Podrobný průvodce včetně příkladů kódu.
type: docs
weight: 20
url: /cs/net/programming-with-text/add-and-search-hidden-text/
---
## Zavedení

V tomto tutoriálu vás provedeme podrobným průvodcem, jak přidat a prohledat skrytý text v souboru PDF pomocí Aspose.PDF for .NET. Ať už jste zkušený vývojář nebo nováček, který chce zlepšit své programovací dovednosti, tento článek vám poskytne informace, které potřebujete k začlenění funkcí skrytého textu do vašich aplikací.

## Předpoklady

Než se ponoříte do kódovací části, existuje několik předpokladů, o které se musíte postarat:

### Kontrolní seznam požadavků
- Visual Studio: Ujistěte se, že máte nainstalované Visual Studio. Tento kurz předpokládá, že používáte .NET Framework.
-  Aspose.PDF pro .NET: Musíte mít knihovnu Aspose.PDF pro .NET. Můžete si jej stáhnout[zde](https://releases.aspose.com/pdf/net/).
- Základní znalost C#: Znalost programování v C# vám pomůže lépe porozumět úryvkům kódu.

## Importujte balíčky

Než budete moci začít s kódem, musíte se ujistit, že importujete potřebné jmenné prostory Aspose.PDF. Jak na to:

### Nastavte svůj projekt
1. Otevřete Visual Studio a vytvořte nový projekt C# nebo použijte existující.
2.  Nainstalujte Aspose.PDF přidáním balíčku NuGet. Můžete to udělat tak, že přejdete do Správce balíčků NuGet a vyhledáte`Aspose.PDF`. 
3.  Případně si můžete knihovnu stáhnout přímo z[zde](https://releases.aspose.com/pdf/net/) a přidejte jej jako referenci do svého projektu.

### Importujte požadované jmenné prostory
V horní části souboru C# importujte následující jmenné prostory:

```csharp
using Aspose.Pdf.Text;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

Tento krok je zásadní, protože tyto jmenné prostory obsahují třídy a metody nezbytné pro manipulaci s dokumenty PDF.

## Vytvoření dokumentu PDF se skrytým textem

Nyní, když jste nastavili, pojďme si projít kroky k vytvoření dokumentu PDF, který obsahuje viditelný i neviditelný text.

### Krok 1: Definujte adresář dokumentů
Nejprve budete chtít nastavit cestu, kam se PDF uloží. Tady začíná kouzlo!

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY"; // Změňte to na svůj adresář
```

 Tento řádek definuje, kam bude uložen váš vygenerovaný PDF. Nezapomeňte vyměnit`YOUR DOCUMENT DIRECTORY` s vaší skutečnou cestou.

### Krok 2: Vytvořte dokument PDF
Dále vytvoříme nový dokument PDF a přidáme do něj stránky.

```csharp
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
Page page = doc.Pages.Add();
```

Zde inicializujeme nový dokument a přidáváme stránku, kam umístíme naše textové fragmenty.

### Krok 3: Přidejte viditelný a skrytý text
Nyní do našeho PDF přidáme viditelný i neviditelný text.

```csharp
TextFragment frag1 = new TextFragment("This is common text.");
TextFragment frag2 = new TextFragment("This is invisible text.");
```

 V tomto úryvku`frag1` budou viditelné, zatímco`frag2` bude příště nastaveno na neviditelné.

### Krok 4: Nastavte Text na Neviditelný
 Chcete-li vytvořit text`frag2` neviditelný, jednoduše jej upravíte`TextState`.

```csharp
frag2.TextState.Invisible = true;
```

 Nastavením této vlastnosti bude jakýkoli text spojený s`frag2` nebude vykreslen při prohlížení PDF.

### Krok 5: Přidejte na stránku textové fragmenty
Nakonec přidáme tyto textové fragmenty na stránku a uložíme PDF.

```csharp
page.Paragraphs.Add(frag1);
page.Paragraphs.Add(frag2);
doc.Save(dataDir + "39400_out.pdf");
doc.Dispose();
```

Tato část kódu přidává na stránku naše textové fragmenty. Poté dokument řádně uložíme a zlikvidujeme.

## Hledání skrytého textu v PDF

Nyní, když jsme vytvořili naše PDF s viditelným i skrytým textem, jak tento skrytý text hledat? Pojďme to rozebrat.

### Krok 1: Načtěte dokument PDF
Chcete-li hledat text v PDF, musíme nejprve načíst dokument, který jsme právě vytvořili.

```csharp
doc = new Aspose.Pdf.Document(dataDir + "39400_out.pdf");
```

### Krok 2: Vytvořte absorbér textových fragmentů
 budeme používat`TextFragmentAbsorber` zachytit všechny textové fragmenty v PDF.

```csharp
TextFragmentAbsorber absorber = new TextFragmentAbsorber();
absorber.Visit(doc.Pages[1]);
```

Zde určíme, že chceme absorbovat všechny fragmenty textu z první stránky.

### Krok 3: Iterujte fragmenty
Nyní můžeme procházet shromážděné fragmenty textu, abychom zjistili, které z nich jsou viditelné a které jsou skryté.

```csharp
foreach (TextFragment fragment in absorber.TextFragments)
{
    Console.WriteLine("Text '{0}' on pos {1} invisibility: {2}",
        fragment.Text, fragment.Position.ToString(), fragment.TextState.Invisible);
}
```

 Tato smyčka kontroluje každý textový fragment a vytiskne jeho obsah spolu s jeho pozicí a stavem viditelnosti. Li`fragment.TextState.Invisible` je nastaveno na true, znamená to, že text je skrytý!

### Krok 4: Zlikvidujte dokument
Nakonec nezapomeňte dokument po dokončení znovu zlikvidovat.

```csharp
doc.Dispose();
```

## Závěr

V tomto tutoriálu jsme prošli vzrušujícím procesem přidávání a vyhledávání skrytého textu v souborech PDF pomocí Aspose.PDF pro .NET. Naučili jsme se, jak vytvořit dokument PDF s viditelným i skrytým textem, a také jak tento skrytý text programově vyhledávat. Tato schopnost může být neuvěřitelně užitečná v různých aplikacích, ať už potřebujete ukládat důvěrné informace nebo poskytnout jedinečný uživatelský zážitek ve svých dokumentech.

Jak se blíže seznámíte s ASPose.PDF, možnosti se stanou nekonečnými. Pokračujte v experimentování a posouvejte hranice toho, čeho můžete s dokumenty PDF dosáhnout!

## FAQ

### Dokáže Aspose.PDF zpracovat šifrované soubory PDF?  
Ano, Aspose.PDF podporuje šifrování a dešifrování dokumentů PDF. Své PDF můžete snadno zabezpečit hesly.

### Je k dispozici zkušební verze pro Aspose.PDF?  
 Absolutně! Bezplatnou zkušební verzi si můžete stáhnout z[zde](https://releases.aspose.com/).

### Jaké programovací jazyky podporuje Aspose.PDF?  
Aspose.PDF poskytuje podporu pro více jazyků, včetně C#, Java a Python.

### Kde najdu dokumentaci k Aspose.PDF?  
 Máte přístup k dokumentaci[zde](https://reference.aspose.com/pdf/net/).

### Jak mohu získat podporu, pokud narazím na problémy?  
 Pro podporu můžete navštívit fóra Aspose[zde](https://forum.aspose.com/c/pdf/10).