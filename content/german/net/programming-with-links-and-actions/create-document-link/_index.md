---
title: Dokumentverknüpfung erstellen
linktitle: Dokumentverknüpfung erstellen
second_title: Aspose.PDF für .NET API-Referenz
description: Entdecken Sie, wie Sie mit Aspose.PDF für .NET Dokumentlinks in PDFs erstellen. Verbessern Sie die Navigation und Interaktivität in Ihren PDF-Dokumenten.
type: docs
weight: 30
url: /de/net/programming-with-links-and-actions/create-document-link/
---
## Einführung

Das Erstellen von Links in PDF-Dokumenten kann das Benutzererlebnis erheblich verbessern und die Navigation reibungsloser und intuitiver gestalten. Wenn Sie sich schon einmal in einem PDF verirrt haben und verzweifelt nach der richtigen Seite gesucht haben, wissen Sie, wie wichtig Links sein können. In diesem Handbuch erfahren Sie, wie Sie Dokumentlinks mit Aspose.PDF für .NET erstellen, einer leistungsstarken Bibliothek, mit der Entwickler PDF-Dateien problemlos verwalten können. Egal, ob Sie einen Bericht, ein eBook oder interaktive Inhalte erstellen, die Möglichkeit, solche Links zu erstellen, kann die Benutzerfreundlichkeit Ihres Dokuments verbessern.

## Voraussetzungen

Bevor Sie in die Welt der PDF-Bearbeitung mit Aspose.PDF für .NET eintauchen, stellen Sie sicher, dass Sie über einige grundlegende Voraussetzungen verfügen:

- Visual Studio: Stellen Sie sicher, dass Sie Visual Studio installiert haben, um .NET-Anwendungen zu erstellen und auszuführen.
- Aspose.PDF für .NET: Sie benötigen die Aspose.PDF-Bibliothek. Sie können[Laden Sie es hier herunter](https://releases.aspose.com/pdf/net/).
- Grundlegende Kenntnisse in C#: Grundlegende Kenntnisse der C#-Programmierung helfen Ihnen, mühelos durch die Codeausschnitte zu navigieren.

### Installieren von Aspose.PDF für .NET

Um Aspose.PDF für .NET zu installieren, können Sie den NuGet-Paketmanager in Visual Studio verwenden. So geht's:

1. Öffnen Sie Ihr Projekt: Starten Sie Visual Studio und öffnen Sie Ihr vorhandenes Projekt oder erstellen Sie ein neues.
   
2. NuGet-Paket-Manager: Klicken Sie im Projektmappen-Explorer mit der rechten Maustaste auf das Projekt.
   
3. NuGet-Pakete verwalten: Wählen Sie die Option „NuGet-Pakete verwalten“.

4. Suchen Sie nach Aspose.PDF: Geben Sie auf der Registerkarte „Durchsuchen“ „Aspose.PDF“ ein und installieren Sie die neueste Version.

5. Installation überprüfen: Stellen Sie sicher, dass sie in Ihren Projektreferenzen angezeigt wird.

Sobald Sie alles eingerichtet haben, können Sie loslegen!

## Pakete importieren

Um mit der Arbeit mit Aspose.PDF für .NET zu beginnen, besteht der erste Schritt darin, die erforderlichen Namespaces in Ihre C#-Datei zu importieren:

```csharp
using System.IO;
using Aspose.Pdf.Annotations;
using Aspose.Pdf;
using System;
```

Diese Namespaces enthalten die erforderlichen Klassen und Funktionen für die Handhabung von PDF-Dokumenten und Anmerkungen. Lassen Sie uns nun die Aufgabe zum Erstellen eines Dokumentlinks in umsetzbare Schritte unterteilen.

Das Erstellen eines Dokumentlinks ist wie das Pflastern einer Straße zwischen zwei Punkten. Sorgen wir dafür, dass diejenigen, die durch Ihr PDF navigieren, dies problemlos tun können!

## Schritt 1: Definieren Sie Ihr Dokumentverzeichnis

Bei jedem Programmiervorhaben ist Organisation der Schlüssel! Beginnen Sie damit, anzugeben, wo sich Ihre Dokumente befinden. So bleiben Ihre Pfade klar und Ihre Dateien zugänglich.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Ersetzen`"YOUR DOCUMENT DIRECTORY"` mit dem Pfad zum Verzeichnis, in dem Ihre PDF-Dateien gespeichert sind. Das könnte so etwas sein wie`"C:\\Documents\\"`, abhängig von Ihrer Konfiguration.

## Schritt 2: Öffnen Sie das PDF-Dokument

Jetzt ist es an der Zeit, das PDF-Dokument zu öffnen, mit dem Sie arbeiten möchten. Hier beginnt Ihre Reise!

```csharp
Document document = new Document(dataDir + "CreateDocumentLink.pdf");
```

 In dieser Zeile erstellen wir eine Instanz des`Document` Klasse und laden unsere Ziel-PDF-Datei. Stellen Sie sicher, dass die Datei „CreateDocumentLink.pdf“ im angegebenen Verzeichnis vorhanden ist, sonst stoßen Sie auf ein kleines Hindernis.

## Schritt 3: Seite für Link-Erstellung festlegen

Als nächstes müssen Sie festlegen, auf welcher Seite Ihres Dokuments der Link erscheinen soll. Angenommen, Sie möchten diesen Link auf der ersten Seite haben.

```csharp
Page page = document.Pages[1];
```

Die Seiten sind in Aspose nullindexiert, d. h. Sie beginnen für den Benutzer bei 1 zu zählen. Dieser Schritt bereitet die Bühne für das Hinzufügen Ihres Links vor.

## Schritt 4: Erstellen Sie die Linkanmerkung

 Das Klicken auf einen Link sollte irgendwohin führen! Lassen Sie uns einen`LinkAnnotation` auf den die Benutzer klicken. Dies ist der Moment, in dem Ihr Link tatsächlich Gestalt annimmt.

```csharp
LinkAnnotation link = new LinkAnnotation(page, new Aspose.Pdf.Rectangle(100, 100, 300, 300));
```

 Hier definiert das Rechteck den anklickbaren Bereich für den Link. Die Parameter`(100, 100, 300, 300)` stellen die Koordinaten des Rechtecks dar (links, unten, rechts, oben). Passen Sie diese Zahlen an die gewünschte Größe des Linkbereichs an.

## Schritt 5: Link-Erscheinungsbild anpassen

Lassen Sie uns nun dafür sorgen, dass der Link etwas hervorsticht! Sie können seine Farbe und sein Verhalten beim Anklicken anpassen.

```csharp
link.Color = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Green);
link.Action = new GoToRemoteAction(dataDir + "RemoveOpenAction.pdf", 1);
```

Hier haben wir die Farbe des Links auf Grün gesetzt und eine Aktion dafür definiert: Navigieren zu einem anderen PDF-Dokument mit dem Namen „RemoveOpenAction.pdf“ ab Seite 1. Sie können den Dateinamen und die Seitenzahl durch Ihr gewünschtes Ziel ersetzen.

## Schritt 6: Link-Anmerkung zur Seite hinzufügen

Wenn Ihr Link fertig ist, ist es an der Zeit, ihn wie einen Faden an einer Nadel an der Seite zu befestigen. 

```csharp
page.Annotations.Add(link);
```

Genau das macht diese Zeile. Sie fügt unsere neu erstellte Link-Anmerkung zur angegebenen Seite hinzu und macht sie so zu einem interaktiven Element in Ihrer PDF-Datei.

## Schritt 7: Speichern Sie Ihr aktualisiertes Dokument

Alles Gute hat ein Ende. Und jetzt ist es an der Zeit, das Dokument mit dem neuen Link zu speichern. 

```csharp
dataDir = dataDir + "CreateDocumentLink_out.pdf";
document.Save(dataDir);
```

Hier geben wir einen neuen Dateinamen an (das „_out.pdf“ zeigt an, dass es sich um eine geänderte Kopie handelt) und speichern Sie das Dokument, um sicherzustellen, dass Ihre gesamte harte Arbeit erhalten bleibt.

## Schritt 8: Konsolenbestätigung

Zum Schluss: Eine kleine Bestätigung schadet nie! Lassen Sie uns selbst eine Benachrichtigung senden, dass der Link-Erstellungsprozess erfolgreich war.

```csharp
Console.WriteLine("\nDocument link created successfully.\nFile saved at " + dataDir);
```

Dass alles reibungslos geklappt hat, wird durch die Verwendung dieser Zeile deutlich.

## Abschluss

Und da haben Sie es! Mit Aspose.PDF für .NET können Sie ganz einfach funktionale, optisch ansprechende Dokumentlinks in Ihren PDF-Dateien erstellen. Indem Sie diese einfachen Schritte befolgen, können Sie die Interaktivität Ihrer Dokumente verbessern und den Lesern die Navigation erleichtern. Warum also mit einem statischen PDF zufrieden sein, wenn ein klickbares Erlebnis nur ein paar Codezeilen entfernt ist? 

## Häufig gestellte Fragen

### Wofür wird Aspose.PDF für .NET verwendet?
Aspose.PDF für .NET ist eine Bibliothek, die es Entwicklern ermöglicht, PDF-Dokumente programmgesteuert zu erstellen, zu bearbeiten und zu konvertieren.

### Kann ich Links zu externen Websites erstellen?
 Ja, Sie können Links zu externen Websites erstellen, indem Sie die Link-Aktion ändern in`GoToRemoteAction` mit der URL.

### Gibt es eine kostenlose Testversion?
 Absolut! Sie können[Laden Sie hier die kostenlose Testversion herunter](https://releases.aspose.com/).

### Wo erhalte ich Unterstützung, wenn Probleme auftreten?
 Sie erreichen uns unter[Aspose Support Forum](https://forum.aspose.com/c/pdf/10) um Hilfe.

### Wie erhalte ich eine vorläufige Lizenz?
 Eine temporäre Lizenz erhalten Sie über die[Seite mit der temporären Lizenz](https://purchase.aspose.com/temporary-license/).