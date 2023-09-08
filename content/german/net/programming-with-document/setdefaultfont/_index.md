---
title: Legen Sie die Standardschriftart in der PDF-Datei fest
linktitle: Legen Sie die Standardschriftart in der PDF-Datei fest
second_title: Aspose.PDF für .NET API-Referenz
description: Erfahren Sie in dieser Schritt-für-Schritt-Anleitung, wie Sie mit Aspose.PDF für .NET die Standardschriftart in einer PDF-Datei festlegen.
type: docs
weight: 280
url: /de/net/programming-with-document/setdefaultfont/
---
Wenn Sie mit PDF-Dokumenten in .NET arbeiten, kann es zu Problemen kommen, wenn die in der PDF-Datei verwendete Schriftart auf dem System, auf dem sie angezeigt oder gedruckt wird, nicht verfügbar ist. Dies kann dazu führen, dass der Text falsch oder gar nicht angezeigt wird. Aspose.PDF für .NET bietet eine Lösung für dieses Problem, indem es Ihnen ermöglicht, eine Standardschriftart für das Dokument festzulegen. In diesem Beispiel erfahren Sie, wie Sie die Standardschriftart mithilfe von Aspose.PDF für .NET festlegen.

## Schritt 1: Legen Sie den Pfad zum Dokumentverzeichnis fest

Wir müssen den Pfad zu dem Verzeichnis festlegen, in dem sich unser PDF-Dokument befindet. Wir werden diesen Pfad in einer Variablen namens „dataDir“ speichern.

```csharp
// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Schritt 2: Laden Sie das PDF-Dokument

 Wir beginnen mit dem Laden eines vorhandenen PDF-Dokuments, in dem Schriftarten fehlen. In diesem Beispiel gehen wir davon aus, dass sich das PDF-Dokument in dem von angegebenen Verzeichnis befindet`dataDir` Variable.

```csharp
string documentName = dataDir + "input.pdf";
using (System.IO.FileStream fs = new System.IO.FileStream(documentName, System.IO.FileMode.Open))
using (Document document = new Document(fs))
{
    // Code kommt hierher
}
```

## Schritt 3: Legen Sie die Standardschriftart fest

 Als Nächstes legen wir mithilfe von die Standardschriftart für das PDF-Dokument fest`PdfSaveOptions` Klasse. In diesem Beispiel legen wir die Standardschriftart auf „Arial“ fest.

```csharp
PdfSaveOptions pdfSaveOptions = new PdfSaveOptions();
pdfSaveOptions.DefaultFontName = "Arial";
```

## Schritt 4: Speichern Sie das aktualisierte Dokument

Abschließend speichern wir das aktualisierte Dokument in einer neuen Datei. In diesem Beispiel speichern wir das aktualisierte Dokument in einer Datei mit dem Namen „output_out.pdf“ im selben Verzeichnis wie die Eingabedatei.

```csharp
document.Save(dataDir + "output_out.pdf", pdfSaveOptions);
```

### Beispielquellcode zum Festlegen der Standardschriftart mit Aspose.PDF für .NET

```csharp
// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Laden Sie ein vorhandenes PDF-Dokument mit fehlender Schriftart
string documentName = dataDir + "input.pdf";
string newName = "Arial";
using (System.IO.FileStream fs = new System.IO.FileStream(documentName, System.IO.FileMode.Open))
using (Document document = new Document(fs))
{
	PdfSaveOptions pdfSaveOptions = new PdfSaveOptions();
	// Geben Sie den Namen der Standardschriftart an
	pdfSaveOptions.DefaultFontName = newName;
	document.Save(dataDir + "output_out.pdf", pdfSaveOptions);
}
```

## Abschluss

Das Festlegen einer Standardschriftart in PDF-Dokumenten mit Aspose.PDF für .NET ist eine einfache und effektive Möglichkeit, sicherzustellen, dass der Text korrekt angezeigt wird, auch wenn die Originalschriftarten nicht verfügbar sind. Durch Befolgen der Schritt-für-Schritt-Anleitung und Verwendung des bereitgestellten C#-Quellcodes können Entwickler ganz einfach die Standardschriftart festlegen und PDFs erstellen, die in verschiedenen Umgebungen ein konsistentes und zuverlässiges Anzeigeerlebnis bieten. Diese Funktion ist besonders nützlich in Szenarien, in denen die PDFs auf verschiedenen Systemen angezeigt oder gedruckt werden, auf denen möglicherweise unterschiedliche Schriftarten installiert sind.

### FAQs zum Festlegen der Standardschriftart in einer PDF-Datei

#### F: Warum ist es wichtig, in PDF-Dokumenten eine Standardschriftart festzulegen?

A: Das Festlegen einer Standardschriftart in PDF-Dokumenten ist wichtig, da dadurch sichergestellt wird, dass der Text auch dann korrekt angezeigt wird, wenn die Originalschriftarten auf dem System, auf dem die PDF-Datei angezeigt oder gedruckt wird, nicht verfügbar sind. Es hilft, Probleme wie fehlenden oder verstümmelten Text zu vermeiden und sorgt für ein konsistentes und zuverlässiges Seherlebnis.

#### F: Kann ich mit Aspose.PDF für .NET eine beliebige Schriftart als Standardschriftart auswählen?

 A: Ja, Sie können mit Aspose.PDF für .NET jede auf dem System verfügbare Schriftart als Standardschriftart auswählen. Geben Sie einfach den Namen der Schriftart im an`DefaultFontName` Eigentum der`PdfSaveOptions` Klasse.

#### F: Was passiert, wenn die angegebene Standardschriftart auf dem System nicht verfügbar ist?

A: Wenn die angegebene Standardschriftart auf dem System nicht verfügbar ist, verwendet der PDF-Viewer eine Ersatzschriftart, um den Text anzuzeigen. Es empfiehlt sich, eine allgemein verfügbare Schriftart wie Arial oder Times New Roman zu wählen, um die Kompatibilität zwischen verschiedenen Systemen sicherzustellen.