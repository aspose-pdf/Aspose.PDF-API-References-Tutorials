---
title: Text und Bild als Absatz in einer PDF-Datei
linktitle: Text und Bild als Absatz in einer PDF-Datei
second_title: Aspose.PDF für .NET API-Referenz
description: Erfahren Sie, wie Sie mit Aspose.PDF für .NET Text und ein Bild als Inline-Absätze in eine PDF-Datei einfügen.
type: docs
weight: 530
url: /de/net/programming-with-text/text-and-image-as-paragraph/
---
In diesem Tutorial wird erläutert, wie Sie mit Aspose.PDF für .NET Text und ein Bild als Inline-Absätze in eine PDF-Datei einfügen. Der bereitgestellte C#-Quellcode demonstriert den Prozess Schritt für Schritt.

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
using Aspose.Pdf.Drawing;
```

## Schritt 3: Legen Sie den Pfad zum Dokumentverzeichnis fest

 Legen Sie den Pfad zu Ihrem Dokumentverzeichnis mit fest`dataDir` Variable:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Ersetzen`"YOUR DOCUMENT DIRECTORY"` mit dem tatsächlichen Pfad zu Ihrem Dokumentverzeichnis.

## Schritt 4: Erstellen Sie ein neues Dokument und eine neue Seite

 Erstelle eine neue`Document` Objekt und fügen Sie eine Seite zu seiner Seitensammlung hinzu:

```csharp
Document doc = new Document();
Page page = doc.Pages.Add();
```

## Schritt 5: Erstellen Sie ein TextFragment und fügen Sie es als Absatz hinzu

 Ein ... kreieren`TextFragment` Objekt und fügen Sie es der Absatzsammlung der Seite hinzu:

```csharp
TextFragment text = new TextFragment("Hello World.. ");
page.Paragraphs.Add(text);
```

## Schritt 6: Fügen Sie ein Bild als Inline-Absatz hinzu

 Erstelle ein`Aspose.Pdf.Image` Objekt und legen Sie es als Inline-Absatz fest, sodass es direkt nach dem vorherigen Absatz erscheint:

```csharp
Aspose.Pdf.Image image = new Aspose.Pdf.Image();
image.IsInLineParagraph = true;
image.File = dataDir + "aspose-logo.jpg";
image.FixHeight = 30; // Optional: Bildhöhe festlegen
image.FixWidth = 100; // Optional: Bildbreite festlegen
page.Paragraphs.Add(image);
```

 Ersetzen`"aspose-logo.jpg"` Geben Sie den tatsächlichen Namen der Bilddatei ein und passen Sie die optionale Bildhöhe und -breite wie gewünscht an.

## Schritt 7: Fügen Sie ein weiteres TextFragment als Inline-Absatz hinzu

 Initialisieren Sie das neu`TextFragment` Objekt mit unterschiedlichem Inhalt und fügen Sie es als Inline-Absatz hinzu:

```csharp
text = new TextFragment(" Hello Again..");
text.IsInLineParagraph = true;
page.Paragraphs.Add(text);
```

## Schritt 8: Speichern Sie das PDF-Dokument

Speichern Sie das geänderte PDF-Dokument:

```csharp
dataDir = dataDir + "TextAndImageAsParagraph_out.pdf";
doc.Save(dataDir);
```

 Unbedingt austauschen`"TextAndImageAsParagraph_out.pdf"` mit dem gewünschten Ausgabedateinamen.

### Beispielquellcode für Text und Bild als Absatz mit Aspose.PDF für .NET 
```csharp
// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Dokumentinstanz instanziieren
Document doc = new Document();
// Seite zur Seitensammlung der Dokumentinstanz hinzufügen
Page page = doc.Pages.Add();
// Erstellen Sie TextFragmnet
TextFragment text = new TextFragment("Hello World.. ");
// Fügen Sie ein Textfragment zur Absatzsammlung des Seitenobjekts hinzu
page.Paragraphs.Add(text);
// Erstellen Sie eine Image-Instanz
Aspose.Pdf.Image image = new Aspose.Pdf.Image();
// Legen Sie das Bild als Inline-Absatz fest, sodass es direkt danach erscheint
// Das vorherige Absatzobjekt (TextFragment)
image.IsInLineParagraph = true;
// Geben Sie den Pfad der Bilddatei an
image.File = dataDir + "aspose-logo.jpg";
// Bildhöhe einstellen (optional)
image.FixHeight = 30;
// Bildbreite festlegen (optional)
image.FixWidth = 100;
// Bild zur Absatzsammlung des Seitenobjekts hinzufügen
page.Paragraphs.Add(image);
// TextFragment-Objekt mit anderem Inhalt neu initialisieren
text = new TextFragment(" Hello Again..");
// Legen Sie TextFragment als Inline-Absatz fest
text.IsInLineParagraph = true;
// Fügen Sie das neu erstellte TextFragment zur Absatzsammlung der Seite hinzu
page.Paragraphs.Add(text);
dataDir = dataDir + "TextAndImageAsParagraph_out.pdf";
doc.Save(dataDir);
Console.WriteLine("\nText and image added successfully as an inline paragraphs.\nFile saved at " + dataDir);
```

## Abschluss

Glückwunsch! Sie haben erfolgreich gelernt, wie Sie mit Aspose.PDF für .NET Text und ein Bild als Inline-Absätze in ein PDF-Dokument einfügen. Dieses Tutorial bietet eine Schritt-für-Schritt-Anleitung vom Einrichten des Projekts bis zum Speichern des geänderten Dokuments. Sie können diesen Code jetzt in Ihre eigenen C#-Projekte integrieren, um das Layout von Text und Bildern in PDF-Dateien anzupassen.

### FAQs

#### F: Was ist der Zweck des Tutorials „Text und Bild als Absatz in einer PDF-Datei“?

A: Das Tutorial „Text und Bild als Absatz in einer PDF-Datei“ soll Benutzern zeigen, wie sie mit Aspose.PDF für .NET sowohl Text als auch Bilder als Inline-Absätze in ein PDF-Dokument einfügen. Das Tutorial bietet Schritt-für-Schritt-Anleitungen und C#-Codebeispiele zur Veranschaulichung des Prozesses.

#### F: Wie hilft dieses Tutorial beim Hinzufügen von Text und Bildern als Inline-Absätze?

A: Dieses Tutorial hilft Benutzern zu verstehen, wie sie Aspose.PDF für .NET verwenden, um sowohl Text als auch Bilder als Inline-Absätze in ein PDF-Dokument zu integrieren. Durch Befolgen der bereitgestellten Schritte und Codebeispiele können Benutzer PDF-Dateien mit benutzerdefinierten Layouts erstellen, die Text und Bilder kombinieren.

#### F: Welche Voraussetzungen sind erforderlich, um diesem Tutorial folgen zu können?

A: Bevor Sie mit dem Tutorial beginnen, sollten Sie über grundlegende Kenntnisse der Programmiersprache C# verfügen. Darüber hinaus muss die Bibliothek Aspose.PDF für .NET installiert sein. Sie können es von der Aspose-Website herunterladen oder mit NuGet in Ihrem Projekt installieren.

#### F: Wie richte ich mein Projekt ein, um diesem Tutorial zu folgen?

A: Erstellen Sie zunächst ein neues C#-Projekt in Ihrer bevorzugten integrierten Entwicklungsumgebung (IDE) und fügen Sie einen Verweis auf die Bibliothek Aspose.PDF für .NET hinzu. Dadurch können Sie die Funktionen der Bibliothek für die Arbeit mit PDF-Dokumenten, Textfragmenten und Bildern nutzen.

#### F: Kann ich dieses Tutorial verwenden, um mehrere Text- und Bildabsätze in eine PDF-Datei einzufügen?

A: Ja, Sie können die bereitgestellten Codebeispiele verwenden, um mehrere Instanzen von Text- und Bildabsätzen innerhalb desselben PDF-Dokuments hinzuzufügen. In diesem Tutorial wird gezeigt, wie Sie Inline-Absätze erstellen, sodass Sie problemlos verschiedene Kombinationen aus Text und Bildern einfügen können.

#### F: Wie lege ich den Inhalt und das Aussehen der Textabsätze und Bilder fest?

 A: Das Tutorial zeigt, wie man erstellt`TextFragment`Objekte zur Darstellung von Textabsätzen und`Aspose.Pdf.Image` Objekte zur Darstellung von Bildern. Mithilfe der bereitgestellten Codebeispiele können Sie den Inhalt, die Abmessungen und das Erscheinungsbild von Text und Bildern anpassen.

#### F: Kann ich das Layout der Inline-Absätze anpassen?

 A: Ja, Sie können das Layout von Inline-Absätzen anpassen, indem Sie deren Positionierung, Abmessungen und Reihenfolge innerhalb der Seite steuern. Das Tutorial zeigt, wie man Inline-Attribute festlegt, z`IsInLineParagraph`, um das Layout von Text- und Bildabsätzen zu steuern.

#### F: Wie speichere ich das geänderte PDF-Dokument?

 A: Um das geänderte PDF-Dokument zu speichern, können Sie das verwenden`Save` Methode der`Document` Objekt. Das Tutorial stellt Codebeispiele bereit, die veranschaulichen, wie das resultierende PDF-Dokument gespeichert wird.