---
title: Načíst pole formuláře v pořadí karet
linktitle: Načíst pole formuláře v pořadí karet
second_title: Aspose.PDF pro .NET API Reference
description: Naučte se, jak načíst pole formuláře v pořadí tabulátorů pomocí Aspose.PDF pro .NET.
type: docs
weight: 240
url: /cs/net/programming-with-forms/retrieve-form-field-in-tab-order/
---
Při práci s dokumenty PDF v C# pomocí Aspose.PDF for .NET můžete narazit na scénář, kdy potřebujete načíst pole formuláře v určitém pořadí karet. To může být užitečné, když chcete provádět operace s poli formuláře na základě jejich pořadí karet. V tomto tutoriálu vás krok za krokem provedeme, jak načíst pole formuláře v pořadí tabulátorů pomocí Aspose.PDF pro .NET.

## Požadavky

Než začneme, ujistěte se, že máte následující předpoklady:

- Visual Studio nainstalované ve vašem systému
- Nainstalovaná knihovna Aspose.PDF pro .NET

Nyní se pojďme ponořit do kroků k načtení polí formuláře v pořadí karet.

## Krok 1: Nastavení adresáře dokumentů

 Chcete-li začít, musíte nastavit adresář dokumentů, kde je umístěn váš dokument PDF. Můžete to provést zadáním cesty k adresáři v`dataDir` variabilní.

```csharp
// Cesta k adresáři dokumentů.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Nahradit`"YOUR DOCUMENT DIRECTORY"` se skutečnou cestou k vašemu adresáři dokumentů.

## Krok 2: Načtení dokumentu PDF

 V tomto kroku načteme dokument PDF pomocí Aspose.PDF for .NET. The`Document` třída poskytuje možnost načítat a manipulovat s dokumenty PDF.

```csharp
Document doc = new Document(dataDir + "Test2.pdf");
```

 Zde,`"Test2.pdf"`je název dokumentu PDF, který chcete načíst. Ujistěte se, že se dokument nachází v zadaném adresáři dokumentů.

## Krok 3: Načtení polí formuláře v pořadí karet

 Abychom mohli načíst pole formuláře v pořadí tabulátorů, musíme mít přístup k`FieldsInTabOrder` majetek z`Page` třída. Tato vlastnost vrací seznam polí formuláře seřazených podle pořadí karet.

```csharp
Page page = doc.Pages[1];
IList<Field> fields = page.FieldsInTabOrder;
string s = "";
foreach (Field field in fields)
{
     s += field. PartialName;
}
```

Ve výše uvedeném úryvku kódu načteme pole formuláře z druhé stránky (`doc.Pages[1]` ) a iterujte každé pole, abyste zřetězili jejich částečná jména do`s` variabilní. Tento fragment kódu můžete upravit podle svých konkrétních požadavků.

## Krok 4: Úprava pořadí karet

 Chcete-li upravit pořadí polí formuláře, můžete tak učinit přístupem k`TabOrder` vlastnost každého pole a přiřazení nové hodnoty pořadí karet. Zde je příklad:

```csharp
(doc.Form[3] as Field).TabOrder = 1;
(doc.Form[1] as Field).TabOrder = 2;
(doc.Form[2] as Field).TabOrder = 3;
```

Ve výše uvedeném fragmentu kódu přiřadíme nové hodnoty pořadí karet třem polím formuláře (`doc.Form[3]`, `doc.Form[1]` a`doc.Form[2]`). Upravte indexy polí a hodnoty pořadí tabulek podle vašich specifických požadavků.

## Krok 5: Uložení upraveného dokumentu

 Po úpravě pořadí polí formuláře je třeba upravený dokument uložit. Můžete to udělat pomocí`Save` metoda`Document` třída.

```csharp
doc.Save(dataDir + "39522_out.pdf");
```

 Zde,`"39522_out.pdf"` je název výstupního souboru, kam bude uložen upravený dokument. Zadejte požadovaný název a umístění výstupního souboru.

### Ukázkový zdrojový kód pro Retrieve Form Field In Tab Order pomocí Aspose.PDF for .NET 
```csharp
// Cesta k adresáři dokumentů.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Test2.pdf");
Page page = doc.Pages[1];
IList<Field> fields = page.FieldsInTabOrder;
string s = "";
foreach (Field field in fields)
{
	s += field.PartialName;
}
(doc.Form[3] as Field).TabOrder = 1;
(doc.Form[1] as Field).TabOrder = 2;
(doc.Form[2] as Field).TabOrder = 3;
doc.Save(dataDir + "39522_out.pdf");
Document doc1 = new Document(dataDir + "39522_out.pdf");
s = "";
foreach (Field field in doc1.Pages[1].FieldsInTabOrder)
{
	s += field.PartialName;
}
string index = "";
foreach (Field field in doc1.Form)
{
	index += field.TabOrder;
}
```

## Závěr

V tomto tutoriálu jsme se naučili, jak načíst pole formuláře v pořadí tabulátorů pomocí Aspose.PDF pro .NET. Probrali jsme kroky spojené s načítáním dokumentu PDF, načítáním polí formuláře v pořadí podle tabulátoru, úpravou pořadí tabulátorů a ukládáním upraveného dokumentu. Pomocí těchto kroků můžete efektivně pracovat s poli formuláře a přizpůsobit jejich pořadí karet podle vašich požadavků.


### FAQ

#### Otázka: Jak mohu použít načtená pole formuláře v kódu C# pro další zpracování?

 Odpověď: Načtená pole formuláře můžete použít v kódu C# přístupem k jejich vlastnostem, jako je např`Value`, `Name`, `Rect`atd. Tyto vlastnosti umožňují číst a upravovat data pole formuláře podle potřeby.

#### Otázka: Mohu načíst pole formuláře ze všech stránek dokumentu PDF v pořadí tabulátorů?

 Odpověď: Ano, pole formuláře můžete načíst ze všech stránek dokumentu PDF procházením každé stránky a přístupem k`FieldsInTabOrder` vlastnost, jak je uvedeno v tutoriálu. Tím získáte pole formuláře seřazená podle pořadí karet na všech stránkách.

#### Otázka: Je možné načíst pouze určité typy polí formulářů, jako jsou textová pole nebo zaškrtávací políčka, v pořadí karet?

Odpověď: Ano, můžete filtrovat pole formuláře na základě jejich typů, jako jsou textová pole nebo zaškrtávací políčka, poté, co je načtete v pořadí karet. Pomocí podmíněných příkazů můžete zkontrolovat typ každého pole formuláře a podle toho je zpracovat.

#### Otázka: Mohu načíst pole formuláře na základě jejich názvů namísto pořadí tabulek?

 Odpověď: Ano, pole formuláře můžete načíst na základě jejich názvů pomocí`doc.Form` kolekce a zadáním názvu pole jako indexu. Například,`doc.Form["fieldName"]`načte pole formuláře se zadaným názvem.

#### Otázka: Podporuje Aspose.PDF for .NET práci se šifrovanými dokumenty PDF?

Odpověď: Ano, Aspose.PDF for .NET poskytuje podporu pro práci se šifrovanými dokumenty PDF. Šifrované soubory PDF můžete načítat a manipulovat s nimi pomocí vhodných parametrů hesla.