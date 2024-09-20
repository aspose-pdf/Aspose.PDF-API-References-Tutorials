---
title: Tabellenelement erstellen
linktitle: Tabellenelement erstellen
second_title: Aspose.PDF für .NET API-Referenz
description: Schritt-für-Schritt-Anleitung zum Erstellen eines Array-Elements mit Aspose.PDF für .NET. Generieren Sie ganz einfach dynamische PDFs mit Tabellen.
type: docs
weight: 80
url: /de/net/programming-with-tagged-pdf/create-table-element/
---
## Einführung

Haben Sie sich schon einmal gefragt, wie Sie mit .NET mühelos Tabellenelemente in einer PDF-Datei erstellen und anpassen können? Dann ist Aspose.PDF für .NET die Lösung für Sie! Ob Sie nun die Berichterstellung automatisieren oder Tabellen für verschiedene Dokumente dynamisch erstellen, Aspose.PDF bietet eine umfangreiche API für die Arbeit mit Tabellenelementen. Diese Anleitung führt Sie Schritt für Schritt durch die Erstellung einer Tabelle, deren Formatierung und stellt sogar sicher, dass sie den PDF/UA-Konformitätsstandards entspricht. Klingt spannend, oder? Lassen Sie uns direkt loslegen!

## Voraussetzungen

Bevor wir beginnen, müssen einige Dinge bereit sein:
1.  Aspose.PDF für .NET: Laden Sie die neueste Version herunter von[Aspose.PDF für .NET herunterladen](https://releases.aspose.com/pdf/net/).
2. Entwicklungsumgebung: Jede .NET-unterstützte IDE (z. B. Visual Studio).
3. Grundkenntnisse in C#: Vertrautheit mit der C#-Programmierung wird empfohlen.

 Vergessen Sie nicht Ihre Aspose.PDF-Lizenz. Wenn Sie keine haben, können Sie die[Kostenlose Testversion](https://releases.aspose.com/) oder fordern Sie ein[vorläufige Lizenz](https://purchase.aspose.com/temporary-license/) um alles auszuprobieren.

## Pakete importieren

Das Wichtigste zuerst: importieren wir die erforderlichen Pakete. Dadurch können wir mit allen relevanten Klassen zum Erstellen von Tabellen in PDF-Dokumenten arbeiten.

```csharp
using Aspose.Pdf.LogicalStructure;
using Aspose.Pdf.Tagged;
using Aspose.Pdf.Text;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

In diesem Abschnitt unterteilen wir den Vorgang zum Erstellen einer Tabelle in mehrere Schritte. Jeder Schritt konzentriert sich auf unterschiedliche Teile des Tabellenerstellungs- und Anpassungsprozesses.

## Schritt 1: Ein neues PDF-Dokument erstellen

Als Erstes müssen wir ein neues PDF-Dokument erstellen. Dieses dient als Container für unsere Tabelle.

```csharp
// Der Pfad zum Dokumentverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Neues PDF-Dokument erstellen
Document document = new Document();
```

 Hier initialisieren wir eine neue Instanz des`Document` Klasse, die unsere leere PDF-Datei sein wird. Vergessen Sie nicht, Ihren Dateipfad anzugeben!

## Schritt 2: Markierten Inhalt einrichten

Als Nächstes müssen wir getaggte Inhalte aktivieren, um die Zugänglichkeit der Tabelle sicherzustellen. Getaggte PDFs sind für die Einhaltung von PDF/UA (Universal Accessibility) erforderlich.

```csharp
// Markierten Inhalt aktivieren
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Example Table");
taggedContent.SetLanguage("en-US");
```

In diesem Schritt werden der Dokumenttitel und die Sprache festgelegt, um sicherzustellen, dass die Tabelle den Zugänglichkeitsstandards entspricht. Zugängliche Dokumente sind für die Benutzererfahrung und die gesetzlichen Anforderungen in einigen Branchen von entscheidender Bedeutung.

## Schritt 3: Erstellen des Tabellenelements

Jetzt kommt der spaßige Teil – das Erstellen der Tabelle selbst!

```csharp
// Holen Sie sich das Stammstrukturelement
StructureElement rootElement = taggedContent.RootElement;
TableElement tableElement = taggedContent.CreateTableElement();
rootElement.AppendChild(tableElement);
```

 Hier verwenden wir die`RootElement` des getaggten Inhalts, um unsere Tabelle anzuhängen. Dadurch wird im Wesentlichen eine Tabelle als untergeordneter Knoten zur Struktur des Dokuments hinzugefügt.

## Schritt 4: Tabellenränder und Überschriften anpassen

Sie möchten nicht, dass Ihr Tisch langweilig aussieht, oder? Lassen Sie uns etwas Stil hinzufügen!

```csharp
tableElement.Border = new BorderInfo(BorderSide.All, 1.2F, Color.DarkBlue);
TableTHeadElement tableTHeadElement = tableElement.CreateTHead();
TableTBodyElement tableTBodyElement = tableElement.CreateTBody();
TableTFootElement tableTFootElement = tableElement.CreateTFoot();
```

 Wir definieren Ränder und fügen der Tabelle Kopfzeilen, Textkörper und Fußzeilen hinzu. Beachten Sie die Verwendung von`BorderInfo` um die Tabellenränder mit einer dunkelblauen Farbe zu gestalten.

## Schritt 5: Zeilen und Zellen zur Tabelle hinzufügen

Füllen wir nun unsere Tabelle mit Zeilen und Zellen. In diesem Teil des Prozesses definieren wir das Layout unserer Tabelle.

### Schritt 5.1: Kopfzeile erstellen

```csharp
TableTRElement headTrElement = tableTHeadElement.CreateTR();
headTrElement.AlternativeText = "Head Row";
headTrElement.BackgroundColor = Color.LightGray;

for (int colIndex = 0; colIndex < 4; colIndex++)
{
    TableTHElement thElement = headTrElement.CreateTH();
    thElement.SetText($"Head {colIndex}");
    thElement.BackgroundColor = Color.GreenYellow;
    thElement.Border = new BorderInfo(BorderSide.All, 4.0F, Color.Gray);
    thElement.Alignment = HorizontalAlignment.Right;
}
```

 Wir erstellen eine Kopfzeile mit 4 Spalten und jede Kopfzeilenzelle erhält die Hintergrundfarbe`GreenYellow`. Wir legen auch einen Rahmen und eine Ausrichtung für die Überschriften fest.

### Schritt 5.2: Textzeilen hinzufügen

```csharp
for (int rowIndex = 0; rowIndex < 50; rowIndex++)
{
    TableTRElement trElement = tableTBodyElement.CreateTR();
    trElement.AlternativeText = $"Row {rowIndex}";

    for (int colIndex = 0; colIndex < 4; colIndex++)
    {
        TableTDElement tdElement = trElement.CreateTD();
        tdElement.SetText($"Cell [{rowIndex}, {colIndex}]");
        tdElement.BackgroundColor = Color.Yellow;
        tdElement.Alignment = HorizontalAlignment.Center;
    }
}
```

Hier erstellen wir dynamisch 50 Zeilen und 4 Spalten, füllen sie mit Text und formatieren die Zellen. Die Hintergrundfarbe ist auf Gelb eingestellt, der Text ist zentriert.

### Schritt 5.3: Fußzeile hinzufügen

```csharp
TableTRElement footTrElement = tableTFootElement.CreateTR();
footTrElement.AlternativeText = "Foot Row";
footTrElement.BackgroundColor = Color.LightSeaGreen;

for (int colIndex = 0; colIndex < 4; colIndex++)
{
    TableTDElement tdElement = footTrElement.CreateTD();
    tdElement.SetText($"Foot {colIndex}");
    tdElement.Alignment = HorizontalAlignment.Center;
}
```

 Um die Tabelle zu vervollständigen, fügen wir eine Fußzeile mit zentriertem Text und einem`LightSeaGreen` Hintergrund.

## Schritt 6: PDF/UA-Konformität validieren

Nachdem die Tabelle erstellt wurde, muss unbedingt sichergestellt werden, dass das PDF PDF/UA-kompatibel ist.

```csharp
document.Save(dataDir + "CreateTableElement.pdf");

// Validieren Sie die PDF/UA-Konformität
document = new Document(dataDir + "CreateTableElement.pdf");
bool isPdfUaCompliance = document.Validate(dataDir + "table.xml", PdfFormat.PDF_UA_1);
Console.WriteLine($"PDF/UA compliance: {isPdfUaCompliance}");
```

Dieses Snippet speichert die PDF-Datei und prüft, ob sie den PDF/UA-Konformitätsstandards entspricht. Wenn das Dokument konform ist, ist es für Benutzer mit Behinderungen zugänglich.

## Abschluss

Herzlichen Glückwunsch! Sie haben mit Aspose.PDF für .NET erfolgreich eine vollständig angepasste Tabelle in einem PDF erstellt. Von der Formatierung der Tabelle bis zur Sicherstellung der PDF/UA-Konformität verfügen Sie nun über eine solide Grundlage für die Generierung dynamischer Tabellen in Ihren PDF-Dokumenten. Vergessen Sie nicht, die umfangreichen Funktionen von Aspose.PDF zu erkunden, um Ihre Dokumente weiter zu verbessern!

## Häufig gestellte Fragen

### Kann ich die Schriftart und den Textstil der Tabelle anpassen?
Ja, Aspose.PDF ermöglicht Ihnen die vollständige Anpassung von Schriftarten, Textstilen und Ausrichtung mithilfe der`TextState` Klasse.

### Wie füge ich dynamisch weitere Spalten oder Zeilen hinzu?
 Sie können die Anzahl der Spalten oder Zeilen anpassen, indem Sie die`rowIndex` Und`colIndex` in den Schleifen.

### Ist es möglich, Zellen in der Tabelle zusammenzuführen?
 Ja, Sie können die`ColSpan` Und`RowSpan` Eigenschaften zum Zusammenführen von Zellen über Spalten oder Zeilen hinweg.

### Was ist PDF/UA-Konformität?
Durch die PDF/UA-Konformität wird sichergestellt, dass das Dokument für Benutzer mit Behinderungen zugänglich ist und internationalen Zugänglichkeitsstandards entspricht.

### Wie teste ich die PDF/UA-Konformität in Aspose.PDF?
 Sie können die`Validate` Methode, um zu überprüfen, ob das Dokument den PDF/UA-Standards entspricht.