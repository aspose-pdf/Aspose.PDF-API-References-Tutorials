---
title: Text und Bild als Absatz in PDF-Datei
linktitle: Text und Bild als Absatz in PDF-Datei
second_title: Aspose.PDF für .NET API-Referenz
description: Erfahren Sie, wie Sie mit Aspose.PDF für .NET Text und ein Bild als Inline-Absätze in eine PDF-Datei einfügen.
type: docs
weight: 530
url: /de/net/programming-with-text/text-and-image-as-paragraph/
---
Dieses Tutorial erklärt, wie Sie mit Aspose.PDF für .NET Text und ein Bild als Inline-Absätze in eine PDF-Datei einfügen. Der bereitgestellte C#-Quellcode demonstriert den Vorgang Schritt für Schritt.

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
using Aspose.Pdf.Drawing;
```

## Schritt 3: Pfad zum Dokumentverzeichnis festlegen

 Legen Sie den Pfad zu Ihrem Dokumentverzeichnis fest mit dem`dataDir` Variable:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Ersetzen`"YOUR DOCUMENT DIRECTORY"` durch den tatsächlichen Pfad zu Ihrem Dokumentverzeichnis.

## Schritt 4: Neues Dokument und neue Seite erstellen

 Erstellen Sie ein neues`Document` Objekt und fügen Sie seiner Seitensammlung eine Seite hinzu:

```csharp
Document doc = new Document();
Page page = doc.Pages.Add();
```

## Schritt 5: Erstellen Sie ein TextFragment und fügen Sie es als Absatz hinzu

 Erstellen Sie ein`TextFragment` Objekt und fügen Sie es der Absatzsammlung der Seite hinzu:

```csharp
TextFragment text = new TextFragment("Hello World.. ");
page.Paragraphs.Add(text);
```

## Schritt 6: Ein Bild als Inline-Absatz hinzufügen

 Erstellen Sie ein`Aspose.Pdf.Image` Objekt und legen Sie es als Inline-Absatz fest, sodass es direkt nach dem vorherigen Absatz angezeigt wird:

```csharp
Aspose.Pdf.Image image = new Aspose.Pdf.Image();
image.IsInLineParagraph = true;
image.File = dataDir + "aspose-logo.jpg";
image.FixHeight = 30; // Optional: Bildhöhe festlegen
image.FixWidth = 100; // Optional: Bildbreite festlegen
page.Paragraphs.Add(image);
```

 Ersetzen`"aspose-logo.jpg"` durch den tatsächlichen Bilddateinamen und passen Sie die optionale Bildhöhe und -breite nach Wunsch an.

## Schritt 7: Ein weiteres TextFragment als Inline-Absatz hinzufügen

 Initialisieren Sie den`TextFragment` Objekt mit anderem Inhalt und fügen Sie es als Inline-Absatz hinzu:

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

 Ersetzen Sie unbedingt`"TextAndImageAsParagraph_out.pdf"` durch den gewünschten Ausgabedateinamen.

### Beispielquellcode für Text und Bild als Absatz mit Aspose.PDF für .NET 
```csharp
// Der Pfad zum Dokumentverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Dokumentinstanz instantiieren
Document doc = new Document();
// Seite zur Seitensammlung der Dokumentinstanz hinzufügen
Page page = doc.Pages.Add();
// Textfragment erstellen
TextFragment text = new TextFragment("Hello World.. ");
// Textfragment zur Absatzsammlung des Seitenobjekts hinzufügen
page.Paragraphs.Add(text);
// Erstellen einer Imageinstanz
Aspose.Pdf.Image image = new Aspose.Pdf.Image();
// Stellen Sie das Bild als Inline-Absatz ein, sodass es direkt danach erscheint
// Das vorherige Absatzobjekt (TextFragment)
image.IsInLineParagraph = true;
// Bilddateipfad angeben
image.File = dataDir + "aspose-logo.jpg";
// Bildhöhe festlegen (optional)
image.FixHeight = 30;
// Bildbreite festlegen (optional)
image.FixWidth = 100;
// Bild zur Absatzsammlung des Seitenobjekts hinzufügen
page.Paragraphs.Add(image);
// TextFragment-Objekt mit anderem Inhalt neu initialisieren
text = new TextFragment(" Hello Again..");
// TextFragment als Inline-Absatz festlegen
text.IsInLineParagraph = true;
// Neu erstelltes TextFragment zur Absatzsammlung der Seite hinzufügen
page.Paragraphs.Add(text);
dataDir = dataDir + "TextAndImageAsParagraph_out.pdf";
doc.Save(dataDir);
Console.WriteLine("\nText and image added successfully as an inline paragraphs.\nFile saved at " + dataDir);
```

## Abschluss

Herzlichen Glückwunsch! Sie haben erfolgreich gelernt, wie Sie mit Aspose.PDF für .NET Text und ein Bild als Inline-Absätze in ein PDF-Dokument einfügen. Dieses Tutorial bietet eine Schritt-für-Schritt-Anleitung vom Einrichten des Projekts bis zum Speichern des geänderten Dokuments. Sie können diesen Code jetzt in Ihre eigenen C#-Projekte integrieren, um das Layout von Text und Bildern in PDF-Dateien anzupassen.

### Häufig gestellte Fragen

#### F: Was ist der Zweck des Tutorials „Text und Bild als Absatz in PDF-Datei“?

A: Das Tutorial „Text und Bild als Absatz in PDF-Datei“ soll Benutzern zeigen, wie sie mit Aspose.PDF für .NET sowohl Text als auch Bilder als Inline-Absätze in ein PDF-Dokument einfügen können. Das Tutorial enthält schrittweise Anleitungen und C#-Codebeispiele, um den Vorgang zu demonstrieren.

#### F: Wie hilft dieses Tutorial beim Hinzufügen von Text und Bildern als Inline-Absätze?

A: Dieses Tutorial hilft Benutzern zu verstehen, wie sie mit Aspose.PDF für .NET sowohl Text als auch Bilder als Inline-Absätze in ein PDF-Dokument einbinden können. Indem sie den bereitgestellten Schritten und Codebeispielen folgen, können Benutzer PDF-Dateien mit benutzerdefinierten Layouts erstellen, die Text und Bilder kombinieren.

#### F: Welche Voraussetzungen sind erforderlich, um diesem Tutorial folgen zu können?

A: Bevor Sie mit dem Tutorial beginnen, sollten Sie über Grundkenntnisse der Programmiersprache C# verfügen. Darüber hinaus müssen Sie die Bibliothek Aspose.PDF für .NET installiert haben. Sie können sie von der Aspose-Website herunterladen oder mit NuGet in Ihrem Projekt installieren.

#### F: Wie richte ich mein Projekt ein, um diesem Tutorial zu folgen?

A: Erstellen Sie zunächst ein neues C#-Projekt in Ihrer bevorzugten integrierten Entwicklungsumgebung (IDE) und fügen Sie einen Verweis auf die Aspose.PDF-Bibliothek für .NET hinzu. Auf diese Weise können Sie die Funktionen der Bibliothek für die Arbeit mit PDF-Dokumenten, Textfragmenten und Bildern nutzen.

#### F: Kann ich dieses Tutorial verwenden, um mehrere Text- und Bildabsätze in eine PDF-Datei einzufügen?

A: Ja, Sie können die bereitgestellten Codebeispiele verwenden, um mehrere Instanzen von Text- und Bildabsätzen in dasselbe PDF-Dokument einzufügen. Dieses Tutorial zeigt, wie Sie Inline-Absätze erstellen, sodass Sie ganz einfach verschiedene Kombinationen aus Text und Bildern einfügen können.

#### F: Wie lege ich Inhalt und Aussehen der Textabsätze und Bilder fest?

 A: Das Tutorial zeigt, wie man`TextFragment`Objekte zur Darstellung von Textabschnitten und`Aspose.Pdf.Image` Objekte zur Darstellung von Bildern. Sie können Inhalt, Abmessungen und Erscheinungsbild von Text und Bildern mithilfe der bereitgestellten Codebeispiele anpassen.

#### F: Kann ich das Layout der Inline-Absätze anpassen?

 A: Ja, Sie können das Layout von Inline-Absätzen anpassen, indem Sie deren Positionierung, Abmessungen und Reihenfolge innerhalb der Seite steuern. Das Tutorial zeigt, wie Sie Inline-Attribute festlegen, wie zum Beispiel`IsInLineParagraph`, um das Layout von Text- und Bildabsätzen zu steuern.

#### F: Wie speichere ich das geänderte PDF-Dokument?

 A: Um das geänderte PDF-Dokument zu speichern, können Sie den`Save` Methode der`Document` Objekt. Das Tutorial enthält Codebeispiele, die zeigen, wie das resultierende PDF-Dokument gespeichert wird.