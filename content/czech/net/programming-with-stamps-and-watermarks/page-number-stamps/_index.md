---
title: Číslo stránky Razítka V Souboru PDF
linktitle: Číslo stránky Razítka V Souboru PDF
second_title: Aspose.PDF pro .NET API Reference
description: Naučte se, jak přidat razítka s čísly stránek do souborů PDF pomocí Aspose.PDF for .NET, prostřednictvím našeho snadno srozumitelného průvodce, doplněného o příklad kódu.
type: docs
weight: 160
url: /cs/net/programming-with-stamps-and-watermarks/page-number-stamps/
---
## Zavedení

Přistihli jste se někdy, že zápasíte s dokumentem PDF a přejete si, aby měl čísla stránek pro snadnější navigaci? Ať už jste student sdílející poznámky, profesionál předkládající zprávy nebo kdokoli, kdo spravuje vícestránkové dokumenty, přidání čísel stránek může skutečně zlepšit přehlednost vašich souborů PDF. Naštěstí s výkonnou knihovnou Aspose.PDF for .NET můžete do dokumentů PDF snadno přidat razítka s čísly stránek. V této příručce vás krok za krokem provedeme celým procesem a zajistíme, že budete vybaveni všemi znalostmi, které potřebujete. Pojďme se ponořit!

## Předpoklady

Než začneme s přidáváním razítek s čísly stránek do vašich dokumentů PDF, ujistěte se, že máte splněny následující předpoklady:

1. Visual Studio: Ujistěte se, že máte v systému nainstalované Visual Studio. Zde budete psát a spouštět svůj kód.
2. .NET Framework: Znalost programování v C# a .NET frameworku je nezbytná, protože Aspose.PDF je navržen pro .NET aplikace.
3.  Knihovna Aspose.PDF: Knihovnu Aspose.PDF si můžete stáhnout z[Aspose PDF Releases](https://releases.aspose.com/pdf/net/). 
4. Základní porozumění souborům PDF: I když nemusíte být odborníkem, základní pochopení toho, jak soubory PDF fungují, vám pomůže lépe porozumět výukovému programu.

Jakmile budete mít tyto předpoklady nastaveny, budete připraveni začít razit čísla stránek!

## Importujte balíčky

Než se ponoříte do kódování, musíte zajistit, aby byly do vašeho projektu importovány potřebné balíčky Aspose.PDF. To je klíčové pro bezproblémové využití funkcí knihovny. Jak na to:

### Vytvořit nový projekt

1. Otevřete Visual Studio.
2.  Klikněte na`File` >`New` >`Project`.
3.  Vyberte šablonu vhodnou pro C# (např. Console Application), pojmenujte ji a klikněte`Create`.

### Přidejte odkaz Aspose.PDF

1. Klepněte pravým tlačítkem myši na název projektu v Průzkumníku řešení.
2.  Klikněte na`Manage NuGet Packages`.
3.  Hledat`Aspose.PDF` a nainstalujte nejnovější verzi.

```csharp
using System.IO;
using System;
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

knihovnou připravenou k provozu se vrhneme do kódování!

Nyní, když je naše prostředí nastaveno, je čas přidat razítka s čísly stránek do souboru PDF. Pro lepší pochopení tento proces rozdělíme do jasných kroků.

## Krok 1: Zadejte adresář dokumentů

Chcete-li začít, musíte určit adresář, kde je umístěn váš soubor PDF. Toto je výchozí bod vašeho projektu.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY"; // Aktualizujte tuto cestu
```

 Vysvětlení: Vyměnit`"YOUR DOCUMENT DIRECTORY"` s cestou vedoucí do adresáře obsahujícího váš soubor PDF. To je důležité, protože říká vašemu kódu, kde najít soubor, se kterým chcete manipulovat.

## Krok 2: Otevřete dokument

Dále otevřeme stávající PDF dokument, do kterého chceme přidat razítka s čísly stránek.

```csharp
Document pdfDocument = new Document(dataDir + "PageNumberStamp.pdf");
```

 Vysvětlení: Zde používáme`Document` třídy poskytované Aspose.PDF k otevření našeho konkrétního souboru PDF. Ujistěte se, že název souboru odpovídá skutečnému souboru, který máte ve svém adresáři.

## Krok 3: Vytvořte razítko s číslem stránky

Nyní přichází ta zábavná část! Pojďme vytvořit razítko s číslem stránky, které přidáme do našeho PDF.

```csharp
PageNumberStamp pageNumberStamp = new PageNumberStamp();
```

 Vysvětlení: The`PageNumberStamp`třídy nám umožní vytvořit razítko, které bude zobrazovat aktuální číslo stránky vzhledem k celkovému počtu stránek v dokumentu.

## Krok 4: Nakonfigurujte razítko

Nyní budete muset nakonfigurovat nastavení razítka. Zde navrhnete, jak razítko vypadá a jak se chová.

```csharp
pageNumberStamp.Background = false;
pageNumberStamp.Format = "Page # of " + pdfDocument.Pages.Count;
pageNumberStamp.BottomMargin = 10;
pageNumberStamp.HorizontalAlignment = HorizontalAlignment.Center;
pageNumberStamp.StartingNumber = 1;
```

Vysvětlení:
- `Background = false`: To znamená, že razítko se objeví v popředí.
- `Format`: Zde nastavujete formát tak, aby se zobrazoval „Stránka X z Y“, kde dynamicky načítáte celkový počet stránek v dokumentu.
- `BottomMargin`: Upraví vzdálenost od spodní části stránky.
- `HorizontalAlignment`: Vodorovně vycentruje razítko.
- `StartingNumber`: Nastavuje počáteční číslo stránky, obvykle od 1.

## Krok 5: Nastavte vlastnosti textu

Dále můžete upravit vzhled textu v razítku.

```csharp
pageNumberStamp.TextState.Font = FontRepository.FindFont("Arial");
pageNumberStamp.TextState.FontSize = 14.0F;
pageNumberStamp.TextState.FontStyle = FontStyles.Bold;
pageNumberStamp.TextState.FontStyle = FontStyles.Italic;
pageNumberStamp.TextState.ForegroundColor = Color.Aqua;
```

Vysvětlení: Tyto atributy konfigurují typ písma, velikost písma, styl (tučné i kurzíva) a barvu textu v razítku, aby byl vizuálně přitažlivý.

## Krok 6: Přidejte razítko na konkrétní stránku

nakonfigurovaným razítkem je čas přidat ho na konkrétní stránku v dokumentu.

```csharp
pdfDocument.Pages[1].AddStamp(pageNumberStamp);
```

 Vysvětlení: Tento řádek přidá razítko na první stránku PDF. Můžete upravit`Pages[1]` index pro další stránky podle potřeby.

## Krok 7: Uložte výstupní dokument

Nakonec upravený dokument PDF uložte, aby byly změny trvalé.

```csharp
dataDir = dataDir + "PageNumberStamp_out.pdf";
pdfDocument.Save(dataDir);
Console.WriteLine("\nPage number stamp added successfully.\nFile saved at " + dataDir);
```

Vysvětlení: Definujete cestu k výstupnímu souboru a ukládáte dokument. Konzole vám dá vědět, že razítko bylo úspěšně přidáno a kde je soubor uložen.

## Závěr

Přidávání razítek s čísly stránek do souborů PDF pomocí Aspose.PDF for .NET je nejen jednoduché, ale také vysoce přizpůsobitelné. Prošli jsme vytvořením razítka s číslem stránky krok za krokem, abychom vám zajistili jasné vodítko. Nyní máte znalosti, jak vylepšit své dokumenty PDF, aby byly uživatelsky přívětivější a profesionálnější. 

## FAQ

### Mohu upravit vzhled čísel stránek?  
Ano! Můžete změnit písmo, velikost, barvu a formátování čísel stránek, jak je ukázáno v průvodci.

### Je Aspose.PDF zdarma k použití?  
 Aspose.PDF nabízí bezplatnou zkušební verzi, ale pro rozsáhlé použití budete potřebovat licenci. Podívejte se na[koupit stránku](https://purchase.aspose.com/buy) pro více informací.

### Co když při implementaci narazím na problémy?  
 Můžete navštívit[Aspose Support Forum](https://forum.aspose.com/c/pdf/10) o pomoc.

### Jak mohu automaticky generovat čísla stránek pro více stránek?  
Kód průvodce automaticky vypočítá celkový počet stránek, takže přizpůsobení pro více stránek je snadné.

### Mohu použít Aspose.PDF v jiných programovacích jazycích?  
Zatímco se tato příručka zaměřuje na .NET, Aspose má knihovny pro Javu, Python a další.