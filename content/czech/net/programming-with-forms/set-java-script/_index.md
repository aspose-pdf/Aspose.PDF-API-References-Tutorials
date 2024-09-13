---
title: Nastavte Java Script
linktitle: Nastavte Java Script
second_title: Aspose.PDF pro .NET API Reference
description: Odemkněte sílu Aspose.PDF pro .NET. Naučte se, jak nastavit JavaScript v polích formuláře pomocí našeho podrobného průvodce.
type: docs
weight: 270
url: /cs/net/programming-with-forms/set-java-script/
---
## Zavedení

Vytváření dynamických a interaktivních PDF může výrazně zlepšit uživatelskou zkušenost, zejména při integraci formulářů a polí do dokumentu. Jedna výkonná knihovna, která to umožňuje, je Aspose.PDF pro .NET. V tomto článku se ponoříme hluboko do nastavení JavaScriptu pro pole formuláře pomocí Aspose.PDF, abychom zajistili, že vaše soubory PDF nejen dobře vypadají, ale také krásně fungují.

## Předpoklady

Než se pustíme do kódování, ujistěte se, že máte vše, co potřebujete, abyste mohli hladce sledovat:

- Visual Studio (nebo jakékoli .NET IDE): Ujistěte se, že je máte nainstalované a správně nastavené.
  
-  Knihovna Aspose.PDF: Budete chtít nejnovější verzi této knihovny. Můžete si jej stáhnout[zde](https://releases.aspose.com/pdf/net/).

- Základní znalost C#: Znalost programování v C# vám pomůže lépe porozumět úryvkům kódu.

-  Soubory PDF: Měli byste mít připravený soubor PDF k testování. V našem příkladu použijeme soubor s názvem`SetJavaScript.pdf`.

- Váš adresář dokumentů: Zjistěte, kde jsou uloženy soubory dokumentů. Na tuto cestu budeme odkazovat v našem kódu.

Až budete mít tyto předpoklady připraveny, jaké nástroje použijeme? Pojďme prozkoumat, co Aspose.PDF umí.

## Importujte balíčky

Chcete-li začít, musíte do projektu C# zahrnout potřebné jmenné prostory. Otevřete svůj hlavní soubor C# a přidejte následující příkazy importu:

```csharp
using System;
using System.IO;
using Aspose.Pdf.Forms;
using Aspose.Pdf.Annotations;
using Aspose.Pdf;
```

Tyto jmenné prostory poskytují přístup k PDF a funkcím souvisejícím s formuláři v knihovně Aspose.PDF.

Jste připraveni vytvořit svůj PDF interaktivní? Popadněte kódovací čepici a pojďme to rozebrat krok za krokem!

## Krok 1: Definujte cestu dokumentu

Nejprve musíme určit umístění našeho souboru PDF. To připravuje půdu pro vše, co následuje. Postup je následující:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Nahradit`"YOUR DOCUMENT DIRECTORY"` se skutečnou cestou, kde se nachází váš soubor PDF. Berte to jako nastavení souřadnic pro mapu pokladu – musíte vědět, kde 'X' označuje místo!

## Krok 2: Načtěte dokument PDF

Jakmile nadefinujeme adresář, načteme náš soubor PDF. 

```csharp
Document doc = new Document(dataDir + "SetJavaScript.pdf");
```

Tento řádek otevře zadaný soubor PDF a připraví jej pro manipulaci. 

## Krok 3: Otevřete pole formuláře

Dále chceme vstoupit do pole formuláře, kde použijeme náš JavaScript. 

```csharp
TextBoxField field = (TextBoxField)doc.Form["textbox1"];
```

 Zde předpokládáme, že ve vašem PDF je textové pole s názvem`textbox1`. Pokud pole s tímto názvem nemáte, můžete jej buď přejmenovat, nebo odpovídajícím způsobem upravit kód. 

## Krok 4: Nastavte akce JavaScriptu

Nyní do našeho textového pole přidáme některé funkce! Nastavíme akce JavaScriptu, které se budou spouštět při určitých událostech. 

```csharp
field.Actions.OnModifyCharacter = new JavascriptAction("AFNumber_Keystroke(2, 1, 1, 0, \"\", true)");
field.Actions.OnFormat = new JavascriptAction("AFNumber_Format(2, 1, 1, 0, \"\", true)");
```

Zde je to, co se děje:
- OnModifyCharacter: Tato funkce JavaScriptu určuje, jak se má pole chovat, když je znak upraven. V tomto případě povoluje dvě desetinné čárky za číslem bez oddělovače.
- OnFormat: Tím je zajištěno, že když uživatel naformátuje číslo, bude se držet stejného pravidla.

Nastavením těchto akcí v podstatě dáváme našemu textovému poli osobnost – jako když ho učíme taneční pohyb!

## Krok 5: Inicializujte hodnotu pole

Dále dáme našemu textovému poli výchozí bod nastavením počáteční hodnoty. 

```csharp
field.Value = "123";
```

Tento řádek nastaví "123" jako předvyplněnou hodnotu v textovém poli. Je to jako příprava jeviště na představení.

## Krok 6: Uložte upravený PDF

Nakonec musíme dokument po provedení všech těchto změn uložit.

```csharp
dataDir = dataDir + "Restricted_out.pdf";
doc.Save(dataDir);
```

 Tím se aktualizuje původní soubor s vašimi změnami a uloží se jako`Restricted_out.pdf`. Berte to jako zpečetění osudu našeho PDF – jakmile je uloženo, je připraveno na svět!

## Krok 7: Potvrďte úspěch

Nakonec zkontrolujeme, zda vše proběhlo hladce. 

```csharp
Console.WriteLine("\nJavaScript on form field setup successfully.\nFile saved at " + dataDir);
```

Spuštění této zprávy vás ujistí, že operace byla úspěšně dokončena, stejně jako přijetí potlesku od publika po skvělém výkonu.

## Závěr

Gratuluji! Úspěšně jste nastavili JavaScript pro pole formuláře v PDF pomocí Aspose.PDF for .NET. Tento výukový program vám nejen poskytl nástroje pro zlepšení interakce s uživatelem, ale také vám umožnil personalizovat si dokumenty jako profesionál. Ať už pracujete s formuláři ve fakturách, průzkumech nebo jiných interaktivních PDF, možnosti jsou skutečně nekonečné.

### FAQ

### Co je Aspose.PDF pro .NET?  
Aspose.PDF je knihovna navržená k vytváření, úpravám a manipulaci se soubory PDF v aplikacích .NET a poskytuje výkonné funkce PDF.

### Potřebuji licenci k používání Aspose.PDF?  
 I když je k dispozici bezplatná zkušební verze, pro plné použití bez omezení je vyžadována licence. Můžete si zakoupit licenci[zde](https://purchase.aspose.com/buy).

### Mohu nastavit JavaScript na jiné typy polí formuláře?  
Absolutně! Aspose.PDF umožňuje akce JavaScriptu v různých polích formuláře, jako jsou zaškrtávací políčka, přepínače a rozevírací seznamy.

### Jak mohu získat podporu pro problémy Aspose.PDF?  
 K podpoře se dostanete přes jejich[forum](https://forum.aspose.com/c/pdf/10) pro jakékoli dotazy nebo problémy.

### Existuje způsob, jak otestovat Aspose.PDF bez nákupu?  
Ano! Aspose poskytuje a[zkušební verze zdarma](https://releases.aspose.com/) k otestování funkcí knihovny, než se zavážete k nákupu.