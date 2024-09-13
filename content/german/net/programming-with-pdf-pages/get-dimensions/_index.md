---
title: PDF-Seitenabmessungen abrufen
linktitle: PDF-Seitenabmessungen abrufen
second_title: Aspose.PDF für .NET API-Referenz
description: In diesem Tutorial erklären wir, wie Sie PDF-Seitenabmessungen ermitteln und mit Aspose.PDF für .NET Manipulationen durchführen. Detaillierte Schritte führen Sie durch den Vorgang.
type: docs
weight: 60
url: /de/net/programming-with-pdf-pages/get-dimensions/
---
## Einführung

Mussten Sie schon einmal die Seitenmaße eines PDF-Dokuments ändern? Vielleicht wollten Sie die Größe einer Seite ändern oder sie drehen, um sie Ihren Anforderungen anzupassen? In diesem Fall sind Sie hier richtig! In diesem Tutorial führen wir Sie durch das Abrufen und Ändern der PDF-Seitenmaße mit Aspose.PDF für .NET. Egal, ob Sie Anfänger oder erfahrener Entwickler sind, Sie werden diese Anleitung einfach und leicht verständlich finden.

Aspose.PDF für .NET ist eine leistungsstarke Bibliothek, mit der Sie mühelos PDF-Dateien erstellen, bearbeiten und transformieren können. Es ist wie ein Schweizer Taschenmesser für PDFs – Sie können jedes kleine Detail genau an Ihre Anforderungen anpassen. Lassen Sie uns also direkt eintauchen und lernen, wie Sie mit diesem fantastischen Tool PDF-Seitenabmessungen abrufen und aktualisieren können!

## Voraussetzungen

Bevor Sie beginnen, müssen einige Dinge bereit sein, damit Sie diesem Tutorial problemlos folgen können:

1.  Aspose.PDF für .NET: Sie können[Laden Sie hier die neueste Version herunter](https://releases.aspose.com/pdf/net/) . Wenn Sie keine Lizenz haben, machen Sie sich keine Sorgen! Sie können eine[Kostenlose Testversion](https://releases.aspose.com/) oder entscheiden Sie sich für eine[vorläufige Lizenz](https://purchase.aspose.com/temporary-license/).
2. Visual Studio: Die Entwicklungsumgebung, die Sie zum Schreiben und Ausführen des Codes verwenden.
3. Grundkenntnisse in C#: Wir halten die Dinge zwar einfach, aber eine gewisse Vertrautheit mit C# wird den Prozess reibungsloser gestalten.
4. Zum Arbeiten geeignete PDF-Datei: Greifen Sie auf eine beliebige Beispiel-PDF-Datei zu oder erstellen Sie zum Testen eine neue.

## Pakete importieren

Um mit Aspose.PDF für .NET zu arbeiten, müssen Sie einige wichtige Namespaces importieren. Dies schafft die Voraussetzungen für die Interaktion mit PDF-Dokumenten. So geht's:

```csharp
using System.IO;
using System;
using Aspose.Pdf;
```

Diese Importe stellen sicher, dass Sie Zugriff auf die Kernklassen haben, die zum Bearbeiten von PDF-Dateien erforderlich sind, insbesondere zum Verwalten von Seiten und Abrufen ihrer Abmessungen.

Nachdem wir nun alles vorbereitet haben, unterteilen wir den Vorgang in leicht verständliche Schritte.

## Schritt 1: Dateipfad festlegen und Dokument laden

Der erste Schritt besteht darin, den Pfad zu Ihrem PDF-Dokument anzugeben und es mit Aspose.PDF zu laden. Dadurch können Sie mit den Seiten in der PDF-Datei interagieren.

```csharp
// Der Pfad zum Dokumentverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Dokument öffnen
Document pdfDocument = new Document(dataDir + "UpdateDimensions.pdf");
```

In diesem Schritt öffnen Sie im Wesentlichen die PDF-Datei, an der Sie arbeiten möchten. Wenn Sie schon einmal eine bestimmte Seite eines Buches geöffnet haben, ist dies ganz ähnlich – aber stattdessen öffnen Sie ein PDF-Dokument, um auf dessen Seiten zuzugreifen.

## Schritt 2: Fügen Sie eine leere Seite hinzu, wenn keine Seiten vorhanden sind

Was ist, wenn Ihr Dokument keine Seiten hat? Keine Sorge! Wir können dem Dokument eine leere Seite hinzufügen und damit arbeiten. So prüfen Sie, ob eine Seite vorhanden ist, und fügen bei Bedarf eine neue hinzu:

```csharp
// Fügt dem PDF-Dokument eine leere Seite hinzu
Page page = pdfDocument.Pages.Count > 0 ? pdfDocument.Pages[1] : pdfDocument.Pages.Add();
```

Diese Codezeile prüft, ob das Dokument bereits eine Seite enthält. Wenn ja, wird die erste Seite ausgewählt (`Pages[1]`). Andernfalls wird eine leere Seite erstellt und der PDF-Datei hinzugefügt.

Stellen Sie es sich so vor, als würden Sie ein leeres Notizbuch öffnen und auf die erste Seite schreiben, wenn dort nichts ist – einfach, oder?

## Schritt 3: Informationen zur Seitenhöhe und -breite abrufen

 Da wir nun eine Seite haben, mit der wir arbeiten können, können wir die Abmessungen der Seite ermitteln. Wir verwenden dazu die`GetPageRect()` Methode zum Abrufen der Höhe und Breite.

```csharp
// Informationen zur Seitenhöhe und -breite abrufen
Console.WriteLine(page.GetPageRect(true).Width.ToString() + ":" + page.GetPageRect(true).Height.ToString());
```

 Hier,`GetPageRect(true)` gibt ein Rechteck zurück, das die Höhe und Breite der Seite umfasst. Es ist, als würde man ein Stück Papier mit einem Lineal messen. Die Ausgabe wird in der Konsole angezeigt und gibt Ihnen die aktuellen Seitenabmessungen an.

## Schritt 4: Drehen Sie die Seite um 90 Grad

Du möchtest die Seite drehen? Kein Problem! Mit einer einfachen Eigenschaft kannst du die Seite um 90 Grad drehen.

```csharp
// Seite um 90 Grad drehen
page.Rotate = Rotation.on90;
```

Dieser Schritt dreht die Seite im Uhrzeigersinn um 90 Grad. Stellen Sie sich vor, Sie drehen ein ausgedrucktes Blatt auf Ihrem Schreibtisch um – jetzt ist es im Querformat!

## Schritt 5: Überprüfen Sie die Seitenabmessungen nach der Drehung erneut

Nach dem Drehen der Seite ist es sinnvoll, die Abmessungen noch einmal zu überprüfen. Warum? Weil die Drehung Ihre Interpretation von Höhe und Breite beeinflussen kann.

```csharp
// Informationen zur Seitenhöhe und -breite abrufen
Console.WriteLine(page.GetPageRect(true).Width.ToString() + ":" + page.GetPageRect(true).Height.ToString());
```

Jetzt werden die Seitenmaße basierend auf der neuen Ausrichtung aktualisiert. Es ist, als würden Sie ein Foto auf Ihrem Telefon drehen – plötzlich wird die Breite zur Höhe und umgekehrt.


## Abschluss

Herzlichen Glückwunsch! Sie haben erfolgreich gelernt, wie Sie die Abmessungen einer PDF-Seite mit Aspose.PDF für .NET abrufen und ändern können. Jetzt sollten Sie in der Lage sein, eine PDF-Datei zu laden, ihre Seitenabmessungen zu überprüfen und die Seite bei Bedarf sogar zu drehen.

Das Bearbeiten von PDFs muss nicht kompliziert sein. Mit Aspose.PDF ist es ganz einfach, indem Sie ein paar Schritte befolgen und intuitive Methoden verwenden. Wenn Sie also das nächste Mal mit den Seitenabmessungen von PDFs umgehen müssen, wissen Sie genau, was zu tun ist!

## Häufig gestellte Fragen

### Kann ich die Seite auch um andere Winkel als 90 Grad drehen?
 Ja, Aspose.PDF ermöglicht Ihnen das Drehen von Seiten um 0, 90, 180 oder 270 Grad mit dem`Rotation` Eigentum.

### Was passiert, wenn mein PDF keine Seiten hat?
 Wenn Ihr PDF keine Seiten hat, können Sie eine leere Seite hinzufügen mit dem`Pages.Add()` Methode, wie in diesem Tutorial gezeigt.

### Kann ich mehrere Seiten gleichzeitig bearbeiten?
Ja, Sie können mehrere Seiten durchlaufen und auf alle Transformationen anwenden, z. B. die Größe ändern oder drehen.

### Haben die Seitenabmessungen Auswirkungen auf den Inhalt der PDF-Datei?
Seitenabmessungen ändern nur die Größe der Leinwand, nicht den Inhalt. Eine Größenänderung kann jedoch die Darstellung des Inhalts auf der Seite verändern.

### Wo finde ich weitere Informationen zu Aspose.PDF für .NET?
 Besuchen Sie die[Dokumentation hier](https://reference.aspose.com/pdf/net/) für ausführlichere Informationen und erweiterte Anwendungsfälle.