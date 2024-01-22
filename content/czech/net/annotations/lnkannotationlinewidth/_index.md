---
title: lnk Šířka čáry anotace
linktitle: lnk Šířka čáry anotace
second_title: Aspose.PDF pro .NET API Reference
description: Tento článek poskytuje podrobného průvodce nastavením šířky řádku lnk Annotation pomocí Aspose.PDF for .NET.
type: docs
weight: 110
url: /cs/net/annotations/lnkannotationlinewidth/
---
Aspose.PDF je výkonný a široce používaný nástroj pro práci se soubory PDF v aplikacích .NET. Poskytuje řadu funkcí pro vytváření, úpravy a manipulaci se soubory PDF, včetně možnosti přidávat na stránky anotace. V tomto tutoriálu si vysvětlíme, jak nastavit šířku řádku anotace odkazu pomocí Aspose.PDF pro .NET.

Jakmile budete mít tyto předpoklady, vytvořte nový projekt konzolové aplikace v sadě Visual Studio. Poté přidejte odkaz na knihovnu Aspose.PDF for .NET kliknutím pravým tlačítkem na projekt v Průzkumníku řešení, výběrem „Spravovat balíčky NuGet“ a vyhledáním „Aspose.PDF“ ve Správci balíčků NuGet.

Chcete-li přidat anotaci lnk do dokumentu PDF, postupujte takto:

##  Krok 1: Vytvořte nový`Document` object.
```csharp
Document doc = new Document();
```
## Krok 2: Přidejte do dokumentu novou stránku.
```csharp
doc.Pages.Add();
```
##  Krok 3: Vytvořte seznam`Point` arrays that represent the ink gesture for the annotation.
```csharp
IList<Point[]> inkList = new List<Point[]>();
```
##  Krok 4: Vytvořte nový`LineInfo` object that defines the properties of the ink gesture.
```csharp
LineInfo lineInfo = new LineInfo();
lineInfo.VerticeCoordinate = new float[] { 55, 55, 70, 70, 70, 90, 150, 60 };
lineInfo.Visibility = true;
lineInfo.LineColor = System.Drawing.Color.Red;
lineInfo.LineWidth = 2;
```
##  Krok 5: Vytvořte nový`Aspose.Pdf.Point` array that represents the gesture from the `LineInfo` object.
```csharp
int length = lineInfo.VerticeCoordinate.Length / 2;
Aspose.Pdf.Point[] gesture = new Aspose.Pdf.Point[length];
for (int i = 0; i < length; i++)
{
    gesture[i] = new Aspose.Pdf.Point(lineInfo.VerticeCoordinate[2 * i], lineInfo.VerticeCoordinate[2 * i + 1]);
}
```
## Krok 6: Přidejte gesto do seznamu gest inkoustu.
```csharp
inkList.Add(gesture);
```
##  Krok 7: Vytvořte nový`InkAnnotation` object that represents the link annotation.
```csharp
InkAnnotation a1 = new InkAnnotation(doc.Pages[1], new Aspose.Pdf.Rectangle(100, 100, 300, 300), inkList);
```
## Krok 8: Nastavte předmět a název anotace.
```csharp
a1.Subject = "Test";
a1.Title = "Title";
```
## Krok 9: Nastavte barvu anotace.
```csharp
a1.Color = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Green);
```
##  Krok 10: Vytvořte nový`Border` object that defines the properties of the annotation's border.
```csharp
Border border = new Border(a1);
border.Width = 3;
border.Effect = BorderEffect.Cloudy;
border.Dash = new Dash(1, 1);
border.Style = BorderStyle.Solid;
```
## Krok 11: Přidejte na stránku anotaci.
```csharp
doc.Pages[1].Annotations.Add(a1);
```
## Krok 12: Uložte dokument do souboru.
```csharp
// Uložit výstupní soubor
doc.Save(dataDir);


```
### Příklad ukazuje šířku řádku anotace lnk s Aspose.PDF pro .NET

```csharp
// Cesta k adresáři dokumentů.
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
doc.Pages.Add();
IList<Point[]> inkList = new List<Point[]>();
LineInfo lineInfo = new LineInfo();
lineInfo.VerticeCoordinate = new float[] { 55, 55, 70, 70, 70, 90, 150, 60 };
lineInfo.Visibility = true;
lineInfo.LineColor = System.Drawing.Color.Red;
lineInfo.LineWidth = 2;
int length = lineInfo.VerticeCoordinate.Length / 2;
Aspose.Pdf.Point[] gesture = new Aspose.Pdf.Point[length];
for (int i = 0; i < length; i++)
{
gesture[i] = new Aspose.Pdf.Point(lineInfo.VerticeCoordinate[2 * i], lineInfo.VerticeCoordinate[2 * i + 1]);
}

inkList.Add(gesture);
InkAnnotation a1 = new InkAnnotation(doc.Pages[1], new Aspose.Pdf.Rectangle(100, 100, 300, 300), inkList);
a1.Subject = "Test";
a1.Title = "Title";
a1.Color = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Green);
Border border = new Border(a1);
border.Width = 3;
border.Effect = BorderEffect.Cloudy;
border.Dash = new Dash(1, 1);
border.Style = BorderStyle.Solid;
doc.Pages[1].Annotations.Add(a1);

dataDir = dataDir + "lnkAnnotationLineWidth_out.pdf";
// Uložit výstupní soubor
doc.Save(dataDir);
```

## Závěr

tomto tutoriálu jsme se naučili, jak nastavit šířku čáry anotace odkazu v dokumentu PDF pomocí Aspose.PDF pro .NET. Aspose.PDF for .NET poskytuje širokou škálu nástrojů a funkcí pro práci s dokumenty PDF, včetně možnosti vytvářet a upravovat anotace odkazů. Pomocí tohoto podrobného průvodce a pomocí poskytnutého zdrojového kódu C# mohou vývojáři snadno přidávat interaktivní odkazy do svých dokumentů PDF, čímž vylepšují uživatelskou zkušenost a interaktivitu svých aplikací. Aspose.PDF for .NET je všestranná knihovna, která umožňuje vývojářům .NET pracovat se soubory PDF efektivně a efektivně.

### FAQ

#### Otázka: Co je anotace odkazu v dokumentu PDF?

Odpověď: Anotace odkazu v dokumentu PDF je interaktivní prvek, který vám umožňuje vytvářet hypertextové odkazy nebo akce, které uživatele nasměrují na jiné místo v rámci stejného dokumentu, na externí web nebo do jiného dokumentu PDF.

#### Otázka: Jak mohu nastavit šířku řádku anotace odkazu pomocí Aspose.PDF pro .NET?

A: Chcete-li nastavit šířku řádku anotace odkazu pomocí Aspose.PDF pro .NET, můžete vytvořit`InkAnnotation` objekt a zadejte vlastnost šířky čáry.

#### Otázka: Jaké vlastnosti lze upravit pro anotaci odkazu v Aspose.PDF pro .NET?

Odpověď: Můžete upravit různé vlastnosti anotace odkazu v Aspose.PDF pro .NET, jako je její umístění, velikost, barva, vlastnosti ohraničení (šířka, styl, vzor čárky a efekt), předmět, název a viditelnost.

#### Otázka: Mohu vytvořit anotaci odkazu, která obsahuje více gest inkoustem?

 Odpověď: Ano, můžete vytvořit anotaci odkazu, která obsahuje více gest inkoustu přidáním více`Point` pole k`InkAnnotation` objekt.

#### Otázka: Jak mohu přidat anotaci odkazu na konkrétní stránku dokumentu PDF?

 Odpověď: Chcete-li přidat anotaci odkazu na konkrétní stránku dokumentu PDF, musíte při vytváření dokumentu zadat číslo stránky.`InkAnnotation` objekt. Například,`new InkAnnotation(doc.Pages[1], ...)` přidá anotaci odkazu na první stránku.