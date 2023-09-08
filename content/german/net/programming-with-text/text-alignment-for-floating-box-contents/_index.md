---
title: Textausrichtung für Floating-Box-Inhalte in PDF-Dateien
linktitle: Textausrichtung für Floating-Box-Inhalte in PDF-Dateien
second_title: Aspose.PDF für .NET API-Referenz
description: Erfahren Sie, wie Sie mit Aspose.PDF für .NET Text in schwebenden Feldern in einer PDF-Datei ausrichten.
type: docs
weight: 520
url: /de/net/programming-with-text/text-alignment-for-floating-box-contents/
---
In diesem Tutorial wird erläutert, wie Sie mit Aspose.PDF für .NET Text in schwebenden Feldern in einer PDF-Datei ausrichten. Der bereitgestellte C#-Quellcode demonstriert den Prozess Schritt für Schritt.

## Voraussetzungen

Bevor Sie mit dem Tutorial fortfahren, stellen Sie sicher, dass Sie über Folgendes verfügen:

- Grundkenntnisse der Programmiersprache C#.
- Aspose.PDF für .NET-Bibliothek installiert. Sie können es von der Aspose-Website herunterladen oder NuGet verwenden, um es in Ihrem Projekt zu installieren.

## Schritt 1: Richten Sie das Projekt ein

Erstellen Sie zunächst ein neues C#-Projekt in Ihrer bevorzugten integrierten Entwicklungsumgebung (IDE) und fügen Sie einen Verweis auf die Aspose.PDF für .NET-Bibliothek hinzu.

## Schritt 2: Importieren Sie die erforderlichen Namespaces

Fügen Sie am Anfang Ihrer C#-Datei die folgenden using-Anweisungen hinzu, um die erforderlichen Namespaces zu importieren:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

## Schritt 3: Legen Sie den Pfad zum Dokumentverzeichnis fest

 Legen Sie den Pfad zu Ihrem Dokumentverzeichnis mit fest`dataDir` Variable:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Ersetzen`"YOUR DOCUMENT DIRECTORY"` mit dem tatsächlichen Pfad zu Ihrem Dokumentverzeichnis.

## Schritt 4: Erstellen Sie ein neues Dokument

 Erstelle eine neue`Document` Objekt:

```csharp
Aspose.Pdf.Document doc = new Document();
doc.Pages.Add();
```

## Schritt 5: Erstellen Sie schwebende Boxen mit Textfragmenten

 Mehrere erstellen`FloatingBox` Objekte mit unterschiedlicher vertikaler und horizontaler Ausrichtung:

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

 Ändern Sie den Text und den Stil des`TextFragment` Objekte nach Wunsch.

## Schritt 6: Speichern Sie das PDF-Dokument

Speichern Sie das geänderte PDF-Dokument:

```csharp
doc.Save(dataDir + "FloatingBox_alignment_review_out.pdf");
```

 Unbedingt austauschen`"FloatingBox_alignment_review_out.pdf"` mit dem gewünschten Ausgabedateinamen.

### Beispielquellcode für die Textausrichtung für Floating-Box-Inhalte mit Aspose.PDF für .NET 
```csharp
// Der Pfad zum Dokumentenverzeichnis.
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

Glückwunsch! Sie haben erfolgreich gelernt, wie Sie mit Aspose.PDF für .NET Text in schwebenden Feldern in einem PDF-Dokument ausrichten. Dieses Tutorial bietet eine Schritt-für-Schritt-Anleitung vom Einrichten des Projekts bis zum Speichern des geänderten Dokuments. Sie können diesen Code jetzt in Ihre eigenen C#-Projekte integrieren, um die Textausrichtung in schwebenden Feldern in PDF-Dateien anzupassen.

### FAQs

#### F: Was ist der Zweck des Tutorials „Textausrichtung für Floating-Box-Inhalte in PDF-Dateien“?

A: Das Tutorial „Textausrichtung für schwebende Boxinhalte in PDF-Dateien“ zielt darauf ab, Benutzern bei der Ausrichtung von Text in schwebenden Boxen in einem PDF-Dokument mit Aspose.PDF für .NET zu helfen. Das Tutorial bietet Schritt-für-Schritt-Anleitungen und C#-Codebeispiele zur Veranschaulichung des Prozesses.

#### F: Wie hilft dieses Tutorial beim Ausrichten von Text in schwebenden Feldern?

A: Dieses Tutorial hilft Benutzern zu verstehen, wie sie Aspose.PDF für .NET verwenden, um Text in schwebenden Feldern in einem PDF-Dokument auszurichten. Durch Befolgen der bereitgestellten Schritte und Codebeispiele können Benutzer die vertikale und horizontale Ausrichtung von Text in schwebenden Feldern anpassen.

#### F: Welche Voraussetzungen sind erforderlich, um diesem Tutorial folgen zu können?

A: Bevor Sie mit dem Tutorial beginnen, sollten Sie über grundlegende Kenntnisse der Programmiersprache C# verfügen. Darüber hinaus muss die Bibliothek Aspose.PDF für .NET installiert sein. Sie können es von der Aspose-Website herunterladen oder mit NuGet in Ihrem Projekt installieren.

#### F: Wie richte ich mein Projekt ein, um diesem Tutorial zu folgen?

A: Erstellen Sie zunächst ein neues C#-Projekt in Ihrer bevorzugten integrierten Entwicklungsumgebung (IDE) und fügen Sie einen Verweis auf die Bibliothek Aspose.PDF für .NET hinzu. Dadurch können Sie die Funktionen der Bibliothek zum Arbeiten mit PDF-Dokumenten und zum Ausrichten von Text in schwebenden Feldern nutzen.

#### F: Kann ich dieses Tutorial verwenden, um Text in jeder Art von Schweberahmen auszurichten?

A: Ja, dieses Tutorial enthält Anweisungen zum Ausrichten von Text in schwebenden Feldern in einem PDF-Dokument mit Aspose.PDF für .NET. Mithilfe der bereitgestellten Codebeispiele können Sie die vertikale und horizontale Ausrichtung von Text in schwebenden Feldern anpassen.

#### F: Wie lege ich die Ausrichtung von Text innerhalb eines schwebenden Felds fest?

 A: Das Tutorial zeigt, wie man erstellt`FloatingBox`Objekte und setzen ihre`VerticalAlignment` Und`HorizontalAlignment` Eigenschaften, um die Ausrichtung des enthaltenen Textes zu steuern. Sie können diese Eigenschaften entsprechend Ihren Anforderungen anpassen.

#### F: Wie kann ich das Erscheinungsbild der schwebenden Boxen anpassen?

 A: Sie können das Erscheinungsbild der schwebenden Boxen anpassen, indem Sie Eigenschaften wie Rahmen, Größe und Textinhalt ändern. Das Tutorial enthält Codebeispiele, die veranschaulichen, wie das erstellt und gestaltet wird`FloatingBox` Objekte.

#### F: Kann ich im selben PDF-Dokument mehrere Schweberahmen mit unterschiedlicher Ausrichtung hinzufügen?

 A: Ja, das Tutorial zeigt, wie man mehrere erstellt`FloatingBox` Objekte mit unterschiedlicher vertikaler und horizontaler Ausrichtung und fügen Sie sie demselben PDF-Dokument hinzu. Dadurch können Sie die Auswirkungen verschiedener Ausrichtungen innerhalb desselben Dokuments sehen.

#### F: Wie speichere ich das geänderte PDF-Dokument?

 A: Um das geänderte PDF-Dokument zu speichern, können Sie das verwenden`Save` Methode der`Document` Objekt. Das Tutorial stellt Codebeispiele bereit, die veranschaulichen, wie das resultierende PDF-Dokument gespeichert wird.