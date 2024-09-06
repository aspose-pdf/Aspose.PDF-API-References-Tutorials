---
title: Určete zalomení řádku v souboru PDF
linktitle: Určete zalomení řádku v souboru PDF
second_title: Aspose.PDF pro .NET API Reference
description: Naučte se, jak určit konce řádků v souboru PDF pomocí Aspose.PDF for .NET.
type: docs
weight: 130
url: /cs/net/programming-with-text/determine-line-break/
---
Tento tutoriál vás provede procesem určování zalomení řádků v souboru PDF pomocí Aspose.PDF pro .NET. Poskytnutý zdrojový kód C# ukazuje potřebné kroky.

## Požadavky
Než začnete, ujistěte se, že máte následující:

- Visual Studio nebo jakýkoli jiný kompilátor C# nainstalovaný na vašem počítači.
- Aspose.PDF pro knihovnu .NET. Můžete si jej stáhnout z oficiálního webu Aspose nebo jej nainstalovat pomocí správce balíčků, jako je NuGet.

## Krok 1: Nastavte projekt
1. Vytvořte nový projekt C# ve vámi preferovaném vývojovém prostředí.
2. Přidejte odkaz na knihovnu Aspose.PDF for .NET.

## Krok 2: Importujte požadované jmenné prostory
Do souboru kódu, kde chcete určit konce řádků, přidejte následující pomocí direktiv v horní části souboru:

```csharp
using Aspose.Pdf;
using System.IO;
```

## Krok 3: Nastavte adresář dokumentů
 V kódu vyhledejte řádek, který říká`string dataDir = "YOUR DOCUMENT DIRECTORY";` a nahradit`"YOUR DOCUMENT DIRECTORY"` s cestou k adresáři, kde jsou uloženy vaše dokumenty.

## Krok 4: Vytvořte novou instanci dokumentu
 Vytvořte nový`Document` objekt přidáním následujícího řádku kódu:

```csharp
Document doc = new Document();
```

## Krok 5: Přidejte do dokumentu stránku
 Přidejte do dokumentu novou stránku pomocí`Add` metoda`Pages`sbírka. V poskytnutém kódu je nová stránka přiřazena k proměnné`page`.

```csharp
Page page = doc.Pages.Add();
```

## Krok 6: Přidejte textové fragmenty se zalomením řádků
Vytvořte smyčku pro přidání více fragmentů textu na stránku, z nichž každý obsahuje odstavec se zalomením řádků.

```csharp
for (int i = 0; i < 4; i++)
{
     TextFragment text = new TextFragment("Lorem ipsum \r\ndolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
     text.TextState.FontSize = 20;
     page.Paragraphs.Add(text);
}
```

## Krok 7: Uložte dokument PDF a extrahujte informace o zalomení řádku
 Uložte dokument PDF pomocí`Save` metoda`Document` objekt. Poté extrahujte informace o zalomení řádku pomocí`GetNotifications` metodu požadované stránky.

```csharp
doc.Save(dataDir + "DetermineLineBreak_out.pdf");
string notifications = doc.Pages[1].GetNotifications();
File.WriteAllText(dataDir + "notifications_out.txt", notifications);
```

### Ukázka zdrojového kódu pro Determine Line Break pomocí Aspose.PDF pro .NET 
```csharp
// Cesta k adresáři dokumentů.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
Page page = doc.Pages.Add();
for (int i = 0; i < 4; i++)
{
	TextFragment text = new TextFragment("Lorem ipsum \r\ndolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.");
	text.TextState.FontSize = 20;
	page.Paragraphs.Add(text);
}
doc.Save(dataDir + "DetermineLineBreak_out.pdf");
string notifications = doc.Pages[1].GetNotifications();
File.WriteAllText(dataDir + "notifications_out.txt", notifications);
```

## Závěr
Úspěšně jste určili zalomení řádků v dokumentu PDF pomocí Aspose.PDF for .NET. Informace o zalomení řádku byly extrahovány a uloženy do textového souboru.

### FAQ

#### Otázka: Co je hlavním zaměřením tohoto tutoriálu?

Odpověď: Tento tutoriál je zaměřen na to, aby vás provedl procesem určování zalomení řádků v souboru PDF pomocí knihovny Aspose.PDF for .NET. Poskytnutý zdrojový kód C# demonstruje nezbytné kroky k dosažení tohoto cíle.

#### Otázka: Které jmenné prostory bych měl importovat pro tento výukový program?

Odpověď: Do souboru kódu, kde chcete určit konce řádků, importujte na začátek souboru následující jmenné prostory:

```csharp
using Aspose.Pdf;
using System.IO;
```

#### Otázka: Jak určím adresář dokumentů?

 A: V kódu najděte řádek`string dataDir = "YOUR DOCUMENT DIRECTORY";` a nahradit`"YOUR DOCUMENT DIRECTORY"` se skutečnou cestou k vašemu adresáři dokumentů.

#### Otázka: Jak vytvořím novou instanci dokumentu?

 Odpověď: V kroku 4 vytvoříte instanci nového`Document` objekt pomocí poskytnutého kódu.

#### Otázka: Jak přidám stránku do dokumentu?

 Odpověď: V kroku 5 přidáte do dokumentu novou stránku pomocí`Add` metoda`Pages` sbírka.

#### Otázka: Jak přidám fragmenty textu se zalomením řádků?

Odpověď: V kroku 6 vytvoříte smyčku pro přidání více fragmentů textu na stránku, z nichž každý obsahuje odstavec se zalomením řádků.

#### Otázka: Jak uložím dokument PDF a extrahuji informace o zalomení řádku?

 Odpověď: V kroku 7 uložíte dokument PDF pomocí`Save` metoda`Document` objekt. Poté extrahujete informace o zalomení řádku pomocí`GetNotifications`metodu požadované stránky a uložte ji do textového souboru.

#### Otázka: Jaký je účel extrahovaných informací o zalomení řádku?

Odpověď: Extrahované informace o zalomení řádků poskytují podrobnosti o zalomení řádků a upozorněních v dokumentu PDF. To může být užitečné pro analýzu a pochopení struktury textu a odstavců v dokumentu.

#### Otázka: Jaký je hlavní poznatek z tohoto tutoriálu?

Odpověď: Podle tohoto kurzu jste se naučili, jak určit konce řádků v dokumentu PDF pomocí Aspose.PDF for .NET. Tyto znalosti můžete použít k extrahování a analýze informací o zalomení řádků ze souborů PDF programově.