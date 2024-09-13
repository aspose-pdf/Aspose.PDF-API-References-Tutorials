---
title: Alle Schriftarten in der PDF-Datei abrufen
linktitle: Alle Schriftarten in der PDF-Datei abrufen
second_title: Aspose.PDF für .NET API-Referenz
description: Erfahren Sie in diesem Schritt-für-Schritt-Tutorial, wie Sie mit Aspose.PDF für .NET alle Schriftarten aus einer PDF-Datei extrahieren. Perfekt für Entwickler und PDF-Enthusiasten.
type: docs
weight: 160
url: /de/net/programming-with-document/getallfonts/
---
## Einführung

Haben Sie sich schon einmal gefragt, wie Sie alle in einer PDF-Datei verwendeten Schriftarten extrahieren können? Egal, ob Sie Entwickler sind und PDF-Dokumente analysieren möchten oder einfach nur neugierig auf die Schriftarten in Ihrem Lieblings-eBook sind, es kann unglaublich nützlich sein, zu wissen, wie man Schriftartinformationen abruft. In diesem Tutorial tauchen wir in die Welt von Aspose.PDF für .NET ein, einer leistungsstarken Bibliothek, mit der Sie PDF-Dateien ganz einfach bearbeiten können. Am Ende dieses Handbuchs können Sie alle in einem beliebigen PDF-Dokument verwendeten Schriftarten extrahieren und auflisten. Also, legen wir los!

## Voraussetzungen

Bevor wir uns in den Code stürzen, müssen einige Dinge bereitstehen:

1. Visual Studio: Stellen Sie sicher, dass Visual Studio auf Ihrem Computer installiert ist. Dies ist die IDE, die wir für dieses Tutorial verwenden werden.
2.  Aspose.PDF für .NET: Sie benötigen die Aspose.PDF-Bibliothek. Sie können sie herunterladen von[Webseite](https://releases.aspose.com/pdf/net/).
3. Grundkenntnisse in C#: Wenn Sie mit der C#-Programmierung vertraut sind, verstehen Sie die Codeausschnitte besser.

## Pakete importieren

Um zu beginnen, müssen Sie die erforderlichen Pakete in Ihr C#-Projekt importieren. So können Sie das tun:

### Neues Projekt erstellen

Öffnen Sie Visual Studio und erstellen Sie ein neues C#-Konsolenanwendungsprojekt. Dies wird die Umgebung sein, in der wir unseren Code schreiben.

### Aspose.PDF-Referenz hinzufügen

1. Klicken Sie im Projektmappen-Explorer mit der rechten Maustaste auf Ihr Projekt.
2. Wählen Sie „NuGet-Pakete verwalten“ aus.
3. Suchen Sie nach „Aspose.PDF“ und installieren Sie die neueste Version.

### Importieren der erforderlichen Namespaces

Importieren Sie oben in Ihrer C#-Datei die erforderlichen Namespaces, indem Sie die folgenden Zeilen einfügen:

```csharp
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

Nachdem wir nun alles eingerichtet haben, fahren wir mit dem Code fort!

## Schritt 1: Richten Sie Ihr Dokumentverzeichnis ein

Als Erstes müssen Sie den Pfad zu Ihrem PDF-Dokument angeben. Hier sucht Aspose.PDF nach der Datei, die Sie analysieren möchten.

```csharp
// Der Pfad zum Dokumentverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Ersetzen`"YOUR DOCUMENT DIRECTORY"` mit dem tatsächlichen Pfad, in dem sich Ihre PDF-Datei befindet. Dies könnte so etwas sein wie`@"C:\Documents\"`.

## Schritt 2: Laden Sie das PDF-Dokument

 Als nächstes laden Sie das PDF-Dokument in Ihre Anwendung. Dies geschieht mit dem`Document` Klasse bereitgestellt von Aspose.PDF.

```csharp
Document doc = new Document(dataDir + "input.pdf");
```

 Ersetzen Sie hier`"input.pdf"` mit dem Namen Ihrer PDF-Datei. Diese Codezeile initialisiert eine neue`Document` Objekt, das Ihr PDF darstellt.

## Schritt 3: Alle Schriftarten abrufen

 Jetzt kommt der spannende Teil! Sie verwenden die`FontUtilities` Klasse, um alle im Dokument verwendeten Schriftarten abzurufen.

```csharp
Aspose.Pdf.Text.Font[] fonts = doc.FontUtilities.GetAllFonts();
```

 Diese Zeile ruft ein Array von`Font` Objekte, die jeweils eine im PDF verwendete Schriftart darstellen.

## Schritt 4: Durchlaufen der Schriftarten

Zum Schluss möchten Sie noch die Namen der Schriftarten anzeigen. Dies geschieht mithilfe einer einfachen Schleife.

```csharp
foreach (Aspose.Pdf.Text.Font font in fonts)
{
    Console.WriteLine(font.FontName);
}
```

Diese Schleife durchläuft jede Schriftart im Array und gibt ihren Namen auf der Konsole aus. So können Sie ganz einfach sehen, welche Schriftarten in Ihrer PDF-Datei verfügbar sind.

## Abschluss

Und da haben Sie es! Sie haben erfolgreich alle Schriftarten aus einer PDF-Datei mit Aspose.PDF für .NET extrahiert. Diese leistungsstarke Bibliothek erleichtert die Bearbeitung von PDF-Dokumenten und mit nur wenigen Codezeilen können Sie auf wertvolle Informationen wie Schriftartnamen zugreifen. Egal, ob Sie einen PDF-Viewer entwickeln, Dokumente analysieren oder einfach nur neugierig sind, dieses Wissen wird Ihnen nützlich sein.

## Häufig gestellte Fragen

### Was ist Aspose.PDF für .NET?
Aspose.PDF für .NET ist eine Bibliothek, die es Entwicklern ermöglicht, PDF-Dokumente programmgesteuert zu erstellen, zu bearbeiten und zu konvertieren.

### Kann ich Aspose.PDF kostenlos nutzen?
 Ja, Aspose bietet eine kostenlose Testversion an, mit der Sie die Bibliothek testen können. Sie können sie herunterladen[Hier](https://releases.aspose.com/).

### Wo finde ich weitere Dokumentation?
 Eine ausführliche Dokumentation finden Sie auf der[Aspose-Website](https://reference.aspose.com/pdf/net/).

### Ist es möglich, aus einem PDF weitere Informationen zu extrahieren?
Auf jeden Fall! Mit Aspose.PDF können Sie unter anderem Text, Bilder und Metadaten extrahieren.

### Wie erhalte ich Support für Aspose.PDF?
 Sie erhalten Unterstützung unter[Aspose-Forum](https://forum.aspose.com/c/pdf/10).