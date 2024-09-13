---
title: Standardschriftart in PDF-Datei festlegen
linktitle: Standardschriftart in PDF-Datei festlegen
second_title: Aspose.PDF für .NET API-Referenz
description: Erfahren Sie in dieser Schritt-für-Schritt-Anleitung, wie Sie mit Aspose.PDF für .NET eine Standardschriftart in PDF-Dateien festlegen. Perfekt für Entwickler, die PDF-Dokumente verbessern möchten.
type: docs
weight: 280
url: /de/net/programming-with-document/setdefaultfont/
---
## Einführung

Haben Sie schon einmal ein PDF-Dokument geöffnet und festgestellt, dass die Schriftarten fehlen oder nicht richtig angezeigt werden? Das kann frustrierend sein, oder? Aber keine Angst! In diesem Tutorial erfahren Sie, wie Sie mit Aspose.PDF für .NET eine Standardschriftart in einer PDF-Datei festlegen. Mit dieser leistungsstarken Bibliothek können Sie PDF-Dokumente ganz einfach bearbeiten, und das Festlegen einer Standardschriftart ist nur eine der vielen Funktionen, die sie bietet. Also schnappen Sie sich Ihren Programmierhut und legen Sie los!

## Voraussetzungen

Bevor wir uns in den Code stürzen, müssen Sie ein paar Dinge vorbereitet haben:

1. Visual Studio: Stellen Sie sicher, dass Visual Studio auf Ihrem Computer installiert ist. Es ist die beste IDE für die .NET-Entwicklung.
2.  Aspose.PDF für .NET: Sie müssen die Aspose.PDF-Bibliothek herunterladen und installieren. Sie finden sie[Hier](https://releases.aspose.com/pdf/net/).
3. Grundkenntnisse in C#: Ein wenig Vertrautheit mit der C#-Programmierung trägt wesentlich zum Verständnis der Beispiele bei, die wir behandeln.

## Pakete importieren

Um zu beginnen, müssen Sie die erforderlichen Pakete in Ihr C#-Projekt importieren. So können Sie das tun:

1. Öffnen Sie Ihr Visual Studio-Projekt.
2. Klicken Sie im Projektmappen-Explorer mit der rechten Maustaste auf Ihr Projekt und wählen Sie „NuGet-Pakete verwalten“ aus.
3.  Suchen nach`Aspose.PDF` und installieren Sie die neueste Version.

Sobald Sie das Paket installiert haben, können Sie mit der Codierung beginnen!

## Schritt 1: Richten Sie Ihr Projekt ein

### Neues Projekt erstellen

Als Erstes erstellen wir ein neues C#-Projekt in Visual Studio:

- Öffnen Sie Visual Studio und wählen Sie „Neues Projekt erstellen“ aus.
- Wählen Sie „Konsolen-App (.NET Core)“ und klicken Sie auf „Weiter“.
-  Geben Sie Ihrem Projekt einen Namen (z. B.`AsposePdfExample`) und klicken Sie auf „Erstellen“.

### Using-Direktiven hinzufügen

 Fügen wir nun die notwendigen using-Direktiven oben in Ihrem`Program.cs` Datei:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
using System.IO;
```

Diese Anweisungen ermöglichen Ihnen den Zugriff auf die Klassen und Methoden von Aspose.PDF.

## Schritt 2: Laden Sie das PDF-Dokument

### Geben Sie den Dokumentpfad an

Als Nächstes müssen Sie den Pfad zum PDF-Dokument angeben, mit dem Sie arbeiten möchten. So geht's:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY"; // Ersetzen Sie es durch Ihr aktuelles Verzeichnis
string documentName = Path.Combine(dataDir, "input.pdf");
```

 Ersetzen Sie unbedingt`"YOUR DOCUMENT DIRECTORY"` durch den tatsächlichen Pfad, in dem sich Ihre PDF-Datei befindet.

### Laden Sie das Dokument

Laden wir nun das vorhandene PDF-Dokument:

```csharp
using (FileStream fs = new FileStream(documentName, FileMode.Open))
{
    Document document = new Document(fs);
}
```

 Dieser Codeausschnitt öffnet die PDF-Datei und erstellt eine`Document` Objekt, das Sie manipulieren können.

## Schritt 3: Legen Sie die Standardschriftart fest

### PdfSaveOptions erstellen

 Jetzt kommt der spannende Teil! Sie müssen eine Instanz von`PdfSaveOptions` So legen Sie die Standardschriftart fest:

```csharp
PdfSaveOptions pdfSaveOptions = new PdfSaveOptions();
```

### Geben Sie den Standardschriftnamen an

Als Nächstes legen Sie den Standardschriftnamen fest. Für dieses Beispiel verwenden wir „Arial“:

```csharp
pdfSaveOptions.DefaultFontName = "Arial";
```

Diese Zeile weist Aspose.PDF an, Arial als Standardschriftart für jeden Text zu verwenden, für den keine Schriftart angegeben ist.

## Schritt 4: Speichern Sie das Dokument

Abschließend ist es an der Zeit, das geänderte PDF-Dokument mit der neuen Standardschriftart zu speichern:

```csharp
document.Save(Path.Combine(dataDir, "output_out.pdf"), pdfSaveOptions);
```

 Diese Zeile speichert das Dokument als`output_out.pdf` im angegebenen Verzeichnis.

## Abschluss

Und da haben Sie es! Sie haben mit Aspose.PDF für .NET erfolgreich eine Standardschriftart in einer PDF-Datei festgelegt. Mit dieser einfachen, aber leistungsstarken Funktion können Sie sicherstellen, dass Ihre Dokumente genau so aussehen, wie Sie es möchten, selbst wenn Schriftarten fehlen. Wenn Sie also das nächste Mal auf eine PDF-Datei mit Schriftartproblemen stoßen, wissen Sie genau, was zu tun ist!

## Häufig gestellte Fragen

### Was ist Aspose.PDF für .NET?
Aspose.PDF für .NET ist eine Bibliothek, die es Entwicklern ermöglicht, PDF-Dokumente programmgesteuert zu erstellen, zu bearbeiten und zu konvertieren.

### Kann ich außer Arial auch andere Schriftarten verwenden?
Ja, Sie können jede auf Ihrem System installierte Schriftart als Standardschriftart festlegen.

### Ist die Nutzung von Aspose.PDF kostenlos?
Aspose.PDF bietet eine kostenlose Testversion, für die volle Funktionalität müssen Sie jedoch eine Lizenz erwerben.

### Wo finde ich weitere Dokumentation?
 Eine ausführliche Dokumentation finden Sie[Hier](https://reference.aspose.com/pdf/net/).

### Wie erhalte ich Support für Aspose.PDF?
 Sie können Unterstützung über das Aspose-Forum erhalten[Hier](https://forum.aspose.com/c/pdf/10).