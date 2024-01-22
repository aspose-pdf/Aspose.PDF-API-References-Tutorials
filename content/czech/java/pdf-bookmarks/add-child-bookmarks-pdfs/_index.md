---
title: Přidejte dětské záložky do PDF
linktitle: Přidejte dětské záložky do PDF
second_title: Aspose.PDF Java PDF Processing API
description: Naučte se, jak vylepšit dokumenty PDF pomocí podřízených záložek pomocí Aspose.PDF for Java. Podrobný průvodce s příklady kódu pro lepší navigaci a organizaci.
type: docs
weight: 11
url: /cs/java/pdf-bookmarks/add-child-bookmarks-pdfs/
---

## Úvod do přidávání dětských záložek do PDF

V tomto článku prozkoumáme, jak přidat podřízené záložky do dokumentů PDF pomocí Aspose.PDF pro Java. Podřízené záložky představují pohodlný způsob, jak organizovat obsah dokumentu PDF a procházet v něm, což uživatelům usnadňuje hledání konkrétních částí nebo témat v dokumentu.

## Předpoklady

Než se pustíme do implementace, ujistěte se, že máte splněny následující předpoklady:

- Vývojové prostředí Java nainstalované ve vašem systému.
-  Aspose.PDF pro knihovnu Java. Můžete si jej stáhnout z[tady](https://releases.aspose.com/pdf/java/).

## Nastavení prostředí

1. Stáhněte si knihovnu Aspose.PDF for Java z poskytnutého odkazu.
2. Přidejte knihovnu do svého projektu Java.

Nyní začněme vytvořením nového dokumentu PDF a přidáním podřízených záložek do něj krok za krokem.

## Vytvoření nového dokumentu PDF

Pro začátek musíme inicializovat dokument PDF a přidat do něj stránky. Zde je fragment kódu, jak začít:

```java
// Inicializujte dokument PDF
Document pdfDocument = new Document();

// Přidejte stránky do PDF
pdfDocument.getPages().add();
pdfDocument.getPages().add();
```

V tomto příkladu jsme vytvořili nový dokument PDF a přidali do něj dvě stránky.

## Přidání nadřazených záložek

Nadřazené záložky slouží jako hlavní sekce nebo kategorie v dokumentu PDF. Pojďme vytvořit nějaké rodičovské záložky:

```java
// Vytvořte nadřazené záložky
OutlineItemCollection outline = pdfDocument.getOutlines();
OutlineItemCollection parentBookmark = new OutlineItemCollection(outline);
parentBookmark.setTitle("Parent Bookmark 1");
outline.add(parentBookmark);

parentBookmark = new OutlineItemCollection(outline);
parentBookmark.setTitle("Parent Bookmark 2");
outline.add(parentBookmark);
```

Přidali jsme dvě nadřazené záložky, „Nadřazená záložka 1“ a „Nadřazená záložka 2“.

## Přidání dětských záložek

Nyní je čas přidat podřízené záložky k nadřazeným záložkám, které jsme vytvořili dříve. Podřízené záložky představují konkrétní témata nebo podsekce v každé nadřazené záložce. Můžete to udělat takto:

```java
// Přidání podřízených záložek do nadřazené záložky 1
OutlineItemCollection childBookmark = new OutlineItemCollection(outline);
childBookmark.setTitle("Child Bookmark 1.1");
parentBookmark.add(childBookmark);

childBookmark = new OutlineItemCollection(outline);
childBookmark.setTitle("Child Bookmark 1.2");
parentBookmark.add(childBookmark);

//Přidejte podřízené záložky do nadřazené záložky 2
childBookmark = new OutlineItemCollection(outline);
childBookmark.setTitle("Child Bookmark 2.1");
parentBookmark.add(childBookmark);
```

Do „Rodičovské záložky 1“ i „Nadřazené záložky 2“ jsme přidali podřízené záložky.

## Přizpůsobení vzhledu záložky

Vzhled záložek můžete přizpůsobit změnou jejich textu a stylu. Navíc můžete do záložek přidat ikony pro lepší vizuální reprezentaci. Zde je příklad, jak na to:

```java
// Přizpůsobte vzhled záložky
parentBookmark.setItalic(true);
childBookmark.setForegroundColor(Color.getGreen());
childBookmark.setIcon(OutlineItemCollection.getItalicIcon());
```

V tomto příkladu jsme udělali nadřazenou záložku kurzívou, změnili barvu textu podřízené záložky na zelenou a přidali jsme do podřízené záložky ikonu kurzíva.

## Zpracování událostí

K záložkám mohou být také přiřazeny akce. Můžete například přidat akce, které se spouštějí, když uživatel klikne na záložku. Zde je návod, jak můžete zpracovat události kliknutí na záložku:

```java
// Přidejte akci do záložky
GoToAction action = new GoToAction(pdfDocument.getPages().get_Item(1));
childBookmark.setAction(action);
```

V tomto kódu jsme přidali akci „Přejít na“ do podřízené záložky, která uživatele po kliknutí přesune na druhou stránku PDF.

## Uložení PDF

Jakmile přidáte všechny potřebné záložky a přizpůsobíte jejich vzhled a akce, můžete upravený dokument PDF uložit:

```java
// Uložte dokument PDF
pdfDocument.save("output.pdf");
```

Váš dokument PDF s podřízenými záložkami je nyní připraven.

## Kompletní zdrojový kód

Zde je úplný zdrojový kód pro přidávání podřízených záložek do dokumentu PDF pomocí Aspose.PDF pro Java:

```java
// Inicializujte dokument PDF
Document pdfDocument = new Document();

// Přidejte stránky do PDF
pdfDocument.getPages().add();
pdfDocument.getPages().add();

// Vytvořte nadřazené záložky
OutlineItemCollection outline = pdfDocument.getOutlines();
OutlineItemCollection parentBookmark = new OutlineItemCollection(outline);
parentBookmark.setTitle("Parent Bookmark 1");
outline.add(parentBookmark);

parentBookmark = new OutlineItemCollection(outline);
parentBookmark.setTitle("Parent Bookmark 2");
outline.add(parentBookmark);

// Přidání podřízených záložek do nadřazené záložky 1
OutlineItemCollection childBookmark = new OutlineItemCollection(outline);
childBookmark.setTitle("Child Bookmark 1.1");
parentBookmark.add(childBookmark);

childBookmark = new OutlineItemCollection(outline);
childBookmark.setTitle("Child Bookmark 1.2");
parentBookmark.add(childBookmark);

//Přidejte podřízené záložky do nadřazené záložky 2
childBookmark = new OutlineItemCollection(outline);
childBookmark.setTitle("Child Bookmark 2.1");
parentBookmark.add(childBookmark);

// Přizpůsobte vzhled záložky
parentBookmark.setItalic(true);
childBookmark.setForegroundColor(Color.getGreen());
childBookmark.setIcon(OutlineItemCollection.getItalicIcon());

// Přidejte akci do záložky
GoToAction action = new GoToAction(pdfDocument.getPages().get_Item(1));
childBookmark.setAction(action);

// Uložte dokument PDF
pdfDocument.save("output.pdf");
```

## Závěr

Přidávání podřízených záložek do PDF pomocí Aspose.PDF for Java je výkonná funkce, která zlepšuje navigaci a organizaci vašich dokumentů. Podle kroků uvedených v tomto článku můžete vytvářet dobře strukturované soubory PDF s nadřazenými a podřízenými záložkami, upravovat jejich vzhled a dokonce přidávat akce pro zlepšení uživatelského zážitku.

## FAQ

### Jak si mohu stáhnout Aspose.PDF pro Javu?

 Aspose.PDF pro Java si můžete stáhnout z webových stránek[tady](https://releases.aspose.com/pdf/java/).

### Jsou podřízené záložky podporovány ve všech prohlížečích PDF?

Ano, podřízené záložky jsou podporovány ve většině moderních prohlížečů PDF a poskytují uživatelům lepší možnosti procházení dokumentů PDF.

### Mohu si vzhled záložek dále přizpůsobit?

Ano, vzhled záložek si můžete přizpůsobit úpravou stylů textu, barev a ikon tak, aby vyhovovaly designu vašeho dokumentu.

### Jaké další akce mohu přidat do záložek?

Kromě akcí „Přejít na“ můžete přidat akce jako akce „URI“ pro otevírání webových odkazů nebo akce „JavaScript“ pro spouštění vlastních skriptů po kliknutí na záložku.

### Je Aspose.PDF for Java vhodný pro komerční projekty?

Ano, Aspose.PDF for Java je vhodný pro osobní i komerční projekty a nabízí širokou škálu funkcí pro manipulaci a generování PDF.