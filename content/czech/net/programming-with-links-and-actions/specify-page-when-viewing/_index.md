---
title: Při prohlížení specifikujte stránku
linktitle: Při prohlížení specifikujte stránku
second_title: Aspose.PDF pro .NET API Reference
description: Naučte se, jak určit stránku pro zobrazení v PDF pomocí Aspose.PDF for .NET. Vylepšete uživatelskou navigaci pomocí tohoto jednoduchého průvodce.
type: docs
weight: 110
url: /cs/net/programming-with-links-and-actions/specify-page-when-viewing/
---
## Zavedení

Chcete vylepšit své aplikace PDF přesměrováním uživatelů na konkrétní stránky při otevření dokumentu? Jste na správném místě! V této příručce se ponoříme do toho nejnutnějšího použití Aspose.PDF pro .NET k určení stránky, která se má zobrazit při otevření PDF. Tato funkce může výrazně zlepšit uživatelskou zkušenost, zvláště když potřebujete upozornit na kritické části dokumentu.

## Předpoklady

Než se ponoříte do kódování, ujistěte se, že máte vše, co potřebujete, abyste mohli začít. Zde je to, co budete potřebovat:

1. Základní znalost .NET: Znalost .NET frameworku je nezbytná. Pokud jste spokojeni s C# a máte základní znalosti o objektově orientovaném programování, jste připraveni!

2.  Aspose.PDF for .NET: Budete muset mít ve svém projektu nainstalovanou knihovnu Aspose.PDF. Pokud jste jej ještě nenainstalovali, můžete si jej stáhnout[zde](https://releases.aspose.com/pdf/net/).

3. Visual Studio: Tento kurz předpokládá, že používáte Visual Studio jako své IDE. Ujistěte se, že jej máte nainstalovaný na vašem počítači.

4. Soubor PDF: Budete potřebovat existující soubor PDF, se kterým budete pracovat. Pokud žádný nemáte, můžete vytvořit vzorový dokument nebo použít libovolný soubor PDF podle svého výběru.

Jakmile budete mít tyto předpoklady na místě, můžeme si vyhrnout rukávy a začít kódovat!

## Importujte balíčky

Nyní, když jsme vše nastaveni, pojďme si nechat importovat potřebné balíčky do našeho projektu. Postupujte takto:

### Spusťte Visual Studio

Otevřete Visual Studio a buď vytvořte nový projekt, nebo načtěte existující, kde chcete implementovat funkci prohlížení stránek PDF.

### Reference Aspose.PDF

Chcete-li používat knihovnu Aspose.PDF, musíte na ni přidat odkaz:

1. Klepněte pravým tlačítkem myši na svůj projekt v Průzkumníku řešení.
2. Vyberte „Spravovat balíčky NuGet“.
3.  Hledat`Aspose.PDF` a nainstalujte balíček.

### Importovat jmenné prostory

Přidejte následující direktivu using v horní části souboru kódu:

```csharp
using System;
using System.IO;
using Aspose.Pdf.Annotations;
using Aspose.Pdf;
```

Nyní jste připraveni začít vytvářet logiku navigace na stránce PDF!

Rozdělme náš úkol do zvládnutelných kroků. Napíšeme kód, který otevře dokument PDF, určí konkrétní stránku, která se má zobrazit při prohlížení, a uloží aktualizovaný dokument. 

## Krok 1: Nastavte adresář dokumentů

Nejprve musíte nastavit cestu k dokumentům:

```csharp
// Cesta k adresáři dokumentů.
string dataDir = "YOUR DOCUMENT DIRECTORY"; // Nahraďte svým adresářem
```

 Tento řádek je v podstatě vaším plánem. Říkáte svému kódu, kde má najít soubor PDF. Nezapomeňte vyměnit`YOUR DOCUMENT DIRECTORY` se skutečnou cestou na vašem počítači.

## Krok 2: Načtěte soubor PDF

Dále načtete soubor PDF do aplikace:

```csharp
// Načtěte soubor PDF
Document doc = new Document(dataDir + "SpecifyPageWhenViewing.pdf");
```

 Zde se děje to, že vytváříte novou instanci a`Document`objekt a zároveň zadejte cestu k vašemu souboru PDF. Můžete si to představit jako otevření knihy, kterou jste právě položili na stůl.

## Krok 3: Otevřete požadovanou stránku

Nyní přejděte na stránku, kterou chcete zobrazit při otevření dokumentu:

```csharp
// Získejte instanci druhé stránky dokumentu
Page page2 = doc.Pages[2]; // Pamatujte, že indexování začíná na 1
```

Zde se dostáváme na druhou stránku vašeho dokumentu. Stojí za zmínku, že číslování stránek v tomto kontextu začíná na 1, takže pokud uvažujete o stránce 2, musíte použít index 2.

## Krok 4: Nastavte faktor zoomu

Můžete upravit úroveň přiblížení stránky, která se zobrazí:

```csharp
// Vytvořte proměnnou pro nastavení faktoru přiblížení cílové stránky
double zoom = 1; // 1 znamená 100% přiblížení
```

Nastavení faktoru přiblížení pomáhá určit, jak velkou část stránky uživatel uvidí ihned po otevření. Hodnota 1 znamená, že stránka se zobrazí při 100% přiblížení, což je obecně dobré výchozí nastavení.

## Krok 5: Vytvořte instanci GoToAction

Pojďme aktivovat navigační funkce:

```csharp
// Vytvořte instanci GoToAction
GoToAction action = new GoToAction(doc.Pages[2]); 
```

 V tomto kroku vytváříte instanci`GoToAction` který v podstatě představuje akci navigace do určitého bodu v PDF – v tomto případě na druhou stránku.

## Krok 6: Definujte cíl

Nyní musíte definovat, kam má akce vést:

```csharp
// Přejděte na stránku 2
action.Destination = new XYZExplicitDestination(page2, 0, page2.Rect.Height, zoom);
```

Tento řádek je jako nastavení cíle GPS pro GoToAction. Říkáte mu, aby přešel na stránku 2 v horní části stránky (výška) a na zadané úrovni přiblížení.

## Krok 7: Nastavte akci Open

Ujistěte se, že tato akce proběhne při otevření dokumentu:

```csharp
// Nastavte akci otevření dokumentu
doc.OpenAction = action;
```

Tímto jste deklarovali, že při otevření vašeho PDF se aktivuje navigační akce, kterou jsme právě definovali. Je to, jako byste položili uvítací podložku na přední dveře vašeho dokumentu.

## Krok 8: Uložte aktualizovaný dokument

Nakonec uložíme dokument s provedenými změnami:

```csharp
// Uložit aktualizovaný dokument
doc.Save(dataDir + "goto2page_out.pdf");
```

Tímto krokem je vaše práce dokončena! Budete mít nový soubor PDF s názvem`goto2page_out.pdf` který se otevře přímo na vámi zadanou stránku.

Tím je kódovací část kompletní! Úspěšně jste naprogramovali Aspose.PDF tak, aby při otevření PDF zobrazil určitou stránku. 

## Závěr

V této příručce jsme postupovali krok za krokem, abychom pochopili, jak specifikovat stránku v souboru PDF pomocí Aspose.PDF for .NET. Tato funkce nejen zlepšuje navigaci vašich uživatelů, ale také zefektivňuje jejich interakci s důležitým obsahem ve vašich dokumentech. Přijetím těchto funkcí vytvoříte uživatelsky přívětivější prostředí, které může odlišit vaše aplikace PDF.

## FAQ

### Co je Aspose.PDF pro .NET?
Aspose.PDF for .NET je knihovna, která umožňuje vývojářům vytvářet, upravovat a spravovat dokumenty PDF v aplikacích .NET.

### Mohu zadat více stránek, které se mají zobrazit?
Ne, dokument můžete nastavit tak, aby se otevřel pouze na jedné zadané stránce. Můžete však vytvořit různé dokumenty pro různé úvodní stránky.

### Co když chci zobrazit stránku s jinou úrovní přiblížení?
 Úroveň přiblížení můžete změnit úpravou`zoom` proměnnou před uložením dokumentu.

### Kde najdu další příklady použití Aspose.PDF?
 Můžete zkontrolovat[dokumentace](https://reference.aspose.com/pdf/net/) pro více příkladů a funkcí.

### Je k dispozici bezplatná zkušební verze pro Aspose.PDF pro .NET?
 Ano! Můžete si stáhnout bezplatnou zkušební verzi Aspose.PDF[zde](https://releases.aspose.com/).