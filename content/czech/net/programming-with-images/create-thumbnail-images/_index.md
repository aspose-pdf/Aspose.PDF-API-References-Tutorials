---
title: Vytvářejte obrázky miniatur v souboru PDF
linktitle: Vytvářejte obrázky miniatur v souboru PDF
second_title: Aspose.PDF pro .NET API Reference
description: Snadno vytvořte miniaturu obrázku v souboru PDF pomocí Aspose.PDF pro .NET.
type: docs
weight: 100
url: /cs/net/programming-with-images/create-thumbnail-images/
---
Tato příručka vás krok za krokem provede vytvořením miniatury v souboru PDF pomocí Aspose.PDF pro .NET. Ujistěte se, že jste již nastavili své prostředí a postupujte podle následujících kroků:

## Krok 1: Definujte adresář dokumentů

Než začnete, ujistěte se, že jste nastavili správný adresář pro dokumenty. Nahradit`"YOUR DOCUMENT DIRECTORY"` v kódu s cestou k adresáři obsahujícímu vaše soubory PDF.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Krok 2: Získejte názvy všech souborů PDF v adresáři

 V tomto kroku získáme názvy všech souborů PDF přítomných v zadaném adresáři pomocí C#`Directory`třída. Soubory budou uloženy v poli řetězců.

```csharp
string[] fileEntries = Directory.GetFiles(dataDir, "*.pdf");
```

## Krok 3: Procházejte všechny soubory PDF a jejich stránky

 V tomto kroku projdeme všechny soubory PDF a jejich stránky, abychom vytvořili miniatury obrázků. Použijeme a`for` smyčka pro iteraci všech souborů.

```csharp
for (int counter = 0; counter < fileEntries.Length; counter++)
{
     // Otevřete dokument PDF
     Document pdfDocument = new Document(fileEntries[counter]);
    
     // Projděte všechny stránky dokumentu
     for (int pageCount = 1; pageCount <= pdfDocument.Pages.Count; pageCount++)
     {
         // Vytvořte stream pro uložení miniatury
         using (FileStream imageStream = new FileStream(dataDir + "\\Thumbnails" + counter.ToString() + "_" + pageCount + ".jpg", FileMode.Create))
         {
             //Vytvořte objekt rozlišení
             Resolution resolution = new Resolution(300);
            
             // Vytvořte zařízení JPEG se zadanými atributy
             JpegDevice jpegDevice = new JpegDevice(45, 59, resolution, 100);
            
             // Převeďte konkrétní stránku a uložte obrázek do streamu
             jpegDevice.Process(pdfDocument.Pages[pageCount], imageStream);
            
             // Zavřete stream
             imageStream.Close();
         }
     }
}
```

### Ukázkový zdrojový kód pro Create Thumbnail Images pomocí Aspose.PDF for .NET 
```csharp
// Cesta k adresáři dokumentů.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Načíst názvy všech souborů PDF v určitém adresáři
string[] fileEntries = Directory.GetFiles(dataDir, "*.pdf");
// Iterujte všechny položky souborů v poli
for (int counter = 0; counter < fileEntries.Length; counter++)
{
	//Otevřete dokument
	Document pdfDocument = new Document(fileEntries[counter]);
	for (int pageCount = 1; pageCount <= pdfDocument.Pages.Count; pageCount++)
	{
		using (FileStream imageStream = new FileStream(dataDir + "\\Thumbanils" + counter.ToString() + "_" + pageCount + ".jpg", FileMode.Create))
		{
			//Vytvořit objekt rozlišení
			Resolution resolution = new Resolution(300);
			//JpegDevice jpegDevice = nové JpegDevice(500, 700, rozlišení, 100);
			JpegDevice jpegDevice = new JpegDevice(45, 59, resolution, 100);
			//Převeďte konkrétní stránku a uložte obrázek do streamu
			jpegDevice.Process(pdfDocument.Pages[pageCount], imageStream);
			//Zavřít stream
			imageStream.Close();
		}
	}
}
System.Console.WriteLine("PDF pages are converted to thumbnails successfully!");
```

## Závěr

gratuluji! Úspěšně jste vytvořili miniatury obrázků ze souborů PDF pomocí Aspose.PDF pro .NET. Miniatury obrázků se ukládají do určeného adresáře. Nyní můžete tyto miniatury použít k zobrazení vizuálního náhledu souborů PDF.

### Časté dotazy pro vytváření náhledů obrázků v souboru PDF

#### Otázka: Jaký je účel vytváření miniatur obrázků ze souborů PDF pomocí Aspose.PDF pro .NET?

Odpověď: Vytváření miniatur obrázků ze souborů PDF umožňuje generovat malé vizuální náhledy každé stránky v PDF, což může být užitečné pro rychlé zobrazení náhledu a procházení obsahu.

#### Otázka: Jak Aspose.PDF for .NET usnadňuje vytváření miniatur obrázků ze souborů PDF?

 Odpověď: Aspose.PDF for .NET poskytuje postupný proces otevírání dokumentů PDF, procházení jejich stránek, vytváření miniatur a jejich ukládání do určeného adresáře pomocí`JpegDevice` třída.

#### Otázka: Proč je důležité definovat adresář dokumentu před zahájením vytváření miniatur?

Odpověď: Určení adresáře dokumentu zajistí správné umístění souborů PDF a uložení výsledných miniatur do požadované výstupní cesty.

####  Otázka: Jak to`Document` class in Aspose.PDF for .NET help in the creation of thumbnail images?

 A:`Document` třída umožňuje otevírat a manipulovat s dokumenty PDF. V tomto případě se používá k načtení souborů PDF, ze kterých budou vytvořeny náhledy obrázků.

####  Otázka: Jakou roli hraje`JpegDevice` class play in the creation of thumbnail images?

 A:`JpegDevice` třída je zodpovědná za převod stránek PDF na obrázky JPEG, které se používají jako miniatury. Umožňuje zadat atributy, jako je šířka, výška, rozlišení a kvalita.

#### Otázka: Jak je každá stránka dokumentu PDF převedena na samostatnou miniaturu?

 A: Vnořený`for` smyčka se používá k iteraci každým souborem PDF a jeho stránkami. Pro každou stránku je vytvořeno zařízení JPEG se zadanými atributy a`Process` metoda se používá k převedení stránky na miniaturu a její uložení do streamu.

#### Otázka: Mohu během procesu vytváření upravit rozlišení nebo kvalitu výsledných miniatur?

Odpověď: Ano, můžete upravit atributy, jako je rozlišení, šířka, výška a kvalita, konfigurací`JpegDevice` objekt před převodem každé stránky.

#### Otázka: Jak mohu využít vygenerované miniatury ve svých projektech nebo aplikacích po procesu vytváření?

Odpověď: Výsledné miniaturní obrázky lze použít k poskytnutí vizuálního náhledu souborů PDF, což uživatelům pomůže rychle identifikovat a procházet obsah.

#### : Existuje nějaké omezení počtu miniatur obrázků, které lze vygenerovat ze souborů PDF pomocí tohoto procesu vytváření?

Odpověď: Počet vygenerovaných miniatur závisí na počtu stránek v každém dokumentu PDF. Každá stránka bude převedena na samostatnou miniaturu.