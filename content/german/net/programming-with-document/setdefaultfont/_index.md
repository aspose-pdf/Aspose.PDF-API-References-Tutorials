---
title: Standardschriftart in PDF-Datei festlegen
linktitle: Standardschriftart in PDF-Datei festlegen
second_title: Aspose.PDF für .NET API-Referenz
description: Erfahren Sie in dieser Schritt-für-Schritt-Anleitung, wie Sie mit Aspose.PDF für .NET die Standardschriftart in einer PDF-Datei festlegen.
type: docs
weight: 280
url: /de/net/programming-with-document/setdefaultfont/
---
Wenn Sie mit PDF-Dokumenten in .NET arbeiten, kann es vorkommen, dass die im PDF verwendete Schriftart auf dem System, auf dem das Dokument angezeigt oder gedruckt wird, nicht verfügbar ist. Dies kann dazu führen, dass der Text falsch oder gar nicht angezeigt wird. Aspose.PDF für .NET bietet eine Lösung für dieses Problem, indem Sie eine Standardschriftart für das Dokument festlegen können. In diesem Beispiel wird gezeigt, wie Sie die Standardschriftart mit Aspose.PDF für .NET festlegen.

## Schritt 1: Pfad zum Dokumentverzeichnis festlegen

Wir müssen den Pfad zum Verzeichnis festlegen, in dem sich unser PDF-Dokument befindet. Wir speichern diesen Pfad in einer Variablen namens „dataDir“.

```csharp
// Der Pfad zum Dokumentverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Schritt 2: Laden Sie das PDF-Dokument

 Wir beginnen mit dem Laden eines vorhandenen PDF-Dokuments, in dem Schriftarten fehlen. In diesem Beispiel gehen wir davon aus, dass sich das PDF-Dokument in dem durch den`dataDir` Variable.

```csharp
string documentName = dataDir + "input.pdf";
using (System.IO.FileStream fs = new System.IO.FileStream(documentName, System.IO.FileMode.Open))
using (Document document = new Document(fs))
{
    // Code kommt hier rein
}
```

## Schritt 3: Standardschriftart festlegen

 Als nächstes legen wir die Standardschriftart für das PDF-Dokument fest. Dazu verwenden wir`PdfSaveOptions`Klasse. In diesem Beispiel legen wir die Standardschriftart auf „Arial“ fest.

```csharp
PdfSaveOptions pdfSaveOptions = new PdfSaveOptions();
pdfSaveOptions.DefaultFontName = "Arial";
```

## Schritt 4: Speichern Sie das aktualisierte Dokument

Zum Schluss speichern wir das aktualisierte Dokument in einer neuen Datei. In diesem Beispiel speichern wir das aktualisierte Dokument in einer Datei namens „output_out.pdf“ im selben Verzeichnis wie die Eingabedatei.

```csharp
document.Save(dataDir + "output_out.pdf", pdfSaveOptions);
```

### Beispiel-Quellcode zum Festlegen der Standardschriftart mit Aspose.PDF für .NET

```csharp
// Der Pfad zum Dokumentverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Laden Sie ein vorhandenes PDF-Dokument mit fehlender Schriftart
string documentName = dataDir + "input.pdf";
string newName = "Arial";
using (System.IO.FileStream fs = new System.IO.FileStream(documentName, System.IO.FileMode.Open))
using (Document document = new Document(fs))
{
	PdfSaveOptions pdfSaveOptions = new PdfSaveOptions();
	// Standard-Schriftartnamen angeben
	pdfSaveOptions.DefaultFontName = newName;
	document.Save(dataDir + "output_out.pdf", pdfSaveOptions);
}
```

## Abschluss

Das Festlegen einer Standardschriftart in PDF-Dokumenten mit Aspose.PDF für .NET ist eine einfache und effektive Möglichkeit, um sicherzustellen, dass der Text korrekt angezeigt wird, auch wenn die Originalschriftarten nicht verfügbar sind. Indem Entwickler der Schritt-für-Schritt-Anleitung folgen und den bereitgestellten C#-Quellcode verwenden, können sie problemlos die Standardschriftart festlegen und PDFs erstellen, die in verschiedenen Umgebungen ein konsistentes und zuverlässiges Anzeigeerlebnis bieten. Diese Funktion ist besonders in Szenarien nützlich, in denen die PDFs auf verschiedenen Systemen angezeigt oder gedruckt werden, auf denen möglicherweise unterschiedliche Schriftarten installiert sind.

### FAQs zum Festlegen der Standardschriftart in einer PDF-Datei

#### F: Warum ist es wichtig, in PDF-Dokumenten eine Standardschriftart festzulegen?

A: Das Festlegen einer Standardschriftart in PDF-Dokumenten ist wichtig, da dadurch sichergestellt wird, dass der Text korrekt angezeigt wird, auch wenn die Originalschriftarten auf dem System, auf dem das PDF angezeigt oder gedruckt wird, nicht verfügbar sind. Dadurch werden Probleme wie fehlender oder verstümmelter Text vermieden und ein konsistentes und zuverlässiges Anzeigeerlebnis gewährleistet.

#### F: Kann ich mit Aspose.PDF für .NET eine beliebige Schriftart als Standardschriftart auswählen?

 A: Ja, Sie können mit Aspose.PDF für .NET jede auf dem System verfügbare Schriftart als Standardschriftart auswählen. Geben Sie einfach den Namen der Schriftart im`DefaultFontName` Eigentum der`PdfSaveOptions` Klasse.

#### F: Was passiert, wenn die angegebene Standardschriftart auf dem System nicht verfügbar ist?

A: Wenn die angegebene Standardschriftart auf dem System nicht verfügbar ist, verwendet der PDF-Viewer eine Ersatzschriftart zur Anzeige des Textes. Es ist ratsam, eine allgemein verfügbare Schriftart wie Arial oder Times New Roman zu wählen, um die Kompatibilität zwischen verschiedenen Systemen sicherzustellen.