---
title: Získejte pole z oblasti v souboru PDF
linktitle: Získejte pole z oblasti v souboru PDF
second_title: Aspose.PDF pro .NET API Reference
description: Pomocí Aspose.PDF for .NET můžete snadno získat pole z konkrétní oblasti v souboru PDF.
type: docs
weight: 130
url: /cs/net/programming-with-forms/get-fields-from-region/
---
V tomto tutoriálu vám ukážeme, jak získat pole konkrétní oblasti v souboru PDF pomocí Aspose.PDF pro .NET. Vysvětlíme vám zdrojový kód C# krok za krokem, který vás provede tímto procesem.

## Krok 1: Příprava

Ujistěte se, že jste importovali potřebné knihovny a nastavili cestu k adresáři vašich dokumentů:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Krok 2: Otevřete soubor PDF

Otevřete soubor PDF:

```csharp
Aspose.Pdf.Document doc = new Aspose.Pdf.Document(dataDir + "GetFieldsFromRegion.pdf");
```

## Krok 3: Vytvořte obdélníkový objekt pro ohraničení oblasti

Vytvořte obdélníkový objekt pro vazbu oblasti, kde chcete získat pole:

```csharp
Aspose.Pdf.Rectangle rectangle = new Aspose.Pdf.Rectangle(35, 30, 500, 500);
```

## Krok 4: Získejte formulář PDF

Získejte dokument ve formátu PDF:

```csharp
Aspose.Pdf.Forms.Form form = doc.Form;
```

## Krok 5: Získejte pole v obdélníkové oblasti

Získejte pole umístěná v zadané obdélníkové oblasti:

```csharp
Aspose.Pdf.Forms.Field[] fields = form.GetFieldsInRect(rectangle);
```

## Krok 6: Zobrazte názvy polí a hodnoty

Iterujte výsledná pole a zobrazte jejich názvy a hodnoty:

```csharp
foreach (Field field in fields)
{
Console.Out.WriteLine("Field name: " + field.FullName + "-" + "Field value: " + field.Value);
}
```

### Ukázkový zdrojový kód pro Get Fields From Region pomocí Aspose.PDF pro .NET 
```csharp
// Cesta k adresáři dokumentů.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Otevřít soubor pdf
Aspose.Pdf.Document doc = new Aspose.Pdf.Document(dataDir + "GetFieldsFromRegion.pdf");
// Vytvořte obdélníkový objekt, abyste získali pole v této oblasti
Aspose.Pdf.Rectangle rectangle = new Aspose.Pdf.Rectangle(35, 30, 500, 500);
// Získejte formulář PDF
Aspose.Pdf.Forms.Form form = doc.Form;
// Získejte pole v obdélníkové oblasti
Aspose.Pdf.Forms.Field[] fields = form.GetFieldsInRect(rectangle);
// Zobrazit názvy polí a hodnoty
foreach (Field field in fields)
{
	// Zobrazit vlastnosti umístění obrázku pro všechna umístění
	Console.Out.WriteLine("Field Name: " + field.FullName + "-" + "Field Value: " + field.Value);
}
```

## Závěr

tomto tutoriálu jsme se naučili, jak získat pole konkrétní oblasti v dokumentu PDF pomocí Aspose.PDF pro .NET. Podle těchto kroků můžete snadno extrahovat pole umístěná v dané obdélníkové oblasti vašeho dokumentu PDF pomocí Aspose.PDF.

### FAQ

#### Otázka: Mohu tuto metodu použít k získání polí z nepravoúhlé oblasti v dokumentu PDF?

 Odpověď: Ne, poskytnutá metoda`GetFieldsInRect` je speciálně navržen pro načítání polí umístěných v obdélníkové oblasti v dokumentu PDF. Pokud potřebujete extrahovat pole z nepravoúhlé oblasti, budete muset implementovat vlastní logiku k identifikaci a extrahování polí na základě jiných kritérií, jako jsou souřadnice pole nebo názvy.

#### Otázka: Jak mohu upravit velikost nebo polohu obdélníku, abych získal pole z jiné oblasti?

 A: Chcete-li získat pole z jiné oblasti, můžete upravit`Aspose.Pdf.Rectangle` parametry objektu použité k definování ohraničujícího obdélníku. The`Rectangle` konstruktor přebírá čtyři parametry:`x`, `y`, `width` a`height`které představují souřadnice levého horního rohu a rozměry obdélníku. Úpravou těchto parametrů se změní oblast, ze které se pole extrahují.

#### Otázka: Co když v zadané obdélníkové oblasti nejsou žádná pole?

 Odpověď: Pokud v zadané obdélníkové oblasti nejsou žádná pole,`GetFieldsInRect` metoda vrátí prázdné pole. Můžete zkontrolovat délku pole, abyste zjistili, zda jsou v oblasti nějaká pole.

#### Otázka: Mohu získat pole z překrývajících se oblastí v dokumentu PDF?

 Odpověď: Ano, můžete získat pole z překrývajících se oblastí v dokumentu PDF vytvořením více`Aspose.Pdf.Rectangle` objektů a volání`GetFieldsInRect` metoda pro každou z nich. Překrývající se oblasti budou řešeny nezávisle a pro každou oblast obdržíte samostatné pole polí.

#### Otázka: Je možné získat pole z konkrétní stránky nebo více stránek v dokumentu PDF?

Odpověď: Ano, můžete získat pole z určité stránky nebo více stránek v dokumentu PDF. Chcete-li toho dosáhnout, můžete načíst dokument PDF a otevřít požadované stránky pomocí`doc.Pages` kolekce a poté aplikujte`GetFieldsInRect` na konkrétní oblast každé stránky.