---
title: Horizontale und vertikale Optionsfelder
linktitle: Horizontale und vertikale Optionsfelder
second_title: Aspose.PDF für .NET API-Referenz
description: Erfahren Sie in diesem Schritt-für-Schritt-Tutorial, wie Sie mit Aspose.PDF für .NET horizontal und vertikal ausgerichtete Optionsfelder in PDF erstellen.
type: docs
weight: 180
url: /de/net/programming-with-forms/horizontally-and-vertically-radio-buttons/
---
## Einführung

Das Erstellen interaktiver PDF-Formulare kann die Benutzererfahrung erheblich verbessern, insbesondere beim Sammeln von Informationen. Eines der häufigsten Formularelemente ist das Optionsfeld, mit dem Benutzer eine Option aus einer Reihe auswählen können. In diesem Tutorial erfahren Sie, wie Sie mit Aspose.PDF für .NET horizontal und vertikal ausgerichtete Optionsfelder erstellen. Egal, ob Sie ein erfahrener Entwickler sind oder gerade erst anfangen, diese Anleitung führt Sie Schritt für Schritt durch den Prozess und stellt sicher, dass Sie jeden Teil klar verstehen.

## Voraussetzungen

Bevor Sie sich in den Code vertiefen, sollten einige Voraussetzungen erfüllt sein:

1.  Aspose.PDF für .NET: Stellen Sie sicher, dass Sie die Aspose.PDF-Bibliothek installiert haben. Sie können sie von der[Website](https://releases.aspose.com/pdf/net/).
2. Visual Studio: Eine Entwicklungsumgebung, in der Sie Ihren Code schreiben und testen können.
3. Grundkenntnisse in C#: Wenn Sie mit der C#-Programmierung vertraut sind, verstehen Sie die Codeausschnitte besser.

## Pakete importieren

Um zu beginnen, müssen Sie die erforderlichen Pakete in Ihr C#-Projekt importieren. So können Sie das tun:

### Neues Projekt erstellen

Öffnen Sie Visual Studio und erstellen Sie ein neues C#-Projekt. Der Einfachheit halber können Sie eine Konsolenanwendung wählen.

### Aspose.PDF-Referenz hinzufügen

1. Klicken Sie im Projektmappen-Explorer mit der rechten Maustaste auf Ihr Projekt.
2. Wählen Sie „NuGet-Pakete verwalten“ aus.
3. Suchen Sie nach „Aspose.PDF“ und installieren Sie die neueste Version.

```csharp
using System;
using System.IO;
using Aspose.Pdf.Facades;
using Aspose.Pdf;
using Aspose.Pdf.Forms;
```

Nachdem Sie nun alles eingerichtet haben, zerlegen wir den Code, um horizontal und vertikal ausgerichtete Optionsfelder zu erstellen.

## Schritt 1: Einrichten des Dokumentverzeichnisses

In diesem Schritt definieren wir den Pfad zum Verzeichnis, in dem Ihre PDF-Dokumente gespeichert werden.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Ersetzen`"YOUR DOCUMENT DIRECTORY"` durch den tatsächlichen Pfad, in dem Sie Ihre PDF-Datei speichern möchten. Dies ist wichtig, da es dem Programm mitteilt, wo es nach Eingabedateien suchen und wo die Ausgabe speichern soll.

## Schritt 2: Laden Sie das vorhandene PDF-Dokument

 Als nächstes müssen wir das PDF-Dokument laden, mit dem wir arbeiten werden. Dies geschieht mit dem`FormEditor` Klasse.

```csharp
FormEditor formEditor = new FormEditor();
formEditor.BindPdf(dataDir + "input.pdf");
```

Hier erstellen wir eine Instanz von`FormEditor` und binden Sie es an eine vorhandene PDF-Datei mit dem Namen`input.pdf`. Stellen Sie sicher, dass diese Datei in Ihrem angegebenen Verzeichnis vorhanden ist.

## Schritt 3: Optionsfeldeigenschaften konfigurieren

Nun legen wir einige Eigenschaften für unsere Optionsfelder fest. Dazu gehören der Abstand zwischen den Feldern, ihre Ausrichtung und ihre Größe.

```csharp
formEditor.RadioGap = 4; // Abstand zwischen Optionsfeldoptionen
formEditor.RadioHoriz = true; // Für horizontale Ausrichtung auf „true“ setzen
formEditor.RadioButtonItemSize = 20; // Größe des Optionsfelds
formEditor.Facade.BorderWidth = 1; // Rahmenbreite
formEditor.Facade.BorderColor = System.Drawing.Color.Black; // Rahmenfarbe
```

 Mit diesen Eigenschaften können Sie festlegen, wie die Optionsfelder im PDF angezeigt werden.`RadioGap` Eigenschaft steuert den Abstand zwischen den Schaltflächen, während`RadioHoriz` bestimmt deren Layout.

## Schritt 4: Horizontale Optionsfelder hinzufügen

Fügen wir nun die horizontalen Optionsfelder zum PDF hinzu.

```csharp
formEditor.Items = new string[] { "First", "Second", "Third" };
formEditor.AddField(FieldType.Radio, "NewField1", 1, 40, 600, 120, 620);
```

 In diesem Code definieren wir die Elemente für die Optionsfelder und fügen sie dem PDF hinzu.`AddField`Die Methode erfordert mehrere Parameter, darunter den Feldtyp, den Feldnamen und die Koordinaten für die Platzierung.

## Schritt 5: Vertikale Optionsfelder hinzufügen

Als Nächstes fügen wir die vertikalen Optionsfelder hinzu. Dazu müssen wir die Ausrichtung wieder auf vertikal ändern.

```csharp
formEditor.RadioHoriz = false; // Für vertikale Ausrichtung auf „false“ setzen
formEditor.Items = new string[] { "First", "Second", "Third" };
formEditor.AddField(FieldType.Radio, "NewField2", 1, 40, 500, 60, 550);
```

Wie zuvor definieren wir die Elemente und fügen sie dem PDF hinzu, dieses Mal werden sie jedoch vertikal ausgerichtet.

## Schritt 6: Speichern Sie das PDF-Dokument

Abschließend müssen wir das geänderte PDF-Dokument speichern.

```csharp
dataDir = dataDir + "HorizontallyAndVerticallyRadioButtons_out.pdf";
formEditor.Save(dataDir);
Console.WriteLine("\nHorizontally and vertically laid out radio buttons successfully.\nFile saved at " + dataDir);
```

Dieser Code speichert das PDF mit den neu hinzugefügten Optionsfeldern. Überprüfen Sie unbedingt das angegebene Verzeichnis für die Ausgabedatei.

## Abschluss

Das Erstellen von Optionsfeldern in einer PDF-Datei mit Aspose.PDF für .NET ist ein unkomplizierter Vorgang. Indem Sie die in diesem Tutorial beschriebenen Schritte befolgen, können Sie Ihren PDF-Formularen problemlos horizontal und vertikal ausgerichtete Optionsfelder hinzufügen. Dies verbessert nicht nur die Interaktivität Ihrer Dokumente, sondern auch das allgemeine Benutzererlebnis. Probieren Sie es also einfach aus!

## Häufig gestellte Fragen

### Was ist Aspose.PDF für .NET?
Aspose.PDF für .NET ist eine leistungsstarke Bibliothek, mit der Entwickler PDF-Dokumente programmgesteuert erstellen, bearbeiten und konvertieren können.

### Kann ich Aspose.PDF kostenlos nutzen?
 Ja, Aspose bietet eine kostenlose Testversion an, mit der Sie die Bibliothek testen können. Sie können sie herunterladen[Hier](https://releases.aspose.com/).

### Wie erhalte ich Support für Aspose.PDF?
 Sie erhalten Unterstützung unter[Aspose-Forum](https://forum.aspose.com/c/pdf/10).

### Ist es möglich, mit Aspose.PDF andere Formularelemente zu erstellen?
Auf jeden Fall! Aspose.PDF unterstützt verschiedene Formularelemente, darunter Textfelder, Kontrollkästchen und Dropdown-Menüs.

### Wo kann ich Aspose.PDF für .NET kaufen?
 Sie können Aspose.PDF für .NET kaufen bei der[Kaufseite](https://purchase.aspose.com/buy).