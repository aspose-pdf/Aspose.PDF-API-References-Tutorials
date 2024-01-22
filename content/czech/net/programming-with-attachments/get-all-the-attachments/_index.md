---
title: Získejte všechny přílohy v souboru PDF
linktitle: Získejte všechny přílohy v souboru PDF
second_title: Aspose.PDF pro .NET API Reference
description: Naučte se, jak získat všechny přílohy v souboru PDF pomocí Aspose.PDF pro .NET. Návod krok za krokem pro snadnou manipulaci.
type: docs
weight: 40
url: /cs/net/programming-with-attachments/get-all-the-attachments/
---
tomto tutoriálu vás krok za krokem provedeme následujícím zdrojovým kódem C#, abyste získali všechny přílohy v souboru PDF pomocí Aspose.PDF pro .NET.

Než začnete, ujistěte se, že jste nainstalovali knihovnu Aspose.PDF a nastavili své vývojové prostředí. Také mít základní znalosti programování v C#.

### Krok 1: Nastavení adresáře dokumentů

V poskytnutém zdrojovém kódu musíte určit adresář, kde se nachází soubor PDF, ze kterého chcete získat přílohy. Změňte proměnnou "dataDir" na požadovaný adresář.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

### Krok 2: Otevřete existující dokument PDF

Stávající dokument PDF otevřeme pomocí zadané cesty.

```csharp
Document pdfDocument = new Document(dataDir + "GetAlltheAttachments.pdf");
```

### Krok 3: Získání sbírky příloh

Získáme sbírku příloh z dokumentu.

```csharp
EmbeddedFileCollection embeddedFiles = pdfDocument.EmbeddedFiles;
```

### Krok 4: Načtení příloh

Procházíme sbírku, abychom získali všechny přílohy a zobrazili jejich informace. Do jednotlivých souborů ukládáme i přílohy.

```csharp
int count = 1;
foreach(FileSpecification fileSpecification in embeddedFiles)
{
Console.WriteLine("Name: {0}", fileSpecification.Name);
Console.WriteLine("Description: {0}", fileSpecification.Description);
Console.WriteLine("MIME Type: {0}", fileSpecification.MIMEType);

// Zkontrolujte, zda parametry objektu obsahují další informace
if (fileSpecification.Params != null)
{
Console.WriteLine("CheckSum: {0}", fileSpecification.Params.CheckSum);
Console.WriteLine("Creation date: {0}", fileSpecification.Params.CreationDate);
Console.WriteLine("Modified date: {0}", fileSpecification.Params.ModDate);
Console.WriteLine("Size: {0}", fileSpecification.Params.Size);
}

// Načtěte přílohu a uložte ji do souboru
byte[] fileContent = new byte[fileSpecification.Contents.Length];
fileSpecification.Contents.Read(fileContent, 0, fileContent.Length);
FileStream fileStream = new FileStream(dataDir + count + "_out" + ".txt", FileMode.Create);
fileStream.Write(fileContent, 0, fileContent.Length);
fileStream.Close();

count += 1;
}
```


### Ukázkový zdrojový kód pro Get Allthe Attachments pomocí Aspose.PDF pro .NET 

```csharp

// Cesta k adresáři dokumentů.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Otevřete dokument
Document pdfDocument = new Document(dataDir + "GetAlltheAttachments.pdf");
// Získejte sbírku vložených souborů
EmbeddedFileCollection embeddedFiles = pdfDocument.EmbeddedFiles;
// Získejte počet vložených souborů
Console.WriteLine("Total files : {0}", embeddedFiles.Count);
int count = 1;
// Projděte sbírku a získejte všechny přílohy
foreach (FileSpecification fileSpecification in embeddedFiles)
{
	Console.WriteLine("Name: {0}", fileSpecification.Name);
	Console.WriteLine("Description: {0}",
	fileSpecification.Description);
	Console.WriteLine("Mime Type: {0}", fileSpecification.MIMEType);
	//Zkontrolujte, zda objekt parametru obsahuje parametry
	if (fileSpecification.Params != null)
	{
		Console.WriteLine("CheckSum: {0}",
		fileSpecification.Params.CheckSum);
		Console.WriteLine("Creation Date: {0}",
		fileSpecification.Params.CreationDate);
		Console.WriteLine("Modification Date: {0}",
		fileSpecification.Params.ModDate);
		Console.WriteLine("Size: {0}", fileSpecification.Params.Size);
	}
	// Získejte přílohu a zapište ji do souboru nebo streamu
	byte[] fileContent = new byte[fileSpecification.Contents.Length];
	fileSpecification.Contents.Read(fileContent, 0,
	fileContent.Length);
	FileStream fileStream = new FileStream(dataDir + count + "_out" + ".txt",
	FileMode.Create);
	fileStream.Write(fileContent, 0, fileContent.Length);
	fileStream.Close();
	count+=1;
}

```

## Závěr

V tomto tutoriálu jsme vysvětlili, jak získat všechny přílohy ze souboru PDF pomocí Aspose.PDF pro .NET. Nyní můžete tyto znalosti využít k extrahování a manipulaci s přílohami ze souborů PDF.

## Časté dotazy pro získání všech příloh v souboru PDF

#### Otázka: Proč bych potřeboval načíst všechny přílohy z dokumentu PDF?

Odpověď: Načítání příloh vám umožňuje přistupovat a manipulovat s dalšími soubory vloženými do PDF, což může být užitečné pro archivaci, sdílení nebo další zpracování.

#### Otázka: Jaké typy souborů lze připojit k dokumentu PDF?

Odpověď: Dokumenty PDF mohou obsahovat širokou škálu připojených souborů, včetně obrázků, dokumentů, tabulek, zvukových souborů a dalších.

#### Otázka: Jak mi tento návod pomůže získat přílohy z PDF pomocí Aspose.PDF pro .NET?

Odpověď: Tento tutoriál poskytuje podrobné pokyny a zdrojový kód C# pro přístup a načtení všech příloh v dokumentu PDF.

#### Otázka: Mohu pomocí tohoto kurzu načíst konkrétní přílohy místo všech příloh?

Odpověď: Ano, poskytnutý kód můžete upravit pro selektivní načítání příloh na základě vašich požadavků.

#### Otázka: Jaké informace o jednotlivých přílohách mohu získat pomocí tohoto kurzu?

Odpověď: Tento kurz ukazuje, jak načíst a zobrazit podrobnosti, jako je název přílohy, popis, typ MIME, datum vytvoření, datum úpravy a velikost.

#### Otázka: Jak se pomocí tohoto kurzu ukládají načtené přílohy?

Odpověď: Výukový program vás provede uložením každé načtené přílohy jako samostatného souboru do určeného adresáře.

#### Otázka: Mohu tyto znalosti použít k extrahování příloh ze souborů PDF chráněných heslem?

Odpověď: Ano, podobné principy můžete použít pro načítání příloh ze souborů PDF chráněných heslem pomocí Aspose.PDF for .NET.

#### Otázka: Jak Aspose.PDF for .NET usnadňuje načítání příloh?

Odpověď: Aspose.PDF for .NET poskytuje intuitivní rozhraní API, které vám umožňuje snadno přistupovat a manipulovat s přílohami v dokumentech PDF.

#### Otázka: Existují konkrétní scénáře, kdy se doporučuje načítání příloh?

Odpověď: Načítání příloh je užitečné, když potřebujete získat přístup k souborům vloženým do PDF, jako je extrahování obrázků, zvukových souborů nebo dalších dokumentů.