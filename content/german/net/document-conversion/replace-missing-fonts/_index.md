---
title: Ersetzen Sie fehlende Schriftarten
linktitle: Ersetzen Sie fehlende Schriftarten
second_title: Aspose.PDF für .NET API-Referenz
description: Schritt-für-Schritt-Anleitung zum Ersetzen fehlender Schriftarten in einer PDF-Datei mit Aspose.PDF für .NET.
type: docs
weight: 260
url: /de/net/document-conversion/replace-missing-fonts/
---
In diesem Tutorial führen wir Sie durch den Prozess des Ersetzens fehlender Schriftarten in einer PDF-Datei mit Aspose.PDF für .NET. Wenn Sie eine PDF-Datei auf einem Computer öffnen, auf dem eine bestimmte Schriftart fehlt, kann es zu Problemen bei der Schriftartenanzeige kommen. In solchen Fällen besteht die Möglichkeit, die fehlende Schriftart durch eine andere auf dem Gerät verfügbare Schriftart zu ersetzen. Wenn Sie die folgenden Schritte ausführen, können Sie fehlende Schriftarten in einer PDF-Datei ersetzen.

## Voraussetzungen
Bevor Sie beginnen, stellen Sie sicher, dass Sie die folgenden Voraussetzungen erfüllen:

- Grundkenntnisse der Programmiersprache C#.
- Aspose.PDF-Bibliothek für .NET auf Ihrem System installiert.
- Eine Entwicklungsumgebung wie Visual Studio.

## Schritt 1: Finden der fehlenden Schriftart
Der erste Schritt besteht darin, die fehlende Schriftart in der PDF-Datei zu finden. Verwenden Sie den folgenden Code:

```csharp
// Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

Aspose.Pdf.Text.Font originalFont = null;
try
{
     // Finden Sie die Originalschrift
     originalFont = FontRepository.FindFont("AgencyFB");
}
catch(Exception)
{
     // Die Schriftart fehlt auf dem Zielcomputer
     // Fügen Sie eine einfache Schriftartersetzung hinzu
     FontRepository.Substitutions.Add(new SimpleFontSubstitution("AgencyFB", "Arial"));
}
```

 Unbedingt austauschen`"YOUR DOCUMENTS DIRECTORY"` mit dem tatsächlichen Verzeichnis, in dem sich Ihre PDF-Datei befindet.

## Schritt 2: Fehlende Schriftart ersetzen
Als Nächstes ersetzen wir die fehlende Schriftart durch eine andere verfügbare Schriftart. Verwenden Sie den folgenden Code:

```csharp
var fileNew = new FileInfo(dataDir + "newfile_out.pdf");
var pdf = new Document(dataDir + "input.pdf");

// Konvertieren Sie die PDF-Datei mit Fehlerbeseitigung in das PDF/A-Format
pdf.Convert(dataDir + "log.xml", PdfFormat.PDF_A_1B, ConvertErrorAction.Delete);

// Speichern Sie die resultierende PDF-Datei
pdf.Save(fileNew.FullName);
```

 Unbedingt austauschen`"input.pdf"` mit dem tatsächlichen Pfad zu Ihrer Original-PDF-Datei und`"newfile_out.pdf"` mit dem gewünschten Namen für die resultierende PDF-Datei.

## Schritt 3: Speichern der resultierenden PDF-Datei
Abschließend speichern wir die resultierende PDF-Datei mit der ersetzten Schriftart. Verwenden Sie den folgenden Code:

```csharp
// Speichern Sie die resultierende PDF-Datei
pdf.Save(fileNew.FullName);
```

Stellen Sie sicher, dass Sie den richtigen Zielpfad für die resultierende PDF-Datei festgelegt haben.

### Beispielquellcode zum Ersetzen fehlender Schriftarten mit Aspose.PDF für .NET

```csharp
// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";

Aspose.Pdf.Text.Font originalFont = null;
try
{
	originalFont = FontRepository.FindFont("AgencyFB");
}
catch (Exception)
{
	// Auf dem Zielcomputer fehlt die Schriftart
	FontRepository.Substitutions.Add(new SimpleFontSubstitution("AgencyFB", "Arial"));
}
var fileNew = new FileInfo(dataDir + "newfile_out.pdf");
var pdf = new Document(dataDir + "input.pdf");
pdf.Convert( dataDir +  "log.xml", PdfFormat.PDF_A_1B, ConvertErrorAction.Delete);
pdf.Save(fileNew.FullName);
```

## Abschluss
In diesem Tutorial haben wir den Schritt-für-Schritt-Prozess zum Ersetzen fehlender Schriftarten in einer PDF-Datei mit Aspose.PDF für .NET behandelt. Wenn Sie die oben beschriebenen Anweisungen befolgen, können Sie fehlende Schriftarten in Ihrer PDF-Datei erfolgreich ersetzen.

### FAQs

#### F: Was ist Aspose.PDF für .NET?

A: Aspose.PDF für .NET ist eine leistungsstarke Bibliothek, die Entwicklern die Arbeit mit PDF-Dokumenten in C#-Anwendungen ermöglicht. Es bietet verschiedene Funktionalitäten, darunter die Möglichkeit, fehlende Schriftarten in PDF-Dateien zu ersetzen.

#### F: Warum sollte ich in einer PDF-Datei auf fehlende Schriftarten stoßen?

A: In einer PDF-Datei können Schriftarten fehlen, wenn die Datei auf einem Computer geöffnet wird, auf dem die erforderlichen Schriftarten nicht installiert sind. Dies kann zu einer Schriftartersetzung führen, die sich auf das visuelle Erscheinungsbild des Dokuments auswirkt.

#### F: Wie kann ich mit Aspose.PDF für .NET fehlende Schriftarten in einer PDF-Datei finden und ersetzen?

 A: Um fehlende Schriftarten zu finden und zu ersetzen, können Sie die verwenden`FontRepository.FindFont` Methode, um zu prüfen, ob die erforderliche Schriftart vorhanden ist. Wenn die Schriftart fehlt, können Sie mithilfe von eine Schriftartenersetzung hinzufügen`FontRepository.Substitutions` Eigentum.

#### F: Kann ich den Schriftersetzungsprozess anpassen?

A: Ja, Sie können den Schriftersetzungsprozess anpassen, indem Sie eine andere Schriftart für die Ersetzung angeben. Im bereitgestellten Code haben wir Arial als Ersatz für die fehlende Schriftart „AgencyFB“ verwendet, Sie können jedoch je nach Ihren Vorlieben eine andere Schriftart auswählen.

#### F: Wie kann ich die Genauigkeit der Schriftwiedergabe nach der Ersetzung sicherstellen?

A: Aspose.PDF für .NET bietet robuste Funktionen zur Schriftartenverarbeitung und gewährleistet eine genaue Schriftartenwiedergabe nach der Ersetzung. Sie können eine Vorschau der resultierenden PDF-Datei anzeigen, um die Schriftartersetzung zu überprüfen.