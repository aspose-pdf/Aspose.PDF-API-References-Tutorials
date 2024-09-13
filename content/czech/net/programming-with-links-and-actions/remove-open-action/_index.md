---
title: Odebrat otevřenou akci
linktitle: Odebrat otevřenou akci
second_title: Aspose.PDF pro .NET API Reference
description: Snadno odstraňte otevřené akce z PDF pomocí Aspose.PDF pro .NET! Jednoduchý návod s podrobnými pokyny pro efektivní správu PDF.
type: docs
weight: 80
url: /cs/net/programming-with-links-and-actions/remove-open-action/
---
## Zavedení

V tomto tutoriálu si projdeme jednoduché kroky potřebné k odstranění otevřené akce z dokumentu PDF pomocí Aspose.PDF for .NET. Budete se divit, jak je to přímočaré – a na konci se budete cítit jako profesionál s PDF! Pojďme se ponořit přímo do předpokladů.

## Předpoklady

Než začneme, budete potřebovat několik věcí:

1. Základní porozumění C#: Znalost programovacího jazyka C# vám pomůže snadno procházet úryvky kódu.
2. Visual Studio: Ujistěte se, že máte nainstalované Visual Studio. Je to nejběžnější IDE pro vývoj .NET.
3.  Aspose.PDF pro .NET: Tuto knihovnu musíte mít po ruce. Můžete si jej stáhnout[zde](https://releases.aspose.com/pdf/net/). 
4. .NET Framework: Ujistěte se, že jste svůj projekt nastavili tak, aby používal .NET Framework (doporučuje se verze 4.0 nebo novější).
5. Soubor PDF s otevřenými akcemi: Toto je dokument, na kterém budeme pracovat. Můžete si jej vytvořit nebo si stáhnout ukázku pro procvičení.

Jakmile budete mít tyto základny pokryté, jste připraveni skočit přímo do toho! Nyní importujme potřebné balíčky, abychom mohli začít kódovat.

## Importujte balíčky

Chcete-li začít s kódováním, budete muset do projektu zahrnout některé základní balíčky. Takto nastavíte základy pro operace, které budete se soubory PDF provádět. Zde je to, co musíte udělat:

### Otevřete svůj projekt

Otevřete projekt .NET v sadě Visual Studio, kde chcete provádět operace.

### Přidejte knihovnu Aspose.PDF

Do projektu budete muset přidat knihovnu Aspose.PDF. Můžete to udělat snadno pomocí NuGet Package Manager. Stačí vyhledat Aspose.PDF a nainstalovat nejnovější stabilní verzi.

### Zahrňte nezbytné jmenné prostory

V horní části souboru C# musíte importovat jmenný prostor Aspose.PDF. Díky tomu bude váš kód vědět, že budete pracovat s funkcemi PDF nabízenými Aspose. Zde je to, co byste měli přidat:

```csharp
using System.IO;
using Aspose.Pdf;
using System;
```

Nyní, když máte vše nastaveno a připraveno, pojďme se pustit do hrubšího odstranění otevřených akcí z dokumentu PDF.

## Krok 1: Definujte adresář dokumentů

V první řadě musíte určit, kde se váš soubor PDF nachází. Berte to jako nastavení vašeho pracovního prostoru. Jak na to:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Nezapomeňte vyměnit`"YOUR DOCUMENT DIRECTORY"` se skutečnou cestou, kde je váš PDF uložen. Například:

```csharp
string dataDir = "C:\\Documents\\";
```

Tím se připraví půda pro několik dalších kroků. 

## Krok 2: Otevřete dokument PDF

Dále načteme dokument PDF do vaší aplikace. Tady se začíná dít kouzlo! Použijte následující kód:

```csharp
Document document = new Document(dataDir + "RemoveOpenAction.pdf");
```

 V tomto kroku říkáme naší aplikaci, aby vytvořila nový`Document` objekt, který představuje soubor PDF s názvem „RemoveOpenAction.pdf“. Ujistěte se, že tento soubor existuje ve vámi určeném adresáři!

## Krok 3: Odstraňte akci Open

Nyní přichází ta vzrušující část – odstranění otevřené akce z dokumentu. Můžete to udělat v jediném řádku kódu. Zde je postup:

```csharp
document.OpenAction = null;
```

Tento řádek v podstatě říká dokumentu, že již není otevřená sada akcí. Je to jako dát vašemu PDF nový začátek těsně před jeho uložením!

## Krok 4: Uložte aktualizovaný dokument

Po odstranění akce otevření budete chtít uložit změny. Zde je návod, jak uložit aktualizovaný dokument zpět do vašeho adresáře:

```csharp
dataDir = dataDir + "RemoveOpenAction_out.pdf";
document.Save(dataDir);
```

Tento kód uloží upravený dokument jako "RemoveOpenAction_out.pdf" ve stejném adresáři. V podstatě jste vytvořili novou verzi svého PDF, která je bez nežádoucích akcí!

## Krok 5: Potvrďte úspěch

Chcete-li dát všem vědět, že operace byla úspěšná, můžete vytisknout potvrzovací zprávu na konzoli. Stačí přidat následující řádek, abyste to pěkně uzavřeli:

```csharp
Console.WriteLine("\nOpen action removed successfully.\nFile saved at " + dataDir);
```

Tento krok není nezbytně nutný, ale je hezké mít po provedení operací uzavření. Dokázali jste to! Úspěšně jste odebrali akci otevření z dokumentu PDF.

## Závěr

tady to máme! S pouhými několika řádky kódu C# a silou Aspose.PDF pro .NET jste zjednodušili své PDF odstraněním otevřené akce. Správa dokumentů nemusí být tak složitá, jak se zdá. Zvládnutím nástrojů, jako je Aspose, můžete převzít kontrolu nad svými soubory PDF a přimět je, aby pracovaly tvrději za vás, nikoli naopak.

## FAQ

### Co jsou akce otevření v souborech PDF?
Akce otevření jsou příkazy provedené při otevření PDF, jako je přehrání zvuku nebo přechod na webovou stránku.

### Musím za Aspose.PDF pro .NET platit?
 Aspose nabízí bezplatnou zkušební verzi. Můžete si jej stáhnout[zde](https://releases.aspose.com/).

### Mohu z PDF odebrat více otevřených akcí?
 Ano, můžete nastavit`OpenAction` majetek do`null` k odstranění všech otevřených akcí.

### Jak otestuji, zda odstranění otevřené akce fungovalo?
Otevřete uložený soubor PDF a zkontrolujte, zda nedošlo k nějaké dříve nastavené akci. Pokud ne, uspěli jste!

### Kde najdu podporu, když narazím na problém?
 Navštivte fórum Aspose, kde najdete podporu ohledně problémů souvisejících s PDF[zde](https://forum.aspose.com/c/pdf/10).