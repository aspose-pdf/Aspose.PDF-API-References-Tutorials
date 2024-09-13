---
title: Gesamten Text aus PDF entfernen
linktitle: Gesamten Text aus PDF entfernen
second_title: Aspose.PDF für .NET API-Referenz
description: Erfahren Sie, wie Sie mit Aspose.PDF für .NET den gesamten Text aus einem PDF-Dokument entfernen.
type: docs
weight: 290
url: /de/net/programming-with-text/remove-all-text-from-pdf/
---
 In diesem Tutorial erklären wir, wie Sie mit der Aspose.PDF-Bibliothek für .NET den gesamten Text aus einem PDF-Dokument entfernen. Wir werden Schritt für Schritt durch den Prozess des Öffnens einer PDF-Datei gehen, indem wir ein`TextFragmentAbsorber` um den gesamten Text zu entfernen und das geänderte PDF mit dem bereitgestellten C#-Quellcode zu speichern.

## Anforderungen

Bevor Sie beginnen, stellen Sie sicher, dass Sie über Folgendes verfügen:

- Die Aspose.PDF-Bibliothek für .NET ist installiert.
- Grundlegende Kenntnisse der C#-Programmierung.

## Schritt 1: Einrichten des Dokumentverzeichnisses

 Zuerst müssen Sie den Pfad zum Verzeichnis festlegen, in dem sich Ihre PDF-Dateien befinden. Ersetzen Sie`"YOUR DOCUMENT DIRECTORY"` im`dataDir` Variable mit dem Pfad zu Ihren PDF-Dateien.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Schritt 2: Öffnen Sie das PDF-Dokument

 Als nächstes öffnen wir das PDF-Dokument mit dem`Document` Klasse aus der Aspose.PDF-Bibliothek.

```csharp
Document pdfDocument = new Document(dataDir + "RemoveAllText.pdf");
```

## Schritt 3: Den gesamten Text entfernen

 Wir initialisieren eine`TextFragmentAbsorber`Objekt und verwenden Sie es, um den gesamten absorbierten Text aus dem PDF-Dokument zu entfernen.

```csharp
TextFragmentAbsorber absorb = new TextFragmentAbsorber();
absorb. RemoveAllText(pdfDocument);
```

## Schritt 4: Speichern Sie die geänderte PDF-Datei

Abschließend speichern wir das geänderte PDF-Dokument in der angegebenen Ausgabedatei.

```csharp
pdfDocument.Save(dataDir + "RemoveAllText_out.pdf", Aspose.Pdf.SaveFormat.Pdf);
```

### Beispielquellcode zum Entfernen des gesamten Textes aus PDF mit Aspose.PDF für .NET 
```csharp
// Der Pfad zum Dokumentverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Dokument öffnen
Document pdfDocument = new Document(dataDir + "RemoveAllText.pdf");
// TextFragmentAbsorber starten
TextFragmentAbsorber absorber = new TextFragmentAbsorber();
// Den gesamten absorbierten Text entfernen
absorber.RemoveAllText(pdfDocument);
// Speichern des Dokuments
pdfDocument.Save(dataDir + "RemoveAllText_out.pdf", Aspose.Pdf.SaveFormat.Pdf);
```

## Abschluss

 In diesem Tutorial haben Sie gelernt, wie Sie mithilfe der Aspose.PDF-Bibliothek für .NET allen Text aus einem PDF-Dokument entfernen. Indem Sie der Schritt-für-Schritt-Anleitung folgen und den bereitgestellten C#-Code ausführen, können Sie ein PDF öffnen, den gesamten Text mithilfe eines`TextFragmentAbsorber`, und speichern Sie die geänderte PDF-Datei.

### Häufig gestellte Fragen

#### F: Was ist der Zweck des Tutorials „Gesamten Text aus PDF entfernen“?

 A: Das Tutorial „Alle Texte aus PDF entfernen“ enthält Anweisungen, wie Sie mit der Aspose.PDF-Bibliothek für .NET alle Texte aus einem PDF-Dokument entfernen können. Das Tutorial führt Sie durch den Vorgang des Öffnens einer PDF-Datei mit einem`TextFragmentAbsorber` um den gesamten Text zu entfernen und die geänderte PDF-Datei zu speichern.

#### F: Warum sollte ich den gesamten Text aus einem PDF-Dokument entfernen wollen?

A: Das Entfernen des gesamten Textes aus einem PDF-Dokument kann in Szenarien nützlich sein, in denen Sie eine Version des Dokuments ohne Textinhalt erstellen müssen. Dies kann aus Datenschutzgründen hilfreich sein oder um eine visuelle Darstellung des Dokumentlayouts zu generieren, ohne dessen Textinformationen anzuzeigen.

#### F: Wie richte ich das Dokumentverzeichnis ein?

A: So richten Sie das Dokumentverzeichnis ein:

1.  Ersetzen`"YOUR DOCUMENT DIRECTORY"` im`dataDir` Variable mit dem Pfad zum Verzeichnis, in dem sich Ihre PDF-Dateien befinden.

#### F: Wie entferne ich mit der Aspose.PDF-Bibliothek den gesamten Text aus einem PDF-Dokument?

A: Das Tutorial führt Sie Schritt für Schritt durch den Vorgang:

1.  Öffnen Sie das PDF-Dokument mit dem`Document` Klasse.
2.  Initialisieren Sie einen`TextFragmentAbsorber` Objekt.
3. Verwenden Sie den Absorber, um den gesamten absorbierten Text aus dem PDF-Dokument zu entfernen.
4. Speichern Sie das geänderte PDF-Dokument.

#### F: Kann ich Text aus bestimmten Bereichen des Dokuments selektiv entfernen?

A: Das Tutorial konzentriert sich auf das Entfernen des gesamten Textes aus dem gesamten PDF-Dokument. Wenn Sie Text aus bestimmten Bereichen selektiv entfernen möchten, müssen Sie den Ansatz ändern und eine komplexere Logik verwenden, um bestimmte Textfragmente zu identifizieren und zu entfernen.

#### F: Wie funktioniert das`TextFragmentAbsorber` work to remove text?

 A: Die`TextFragmentAbsorber`ist eine Klasse der Aspose.PDF-Bibliothek, die Textfragmente aus einem PDF-Dokument aufnehmen kann. Durch die Verwendung der`RemoveAllText` Methode der`TextFragmentAbsorber` Klasse können Sie alle aufgenommenen Textfragmente aus dem Dokument entfernen.

#### F: Was ist das erwartete Ergebnis der Ausführung des bereitgestellten Codes?

A: Indem Sie dem Lernprogramm folgen und den bereitgestellten C#-Code ausführen, entfernen Sie den gesamten Text aus dem PDF-Eingabedokument und speichern die geänderte Version als PDF-Ausgabedatei.

#### F: Kann ich den Code ändern, um Text nur von bestimmten Seiten oder Bereichen zu entfernen?

A: Ja, Sie können den Code ändern, um dies zu erreichen. Für die selektive Textentfernung müssen Sie den Code anpassen, um bestimmte Seiten oder Bereiche im PDF-Dokument anzusprechen.

#### F: Ist für dieses Tutorial eine gültige Aspose-Lizenz erforderlich?

A: Ja, eine gültige Aspose-Lizenz ist erforderlich, um den Code in diesem Tutorial erfolgreich auszuführen. Sie können eine Volllizenz oder eine 30-tägige temporäre Lizenz von der Aspose-Website erhalten.