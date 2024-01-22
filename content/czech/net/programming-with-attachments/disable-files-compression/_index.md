---
title: Zakázat kompresi souborů v souboru PDF
linktitle: Zakázat kompresi souborů v souboru PDF
second_title: Aspose.PDF pro .NET API Reference
description: Naučte se, jak zakázat kompresi souborů v souboru PDF pomocí Aspose.PDF pro .NET. Návod krok za krokem pro snadnou manipulaci.
type: docs
weight: 30
url: /cs/net/programming-with-attachments/disable-files-compression/
---
V tomto tutoriálu vás krok za krokem provedeme následujícím zdrojovým kódem C#, jak zakázat kompresi souborů v PDF pomocí Aspose.PDF for .NET.

Než začnete, ujistěte se, že jste nainstalovali knihovnu Aspose.PDF a nastavili své vývojové prostředí. Také mít základní znalosti programování v C#.

### Krok 1: Nastavení adresáře dokumentů

V poskytnutém zdrojovém kódu musíte zadat adresář, kde se nachází soubor PDF, ve kterém chcete zakázat kompresi souborů. Změňte proměnnou "dataDir" na požadovaný adresář.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

### Krok 2: Otevřete existující dokument PDF

Stávající dokument PDF otevřeme pomocí zadané cesty.

```csharp
Document pdfDocument = new Document(dataDir + "GetAlltheAttachments.pdf");
```

### Krok 3: Nastavení nového souboru pro přidání jako přílohy

Nakonfigurujeme nový soubor, který chceme přidat jako přílohu. V tomto příkladu přidáme textový soubor s názvem "test_out.txt" a popisem "Ukázkový textový soubor".

```csharp
FileSpecification fileSpecification = new FileSpecification("test_out.txt", "Sample text file");
```

### Krok 4: Zakažte kompresi souborů

Kompresi souborů zakážeme nastavením vlastnosti Encoding objektu FileSpecification na FileEncoding.None.

```csharp
fileSpecification.Encoding = FileEncoding.None;
```

### Krok 5: Přidání přílohy do kolekce příloh dokumentu

Přílohu přidáme do sbírky příloh dokumentu.

```csharp
pdfDocument.EmbeddedFiles.Add(fileSpecification);
```

### Krok 6: Uložte nový výstupní soubor

Nakonec výsledný nový PDF soubor s názvem „DisableFilesCompression_out.pdf“ uložíme do zadaného adresáře.

```csharp
pdfDocument.Save(dataDir + "DisableFilesCompression_out.pdf");
```


### Ukázkový zdrojový kód pro Zakázat kompresi souborů pomocí Aspose.PDF pro .NET 

```csharp

// Cesta k adresáři dokumentů.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document pdfDocument = new Document(dataDir + "GetAlltheAttachments.pdf");
// Nastavte nový soubor, který má být přidán jako příloha
FileSpecification fileSpecification = new FileSpecification("test_out.txt", "Sample text file");
// Specifikujte Encoding proparty nastavením na FileEncoding.None
fileSpecification.Encoding = FileEncoding.None;
//Přidejte přílohu do sbírky příloh dokumentu
pdfDocument.EmbeddedFiles.Add(fileSpecification);
dataDir = dataDir + "DisableFilesCompression_out.pdf";
// Uložit nový výstup
pdfDocument.Save(dataDir);
Console.WriteLine("\nFile compression disabled successfully.\nFile saved at " + dataDir);

```

## Závěr

V tomto tutoriálu jsme vysvětlili, jak zakázat kompresi souborů v PDF pomocí Aspose.PDF pro .NET. Nyní můžete tyto znalosti využít k zachování integrity připojených souborů bez komprese.

## Časté dotazy pro zakázání komprese souborů v souboru PDF

#### Otázka: Proč bych měl chtít zakázat kompresi souborů v dokumentu PDF?

Odpověď: Zakázání komprese souborů zajistí, že přiložené soubory v dokumentu PDF zůstanou nekomprimované, čímž se zachová jejich původní kvalita a obsah.

#### Otázka: Jak deaktivace komprese souborů prospěje přílohám PDF?

Odpověď: Zakázání komprese zabrání jakékoli ztrátě dat nebo kvality, ke které může dojít během procesu komprese, a zajistí, že připojené soubory budou zobrazeny tak, jak jsou.

#### Otázka: Mohu pomocí tohoto kurzu selektivně zakázat kompresi pro konkrétní přílohy?

Odpověď: Ano, tento výukový program vás provede deaktivací komprese souborů pro jednotlivé přílohy v dokumentu PDF a poskytuje jemné ovládání.

#### Otázka: Pro jaké typy příloh mohu zakázat kompresi?

Odpověď: Můžete zakázat kompresi pro jakýkoli typ přílohy, jako jsou obrázky, dokumenty, tabulky a další, a zajistit tak zachování jejich integrity.

#### Otázka: Má zakázání komprese vliv na celkovou velikost souboru dokumentu PDF?

Odpověď: Zakázání komprese pro přílohy může vést k mírnému zvětšení celkové velikosti souboru dokumentu PDF, protože nekomprimované soubory zabírají více místa.

#### Otázka: Jak Aspose.PDF for .NET usnadňuje proces deaktivace komprese souborů?

Odpověď: Aspose.PDF for .NET poskytuje snadno použitelné rozhraní API, které vám umožňuje zakázat kompresi souborů pro přílohy, jak je ukázáno v poskytnutém zdrojovém kódu.

#### Otázka: Mohu později v případě potřeby znovu povolit kompresi pro přílohy?

Odpověď: Ano, v případě potřeby můžete upravit nastavení přílohy a znovu povolit kompresi.

#### Otázka: Co se stane, když otevřu PDF na zařízení nebo softwaru, který podporuje kompresi?

Odpověď: Pokud otevřete PDF na zařízení nebo softwaru, který podporuje kompresi, příloha se může zobrazit nekomprimovaná, což může mít vliv na velikost souboru a výkon vykreslování.

#### Otázka: Existují konkrétní scénáře, kdy se doporučuje deaktivovat kompresi?

Odpověď: Zakázání komprese se doporučuje pro přílohy, kde je prioritou zachování původní kvality a integrity dat, jako jsou obrázky ve vysokém rozlišení nebo citlivé dokumenty.