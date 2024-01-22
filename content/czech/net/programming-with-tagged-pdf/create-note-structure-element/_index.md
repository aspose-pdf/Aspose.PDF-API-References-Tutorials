---
title: Vytvořit prvek struktury poznámky
linktitle: Vytvořit prvek struktury poznámky
second_title: Aspose.PDF pro .NET API Reference
description: Podrobný průvodce vytvářením strukturovaných položek poznámek v dokumentu PDF pomocí Aspose.PDF pro .NET.
type: docs
weight: 30
url: /cs/net/programming-with-tagged-pdf/create-note-structure-element/
---
V tomto tutoriálu vám poskytneme podrobný návod, jak vytvořit prvek struktury poznámky v dokumentu PDF pomocí Aspose.PDF pro .NET. Aspose.PDF je výkonná knihovna, která vám umožňuje programově vytvářet, manipulovat a převádět dokumenty PDF. Pomocí funkcí struktury označeného obsahu Aspose.PDF můžete do svého dokumentu PDF přidat strukturované poznámky.

## Předpoklady

Než začnete, ujistěte se, že máte splněny následující předpoklady:

1. Visual Studio nainstalované s .NET frameworkem.
2. Knihovna Aspose.PDF pro .NET.

## Krok 1: Nastavení projektu

Chcete-li začít, vytvořte nový projekt v sadě Visual Studio a přidejte odkaz na knihovnu Aspose.PDF for .NET. Knihovnu si můžete stáhnout z oficiálních stránek Aspose a nainstalovat ji do svého počítače.

## Krok 2: Importujte potřebné jmenné prostory

Do souboru s kódem C# importujte jmenné prostory potřebné pro přístup ke třídám a metodám poskytovaným Aspose.PDF:

```csharp
using System;
using Aspose.Pdf;
using Aspose.Pdf.Tagged;
```

## Krok 3: Vytvoření dokumentu PDF a strukturovaných prvků poznámky

K vytvoření dokumentu PDF a přidání strukturovaných prvků poznámky použijte následující kód:

```csharp
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";
string outFile = dataDir + "45929_doc.pdf";
string logFile = dataDir + "45929_log.xml";

Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Sample Grade Items");
taggedContent.SetLanguage("fr-FR");

ParagraphElement paragraph = taggedContent.CreateParagraphElement();
taggedContent.RootElement.AppendChild(paragraph);

NoteElement note1 = taggedContent.CreateNoteElement();
paragraph. AppendChild(note1);
note1.SetText("Note with automatically generated ID. ");

NoteElement note2 = taggedContent.CreateNoteElement();
paragraph. AppendChild(note2);
note2.SetText("Note with ID = 'note_002'.");
note2.SetId("note_002");

NoteElement note3 = taggedContent.CreateNoteElement();
paragraph. AppendChild(note3);
note3.SetText("Note with ID = 'note_003'.");
note3.SetId("note_003");
```

Tento kód vytvoří prázdný dokument PDF a přidá do odstavce strukturované prvky poznámky. Každá poznámka je vytvořena pomocí metod poskytovaných Aspose.PDF.

## Krok 4: Uložení dokumentu PDF

K uložení dokumentu PDF použijte následující kód:

```csharp
document. Save(outFile);
```

Tento kód uloží dokument PDF se strukturovanými prvky poznámky do určeného souboru.

### Ukázkový zdrojový kód pro Create Note Structure Element pomocí Aspose.PDF for .NET 

```csharp
// Cesta k adresáři dokumentů.
string dataDir = "YOUR DOCUMENT DIRECTORY";
string outFile = dataDir + "45929_doc.pdf";
string logFile = dataDir + "45929_log.xml";
// Vytvořit dokument Pdf
Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Sample of Note Elements");
taggedContent.SetLanguage("en-US");
// Přidat prvek odstavce
ParagraphElement paragraph = taggedContent.CreateParagraphElement();
taggedContent.RootElement.AppendChild(paragraph);
// Přidat NoteElement
NoteElement note1 = taggedContent.CreateNoteElement();
paragraph.AppendChild(note1);
note1.SetText("Note with auto generate ID. ");
// Přidat NoteElement
NoteElement note2 = taggedContent.CreateNoteElement();
paragraph.AppendChild(note2);
note2.SetText("Note with ID = 'note_002'. ");
note2.SetId("note_002");
// Přidat NoteElement
NoteElement note3 = taggedContent.CreateNoteElement();
paragraph.AppendChild(note3);
note3.SetText("Note with ID = 'note_003'. ");
note3.SetId("note_003");
// Musí vyvolat výjimku – Aspose.Pdf.Tagged.TaggedException : Prvek struktury s ID='note_002' již existuje
//note3.SetId("note_002");
// Výsledný dokument není v souladu s PDF/UA, pokud ClearId() použitý pro prvek struktury poznámky
//note3.ClearId();
// Uložit označený dokument PDF
document.Save(outFile);
// Kontrola shody s PDF/UA
document = new Document(outFile);
bool isPdfUaCompliance = document.Validate(logFile, PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA compliance: {0}", isPdfUaCompliance));

```

## Závěr

V tomto tutoriálu jste se naučili, jak vytvořit prvky struktury poznámky v dokumentu PDF pomocí Aspose.PDF for .NET. Prvky strukturované poznámky vám umožňují přidat do dokumentu PDF další strukturované informace.

### FAQ

#### Otázka: Jaký je účel vytváření prvků struktury poznámky v dokumentu PDF pomocí Aspose.PDF pro .NET?

Odpověď: Vytváření prvků struktury poznámky v dokumentu PDF pomocí Aspose.PDF for .NET vám umožňuje přidávat k obsahu dokumentu strukturované poznámky. Tyto poznámky mohou poskytnout další kontext, vysvětlení nebo odkazy na konkrétní části obsahu.

#### Otázka: Jak pomáhá knihovna Aspose.PDF při vytváření prvků struktury poznámky v dokumentu PDF?

Odpověď: Aspose.PDF for .NET je výkonná knihovna, která poskytuje funkce pro vytváření, manipulaci a převod dokumentů PDF programově. V tomto kurzu se funkce struktury označeného obsahu knihovny používají k vytváření strukturovaných prvků poznámky v obsahu dokumentu PDF.

#### Otázka: Jaké jsou předpoklady pro vytváření prvků struktury poznámky v dokumentu PDF pomocí Aspose.PDF pro .NET?

Odpověď: Než začnete, ujistěte se, že máte nainstalované Visual Studio s rozhraním .NET a že máte ve svém projektu odkaz na knihovnu Aspose.PDF pro .NET.

#### Otázka: Jak poskytnutý kód C# vytváří prvky struktury poznámky v obsahu dokumentu PDF?

Odpověď: Kód ukazuje, jak vytvořit dokument PDF, definovat strukturované prvky poznámky a přidat je do odstavce. Každá poznámka je vytvořena pomocí metod poskytovaných Aspose.PDF, což vám umožňuje začlenit strukturované poznámky do obsahu.

#### Otázka: Mohu přizpůsobit obsah a vlastnosti prvků struktury poznámky, které vytvořím?

Odpověď: Ano, můžete přizpůsobit obsah a vlastnosti prvků struktury poznámky pomocí metod a vlastností poskytovaných knihovnou Aspose.PDF. Kód ukazuje, jak nastavit text a ID prvků poznámky, ale můžete je dále upravit podle potřeby.

#### Otázka: Jak je vytvořen hierarchický vztah mezi prvky struktury poznámky a obsahem dokumentu?

 Odpověď: Hierarchický vztah je vytvořen přidáním prvků struktury poznámky jako potomků jiných strukturovaných prvků, jako jsou odstavce. V kódu jsou prvky poznámky připojeny k prvku odstavce pomocí`AppendChild` metoda.

#### Otázka: Mohu přiřadit jedinečná ID prvkům struktury poznámky?

Odpověď: Ano, můžete přiřadit jedinečná ID prvkům struktury poznámky pomocí`SetId` metoda. Kód ukazuje, jak nastavit ID prvků poznámky na jedinečné hodnoty.

#### Otázka: Co se stane, když se pokusím přiřadit duplicitní ID prvku struktury poznámky?

Odpověď: Pokus o přiřazení duplicitního ID prvku struktury poznámky bude mít za následek výjimku. Kód uvedený v kurzu obsahuje komentář ilustrující tento scénář.

#### Otázka: Jak mohu zajistit shodu s PDF/UA při vytváření prvků struktury poznámky?

 Odpověď: Kód poskytnutý v tutoriálu ukazuje, jak ověřit shodu s PDF/UA pomocí`Validate` metoda. Ověřením dokumentu podle standardu PDF/UA můžete zajistit, aby přidané prvky struktury poznámky odpovídaly pokynům pro usnadnění.

#### Otázka: Mohu tento přístup použít k přidání prvků struktury poznámky do existujícího dokumentu PDF?

Odpověď: Ano, poskytnutý přístup můžete upravit a přidat prvky struktury poznámky do existujícího dokumentu PDF. Namísto vytvoření nového dokumentu byste načetli existující dokument pomocí Aspose.PDF a poté byste podle podobných kroků přidali prvky poznámky.
