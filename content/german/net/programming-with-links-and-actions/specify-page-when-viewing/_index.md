---
title: Seite beim Anzeigen angeben
linktitle: Seite beim Anzeigen angeben
second_title: Aspose.PDF für .NET API-Referenz
description: Erfahren Sie, wie Sie mit Aspose.PDF für .NET eine Seite angeben, die in einer PDF-Datei angezeigt werden soll. Verbessern Sie die Benutzernavigation mit dieser einfachen Anleitung.
type: docs
weight: 110
url: /de/net/programming-with-links-and-actions/specify-page-when-viewing/
---
## Einführung

Möchten Sie Ihre PDF-Anwendungen verbessern, indem Sie Benutzer beim Öffnen eines Dokuments auf bestimmte Seiten leiten? Dann sind Sie hier genau richtig! In diesem Handbuch werden wir uns eingehend mit der Verwendung von Aspose.PDF für .NET befassen, um die Seite anzugeben, die beim Öffnen einer PDF-Datei angezeigt werden soll. Diese Funktion kann das Benutzererlebnis erheblich verbessern, insbesondere wenn Sie die Aufmerksamkeit auf kritische Abschnitte Ihres Dokuments lenken müssen.

## Voraussetzungen

Bevor wir uns in die Programmierung stürzen, stellen wir sicher, dass Sie alles haben, was Sie zum Starten brauchen. Folgendes benötigen Sie:

1. Grundkenntnisse in .NET: Kenntnisse des .NET-Frameworks sind unerlässlich. Wenn Sie mit C# vertraut sind und über Grundkenntnisse in objektorientierter Programmierung verfügen, sind Sie startklar!

2.  Aspose.PDF für .NET: Sie müssen die Aspose.PDF-Bibliothek in Ihrem Projekt installiert haben. Wenn Sie sie noch nicht installiert haben, können Sie sie herunterladen[Hier](https://releases.aspose.com/pdf/net/).

3. Visual Studio: Dieses Tutorial setzt voraus, dass Sie Visual Studio als IDE verwenden. Stellen Sie sicher, dass es auf Ihrem Computer installiert ist.

4. Eine PDF-Datei: Sie benötigen eine vorhandene PDF-Datei, mit der Sie arbeiten. Wenn Sie keine haben, können Sie ein Beispieldokument erstellen oder eine beliebige PDF-Datei Ihrer Wahl verwenden.

Sobald diese Voraussetzungen erfüllt sind, können wir die Ärmel hochkrempeln und mit dem Programmieren beginnen!

## Pakete importieren

Nachdem wir nun alles eingerichtet haben, importieren wir die erforderlichen Pakete in unser Projekt. Folgen Sie diesen Schritten:

### Starten Sie Visual Studio

Öffnen Sie Visual Studio und erstellen Sie entweder ein neues Projekt oder laden Sie ein vorhandenes, in dem Sie die Funktion zur PDF-Seitenanzeige implementieren möchten.

### Referenz Aspose.PDF

Um die Aspose.PDF-Bibliothek zu verwenden, müssen Sie einen Verweis darauf hinzufügen:

1. Klicken Sie im Projektmappen-Explorer mit der rechten Maustaste auf Ihr Projekt.
2. Wählen Sie „NuGet-Pakete verwalten“ aus.
3.  Suchen nach`Aspose.PDF` und installieren Sie das Paket.

### Namespaces importieren

Fügen Sie oben in Ihrer Codedatei die folgende Using-Direktive hinzu:

```csharp
using System;
using System.IO;
using Aspose.Pdf.Annotations;
using Aspose.Pdf;
```

Jetzt können Sie mit dem Erstellen der Navigationslogik für Ihre PDF-Seite beginnen!

Lassen Sie uns unsere Aufgabe in überschaubare Schritte unterteilen. Wir schreiben Code, der ein PDF-Dokument öffnet, eine bestimmte Seite angibt, die beim Anzeigen angezeigt werden soll, und das aktualisierte Dokument speichert. 

## Schritt 1: Dokumentverzeichnis festlegen

Zuerst müssen Sie den Pfad zu Ihren Dokumenten festlegen:

```csharp
// Der Pfad zum Dokumentverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY"; // Ersetzen Sie es durch Ihr Verzeichnis
```

 Diese Zeile ist im Wesentlichen Ihre Roadmap. Sie sagen Ihrem Code, wo die PDF-Datei zu finden ist. Stellen Sie sicher, dass Sie ersetzen`YOUR DOCUMENT DIRECTORY` durch den tatsächlichen Pfad auf Ihrem Computer.

## Schritt 2: Laden Sie die PDF-Datei

Als nächstes laden Sie die PDF-Datei in Ihre Anwendung:

```csharp
// Laden Sie die PDF-Datei
Document doc = new Document(dataDir + "SpecifyPageWhenViewing.pdf");
```

 Was hier passiert, ist, dass Sie eine neue Instanz eines`Document`Objekt, während Sie den Pfad zu Ihrer PDF-Datei angeben. Sie können es sich so vorstellen, als würden Sie das Buch öffnen, das Sie gerade auf den Tisch gelegt haben.

## Schritt 3: Rufen Sie die gewünschte Seite auf

Greifen wir nun auf die Seite zu, die beim Öffnen des Dokuments angezeigt werden soll:

```csharp
// Holen Sie sich die Instanz der zweiten Seite des Dokuments
Page page2 = doc.Pages[2]; // Denken Sie daran, die Indizierung beginnt bei 1
```

Hier greifen wir auf die zweite Seite Ihres Dokuments zu. Beachten Sie, dass die Seitennummerierung in diesem Zusammenhang bei 1 beginnt. Wenn Sie also an Seite 2 denken, müssen Sie einen Index von 2 verwenden.

## Schritt 4: Zoomfaktor einstellen

Sie können die Zoomstufe der anzuzeigenden Seite anpassen:

```csharp
// Erstellen Sie die Variable, um den Zoomfaktor der Zielseite festzulegen
double zoom = 1; // 1 bedeutet 100 % Zoom
```

Durch Festlegen eines Zoomfaktors können Sie bestimmen, wie viel von der Seite der Benutzer unmittelbar nach dem Öffnen sieht. Ein Wert von 1 bedeutet, dass die Seite mit 100 % Zoom angezeigt wird, was im Allgemeinen ein guter Standardwert ist.

## Schritt 5: Erstellen der GoToAction-Instanz

Lassen Sie uns die Navigationsfunktionen in Aktion erleben:

```csharp
// Erstellen einer GoToAction-Instanz
GoToAction action = new GoToAction(doc.Pages[2]); 
```

 In diesem Schritt erstellen Sie eine Instanz von`GoToAction` Dies stellt im Wesentlichen die Aktion dar, zu einem bestimmten Punkt im PDF zu navigieren – in diesem Fall zur zweiten Seite.

## Schritt 6: Ziel festlegen

Nun müssen Sie definieren, wohin die Aktion führen soll:

```csharp
// Gehe zu Seite 2
action.Destination = new XYZExplicitDestination(page2, 0, page2.Rect.Height, zoom);
```

Diese Zeile ist wie das Festlegen eines GPS-Ziels für die GoToAction. Sie sagen ihr, dass sie zur Seite 2 oben auf der Seite (Höhe) und mit der angegebenen Zoomstufe gehen soll.

## Schritt 7: Festlegen der Öffnungsaktion

Stellen wir sicher, dass diese Aktion beim Öffnen des Dokuments stattfindet:

```csharp
// Festlegen der Aktion zum Öffnen des Dokuments
doc.OpenAction = action;
```

Damit haben Sie festgelegt, dass beim Öffnen Ihrer PDF-Datei die soeben definierte Navigationsaktion aktiviert wird. Es ist, als hätten Sie die Fußmatte vor die Eingangstür Ihres Dokuments gelegt.

## Schritt 8: Speichern Sie das aktualisierte Dokument

Abschließend speichern wir das Dokument mit den vorgenommenen Änderungen:

```csharp
// Aktualisiertes Dokument speichern
doc.Save(dataDir + "goto2page_out.pdf");
```

Mit diesem Schritt schließen Sie Ihre Arbeit ab! Sie erhalten eine neue PDF-Datei mit dem Namen`goto2page_out.pdf` das direkt die von Ihnen angegebene Seite öffnet.

Damit ist der Codierungsteil abgeschlossen! Sie haben Aspose.PDF erfolgreich so programmiert, dass beim Öffnen einer PDF-Datei eine bestimmte Seite angezeigt wird. 

## Abschluss

In diesem Handbuch haben wir Schritt für Schritt erklärt, wie Sie mit Aspose.PDF für .NET eine Seite in einer PDF-Datei angeben. Diese Funktion verbessert nicht nur die Navigation für Ihre Benutzer, sondern optimiert auch deren Interaktion mit wichtigen Inhalten in Ihren Dokumenten. Durch die Nutzung solcher Funktionen schaffen Sie eine benutzerfreundlichere Erfahrung, die Ihre PDF-Anwendungen von anderen abheben kann.

## Häufig gestellte Fragen

### Was ist Aspose.PDF für .NET?
Aspose.PDF für .NET ist eine Bibliothek, die es Entwicklern ermöglicht, PDF-Dokumente innerhalb von .NET-Anwendungen zu erstellen, zu ändern und zu verwalten.

### Kann ich mehrere anzuzeigende Seiten angeben?
Nein, Sie können das Dokument nur so einstellen, dass es auf einer bestimmten Seite geöffnet wird. Sie können jedoch für verschiedene Anfangsseiten unterschiedliche Dokumente erstellen.

### Was ist, wenn ich eine Seite mit einer anderen Zoomstufe anzeigen möchte?
 Sie können die Zoomstufe ändern, indem Sie den`zoom` Variable, bevor Sie das Dokument speichern.

### Wo finde ich weitere Beispiele zur Verwendung von Aspose.PDF?
 Sie können die[Dokumentation](https://reference.aspose.com/pdf/net/) für weitere Beispiele und Funktionen.

### Gibt es eine kostenlose Testversion für Aspose.PDF für .NET?
 Ja! Sie können eine kostenlose Testversion von Aspose.PDF herunterladen[Hier](https://releases.aspose.com/).