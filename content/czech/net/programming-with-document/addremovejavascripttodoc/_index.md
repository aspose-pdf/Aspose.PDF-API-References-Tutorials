---
title: Přidat Odebrat Javascript do dokumentu PDF
linktitle: Přidat Remove Javascript To Doc
second_title: Aspose.PDF pro .NET API Reference
description: Naučte se, jak přidat a odebrat JavaScript do dokumentu PDF pomocí Aspose.PDF for .NET. Podrobný průvodce s výukovým programem kódu pro skriptování na úrovni dokumentu.
type: docs
weight: 30
url: /cs/net/programming-with-document/addremovejavascripttodoc/
---
## Zavedení

V této příručce si projdeme, jak pomocí Aspose.PDF for .NET vložit JavaScript do souboru PDF a jak jej v případě potřeby odstranit. Na konci tohoto tutoriálu budete mít jasno v tom, jak snadno manipulovat s JavaScriptem v PDF.

## Předpoklady

Než se pustíme do kódu, je potřeba nastavit několik věcí:

1.  Aspose.PDF for .NET: Budete potřebovat knihovnu Aspose.PDF for .NET nainstalovanou ve vašem projektu. Pokud ji ještě nemáte, stáhněte si knihovnu z[Stránka ke stažení Aspose.PDF pro .NET](https://releases.aspose.com/pdf/net/).
2. IDE nebo textový editor: Můžete použít jakékoli IDE kompatibilní s .NET, jako je Visual Studio.
3. Základní znalosti C#: Tento tutoriál předpokládá, že ovládáte C# a znáte práci s PDF.
4. Licence: Ujistěte se, že používáte platnou licenci, abyste se vyhnuli omezením. Dočasnou licenci můžete získat od[zde](https://purchase.aspose.com/temporary-license/).

## Importujte balíčky

Chcete-li začít používat Aspose.PDF pro .NET, budete muset do svého projektu importovat potřebné jmenné prostory. Zde je postup:

```csharp
using System.IO;
using System;
using Aspose.Pdf;
using Aspose.Pdf.Annotations;
using Aspose.Pdf.Text;
using System.Collections;
```

 Tyto dva jmenné prostory jsou nezbytné.`Aspose.Pdf` umožňuje pracovat s dokumenty PDF, přičemž`System.Collections` bude použit pro manipulaci s JavaScriptovými klíči.

Pojďme si celý proces přidávání a odebírání JavaScriptu z PDF rozebrat do snadno srozumitelných kroků.

## Krok 1: Inicializujte nový dokument PDF

První věc, kterou musíte udělat, je vytvořit nový dokument PDF. Tento dokument bude sloužit jako naše prázdné plátno pro přidání JavaScriptu.

```csharp
Document doc = new Document();
doc.Pages.Add();
```

 Zde inicializujeme nový`Document` objekt a přidat k němu prázdnou stránku. Berte to jako základ vašeho PDF.

## Krok 2: Přidejte JavaScript do PDF

Nyní, když máme dokument, je čas přidat do něj JavaScript. JavaScript v souborech PDF lze použít k přidání vlastního chování, jako jsou upozornění nebo ověření formuláře.

```csharp
doc.JavaScript["func1"] = "function func1() { hello(); }";
doc.JavaScript["func2"] = "function func2() { hello(); }";
```

Do tohoto fragmentu kódu přidáváme dvě funkce JavaScriptu (`func1` a`func2` ) do PDF. Tyto funkce mohou provádět různé úkoly v závislosti na vašich potřebách. Zde jen voláme zástupnou funkci nazvanou`hello()`.

## Krok 3: Uložte PDF pomocí JavaScriptu

Jakmile přidáte požadovaný JavaScript, je čas uložit PDF.

```csharp
doc.Save(dataDir + "AddJavascript.pdf");
```

 Tím se dokument uloží s JavaScriptem pod jménem`AddJavascript.pdf` v zadaném adresáři (`dataDir`).

## Krok 4: Načtěte a zobrazte JavaScript ve stávajícím PDF

Řekněme, že potřebujete zkontrolovat nebo upravit funkce JavaScriptu v existujícím PDF. Prvním krokem je načtení souboru PDF a přístup ke klíčům JavaScriptu.

```csharp
Document doc1 = new Document(dataDir + "AddJavascript.pdf");
IList keys = (System.Collections.IList)doc1.JavaScript.Keys;
```

 Načítáme stávající`AddJavascript.pdf` a uložením JavaScriptových klíčů do seznamu. The`Keys` vlastnost vrací názvy všech funkcí JavaScriptu připojených k dokumentu.

## Krok 5: Zobrazení funkcí JavaScriptu

Dále můžeme iterovat funkce JavaScriptu, abychom viděli, co je v dokumentu k dispozici.

```csharp
Console.WriteLine("=============================== ");
foreach (string key in keys)
{
    Console.WriteLine(key + " ==> " + doc1.JavaScript[key]);
}
```

Tím se vytiskne každý název funkce JavaScript a jeho odpovídající kód do konzoly. Je to užitečné, pokud chcete ověřit, jaké funkce jsou aktuálně v dokumentu.

## Krok 6: Odstraňte JavaScript z PDF

 Nyní řekněme, že chcete odstranit konkrétní funkci JavaScriptu, např`func1`. Můžete to udělat takto:

```csharp
doc1.JavaScript.Remove("func1");
Console.WriteLine("Key 'func1' removed ");
```

 The`Remove` metoda převezme název funkce JavaScript jako argument a odstraní jej z dokumentu.

## Krok 7: Ověřte odstranění JavaScriptu

 Po odstranění JavaScriptu můžete znovu vytisknout zbývající funkce, abyste to potvrdili`func1` byl úspěšně smazán.

```csharp
Console.WriteLine("=============================== ");
foreach (string key in keys)
{
    Console.WriteLine(key + " ==> " + doc1.JavaScript[key]);
}
Console.WriteLine("Javascript added/removed successfully.");
```

Tato poslední část kódu zajišťuje, že je vše na svém místě a funkce JavaScriptu jsou správně aktualizovány.

## Závěr

Gratuluji! Právě jste se naučili přidávat a odstraňovat JavaScript z dokumentu PDF pomocí Aspose.PDF pro .NET. Tuto výkonnou funkci lze využít pro různé úkoly, od přidávání dynamických zpráv až po provádění vlastních výpočtů nebo ověřování. Manipulací s JavaScriptem v rámci PDF můžete výrazně zlepšit uživatelský dojem.

## FAQ

### Mohu do jednoho PDF přidat více funkcí JavaScriptu?
 Absolutně! Můžete přidat tolik funkcí JavaScript, kolik potřebujete, pomocí`doc.JavaScript` sbírka.

### Co se stane, když se pokusím odstranit neexistující funkci JavaScriptu?
 Pokud funkce neexistuje,`Remove` metoda nevyhodí chybu, ale také nic neodstraní.

### Je možné spustit JavaScript ihned po otevření PDF?
Ano! JavaScript můžete nakonfigurovat tak, aby se spouštěl u určitých spouštěčů, jako je otevření dokumentu nebo kliknutí na tlačítko.

### Mohu upravit JavaScript poté, co byl přidán do PDF?
Ano, můžete načíst existující PDF, získat přístup k jeho JavaScriptu, upravit kód a dokument znovu uložit.

### Má odstranění JavaScriptu vliv na zbytek obsahu PDF?
Ne, odstranění JavaScriptu ovlivní pouze skript. Obsah PDF zůstává nezměněn.