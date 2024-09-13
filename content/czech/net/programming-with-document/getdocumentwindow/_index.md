---
title: Okno Získat dokument
linktitle: Okno Získat dokument
second_title: Aspose.PDF pro .NET API Reference
description: Naučte se používat funkci GetDocumentWindow Aspose.PDF for .NET k načtení informací o vlastnostech okna dokumentu PDF.
type: docs
weight: 170
url: /cs/net/programming-with-document/getdocumentwindow/
---
# Zavedení

Pracujete s PDF a chcete mít větší kontrolu nad tím, jak se zobrazí po otevření? Ať už se jedná o skrytí panelu nabídek nebo změnu velikosti okna tak, aby se vešlo na první stránku, Aspose.PDF for .NET vám poskytuje všechny nástroje, které potřebujete k přizpůsobení chování PDF při otevření v prohlížeči. V tomto tutoriálu rozebereme, jak načíst a manipulovat s nastavením okna dokumentu v Aspose.PDF pro .NET.


# Předpoklady

Než se ponoříte do výukového programu, ujistěte se, že máte splněny následující předpoklady:

- Aspose.PDF for .NET nainstalovaný ve vašem vývojovém prostředí.
  - [Stáhněte si Aspose.PDF pro .NET](https://releases.aspose.com/pdf/net/)
-  Platná licence pro Aspose.PDF, nebo můžete získat a[zkušební verze zdarma](https://releases.aspose.com/) nebo[dočasná licence](https://purchase.aspose.com/temporary-license/).
- Základní znalost .NET a C#.
- Visual Studio nebo jiné vhodné IDE.

# Importujte balíčky

Než začnete psát jakýkoli kód, budete muset naimportovat potřebné balíčky. Otevřete svůj projekt a do horní části souboru C# přidejte následující jmenný prostor:

```csharp
using System.IO;
using System;
using Aspose.Pdf;
```

To vám umožní přístup ke všem třídám a metodám potřebným pro manipulaci s dokumenty PDF pomocí Aspose.PDF pro .NET.

 Nyní si rozeberme proces načítání různých nastavení okna dokumentu. Pro tento příklad použijeme ukázkový soubor PDF s názvem`GetDocumentWindow.pdf`.

## Krok 1: Nastavte cestu k adresáři dokumentu

Nejprve musíme definovat cestu k našemu souboru PDF. Je důležité, abyste měli správnou cestu k souboru, abyste se vyhnuli chybám během provádění.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Tady, vyměňte`"YOUR DOCUMENT DIRECTORY"` se skutečným adresářem, kde se nachází váš soubor PDF. Toto je váš pracovní adresář, odkud načtete dokument PDF.

## Krok 2: Otevřete dokument PDF

Nyní, když je cesta k souboru nastavena, je dalším krokem otevření dokumentu PDF pomocí Aspose.PDF. Tím se dokument načte do paměti, což vám umožní získat jeho vlastnosti.

```csharp
Document pdfDocument = new Document(dataDir + "GetDocumentWindow.pdf");
```

Pomocí tohoto jednoduchého řádku kódu jste úspěšně načetli soubor PDF do`pdfDocument` objekt, který vám nyní umožní přístup ke všem jeho vlastnostem.

## Krok 3: Načtěte stav centrování okna

 Dále zkontrolujeme, zda má být okno dokumentu při otevření vystředěno. Výchozí hodnota pro toto je`false`.

```csharp
Console.WriteLine("CenterWindow : {0}", pdfDocument.CenterWindow);
```

 Pokud je výstup`true`, okno dokumentu se otevře uprostřed obrazovky. V opačném případě se otevře ve výchozí poloze.

## Krok 4: Zkontrolujte směr textu

Dalším zásadním aspektem vzhledu PDF je směr textu, který určuje, zda se text čte zleva doprava (L2R) nebo zprava doleva (R2L). Tyto informace můžete získat pomocí následujícího kódu:

```csharp
Console.WriteLine("Direction : {0}", pdfDocument.Direction);
```

 Výstup bude`L2R` pro text zleva doprava a`R2L` pro text psaný zprava doleva. Toto nastavení je užitečné zejména pro dokumenty v jazycích, jako je arabština nebo hebrejština.

## Krok 5: Zobrazení názvu dokumentu v okně

Další vlastnost umožňuje řídit, zda se má v záhlaví okna zobrazovat název dokumentu nebo název souboru. Ve výchozím nastavení je toto nastaveno`false`, což znamená, že se zobrazí název souboru.

```csharp
Console.WriteLine("DisplayDocTitle : {0}", pdfDocument.DisplayDocTitle);
```

Pokud chcete, aby se místo názvu souboru zobrazoval název dokumentu, musí být toto nastavení povoleno.

## Krok 6: Změňte velikost okna tak, aby se vešlo na první stránku

Někdy můžete chtít, aby se okno dokumentu po otevření automaticky změnilo tak, aby se vešlo na první stránku PDF. Zde je návod, jak zkontrolovat, zda je tato funkce povolena:

```csharp
Console.WriteLine("FitWindow : {0}", pdfDocument.FitWindow);
```

 Ve výchozím nastavení je toto nastaveno`false`, což znamená, že velikost okna zůstane bez ohledu na velikost první stránky.

## Krok 7: Skryjte panel nabídek

Chcete-li dosáhnout cílenějšího čtení, možná budete chtít skrýt lištu nabídky v aplikaci prohlížeče. Toto nastavení můžete získat pomocí následujícího řádku:

```csharp
Console.WriteLine("HideMenuBar : {0}", pdfDocument.HideMenubar);
```

 To se vrátí`true` pokud je panel nabídek skrytý a`false` jinak.

## Krok 8: Skryjte panel nástrojů

Podobně můžete také chtít skrýt panel nástrojů v prohlížeči PDF pro čistší uživatelské rozhraní. Toto nastavení lze získat následovně:

```csharp
Console.WriteLine("HideToolBar : {0}", pdfDocument.HideToolBar);
```

Pokud je toto nastavení povoleno, panel nástrojů se při otevření PDF skryje.

## Krok 9: Skryjte posuvníky a prvky uživatelského rozhraní

Pokud chcete zobrazit pouze obsah stránky bez dalších prvků uživatelského rozhraní, jako jsou posuvníky, toto nastavení řídí toto chování:

```csharp
Console.WriteLine("HideWindowUI : {0}", pdfDocument.HideWindowUI);
```

 Při nastavení na`true`, prohlížeč PDF skryje posuvníky a další prvky uživatelského rozhraní a ponechá pouze obsah dokumentu.

## Krok 10: Nastavte režim stránky mimo celou obrazovku

 Způsob zobrazení dokumentu při ukončení režimu celé obrazovky můžete ovládat pomocí tlačítka`NonFullScreenPageMode` vlastnictví. Toto nastavení je užitečné pro definování způsobu interakce uživatele s dokumentem v režimu jiné než celé obrazovky.

```csharp
Console.WriteLine("NonFullScreenPageMode : {0}", pdfDocument.NonFullScreenPageMode);
```

Výstup lze nastavit na různé režimy, jako jsou miniatury, obrysy nebo panel příloh.

## Krok 11: Definujte rozvržení stránky

Toto nastavení umožňuje řídit způsob rozvržení stránek dokumentu. Můžete se například rozhodnout pro zobrazení jedné stránky nebo souvislé zobrazení sloupců:

```csharp
Console.WriteLine("PageLayout : {0}", pdfDocument.PageLayout);
```

To dává uživatelům flexibilitu při čtení nebo prohlížení obsahu dokumentu.

## Krok 12: Určete režim stránky

 Konečně,`PageMode` vlastnost definuje, jak se má dokument zobrazit při otevření. Možnosti zahrnují zobrazení miniatur, vstup do režimu celé obrazovky nebo zobrazení panelu příloh.

```csharp
Console.WriteLine("PageMode : {0}", pdfDocument.PageMode);
```

V závislosti na vašich potřebách to můžete nastavit na jakýkoli režim, který vyhovuje účelu vašeho PDF.

## Závěr

Jak můžete vidět, Aspose.PDF for .NET poskytuje komplexní nástroje pro manipulaci s tím, jak se vaše dokumenty PDF zobrazují v různých prohlížečích PDF. Ať už chcete skrýt panel nástrojů, vycentrovat okno nebo ovládat směr textu, Aspose.PDF nabízí flexibilitu pro vylepšení uživatelského zážitku ze sledování.

# Nejčastější dotazy

### Mohu přizpůsobit počáteční úroveň přiblížení PDF?
Ano, Aspose.PDF umožňuje nastavit úroveň přiblížení při otevření dokumentu.

### Jak mohu uzamknout velikost okna PDF?
 Můžete nastavit`FitWindow` vlastnost, která zabrání změně velikosti okna.

### Podporuje Aspose.PDF různé režimy čtení?
Ano, podporuje různé režimy, jako je celá obrazovka, miniatury a přílohy.

### Je možné skrýt posuvníky v prohlížeči PDF?
 Rozhodně můžete skrýt posuvníky nastavením`HideWindowUI` majetek do`true`.

### Mohu při otevření vycentrovat okno dokumentu?
 Ano, můžete to ovládat nastavením`CenterWindow` vlastnictví.