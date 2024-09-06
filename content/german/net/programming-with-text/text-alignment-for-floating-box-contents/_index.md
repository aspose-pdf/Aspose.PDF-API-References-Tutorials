---
title: Textausrichtung für schwebende Boxinhalte in PDF-Datei
linktitle: Textausrichtung für schwebende Boxinhalte in PDF-Datei
second_title: Aspose.PDF für .NET API-Referenz
description: Erfahren Sie, wie Sie mit Aspose.PDF für .NET Text in schwebenden Feldern in PDF-Dateien ausrichten.
type: docs
weight: 520
url: /de/net/programming-with-text/text-alignment-for-floating-box-contents/
---
Dieses Tutorial erklärt, wie Sie mit Aspose.PDF für .NET Text in schwebenden Boxen in PDF-Dateien ausrichten. Der bereitgestellte C#-Quellcode demonstriert den Vorgang Schritt für Schritt.

## Voraussetzungen

Bevor Sie mit dem Lernprogramm fortfahren, stellen Sie sicher, dass Sie über Folgendes verfügen:

- Grundkenntnisse der Programmiersprache C#.
- Aspose.PDF für .NET-Bibliothek installiert. Sie können es von der Aspose-Website beziehen oder NuGet verwenden, um es in Ihrem Projekt zu installieren.

## Schritt 1: Einrichten des Projekts

Beginnen Sie mit der Erstellung eines neuen C#-Projekts in Ihrer bevorzugten integrierten Entwicklungsumgebung (IDE) und fügen Sie einen Verweis auf die Aspose.PDF-Bibliothek für .NET hinzu.

## Schritt 2: Erforderliche Namespaces importieren

Fügen Sie am Anfang Ihrer C#-Datei die folgenden Using-Direktiven hinzu, um die erforderlichen Namespaces zu importieren:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

## Schritt 3: Pfad zum Dokumentverzeichnis festlegen

 Legen Sie den Pfad zu Ihrem Dokumentverzeichnis fest mit dem`dataDir` Variable:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Ersetzen`"YOUR DOCUMENT DIRECTORY"` durch den tatsächlichen Pfad zu Ihrem Dokumentverzeichnis.

## Schritt 4: Neues Dokument erstellen

 Erstellen Sie ein neues`Document` Objekt:

```csharp
Aspose.Pdf.Document doc = new Document();
doc.Pages.Add();
```

## Schritt 5: Schwebende Boxen mit Textfragmenten erstellen

 Erstellen Sie mehrere`FloatingBox` Objekte mit unterschiedlicher vertikaler und horizontaler Ausrichtung:

```csharp
Aspose.Pdf.FloatingBox floatBox = new Aspose.Pdf.FloatingBox(100, 100);
floatBox.VerticalAlignment = VerticalAlignment.Bottom;
floatBox.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Right;
floatBox.Paragraphs.Add(new TextFragment("FloatingBox_bottom"));
floatBox.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, Aspose.Pdf.Color.Blue);
doc.Pages[1].Paragraphs.Add(floatBox);

Aspose.Pdf.FloatingBox floatBox1 = new Aspose.Pdf.FloatingBox(100, 100);
floatBox1.VerticalAlignment = VerticalAlignment.Center;
floatBox1.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Right;
floatBox1.Paragraphs.Add(new TextFragment("FloatingBox_center"));
floatBox1.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, Aspose.Pdf.Color.Blue);
doc.Pages[1].Paragraphs.Add(floatBox1);

Aspose.Pdf.FloatingBox floatBox2 = new Aspose.Pdf.FloatingBox(100, 100);
floatBox2.VerticalAlignment = VerticalAlignment.Top;
floatBox2.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Right;
floatBox2.Paragraphs.Add(new TextFragment("FloatingBox_top"));
floatBox2.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, Aspose.Pdf.Color.Blue);
doc.Pages[1].Paragraphs.Add(floatBox2);
```

 Ändern Sie den Text und das Styling der`TextFragment` Objekte nach Wunsch.

## Schritt 6: Speichern Sie das PDF-Dokument

Speichern Sie das geänderte PDF-Dokument:

```csharp
doc.Save(dataDir + "FloatingBox_alignment_review_out.pdf");
```

 Ersetzen Sie unbedingt`"FloatingBox_alignment_review_out.pdf"` durch den gewünschten Ausgabedateinamen.

### Beispielquellcode für die Textausrichtung für schwebende Boxinhalte mit Aspose.PDF für .NET 
```csharp
// Der Pfad zum Dokumentverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Aspose.Pdf.Document doc = new Document();
doc.Pages.Add();
Aspose.Pdf.FloatingBox floatBox = new Aspose.Pdf.FloatingBox(100, 100);
floatBox.VerticalAlignment = VerticalAlignment.Bottom;
floatBox.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Right;
floatBox.Paragraphs.Add(new TextFragment("FloatingBox_bottom"));
floatBox.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, Aspose.Pdf.Color.Blue);
doc.Pages[1].Paragraphs.Add(floatBox);
Aspose.Pdf.FloatingBox floatBox1 = new Aspose.Pdf.FloatingBox(100, 100);
floatBox1.VerticalAlignment = VerticalAlignment.Center;
floatBox1.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Right;
floatBox1.Paragraphs.Add(new TextFragment("FloatingBox_center"));
floatBox1.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, Aspose.Pdf.Color.Blue);
doc.Pages[1].Paragraphs.Add(floatBox1);
Aspose.Pdf.FloatingBox floatBox2 = new Aspose.Pdf.FloatingBox(100, 100);
floatBox2.VerticalAlignment = VerticalAlignment.Top;
floatBox2.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Right;
floatBox2.Paragraphs.Add(new TextFragment("FloatingBox_top"));
floatBox2.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, Aspose.Pdf.Color.Blue);
doc.Pages[1].Paragraphs.Add(floatBox2);
doc.Save(dataDir + "FloatingBox_alignment_review_out.pdf");
```

## Abschluss

Herzlichen Glückwunsch! Sie haben erfolgreich gelernt, wie Sie mit Aspose.PDF für .NET Text in schwebenden Boxen in einem PDF-Dokument ausrichten. Dieses Tutorial bietet eine Schritt-für-Schritt-Anleitung vom Einrichten des Projekts bis zum Speichern des geänderten Dokuments. Sie können diesen Code jetzt in Ihre eigenen C#-Projekte integrieren, um die Ausrichtung von Text in schwebenden Boxen in PDF-Dateien anzupassen.

### Häufig gestellte Fragen

#### F: Was ist der Zweck des Tutorials „Textausrichtung für schwebende Boxinhalte in PDF-Dateien“?

A: Das Tutorial „Textausrichtung für schwebende Boxinhalte in PDF-Dateien“ soll Benutzern zeigen, wie sie Text in schwebenden Boxen in einem PDF-Dokument mit Aspose.PDF für .NET ausrichten können. Das Tutorial enthält schrittweise Anleitungen und C#-Codebeispiele zur Demonstration des Vorgangs.

#### F: Wie hilft dieses Tutorial beim Ausrichten von Text in schwebenden Boxen?

A: Dieses Tutorial hilft Benutzern zu verstehen, wie sie Aspose.PDF für .NET verwenden können, um Text in schwebenden Boxen in einem PDF-Dokument auszurichten. Indem Benutzer die bereitgestellten Schritte und Codebeispiele befolgen, können sie die vertikale und horizontale Ausrichtung von Text in schwebenden Boxen anpassen.

#### F: Welche Voraussetzungen sind erforderlich, um diesem Tutorial folgen zu können?

A: Bevor Sie mit dem Tutorial beginnen, sollten Sie über Grundkenntnisse der Programmiersprache C# verfügen. Darüber hinaus müssen Sie die Bibliothek Aspose.PDF für .NET installiert haben. Sie können sie von der Aspose-Website herunterladen oder mit NuGet in Ihrem Projekt installieren.

#### F: Wie richte ich mein Projekt ein, um diesem Tutorial zu folgen?

A: Erstellen Sie zunächst ein neues C#-Projekt in Ihrer bevorzugten integrierten Entwicklungsumgebung (IDE) und fügen Sie einen Verweis auf die Aspose.PDF-Bibliothek für .NET hinzu. Auf diese Weise können Sie die Funktionen der Bibliothek für die Arbeit mit PDF-Dokumenten und die Ausrichtung von Text in schwebenden Feldern nutzen.

#### F: Kann ich dieses Tutorial verwenden, um Text innerhalb einer beliebigen Art von schwebendem Feld auszurichten?

A: Ja, dieses Tutorial enthält Anweisungen zum Ausrichten von Text in schwebenden Boxen in einem PDF-Dokument mit Aspose.PDF für .NET. Sie können die bereitgestellten Codebeispiele verwenden, um die vertikale und horizontale Ausrichtung von Text in schwebenden Boxen anzupassen.

#### F: Wie lege ich die Textausrichtung innerhalb eines schwebenden Felds fest?

 A: Das Tutorial zeigt, wie man`FloatingBox`Objekte und legen Sie deren`VerticalAlignment` Und`HorizontalAlignment` Eigenschaften zur Steuerung der Ausrichtung des enthaltenen Textes. Sie können diese Eigenschaften Ihren Anforderungen entsprechend anpassen.

#### F: Wie kann ich das Erscheinungsbild der schwebenden Boxen anpassen?

 A: Sie können das Erscheinungsbild der schwebenden Boxen anpassen, indem Sie Eigenschaften wie Rahmen, Größe und Textinhalt ändern. Das Tutorial enthält Codebeispiele, die zeigen, wie Sie die`FloatingBox` Objekte.

#### F: Kann ich mehrere schwebende Boxen mit unterschiedlicher Ausrichtung in dasselbe PDF-Dokument einfügen?

 A: Ja, das Tutorial zeigt, wie man mehrere`FloatingBox` Objekte mit unterschiedlicher vertikaler und horizontaler Ausrichtung und fügen Sie sie demselben PDF-Dokument hinzu. Auf diese Weise können Sie die Auswirkungen verschiedener Ausrichtungen innerhalb desselben Dokuments sehen.

#### F: Wie speichere ich das geänderte PDF-Dokument?

 A: Um das geänderte PDF-Dokument zu speichern, können Sie den`Save` Methode der`Document` Objekt. Das Tutorial enthält Codebeispiele, die zeigen, wie das resultierende PDF-Dokument gespeichert wird.