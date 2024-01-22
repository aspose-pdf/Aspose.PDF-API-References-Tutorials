---
title: Extrahujte informace o podpisu
linktitle: Extrahujte informace o podpisu
second_title: Aspose.PDF pro .NET API Reference
description: Extrahování informací o podpisu pomocí Aspose.PDF pro .NET.
type: docs
weight: 80
url: /cs/net/programming-with-security-and-signatures/extract-signature-info/
---
Proces extrahování informací o podpisu z dokumentu PDF může být docela užitečný v různých situacích. Ať už potřebujete ověřit pravost podepsaného dokumentu nebo analyzovat certifikát použitý pro podpis, knihovna Aspose.PDF for .NET poskytuje pohodlné řešení. V tomto tutoriálu vás provedeme procesem extrahování informací o podpisu krok za krokem pomocí dodaného zdrojového kódu C#.

## Požadavky

Než začneme, ujistěte se, že máte splněny následující předpoklady:

1. Základní znalost programovacího jazyka C#.
2. Knihovna Aspose.PDF for .NET nainstalovaná ve vašem systému.
3. Platný dokument PDF s jedním nebo více podpisovými poli.

Nyní se pojďme ponořit do detailů implementace.

## Krok 1: Import požadovaných knihoven

 Chcete-li začít, musíte do svého projektu C# importovat potřebné knihovny. V tomto případě musíme importovat`Aspose.Pdf` a`System.IO` jmenné prostory. To lze provést přidáním následujícího kódu na začátek souboru C#:

```csharp
using Aspose.Pdf;
using System.IO;
```

## Krok 2: Nastavení cesty dokumentu

Dále musíte nastavit cestu k dokumentu PDF, ze kterého chcete extrahovat informace o podpisu. Nahradit`"YOUR DOCUMENTS DIRECTORY"` v následujícím fragmentu kódu se skutečnou cestou k vašemu dokumentu:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
string input = dataDir + "ExtractSignatureInfo.pdf";
```

## Krok 3: Extrahování informací o podpisu

Nyní přejdeme k hlavní části kódu, kde extrahujeme informace o podpisu z dokumentu PDF. Iterujeme každé pole ve formuláři dokumentu a zkontrolujeme, zda se jedná o pole podpisu. Pokud je pole podpisu nalezeno, pokračujeme v extrahování certifikátu. Přidejte následující fragment kódu:

```csharp
using (Document pdfDocument = new Document(input))
{
     foreach(Field field in pdfDocument.Form)
     {
         SignatureField sf = field as SignatureField;
         if (sf != null)
         {
             // Rozbalte certifikát
             Stream cerStream = sf.ExtractCertificate();
             if (cerStream != null)
             {
                 using (cerStream)
                 {
                     byte[] bytes = new byte[cerStream.Length];
                     using (FileStream fs = new FileStream(dataDir + @"input.cer", FileMode.CreateNew))
                     {
                         cerStream.Read(bytes, 0, bytes.Length);
                         fs.Write(bytes, 0, bytes.Length);
                     }
                 }
             }
         }
     }
}
```

## Krok 4: Extrahování certifikátu

V tomto kroku vyjmeme certifikát z pole podpisu a uložíme jej jako soubor. Extrahovaný certifikát lze dále analyzovat nebo použít pro účely ověření. Níže uvedený fragment kódu ukazuje proces extrakce a ukládání:

```csharp
Stream cerStream = sf.ExtractCertificate();
if (cerStream != null)
{
     using (cerStream)
     {
         byte[] bytes = new byte[cerStream.Length];
         using (FileStream fs = new FileStream(dataDir + @"input.cer", FileMode.CreateNew))
         {
             cerStream.Read(bytes, 0, bytes.Length);
             fs.Write(bytes, 0, bytes.Length);
         }
     }
}
```

## Krok 5

: Uložení certifikátu

Nakonec rozbalený certifikát uložíme jako soubor. V tomto příkladu je certifikát uložen pod názvem "input.cer" v určeném adresáři. Kód můžete upravit tak, aby vyhovoval vašim požadavkům. Zde je fragment kódu pro uložení certifikátu:

```csharp
using (FileStream fs = new FileStream(dataDir + @"input.cer", FileMode.CreateNew))
{
     fs.Write(bytes, 0, bytes.Length);
}
```

A je to! Úspěšně jste extrahovali informace o podpisu pomocí Aspose.PDF pro .NET. Neváhejte a integrujte tento kód do svých vlastních aplikací nebo jej upravte podle svých potřeb.

### Ukázkový zdrojový kód pro extrahování informací o podpisu pomocí Aspose.PDF pro .NET 
```csharp
try
{
	// Cesta k adresáři dokumentů.
	string dataDir = "YOUR DOCUMENTS DIRECTORY";
	string input = dataDir + "ExtractSignatureInfo.pdf";
	using (Document pdfDocument = new Document(input))
	{
		foreach (Field field in pdfDocument.Form)
		{
			SignatureField sf = field as SignatureField;
			if (sf != null)
			{
				Stream cerStream = sf.ExtractCertificate();
				if (cerStream != null)
				{
					using (cerStream)
					{
						byte[] bytes = new byte[cerStream.Length];
						using (FileStream fs = new FileStream(dataDir + @"input.cer", FileMode.CreateNew))
						{
							cerStream.Read(bytes, 0, bytes.Length);
							fs.Write(bytes, 0, bytes.Length);
						}
					}
				}
			}
		}
	}
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## Závěr

V tomto tutoriálu jsme prošli podrobným průvodcem, jak extrahovat informace o podpisu z dokumentu PDF pomocí knihovny Aspose.PDF for .NET. Probrali jsme proces importu požadovaných knihoven, nastavení cesty k dokumentu, extrahování informací o podpisu, extrahování certifikátu a jeho uložení do souboru. Pomocí těchto kroků můžete snadno získat podrobnosti podpisu a pracovat s nimi podle potřeby.

### FAQ

#### Otázka: Proč bych potřeboval extrahovat informace o podpisu z dokumentu PDF?

Odpověď: Extrahování informací o podpisu z dokumentu PDF je užitečné pro ověření pravosti podepsaného dokumentu a analýzu certifikátu použitého pro podpis. Tento proces pomáhá zajistit integritu podepsaného obsahu a může být nezbytný pro právní a bezpečnostní účely.

#### Otázka: Co je Aspose.PDF pro .NET?

A: Aspose.PDF for .NET je knihovna, která umožňuje vývojářům pracovat s dokumenty PDF v aplikacích .NET. Poskytuje širokou škálu funkcí pro vytváření, úpravy a interakci se soubory PDF programově.

#### Otázka: Jaké jsou předpoklady pro extrahování informací o podpisu pomocí Aspose.PDF pro .NET?

Odpověď: K extrahování informací o podpisu potřebujete základní znalost programovacího jazyka C#, knihovny Aspose.PDF for .NET nainstalované ve vašem systému a platný dokument PDF obsahující jedno nebo více podpisových polí.

#### Otázka: Jak naimportuji požadované knihovny pro proces extrakce?

Odpověď: Potřebné knihovny můžete importovat přidáním souboru`using` směrnice pro`Aspose.Pdf` a`System.IO` na začátku vašeho souboru C#. Tyto direktivy vám umožňují používat třídy a metody požadované pro extrakci informací o podpisu.

#### Otázka: Jak specifikuji dokument PDF pro extrahování informací o podpisu?

 Odpověď: Cestu k dokumentu PDF můžete nastavit nahrazením`"YOUR DOCUMENTS DIRECTORY"` se skutečnou cestou k vašemu dokumentu v poskytnutém fragmentu kódu. Tato cesta se používá k načtení dokumentu PDF, ze kterého chcete extrahovat informace o podpisu.

#### Otázka: Jaký je proces extrahování informací o podpisu z dokumentu PDF?

Odpověď: Proces extrakce zahrnuje opakování polí formuláře dokumentu PDF, kontrolu, zda je každé pole polem podpisu, a pokud ano, extrahování přidruženého certifikátu. Extrahovaný certifikát lze uložit jako soubor pro další analýzu nebo ověření.

#### Otázka: Jak je certifikát extrahován z pole podpisu?

A: Certifikát je extrahován z pole podpisu pomocí`ExtractCertificate()` metoda poskytovaná společností`SignatureField` třídy v Aspose.PDF pro .NET. Tato metoda vrací proud obsahující data certifikátu.

#### Otázka: Jak uložím extrahovaný certifikát jako soubor?

 Odpověď: Extrahovaný certifikát můžete uložit jako soubor přečtením toku certifikátů a zapsáním jeho obsahu do souboru pomocí`FileStream` třída. Kód uvedený v tutoriálu tento proces demonstruje.

#### Otázka: Mohu použít tento extrahovaný certifikát pro ověření podpisu?

Odpověď: Ano, extrahovaný certifikát lze použít k ověření podpisu. Můžete analyzovat podrobnosti certifikátu a ověřit jeho pravost, abyste zajistili integritu podepsaného dokumentu.

#### Otázka: Jak mohu tento kód integrovat do svých vlastních aplikací?

Odpověď: Poskytnutý kód můžete integrovat do svých vlastních aplikací C# podle podrobného průvodce. Podle potřeby upravte cesty a názvy souborů a začleňte kód do svých stávajících projektů.

#### Otázka: Existují další funkce v Aspose.PDF pro .NET související se správou podpisů?

Odpověď: Ano, Aspose.PDF pro .NET poskytuje řadu funkcí pro práci s digitálními podpisy, včetně podepisování dokumentů, ověřování podpisů a přidávání informací o časovém razítku. Další podrobnosti o těchto funkcích naleznete v oficiální dokumentaci.

#### Otázka: Kde najdu další zdroje pro použití Aspose.PDF pro .NET?

 Odpověď: Další informace, návody a zdroje o používání Aspose.PDF pro .NET[Aspose.PDF pro .NET](https://reference.aspose.com/pdf/net/).

#### Otázka: Je možné extrahovat podpisy ze zašifrovaných dokumentů PDF?

Odpověď: Schopnost extrahovat podpisy ze zašifrovaných dokumentů PDF může záviset na nastavení šifrování a oprávněních dokumentu. Možná se budete muset ujistit, že máte potřebná oprávnění pro přístup a extrahování informací o podpisu.

#### Otázka: Mohu extrahovat více podpisů z jednoho dokumentu PDF?

Odpověď: Ano, poskytnutý kód můžete upravit tak, aby procházel všemi poli podpisu v dokumentu PDF a extrahoval informace o podpisu z každého z nich. To vám umožní extrahovat informace o více podpisech přítomných v dokumentu.

#### Otázka: Jaké jsou praktické případy použití pro extrakci informací o podpisu?

Odpověď: Některé praktické případy použití pro extrakci informací o podpisu zahrnují ověřování pravosti digitálně podepsaných dokumentů, analýzu podrobností certifikátu pro účely shody a udržování záznamů podpisů a signatářů pro účely auditu.

#### Otázka: Existují nějaké právní aspekty při extrahování informací o podpisu?

Odpověď: Získávání informací o podpisu může mít právní důsledky, zejména při manipulaci s právně závaznými dokumenty. Ujistěte se, že dodržujete příslušné předpisy a zákony týkající se elektronických podpisů a pravosti dokumentů ve vaší jurisdikci.