---
title: Bild als Seitenhintergrund in der PDF-Datei festlegen
linktitle: Bild als Seitenhintergrund in der PDF-Datei festlegen
second_title: Aspose.PDF für .NET API-Referenz
description: Schritt-für-Schritt-Anleitung zum Festlegen eines Bilds als Seitenhintergrund in einer PDF-Datei mit Aspose.PDF für .NET.
type: docs
weight: 110
url: /de/net/programming-with-pdf-pages/image-as-background/
---
In diesem Tutorial führen wir Sie Schritt für Schritt durch den Prozess zum Festlegen eines Bilds als Seitenhintergrund mit Aspose.PDF für .NET. Wir erklären Ihnen den gebündelten C#-Quellcode und stellen Ihnen eine umfassende Anleitung zur Verfügung, die Ihnen hilft, diese Funktion zu verstehen und in Ihren eigenen Projekten zu implementieren. Am Ende dieses Tutorials erfahren Sie, wie Sie mit Aspose.PDF für .NET ein Bild als Seitenhintergrund in ein PDF-Dokument einfügen.

## Voraussetzungen
Bevor Sie beginnen, stellen Sie sicher, dass Sie über Folgendes verfügen:

- Grundkenntnisse der Programmiersprache C#
- Aspose.PDF für .NET in Ihrer Entwicklungsumgebung installiert

## Schritt 1: Definieren Sie das Dokumentenverzeichnis
Zuerst müssen Sie den Pfad zu Ihrem Dokumentenverzeichnis festlegen. Dies ist der Ort, an dem Sie Ihr bearbeitetes PDF-Dokument speichern möchten. Ersetzen Sie „IHR DOKUMENTENVERZEICHNIS“ durch den entsprechenden Pfad.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Schritt 2: Erstellen Sie ein neues Dokument
 Anschließend können Sie mithilfe von ein neues Dokumentobjekt erstellen`Document` Klasse.

```csharp
Document doc = new Document();
```

## Schritt 3: Fügen Sie dem Dokument eine neue Seite hinzu
 Jetzt können Sie mit dem eine neue Seite zum Document-Objekt hinzufügen`Add()` Methode der`Pages` Klasse.

```csharp
Page page = doc.Pages.Add();
```

## Schritt 4: Erstellen Sie ein Hintergrundartefaktobjekt
Anschließend können Sie ein neues BackgroundArtifact-Objekt erstellen, um das Hintergrundbild festzulegen.

```csharp
BackgroundArtifact background = new BackgroundArtifact();
background.BackgroundImage = File.OpenRead(dataDir + "aspose-total-for-net.jpg");
```

## Schritt 5: Fügen Sie der Seite den Hintergrund hinzu
Anschließend können Sie das BackgroundArtifact-Objekt mithilfe von zur Artefaktsammlung der Seite hinzufügen`Artifacts` Eigentum der`Page` Klasse.

```csharp
page. Artifacts. Add(background);
```

## Schritt 6: Speichern Sie das PDF-Dokument
 Abschließend können Sie das PDF-Dokument mit in einer Datei speichern`Save()` Methode der`Document`Klasse. Stellen Sie sicher, dass Sie den richtigen Pfad und Dateinamen angeben.

```csharp
doc.Save(dataDir + "ImageAsBackground_out.pdf");
```

### Beispielquellcode für „Bild als Hintergrund“ mit Aspose.PDF für .NET 

```csharp

// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Erstellen Sie ein neues Document-Objekt
Document doc = new Document();
// Fügen Sie dem Dokumentobjekt eine neue Seite hinzu
Page page = doc.Pages.Add();
// Erstellen Sie ein Hintergrundartefaktobjekt
BackgroundArtifact background = new BackgroundArtifact();
// Geben Sie das Bild für das Hintergrundartefaktobjekt an
background.BackgroundImage = File.OpenRead(dataDir + "aspose-total-for-net.jpg");
// Hintergrundartefakt zur Artefaktsammlung der Seite hinzufügen
page.Artifacts.Add(background);
dataDir = dataDir + "ImageAsBackground_out.pdf";
// Speichern Sie das Dokument
doc.Save(dataDir);
System.Console.WriteLine("\nImage as page background added successfully.\nFile saved at " + dataDir);

```

## Abschluss
In diesem Tutorial haben wir gelernt, wie man mit Aspose.PDF für .NET ein Bild als Seitenhintergrund in einem PDF-Dokument festlegt. Wenn Sie dieser Schritt-für-Schritt-Anleitung folgen, können Sie ganz einfach ein Hintergrundbild zu Ihren PDF-Dokumenten hinzufügen. Aspose.PDF bietet eine leistungsstarke und flexible API für die Arbeit mit PDF-Dateien, einschließlich der Anpassung des Seitenhintergrunds. Sie können diese Funktion jetzt in Ihren eigenen Projekten anwenden, um PDF-Dokumente mit benutzerdefinierten Hintergrundbildern zu erstellen

### FAQs zum Festlegen eines Bildes als Seitenhintergrund in einer PDF-Datei

#### F: Wie kann ich mit Aspose.PDF für .NET ein Bild als Seitenhintergrund in einem PDF-Dokument festlegen?

A: Um mit Aspose.PDF für .NET ein Bild als Seitenhintergrund in einem PDF-Dokument festzulegen, können Sie die folgenden Schritte ausführen:

1. Legen Sie das Dokumentverzeichnis fest, indem Sie den Pfad angeben, in dem Sie Ihr bearbeitetes PDF-Dokument speichern möchten.
2.  Erstellen Sie ein neues Document-Objekt mit`Document` Klasse.
3.  Fügen Sie mit dem eine neue Seite zum Document-Objekt hinzu`Add()` Methode der`Pages` Klasse.
4.  Erstellen Sie ein neues BackgroundArtifact-Objekt, um das Hintergrundbild festzulegen. Sie können die Bilddatei mit angeben`File.OpenRead()` Methode.
5.  Fügen Sie das BackgroundArtifact-Objekt mit der Artefaktsammlung der Seite hinzu`Artifacts` Eigentum der`Page` Klasse.
6.  Speichern Sie das PDF-Dokument mit in einer Datei`Save()` Methode der`Document` Klasse und geben Sie den richtigen Pfad und Dateinamen für die Ausgabe an.

#### F: Kann ich verschiedenen Seiten des PDF-Dokuments mehrere Hintergrundbilder hinzufügen?

A: Ja, Sie können mehrere Hintergrundbilder zu verschiedenen Seiten des PDF-Dokuments hinzufügen, indem Sie den im Tutorial beschriebenen Vorgang für jede Seite wiederholen. Erstellen Sie einfach ein neues BackgroundArtifact-Objekt mit dem gewünschten Bild für jede Seite und fügen Sie es der Artefaktsammlung der jeweiligen Seite hinzu.

#### F: Kann ich die Bildskalierung oder -positionierung auf das Hintergrundbild auf der Seite anwenden?

 A: Ja, Sie können die Bildskalierung oder -positionierung auf das Hintergrundbild auf der Seite anwenden, indem Sie das bearbeiten`background.BackgroundImage` Eigenschaft des BackgroundArtifact-Objekts. Bevor Sie das BackgroundArtifact zur Seite hinzufügen, können Sie die Bildeigenschaften wie Breite, Höhe und Position ändern, um anzupassen, wie das Bild als Hintergrund angezeigt wird.

#### F: Unterstützt Aspose.PDF für .NET das Hinzufügen von Hintergrundbildern zu vorhandenen PDF-Dokumenten mit Inhalt?

A: Ja, mit Aspose.PDF für .NET können Sie Hintergrundbilder zu vorhandenen PDF-Dokumenten mit Inhalt hinzufügen. Sie können ein vorhandenes PDF-Dokument laden, das Hintergrundbild zur gewünschten Seite hinzufügen und dann das aktualisierte Dokument in einer neuen Datei speichern oder die Originaldatei überschreiben.

#### F: Kann ich Bilder in verschiedenen Formaten als Seitenhintergrund verwenden, z. B. PNG oder BMP?

A: Ja, Sie können neben dem im Tutorial verwendeten JPEG-Format auch Bilder in verschiedenen Formaten als Seitenhintergrund verwenden, z. B. PNG oder BMP. Aspose.PDF für .NET unterstützt eine Vielzahl von Bildformaten und Sie können jedes unterstützte Bildformat als Hintergrund für PDF-Seiten verwenden.