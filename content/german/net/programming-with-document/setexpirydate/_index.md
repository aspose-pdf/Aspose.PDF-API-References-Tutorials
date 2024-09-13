---
title: Ablaufdatum in PDF-Datei festlegen
linktitle: Ablaufdatum in PDF-Datei festlegen
second_title: Aspose.PDF für .NET API-Referenz
description: Erfahren Sie, wie Sie mit Aspose.PDF für .NET ein Ablaufdatum in PDF-Dateien festlegen. Verbessern Sie die Dokumentensicherheit mit dieser Schritt-für-Schritt-Anleitung.
type: docs
weight: 300
url: /de/net/programming-with-document/setexpirydate/
---
## Einführung

Im heutigen digitalen Zeitalter ist die Verwaltung und Sicherung von Dokumenten wichtiger denn je. Stellen Sie sich vor, Sie versenden eine PDF-Datei, auf die nach einem bestimmten Datum automatisch nicht mehr zugegriffen werden kann. Klingt wie Zauberei, oder? Mit Aspose.PDF für .NET können Sie ganz einfach ein Ablaufdatum für Ihre PDF-Dateien festlegen. Diese Funktion ist besonders nützlich für vertrauliche Dokumente, deren Zugriff nach einem bestimmten Zeitraum eingeschränkt werden muss. In diesem Tutorial führen wir Sie Schritt für Schritt durch den Vorgang zum Festlegen eines Ablaufdatums in einer PDF-Datei. Also, schnappen Sie sich Ihren Programmierhut und legen Sie los!

## Voraussetzungen

Bevor wir beginnen, müssen Sie einige Dinge vorbereitet haben:

1. Entwicklungsumgebung: Stellen Sie sicher, dass Sie eine .NET-Entwicklungsumgebung eingerichtet haben. Dies kann Visual Studio oder eine andere IDE sein, die .NET unterstützt.
2.  Aspose.PDF für .NET: Sie müssen die Aspose.PDF-Bibliothek installiert haben. Wenn Sie dies noch nicht getan haben, können Sie es hier herunterladen:[Hier](https://releases.aspose.com/pdf/net/).
3. Grundkenntnisse in C#: Dieses Tutorial setzt voraus, dass Sie über Grundkenntnisse in der C#-Programmierung verfügen. Wenn Sie neu bei C# sind, machen Sie sich keine Sorgen! Wir halten es einfach und unkompliziert.

## Pakete importieren

Um mit Aspose.PDF zu beginnen, müssen Sie die erforderlichen Namespaces in Ihr C#-Projekt importieren. So können Sie es tun:

```csharp
using System.IO;
using System;
using Aspose.Pdf;
using Aspose.Pdf.Annotations;
using Aspose.Pdf.Text;
```

Diese Namespaces bieten Ihnen Zugriff auf die Kernfunktionen, die für die Arbeit mit PDF-Dokumenten in Aspose.PDF erforderlich sind.

## Schritt 1: Richten Sie Ihr Dokumentverzeichnis ein

Als Erstes müssen Sie den Pfad zu Ihrem Dokumentverzeichnis angeben. Hier wird Ihr Ausgabe-PDF gespeichert. 

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Ersetzen`"YOUR DOCUMENT DIRECTORY"` durch den tatsächlichen Pfad, in dem Sie Ihre PDF-Datei speichern möchten. Das ist, als würden Sie Ihrem Programm sagen: „Hey, hier bewahre ich meine Dateien auf!“

## Schritt 2: Instanziieren des Dokumentobjekts

 Als nächstes müssen Sie eine neue Instanz des`Document` Klasse. Dies ist Ihre Leinwand, auf der Sie Ihr PDF erstellen.

```csharp
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
```

 Denken Sie an die`Document` Objekt als leeres Blatt Papier. Sie können es beliebig mit Inhalt füllen!

## Schritt 3: Eine Seite zum PDF hinzufügen

Nachdem Sie Ihr Dokument eingerichtet haben, ist es an der Zeit, eine Seite hinzuzufügen. Hier wird Ihr Inhalt platziert.

```csharp
doc.Pages.Add();
```

Sie haben gerade eine neue Seite in Ihrem PDF erstellt. Das ist, als würden Sie Ihrem Notizbuch eine neue Seite hinzufügen, auf der Sie Ihre Gedanken notieren können.

## Schritt 4: Text zur Seite hinzufügen

Lassen Sie uns diese Seite etwas interessanter gestalten, indem wir etwas Text hinzufügen. Wir werden eine einfache „Hallo Welt“-Nachricht hinzufügen.

```csharp
doc.Pages[1].Paragraphs.Add(new TextFragment("Hello World..."));
```

Diese Codezeile fügt der ersten Seite Ihrer PDF-Datei ein Textfragment hinzu. Das ist, als würden Sie oben auf Ihrer Seite einen Titel schreiben!

## Schritt 5: JavaScript für Ablaufdatum erstellen

Jetzt kommt der spaßige Teil! Sie erstellen eine JavaScript-Aktion, die das Ablaufdatum der PDF-Datei überprüft. Wenn das aktuelle Datum das Ablaufdatum überschreitet, wird der Benutzer durch eine Meldung darauf hingewiesen.

```csharp
JavascriptAction javaScript = new JavascriptAction(
"var year=2017;"
+ "var month=5;"
+ "today = new Date(); today = new Date(today.getFullYear(), today.getMonth());"
+ "expiry = new Date(year, month);"
+ "if (today.getTime() > expiry.getTime())"
+ "app.alert('The file is expired. You need a new one.');");
```

Folgendes ist passiert:
- Das Ablaufjahr und den Ablaufmonat legen Sie selbst fest.
- Sie erhalten das heutige Datum.
- Sie vergleichen das heutige Datum mit dem Verfallsdatum.
- Wenn das heutige Datum das Ablaufdatum überschritten hat, erscheint eine Meldung!

## Schritt 6: JavaScript als PDF-Öffnen-Aktion festlegen

Nun müssen Sie die JavaScript-Aktion als Öffnungsaktion für Ihr PDF-Dokument festlegen. Das bedeutet, dass das JavaScript ausgeführt wird, sobald das PDF geöffnet wird.

```csharp
doc.OpenAction = javaScript;
```

Diese Zeile weist das PDF an, JavaScript auszuführen, wenn es jemand öffnet. Das ist, als ob Sie eine Erinnerung einrichten, die ausgelöst wird, sobald Sie Ihren Kalender öffnen!

## Schritt 7: Speichern Sie das PDF-Dokument

Schließlich ist es an der Zeit, Ihr PDF-Dokument mit der Ablaufdatumsfunktion zu speichern. 

```csharp
dataDir = dataDir + "SetExpiryDate_out.pdf";
doc.Save(dataDir);
```

Diese Zeile speichert Ihr PDF im angegebenen Verzeichnis unter dem Namen „SetExpiryDate_out.pdf“. Es ist, als ob Sie Ihr fertiges Kunstwerk in einen Rahmen stecken würden!

## Abschluss

Und da haben Sie es! Sie haben erfolgreich eine PDF-Datei mit Ablaufdatum mit Aspose.PDF für .NET erstellt. Diese Funktion erhöht nicht nur die Sicherheit, sondern sorgt auch dafür, dass vertrauliche Informationen unter Kontrolle bleiben. Egal, ob Sie Verträge, Berichte oder andere wichtige Dokumente versenden, das Festlegen eines Ablaufdatums kann entscheidend sein.

## Häufig gestellte Fragen

### Was ist Aspose.PDF für .NET?
Aspose.PDF für .NET ist eine leistungsstarke Bibliothek, mit der Entwickler PDF-Dokumente in .NET-Anwendungen erstellen, bearbeiten und konvertieren können.

### Kann ich Aspose.PDF kostenlos nutzen?
 Ja, Sie können eine kostenlose Testversion von Aspose.PDF verwenden. Sie können es herunterladen[Hier](https://releases.aspose.com/).

### Wie kaufe ich Aspose.PDF?
Sie können Aspose.PDF kaufen, indem Sie die[Kaufseite](https://purchase.aspose.com/buy).

### Was ist, wenn ich Unterstützung brauche?
Wenn Sie Fragen haben oder Hilfe benötigen, besuchen Sie bitte die[Aspose-Supportforum](https://forum.aspose.com/c/pdf/10).

### Kann ich eine temporäre Lizenz für Aspose.PDF erhalten?
 Ja, Sie können eine temporäre Lizenz anfordern[Hier](https://purchase.aspose.com/temporary-license/).