---
title: Untergeordnetes Lesezeichen in PDF-Datei hinzufügen
linktitle: Untergeordnetes Lesezeichen in PDF-Datei hinzufügen
second_title: Aspose.PDF für .NET API-Referenz
description: Erfahren Sie in dieser Schritt-für-Schritt-Anleitung, wie Sie mit Aspose.PDF für .NET untergeordnete Lesezeichen in PDF-Dateien einfügen. Verbessern Sie Ihre PDF-Navigation.
type: docs
weight: 20
url: /de/net/programming-with-bookmarks/add-child-bookmark/
---
## Einführung

Im digitalen Zeitalter ist die effiziente Verwaltung von Dokumenten von entscheidender Bedeutung, insbesondere bei PDFs. Haben Sie schon einmal endlos durch eine lange PDF-Datei gescrollt, um einen bestimmten Abschnitt zu finden? Frustrierend, oder? Hier kommen Lesezeichen ins Spiel! Sie fungieren als Inhaltsverzeichnis und ermöglichen es den Lesern, problemlos durch das Dokument zu navigieren. In diesem Tutorial erfahren Sie, wie Sie mit Aspose.PDF für .NET untergeordnete Lesezeichen zu einer PDF-Datei hinzufügen. Am Ende dieses Handbuchs können Sie Ihre PDF-Dokumente verbessern und sie benutzerfreundlicher und übersichtlicher gestalten.

## Voraussetzungen

Bevor wir uns mit den Einzelheiten des Hinzufügens von Lesezeichen befassen, müssen Sie einige Dinge vorbereitet haben:

1.  Aspose.PDF für .NET: Stellen Sie sicher, dass Sie die Aspose.PDF-Bibliothek installiert haben. Sie können sie von der[Website](https://releases.aspose.com/pdf/net/).
2. Visual Studio: Eine Entwicklungsumgebung, in der Sie Ihren Code schreiben und testen können.
3. Grundkenntnisse in C#: Wenn Sie mit der C#-Programmierung vertraut sind, verstehen Sie die Codeausschnitte besser.

## Pakete importieren

Um zu beginnen, müssen Sie die erforderlichen Pakete in Ihr C#-Projekt importieren. So können Sie das tun:

### Neues Projekt erstellen

Öffnen Sie Visual Studio und erstellen Sie ein neues C#-Projekt. Wählen Sie der Einfachheit halber eine Konsolenanwendung.

### Aspose.PDF-Referenz hinzufügen

1. Klicken Sie im Projektmappen-Explorer mit der rechten Maustaste auf Ihr Projekt.
2. Wählen Sie „NuGet-Pakete verwalten“ aus.
3. Suchen Sie nach „Aspose.PDF“ und installieren Sie die neueste Version.

### Importieren der erforderlichen Namespaces

 Ganz oben auf Ihrer`Program.cs` Importieren Sie die erforderlichen Namespaces:

```csharp
using System;
using System.IO;
using Aspose.Pdf.Annotations;
using Aspose.Pdf;
```
Nachdem Sie nun alles eingerichtet haben, gehen wir nun Schritt für Schritt durch, wie Sie untergeordnete Lesezeichen hinzufügen.

## Schritt 1: Richten Sie Ihr Dokumentverzeichnis ein

Bevor Sie eine PDF-Datei bearbeiten können, müssen Sie angeben, wo Ihre Dokumente gespeichert sind. Dies ist wichtig, damit der Code Ihre PDF-Datei findet.

```csharp
// Der Pfad zum Dokumentverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Ersetzen`"YOUR DOCUMENT DIRECTORY"` mit dem tatsächlichen Pfad, in dem sich Ihre PDF-Datei befindet. Das ist, als ob Sie Ihrem Code eine Karte geben, mit der Sie den Schatz finden können!

## Schritt 2: Öffnen Sie das PDF-Dokument

Nachdem wir das Verzeichnis eingerichtet haben, ist es an der Zeit, das PDF-Dokument zu öffnen, mit dem Sie arbeiten möchten.

```csharp
// Dokument öffnen
Document pdfDocument = new Document(dataDir + "AddChildBookmark.pdf");
```

 Hier schaffen wir ein neues`Document` Objekt, das Ihre PDF-Datei lädt. Stellen Sie sich das so vor, als würden Sie ein Buch öffnen, um mit dem Lesen zu beginnen.

## Schritt 3: Ein übergeordnetes Lesezeichen erstellen

Als Nächstes erstellen wir ein übergeordnetes Lesezeichen. Dieses Lesezeichen dient als Hauptüberschrift, unter der wir untergeordnete Lesezeichen hinzufügen.

```csharp
// Übergeordnetes Lesezeichenobjekt erstellen
OutlineItemCollection pdfOutline = new OutlineItemCollection(pdfDocument.Outlines);
pdfOutline.Title = "Parent Outline";
pdfOutline.Italic = true;
pdfOutline.Bold = true;
```

 In diesem Snippet erstellen wir ein neues`OutlineItemCollection` für das übergeordnete Lesezeichen. Wir legen den Titel und den Stil (kursiv und fett) fest, damit es auffällt. Das ist, als würden Sie Ihrem Kapitel einen einprägsamen Titel geben!

## Schritt 4: Ein untergeordnetes Lesezeichen erstellen

Fügen wir nun unter dem gerade erstellten übergeordneten Lesezeichen ein untergeordnetes Lesezeichen hinzu.

```csharp
// Erstellen eines untergeordneten Lesezeichenobjekts
OutlineItemCollection pdfChildOutline = new OutlineItemCollection(pdfDocument.Outlines);
pdfChildOutline.Title = "Child Outline";
pdfChildOutline.Italic = true;
pdfChildOutline.Bold = true;
```

Ähnlich wie beim übergeordneten Lesezeichen erstellen wir ein untergeordnetes Lesezeichen mit eigenem Titel und Stil. Dieses untergeordnete Lesezeichen wird unter dem übergeordneten Lesezeichen verschachtelt, wodurch eine Hierarchie entsteht.

## Schritt 5: Das untergeordnete Lesezeichen dem übergeordneten Lesezeichen hinzufügen

Nachdem beide Lesezeichen erstellt wurden, ist es an der Zeit, sie miteinander zu verknüpfen.

```csharp
// Untergeordnetes Lesezeichen zur Sammlung übergeordneter Lesezeichen hinzufügen
pdfOutline.Add(pdfChildOutline);
```

Diese Codezeile fügt das untergeordnete Lesezeichen zur Sammlung des übergeordneten Lesezeichens hinzu. Das ist, als ob Sie eine Unterüberschrift unter einen Kapiteltitel setzen würden!

## Schritt 6: Das übergeordnete Lesezeichen zum Dokument hinzufügen

Nachdem wir nun unsere übergeordneten und untergeordneten Lesezeichen eingerichtet haben, müssen wir das übergeordnete Lesezeichen zur Gliederungssammlung des Dokuments hinzufügen.

```csharp
// Fügen Sie der Gliederungssammlung des Dokuments ein übergeordnetes Lesezeichen hinzu.
pdfDocument.Outlines.Add(pdfOutline);
```

Dieser Schritt stellt sicher, dass das übergeordnete Lesezeichen zusammen mit seinem untergeordneten Lesezeichen nun Teil des PDF-Dokuments ist. Es ist, als ob Sie Ihr Buch mit allen Kapiteln offiziell veröffentlichen würden!

## Schritt 7: Speichern Sie das Dokument

Zum Schluss speichern wir die Änderungen, die wir am PDF-Dokument vorgenommen haben.

```csharp
dataDir = dataDir + "AddChildBookmark_out.pdf";
// Ausgabe speichern
pdfDocument.Save(dataDir);
Console.WriteLine("\nChild bookmark added successfully.\nFile saved at " + dataDir);
```

Hier geben wir den Ausgabedateinamen an und speichern das Dokument. Sobald der Vorgang abgeschlossen ist, wird eine Bestätigungsmeldung angezeigt. Es ist, als ob Sie das Buch schließen, nachdem Sie Ihr Meisterwerk geschrieben haben!

## Abschluss

Herzlichen Glückwunsch! Sie haben mit Aspose.PDF für .NET erfolgreich untergeordnete Lesezeichen zu einer PDF-Datei hinzugefügt. Diese einfache, aber leistungsstarke Funktion kann die Benutzerfreundlichkeit Ihrer Dokumente erheblich verbessern und den Lesern die Navigation darin erleichtern. Egal, ob Sie Berichte, eBooks oder andere PDF-Dokumente erstellen, Lesezeichen sind ein echter Game-Changer.

## Häufig gestellte Fragen

### Was ist Aspose.PDF für .NET?
Aspose.PDF für .NET ist eine leistungsstarke Bibliothek, mit der Entwickler PDF-Dokumente programmgesteuert erstellen, bearbeiten und konvertieren können.

### Kann ich mehrere untergeordnete Lesezeichen hinzufügen?
Ja, Sie können mehrere untergeordnete Lesezeichen unter einem einzigen übergeordneten Lesezeichen erstellen, indem Sie die Schritte zum Erstellen und Hinzufügen untergeordneter Lesezeichen wiederholen.

### Ist die Nutzung von Aspose.PDF kostenlos?
 Aspose.PDF bietet eine kostenlose Testversion an, für die volle Funktionalität müssen Sie jedoch eine Lizenz erwerben. Schauen Sie sich die[Kaufen-Seite](https://purchase.aspose.com/buy) für weitere Details.

### Wo finde ich weitere Dokumentation?
 Eine umfassende Dokumentation finden Sie auf Aspose.PDF für .NET[Hier](https://reference.aspose.com/pdf/net/).

### Was ist, wenn ich auf Probleme stoße?
Wenn Sie auf Probleme stoßen, finden Sie Hilfe auf der[Aspose-Supportforum](https://forum.aspose.com/c/pdf/10).
