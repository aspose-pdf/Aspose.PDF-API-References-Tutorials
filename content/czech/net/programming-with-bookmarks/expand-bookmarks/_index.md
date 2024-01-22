---
title: Rozbalte záložky v souboru PDF
linktitle: Rozbalte záložky v souboru PDF
second_title: Aspose.PDF pro .NET API Reference
description: Snadno rozbalte záložky v souboru PDF pro lepší navigaci s Aspose.PDF pro .NET.
type: docs
weight: 50
url: /cs/net/programming-with-bookmarks/expand-bookmarks/
---
Rozšířením záložek v souboru PDF se ve výchozím nastavení zobrazí všechny otevřené záložky. S Aspose.PDF pro .NET můžete snadno rozšířit záložky pomocí následujícího zdrojového kódu:

## Krok 1: Importujte požadované knihovny

Než začnete, musíte importovat potřebné knihovny pro váš projekt C#. Zde je nezbytná dovozní směrnice:

```csharp
using Aspose.Pdf;
```

## Krok 2: Nastavte cestu ke složce dokumentů

 V tomto kroku musíte zadat cestu ke složce obsahující soubor PDF, jehož záložky chcete rozbalit. Nahradit`"YOUR DOCUMENT DIRECTORY"` následujícím kódu se skutečnou cestou ke složce dokumentů:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Krok 3: Otevřete dokument PDF

Nyní otevřeme dokument PDF, jehož záložky chceme rozšířit pomocí následujícího kódu:

```csharp
Document doc = new Document(dataDir + "input.pdf");
```

## Krok 4: Nastavte režim zobrazení stránky

 tomto kroku nastavíme režim zobrazení stránky tak, aby se ve výchozím nastavení zobrazovaly záložky. Používáme`PageMode` vlastnictvím`doc` objekt pro nastavení požadovaného režimu stránky. Zde je odpovídající kód:

```csharp
doc.PageMode = PageMode.UseOutlines;
```

## Krok 5: Procházejte záložky a rozbalte je

 Nyní projdeme každou položku záložky v kolekci záložek dokumentu a nastavíme stav otevření každé položky na`true` ve výchozím nastavení je rozbalíte. Zde je odpovídající kód:

```csharp
foreach(OutlineItemCollection item in doc.Outlines)
{
     item. Open = true;
}
```

## Krok 6: Uložte aktualizovaný soubor

 Nakonec uložíme aktualizovaný soubor PDF pomocí`Save` metoda`doc` objekt. Zde je odpovídající kód:

```csharp
dataDir = dataDir + "ExpandBookmarks_out.pdf";
doc.Save(dataDir);
```

### Ukázkový zdrojový kód pro Expand Bookmarks pomocí Aspose.PDF pro .NET 
```csharp
// Cesta k adresáři dokumentů.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Otevřete dokument
Document doc = new Document(dataDir + "input.pdf");
// Nastavte režim zobrazení stránky, tj. zobrazení miniatur, zobrazení na celou obrazovku, zobrazení panelu příloh
doc.PageMode = PageMode.UseOutlines;
// Procházejte každou položku Ouline ve sbírce obrysů souboru PDF
foreach (OutlineItemCollection item in doc.Outlines)
{
	// Nastavte otevřený stav položky osnovy
	item.Open = true;
}
dataDir = dataDir + "ExpandBookmarks_out.pdf";
// Uložit výstup
doc.Save(dataDir);
Console.WriteLine("\nBookmarks expanded successfully.\nFile saved at " + dataDir);
```

## Závěr

gratuluji! Nyní máte krok za krokem průvodce vývojem záložek pomocí Aspose.PDF pro .NET. Tento kód můžete použít k zobrazení všech výchozích záložek v dokumentech PDF.

Nezapomeňte se podívat na oficiální dokumentaci Aspose.PDF, kde najdete další informace o pokročilých funkcích manipulace se záložkami.

### Časté dotazy pro rozšíření záložek v souboru PDF

#### Otázka: Co jsou záložky v souboru PDF?

Odpověď: Záložky v souboru PDF jsou navigační pomůcky, které uživatelům umožňují rychle přejít na určité části nebo stránky v dokumentu. Poskytují pohodlný způsob přístupu k různým částem dokumentu.

#### Otázka: Proč bych měl chtít rozbalit záložky v souboru PDF?

Odpověď: Rozšíření záložek může zlepšit uživatelské prostředí tím, že ve výchozím nastavení zobrazí všechny záložky v rozbaleném stavu. To dává uživatelům jasný přehled o struktuře dokumentu a umožňuje jim snadno přecházet do různých sekcí.

#### Otázka: Jak naimportuji potřebné knihovny pro můj projekt C#?

Odpověď: Chcete-li importovat požadovanou knihovnu pro váš projekt C#, použijte následující importní direktivu:

```csharp
using Aspose.Pdf;
```

Tato směrnice vám umožňuje používat třídy a metody poskytované Aspose.PDF pro .NET.

#### Otázka: Jak určím cestu ke složce dokumentů?

 Odpověď: V poskytnutém zdrojovém kódu nahraďte`"YOUR DOCUMENT DIRECTORY"` se skutečnou cestou ke složce obsahující soubor PDF, se kterým chcete pracovat. To zajistí, že kód dokáže najít cílový soubor PDF.

#### Otázka: Jak mohu otevřít dokument PDF, abych rozbalil jeho záložky?

Odpověď: Chcete-li otevřít dokument PDF pro rozbalení záložek, použijte následující kód:

```csharp
Document doc = new Document(dataDir + "input.pdf");
```

 Nahradit`"input.pdf"` se skutečným názvem souboru.

#### Otázka: Jak nastavím režim zobrazení stránky, aby se ve výchozím nastavení zobrazovaly záložky?

A: Chcete-li nastavit režim zobrazení stránky tak, aby se ve výchozím nastavení zobrazovaly záložky, použijte`PageMode` vlastnictvím`doc` objekt:

```csharp
doc.PageMode = PageMode.UseOutlines;
```

#### Otázka: Jak rozbalím všechny záložky v dokumentu PDF?

 A: Chcete-li rozbalit všechny záložky, procházejte každou položku záložky v kolekci obrysů dokumentu a nastavte`Open` majetek do`true`:

```csharp
foreach (OutlineItemCollection item in doc.Outlines)
{
    item.Open = true;
}
```

#### Otázka: Co se stane, pokud má záložka vnořené podřízené záložky?

Odpověď: Pokud má záložka vnořené podřízené záložky, rozbalení nadřazené záložky rozšíří i její podřízené záložky, což poskytne komplexní pohled na strukturu dokumentu.

#### Otázka: Jak uložím aktualizovaný soubor PDF po rozbalení záložek?

Odpověď: Chcete-li uložit aktualizovaný soubor PDF po rozbalení záložek, použijte následující kód:

```csharp
dataDir = dataDir + "ExpandBookmarks_out.pdf";
doc.Save(dataDir);
```

#### Otázka: Mohu přizpůsobit vzhled rozšířených záložek?

Odpověď: I když se tento tutoriál ve výchozím nastavení zaměřuje na rozšiřování záložek, vzhled záložek můžete upravit pomocí dalších funkcí a vlastností Aspose.PDF.