---
title: Tabellenzeile formatieren
linktitle: Tabellenzeile formatieren
second_title: Aspose.PDF für .NET API-Referenz
description: Erfahren Sie mithilfe einer Schritt-für-Schritt-Anleitung, wie Sie Tabellenzeilen in einer PDF-Datei mit Aspose.PDF für .NET formatieren und so mühelos die Formatierung Ihres Dokuments verbessern.
type: docs
weight: 180
url: /de/net/programming-with-tagged-pdf/style-table-row/
---
## Einführung

Wenn es darum geht, gut strukturierte und schön formatierte PDF-Dokumente zu erstellen, ist Aspose.PDF für .NET die Lösung der Wahl. Egal, ob Sie Berichte oder Rechnungen automatisieren oder dynamische Tabellen erstellen, das Formatieren von Tabellen mit verschiedenen Stilen ist der Schlüssel zu einem ansprechenden Dokument. In diesem Tutorial werden wir uns eingehend mit dem Formatieren einer Tabellenzeile mit Aspose.PDF für .NET befassen. Und keine Sorge, ich werde Sie Schritt für Schritt anleiten, genau wie bei einem guten Gespräch bei einer Tasse Kaffee!

## Voraussetzungen

Bevor wir uns ins Detail stürzen, sollten wir sicherstellen, dass Sie alles vorbereitet haben. Sie benötigen:

1. Aspose.PDF für .NET-Bibliothek  
    Wenn Sie es noch nicht haben, können Sie es hier herunterladen:[Hier](https://releases.aspose.com/pdf/net/) Sie können auch eine[Kostenlose Testversion](https://releases.aspose.com/) um loszulegen.
2. Entwicklungsumgebung  
   Richten Sie Visual Studio oder eine C#-IDE Ihrer Wahl ein. Sie müssen außerdem .NET installieren, aber ich gehe davon aus, dass Sie damit bereits vertraut sind.
3. Grundkenntnisse in C# und .NET  
   Mit guten Kenntnissen in C# ist dieses Tutorial ein Kinderspiel. Aber keine Sorge, ich werde jeden Schritt im Detail erklären!

## Pakete importieren

Bevor wir mit Aspose.PDF arbeiten können, müssen wir die erforderlichen Namespaces importieren. Stellen Sie sicher, dass Sie in Ihrem C#-Projekt Folgendes einschließen:

```csharp
using Aspose.Pdf.LogicalStructure;
using Aspose.Pdf.Tagged;
using Aspose.Pdf.Text;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

Diese sind wichtig, um die Tabelle zu erstellen und zu gestalten und natürlich um aus Compliance-Gründen mit getaggten Inhalten zu arbeiten.

Lassen Sie uns die Aufgabe nun Schritt für Schritt aufschlüsseln, damit Sie Ihre Tabellenzeilen wie ein Profi gestalten können!

## Schritt 1: Ein neues PDF-Dokument erstellen

Das Wichtigste zuerst: Lassen Sie uns ein brandneues PDF-Dokument erstellen. Dieses Dokument enthält alle formatierten Tabellenzeilen.

```csharp
// Der Pfad zum Dokumentverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Dokument erstellen
Document document = new Document();
```

 Hier initialisieren wir einfach eine neue`Document` Objekt, das unsere PDF-Datei darstellt. Stellen Sie sicher, dass Sie den Verzeichnispfad festlegen, in dem Sie Ihre Ausgabedateien speichern.

## Schritt 2: Mit getaggten Inhalten arbeiten

Um Ihr PDF barrierefrei zu strukturieren, arbeiten wir mit getaggten Inhalten. Dies hilft beim Erstellen strukturierter Elemente wie Tabellen und stellt sicher, dass diese Barrierefreiheitsstandards wie PDF/UA entsprechen.

```csharp
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Example table row style");
taggedContent.SetLanguage("en-US");
```

Hier legen wir den Titel und die Sprache für den getaggten Inhalt der PDF-Datei fest. Das ist, als würden Sie Ihrer PDF-Datei einen Namen geben und ihr sagen, welche Sprache sie sprechen soll!

## Schritt 3: Definieren Sie die Tabellenstruktur

Als Nächstes definieren wir die Struktur der Tabelle, die wir erstellen möchten. Jede Tabelle benötigt eine Kopfzeile, einen Textkörper und eine Fußzeile – ähnlich wie ein gut organisierter Blogbeitrag!

```csharp
// Stammstrukturelement abrufen
StructureElement rootElement = taggedContent.RootElement;

// Tabellenstrukturelement erstellen
TableElement tableElement = taggedContent.CreateTableElement();
rootElement.AppendChild(tableElement);
TableTHeadElement tableTHeadElement = tableElement.CreateTHead();
TableTBodyElement tableTBodyElement = tableElement.CreateTBody();
TableTFootElement tableTFootElement = tableElement.CreateTFoot();
```

Was wir hier tun, ist eine Tabelle mit einer Kopfzeile (`THead`), Körper (`TBody`) und der Fußzeile (`TFoot`). Diese Elemente werden unsere Zeilen enthalten.

## Schritt 4: Fügen Sie die Tabellenkopfzeile hinzu

Tabellen ohne Überschriften sind wie Bücher ohne Titel. Lassen Sie uns zuerst die Überschriftenzeile erstellen, um den Daten einen Kontext zu geben.

```csharp
TableTRElement headTrElement = tableTHeadElement.CreateTR();
headTrElement.AlternativeText = "Head Row";
for (int colIndex = 0; colIndex < 3; colIndex++)
{
    TableTHElement thElement = headTrElement.CreateTH();
    thElement.SetText(String.Format("Head {0}", colIndex));
}
```

Hier durchlaufen wir die Schleife und fügen drei Header-Zellen hinzu (`TableTHElement`), und geben Sie jedem einen beschreibenden Text. Einfach, oder?

## Schritt 5: Gestaltete Textzeilen hinzufügen

Jetzt kommt der spaßige Teil – das Stylen der Zeilen! Lassen Sie uns sieben Zeilen mit benutzerdefinierten Styles erstellen. Wir legen Hintergrundfarben, Rahmen, Polsterung und Textausrichtung fest.

```csharp
for (int rowIndex = 0; rowIndex < 7; rowIndex++)
{
    TableTRElement trElement = tableTBodyElement.CreateTR();
    trElement.AlternativeText = String.Format("Row {0}", rowIndex);
    trElement.BackgroundColor = Color.LightGoldenrodYellow;
    trElement.Border = new BorderInfo(BorderSide.All, 0.75F, Color.DarkGray);
    trElement.DefaultCellBorder = new BorderInfo(BorderSide.All, 0.50F, Color.Blue);
    trElement.MinRowHeight = 100.0;
    trElement.FixedRowHeight = 120.0;
    trElement.IsInNewPage = (rowIndex % 3 == 1);
    trElement.IsRowBroken = true;

    for (int colIndex = 0; colIndex < 3; colIndex++)
    {
        TableTDElement tdElement = trElement.CreateTD();
        tdElement.SetText(String.Format("Cell [{0}, {1}]", rowIndex, colIndex));
    }
}
```

- Hintergrundfarbe: Wir haben ein helles Goldrutengelb für einen professionellen und dennoch warmen Touch verwendet.
- Ränder: Jede Reihe erhält einen dunkelgrauen Außenrand und blaue Zellränder für ein klares Aussehen.
- Höhe und Polsterung: Die Zeilenhöhen werden festgelegt und für ein sauberes Erscheinungsbild wird eine Polsterung hinzugefügt.
- Seitenumbrüche: Um die Tabelle lesbarer zu machen, beginnt jede zweite Zeile auf einer neuen Seite.

## Schritt 6: Fußzeile hinzufügen

Ähnlich wie die Kopfzeile verankert die Fußzeile die Tabelle. Lassen Sie uns eine erstellen.

```csharp
TableTRElement footTrElement = tableTFootElement.CreateTR();
footTrElement.AlternativeText = "Foot Row";
for (int colIndex = 0; colIndex < 3; colIndex++)
{
    TableTDElement tdElement = footTrElement.CreateTD();
    tdElement.SetText(String.Format("Foot {0}", colIndex));
}
```

Wir durchlaufen einfach drei Fußzeilenzellen und fügen etwas Text hinzu. Der alternative Text für die Fußzeile lautet „Fußzeile“, um sie zugänglich zu machen.

## Schritt 7: Speichern Sie das PDF-Dokument

Nachdem der Tisch nun vollständig aufgestellt ist, ist es an der Zeit, Ihr Meisterwerk zu speichern!

```csharp
document.Save(dataDir + "StyleTableRow.pdf");
```

So einfach wird Ihre PDF-Datei mit allen schönen Tabellenzeilen gespeichert, die wir gerade gestaltet haben.

## Schritt 8: PDF/UA-Konformität validieren

Um sicherzustellen, dass unser PDF den Zugänglichkeitsstandards entspricht, validieren wir es auf PDF/UA-Konformität.

```csharp
document = new Document(dataDir + "StyleTableRow.pdf");
bool isPdfUaCompliance = document.Validate(dataDir + "StyleTableRow.xml", PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA compliance: {0}", isPdfUaCompliance));
```

Dadurch wird sichergestellt, dass Ihr PDF dem PDF/UA-Standard entspricht und für alle zugänglich ist. Barrierefreiheit ist das A und O!

## Abschluss

Und da haben Sie es! Mit nur wenigen Codezeilen haben Sie mit Aspose.PDF für .NET eine vollständig gestaltete Tabelle in einem PDF erstellt. Von Kopf- bis Fußzeilen haben wir jede Zeile gestaltet, Zugänglichkeitselemente hinzugefügt und das Dokument sogar auf Konformität geprüft. Egal, ob Sie an Unternehmensberichten oder Präsentationen arbeiten oder einfach nur Spaß mit PDFs haben, dieser Leitfaden hat alles, was Sie brauchen. Jetzt können Sie anfangen, Ihre Tabellen wie ein Profi zu gestalten!

## Häufig gestellte Fragen

### Kann ich auch den Schriftstil der Tabelle ändern?  
 Ja! Sie können den Schriftstil mit dem`TextState` Objekt für jede Zelle, was eine vollständige Anpassung ermöglicht.

### Wie füge ich meiner Tabelle weitere Spalten hinzu?  
 Passen Sie einfach die`colCount`Variable und fügen Sie in den Schleifen weitere Zellen für Kopf-, Text- und Fußzeilen hinzu.

### Was passiert, wenn ich die Zeilenhöhe nicht festlege?  
Wenn Sie die Zeilenhöhe nicht festlegen, wird die Tabelle automatisch basierend auf dem Inhalt angepasst.

### Kann ich dies für eine dynamische Zeilenanzahl verwenden?  
Auf jeden Fall! Sie können Daten aus einer Datenbank oder einer anderen Quelle abrufen und die Zeilen- und Spaltenanzahl dynamisch anpassen.

### Ist die Nutzung von Aspose.PDF für .NET kostenlos?  
 Aspose.PDF für .NET ist ein lizenziertes Produkt, aber Sie können es mit einem[Kostenlose Testversion](https://releases.aspose.com/) oder erhalten Sie eine[vorläufige Lizenz](https://purchase.aspose.com/temporary-license/).