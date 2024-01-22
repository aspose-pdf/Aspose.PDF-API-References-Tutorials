---
title: Zachovat práva
linktitle: Zachovat práva
second_title: Aspose.PDF pro .NET API Reference
description: Zachovejte práva na formuláře ve svých dokumentech PDF pomocí Aspose.PDF pro .NET.
type: docs
weight: 210
url: /cs/net/programming-with-forms/preserve-rights/
---
V tomto tutoriálu vám ukážeme, jak zachovat práva k formulářům v dokumentu PDF pomocí Aspose.PDF for .NET. Vysvětlíme vám zdrojový kód C# krok za krokem, který vás provede tímto procesem.

## Krok 1: Příprava

Ujistěte se, že jste importovali potřebné knihovny a nastavili cestu k adresáři vašich dokumentů:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Krok 2: Otevřete dokument

 Otevřete zdrojový dokument PDF pomocí a`FileStream` s oprávněním ke čtení a zápisu:

```csharp
FileStream fs = new FileStream(dataDir + "input.pdf", FileMode.Open, FileAccess.ReadWrite);
Aspose.Pdf.Document pdfDocument = new Aspose.Pdf.Document(fs);
```

## Krok 3: Upravte pole formuláře

Projděte všechna pole formuláře v dokumentu a proveďte potřebné změny. V tomto příkladu měníme hodnotu pole formuláře, které má v názvu „A1“:

```csharp
foreach(Field formField in pdfDocument.Form)
{
if (formField.FullName.Contains("A1"))
{
TextBoxField textBoxField = formField as TextBoxField;
textBoxField.Value = "Testing";
}
}
```

## Krok 4: Uložte aktualizovaný dokument

Uložte upravený dokument PDF:

```csharp
pdfDocument.Save();
```

##  Krok 5: Zavřete`FileStream`

 Nezapomeňte zavřít`FileStream` objekt, až budete hotovi:

```csharp
fs. Close();
```

### Ukázkový zdrojový kód pro zachování práv pomocí Aspose.PDF pro .NET 
```csharp
// Cesta k adresáři dokumentů.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Přečtěte si zdrojový formulář PDF pomocí FileAccess of Read and Write.
// Potřebujeme oprávnění ReadWrite, protože po úpravě
// Aktualizovaný obsah musíme uložit do stejného dokumentu/souboru.
FileStream fs = new FileStream(dataDir + "input.pdf", FileMode.Open, FileAccess.ReadWrite);
// Instancia dokumentu instance
Aspose.Pdf.Document pdfDocument = new Aspose.Pdf.Document(fs);
// Získejte hodnoty ze všech polí
foreach (Field formField in pdfDocument.Form)
{
	// Pokud celý název pole obsahuje A1, proveďte operaci
	if (formField.FullName.Contains("A1"))
	{
		// Přenést pole formuláře jako textové pole
		TextBoxField textBoxField = formField as TextBoxField;
		// Upravit hodnotu pole
		textBoxField.Value = "Testing";
	}
}
// Uložte aktualizovaný dokument do save FileStream
pdfDocument.Save();
// Zavřete objekt File Stream
fs.Close();
```

## Závěr

V tomto tutoriálu jsme se naučili, jak zachovat práva k formuláři v dokumentu PDF pomocí Aspose.PDF pro .NET. Pomocí těchto kroků můžete snadno přistupovat k polím formuláře a provádět konkrétní změny při zachování oprávnění k přístupu a zápisu.


### FAQ

#### Otázka: Mohu zachovat práva určitých polí formuláře, aniž bych ovlivnil ostatní v dokumentu PDF?

 Odpověď: Ano, pomocí`FullName` vlastnost polí formuláře, můžete zacílit na konkrétní pole formuláře pro zachování, zatímco ostatní zůstanou nedotčena.

#### Otázka: Mohu zachovat práva na formulář v dokumentu PDF chráněném heslem?

Odpověď: Ano, Aspose.PDF for .NET vám umožňuje zachovat práva k formuláři i v dokumentech PDF chráněných heslem, pokud zadáte správné heslo pro přístup a úpravu souboru.

#### Otázka: Co se stane, když se pokusím upravit pole formuláře bez příslušných přístupových práv?

Odpověď: Pokud se pokusíte upravit pole formuláře bez příslušných přístupových práv, změny se do dokumentu PDF neuloží a můžete obdržet výjimku nebo chybovou zprávu.

#### Otázka: Je Aspose.PDF for .NET kompatibilní se všemi verzemi .NET Framework?

Odpověď: Ano, Aspose.PDF pro .NET je kompatibilní se všemi verzemi .NET Framework, včetně .NET Core a .NET Standard.

#### Otázka: Mohu zachovat práva na formuláře v dokumentu PDF programově v jiných programovacích jazycích kromě C#?

Odpověď: Ano, Aspose.PDF pro .NET podporuje kromě C# různé programovací jazyky, jako je VB.NET a ASP.NET.