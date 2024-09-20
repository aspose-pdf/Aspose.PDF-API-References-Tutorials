---
title: Tabelle im PDF-Dokument rendern
linktitle: Tabelle im PDF-Dokument rendern
second_title: Aspose.PDF für .NET API-Referenz
description: Erstellen Sie ganz einfach professionelle PDFs, indem Sie Tabellen mit Aspose.PDF für .NET rendern. Folgen Sie unserer Schritt-für-Schritt-Anleitung zur Masterdokumenterstellung.
type: docs
weight: 170
url: /de/net/programming-with-tables/render-table/
---
## Einführung

Das programmgesteuerte Erstellen professioneller PDFs kann eine gewaltige Aufgabe sein, aber mit Aspose.PDF für .NET wird es zum Kinderspiel. Egal, ob Sie Berichte, Rechnungen oder andere Dokumenttypen erstellen, die tabellarische Daten erfordern, Aspose.PDF bietet die Tools, die Sie benötigen. In diesem Tutorial erfahren Sie Schritt für Schritt, wie Sie Tabellen in einem PDF-Dokument rendern. Am Ende haben Sie ein solides Verständnis dafür, wie Sie Tabellen bearbeiten, Seiteneigenschaften verwalten und PDF-Dateien problemlos speichern können.

## Voraussetzungen

Bevor wir uns in den Code vertiefen, hier ist, was Sie brauchen:

-  Visual Studio: Stellen Sie sicher, dass Visual Studio auf Ihrem Computer installiert ist. Sie können es herunterladen[Hier](https://visualstudio.microsoft.com/downloads/).
-  Aspose.PDF für .NET: Sie können die Aspose.PDF-Bibliothek ganz einfach herunterladen von der[Aspose-Veröffentlichungsseite](https://releases.aspose.com/pdf/net/).
- Grundkenntnisse in C#: Wenn Sie die Grundlagen von C# verstehen, können Sie den Schritten besser folgen.
- .NET Framework: Stellen Sie idealerweise sicher, dass Sie in einer kompatiblen .NET-Umgebung arbeiten.

Sobald Sie diese Voraussetzungen erfüllt haben, können Sie mit der Erstellung Ihrer PDF-Dokumente beginnen!

## Pakete importieren

Zu Beginn Ihrer C#-Datei müssen Sie die erforderlichen Aspose.PDF-Namespaces importieren. Dadurch können Sie die Bibliotheksfunktionen in unserem Projekt nutzen.

```csharp
using System;
using System.IO;
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

 Stellen Sie sicher, dass Sie die erforderlichen Verweise auf die Aspose.PDF-Bibliothek in Ihrem Projekt hinzugefügt haben. Wenn Sie NuGet verwenden, können Sie es einfach hinzufügen, indem Sie nach`Aspose.PDF`.

Nachdem wir nun alles eingerichtet haben, unterteilen wir den Vorgang zum Rendern einer Tabelle in ein PDF-Dokument in überschaubare Schritte. Keine Sorge, ich werde Sie mit klaren Anweisungen durch jeden Schritt führen!

## Schritt 1: Dokument- und Seiteninformationen einrichten

Als Erstes müssen wir ein neues Dokument erstellen und dessen Seiteneinstellungen konfigurieren. So geht's:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
PageInfo pageInfo = doc.PageInfo;
Aspose.Pdf.MarginInfo marginInfo = pageInfo.Margin;

marginInfo.Left = 37;
marginInfo.Right = 37;
marginInfo.Top = 37;
marginInfo.Bottom = 37;

pageInfo.IsLandscape = true;
```

Erläuterung: 
- Wir beginnen damit, festzulegen, wo unser Dokument gespeichert wird (`dataDir`). 
-  Dann erstellen wir eine neue Instanz des`Document` Klasse. 
- Wir konfigurieren die Seitenränder, um etwas Luft um unsere Tabelle herum zu schaffen.
- Zum Schluss stellen wir das Dokument auf Querformat ein, was bei der Anzeige breiterer Tabellen hilfreich ist.

## Schritt 2: Erstellen Sie die erste Tabelle

Als Nächstes erstellen wir unsere erste Tabelle und füllen sie mit einigen Beispieldaten:

```csharp
Aspose.Pdf.Table table = new Aspose.Pdf.Table();
table.ColumnWidths = "50 100"; // Spaltenbreiten definieren
```

 Erklärung: Hier instantiieren wir die`Table` Klasse und legen Sie die Spaltenbreiten fest. Die erste Spalte ist 50 Einheiten breit und die zweite Spalte 100 Einheiten.

## Schritt 3: Füllen Sie die Tabelle mit Zeilen

Fügen wir nun in einer Schleife Zeilen zu unserer Tabelle hinzu:

```csharp
Page curPage = doc.Pages.Add(); // Hinzufügen einer neuen Seite
for (int i = 1; i <= 120; i++)
{
    Aspose.Pdf.Row row = table.Rows.Add();
    row.FixedRowHeight = 15; // Festlegen einer festen Höhe für Zeilen
    
    Aspose.Pdf.Cell cell1 = row.Cells.Add();
    cell1.Paragraphs.Add(new TextFragment("Content 1"));
    
    Aspose.Pdf.Cell cell2 = row.Cells.Add();
    cell2.Paragraphs.Add(new TextFragment("HHHHH"));
}
```

Erläuterung: 
- Hier erstellen wir eine neue Seite, um unsere Tabelle hinzuzufügen.
-  Wir verwenden ein`for` Schleife, um unserer Tabelle 120 Zeilen hinzuzufügen. Jede Zeile hat eine feste Höhe von 15 Einheiten.
- Innerhalb jeder Zeile fügen wir zwei Zellen hinzu und füllen sie mit Text.

## Schritt 4: Die erste Tabelle zur Seite hinzufügen

Sobald wir die Tabelle ausgefüllt haben, fügen wir sie der aktuellen Seite hinzu:

```csharp
Aspose.Pdf.Paragraphs paragraphs = curPage.Paragraphs;
paragraphs.Add(table);
```

Erklärung: Dieser Schritt fügt einfach die von uns erstellte Tabelle zu den Absätzen der aktuellen Seite hinzu, wodurch die Tabelle im PDF-Dokument sichtbar wird.

## Schritt 5: Erstellen Sie eine zweite Tabelle

Erstellen wir nun eine zweite Tabelle mit anderem Inhalt und fügen sie einer neuen Seite hinzu:

```csharp
Aspose.Pdf.Table table1 = new Aspose.Pdf.Table();
table1.ColumnWidths = "100 100";
for (int i = 1; i <= 10; i++)
{
    Aspose.Pdf.Row row = table1.Rows.Add();
    Aspose.Pdf.Cell cell1 = row.Cells.Add();
    cell1.Paragraphs.Add(new TextFragment("LAAAAAAA"));
    
    Aspose.Pdf.Cell cell2 = row.Cells.Add();
    cell2.Paragraphs.Add(new TextFragment("LAAGGGGGG"));
}
table1.IsInNewPage = true; // Festlegen, dass die zweite Tabelle auf einer neuen Seite angezeigt wird
paragraphs.Add(table1);
```

Erläuterung: 
- Dieser Codeausschnitt erstellt eine neue Tabelle mit zwei Spalten, beide 100 Einheiten breit.
-  A`for` Schleife fügt 10 Zeilen mit Beispielinhalten hinzu.
-  Durch die Einstellung`table1.IsInNewPage` auf „true“ setzen, stellen wir sicher, dass diese Tabelle auf einer neuen Seite angezeigt wird, damit alles organisiert und übersichtlich bleibt.

## Schritt 6: Speichern Sie das Dokument

Nachdem unsere Tabellen nun fertig sind, speichern wir unser Dokument:

```csharp
dataDir = dataDir + "IsNewPageProperty_Test_out.pdf";
doc.Save(dataDir);
```

 Erklärung: Wir geben den Dateinamen an und speichern das Dokument im angegebenen Verzeichnis. Wenn Sie diesen Code ausführen, wird eine PDF-Datei mit dem Titel`IsNewPageProperty_Test_out.pdf` wird an Ihrem angegebenen Standort erstellt.

## Schritt 7: Bestätigungsnachricht

Um dem Benutzer abschließend mitzuteilen, dass alles reibungslos funktioniert hat, können wir eine freundliche Konsolennachricht hinzufügen:

```csharp
Console.WriteLine("\nTable rendered successfully on a page.\nFile saved at " + dataDir);
```

Erklärung: Auf diese Weise lässt sich auf einfache Weise bestätigen, dass der Vorgang erfolgreich war und wo der Benutzer seine neue PDF-Datei finden kann.

## Abschluss

Und da haben Sie es! Sie haben erfolgreich Tabellen in einem PDF-Dokument mit Aspose.PDF für .NET gerendert. Mit nur wenigen Codezeilen können Sie große Datenmengen in einem organisierten Format verarbeiten und präsentieren, sodass Ihre Dokumente sowohl informativ als auch optisch ansprechend sind. Egal, ob Sie an Inventarlisten, Finanzberichten oder Bildungsdokumenten arbeiten, Tabellen sind eine hervorragende Möglichkeit, komplexe Informationen auf einen Blick zu vermitteln.

## Häufig gestellte Fragen

### Kann ich das Erscheinungsbild der Tabellen in Aspose.PDF anpassen?  
Auf jeden Fall! Sie können Farben, Rahmen, Schriftarten und andere Eigenschaften anpassen, um das Erscheinungsbild Ihrer Tabellen zu verbessern.

### Ist die Nutzung von Aspose.PDF kostenlos?  
 Aspose.PDF bietet eine kostenlose Testversion an, für die kommerzielle Nutzung ist jedoch ein Kauf erforderlich. Sie können die Preise überprüfen[Hier](https://purchase.aspose.com/buy).

### Wie erhalte ich Support bei Problemen mit Aspose.PDF?  
 Sie können im Aspose-Supportforum Hilfe suchen[Hier](https://forum.aspose.com/c/pdf/10).

### Gibt es Einschränkungen für die kostenlose Testversion?  
 Ja, die Testversion kann bestimmte Einschränkungen aufweisen, z. B. Wasserzeichen auf generierten Dokumenten. Für die volle Funktionalität sollten Sie eine temporäre Lizenz erwerben.[Hier](https://purchase.aspose.com/temporary-license/).

### Wo finde ich weitere Informationen zu den Funktionen von Aspose.PDF?  
 Sie können die umfassende Dokumentation erkunden, die verfügbar ist[Hier](https://reference.aspose.com/pdf/net/).