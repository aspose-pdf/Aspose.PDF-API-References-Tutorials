---
title: XForm auf Seite zeichnen
linktitle: XForm auf Seite zeichnen
second_title: Aspose.PDF für .NET API-Referenz
description: Schritt-für-Schritt-Anleitung zum Zeichnen eines XForm-Formulars auf einer PDF-Seite mit Aspose.PDF für .NET. Fügen Sie das Formular hinzu und positionieren Sie es auf der Seite.
type: docs
weight: 10
url: /de/net/programming-with-operators/draw-xform-on-page/
---
In diesem Tutorial stellen wir Ihnen eine Schritt-für-Schritt-Anleitung zum Zeichnen einer XForm auf einer Seite mit Aspose.PDF für .NET zur Verfügung. Aspose.PDF ist eine leistungsstarke Bibliothek, mit der Sie PDF-Dokumente programmgesteuert erstellen, bearbeiten und konvertieren können. Mithilfe der von Aspose.PDF bereitgestellten Operatoren können Sie ein XForm-Formular auf einer vorhandenen PDF-Seite hinzufügen und positionieren.

## Voraussetzungen

Bevor Sie beginnen, stellen Sie sicher, dass die folgenden Voraussetzungen erfüllt sind:

1. Visual Studio mit .NET Framework installiert.
2. Die Aspose.PDF-Bibliothek für .NET.

## Schritt 1: Projekteinrichtung

Erstellen Sie zunächst ein neues Projekt in Visual Studio und fügen Sie einen Verweis auf die Aspose.PDF für .NET-Bibliothek hinzu. Sie können die Bibliothek von der offiziellen Website von Aspose herunterladen und auf Ihrem Computer installieren.

## Schritt 2: Importieren Sie die erforderlichen Namespaces

Importieren Sie in Ihre C#-Codedatei die Namespaces, die für den Zugriff auf die von Aspose.PDF bereitgestellten Klassen und Methoden erforderlich sind:

```csharp
using System;
using System.IO;
using Aspose.Pdf;
using Aspose.Pdf.Operators;
```

## Schritt 3: Dateipfade festlegen

Definieren Sie die Dateipfade für das Hintergrundbild, die Eingabe-PDF-Datei und die Ausgabe-PDF-Datei:

```csharp
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";
string imageFile = dataDir + "aspose-logo.jpg";
string inFile = dataDir + "DrawXFormOnPage.pdf";
string outFile = dataDir + "blank-sample2_out.pdf";
```

Geben Sie unbedingt die tatsächlichen Dateipfade auf Ihrem Computer an.

## Schritt 4: Laden der Eingabe-PDF-Datei

Verwenden Sie den folgenden Code, um die Eingabe-PDF-Datei zu laden:

```csharp
using (Document doc = new Document(inFile))
{
OperatorCollection pageContents = doc.Pages[1].Contents;
// Der folgende Code verwendet die GSave/GRestore-Operatoren
// Der Code verwendet den ContatenateMatrix-Operator, um die XForm zu positionieren
// Der Code verwendet den Do-Operator, um die XForm auf der Seite zu zeichnen
// GSave/GRestore-Operatoren umschließen vorhandenen Inhalt
// Dies geschieht, um den anfänglichen Grafikstatus am Ende des vorhandenen Inhalts zu erhalten
// andernfalls kann es sein, dass am Ende der Kette vorhandener Operatoren unerwünschte Transformationen zurückbleiben
pageContents. Insert(1, new GSave());
pageContents. Add(new GRestore());
// Fügen Sie den GSave-Operator hinzu, um den Grafikstatus nach neuen Befehlen ordnungsgemäß zurückzusetzen
pageContents. Add(new GSave());

// Erstellen Sie die XForm
XForm form = XForm.CreateNewForm(doc.Pages[1], doc);
doc.Pages[1].Resources.Forms.Add(form);
form.Contents.Add(new GSave());
// Legen Sie die Breite und Höhe des Bildes fest
form.Contents.Add(new ConcatenateMatrix(200, 0, 0, 200, 0, 0));
// Laden Sie das Bild in einen Stream
Stream imageStream = new FileStream(imageFile, FileMode.Open);
// Fügen Sie das Bild zur XForm-Ressourcenbildersammlung hinzu
form.Resources.Images.Add(imageStream);
XImage ximage = form.Resources.Images[form.Resources.Images.Count];
// Verwendung des Do-Operators: Dieser Operator zeichnet das Bild
form.Contents.Add(new Do(ximage.Name));
form.Contents.Add(new GRestore());

pageContents. Add(new GSave());
//Positionieren Sie die XForm an den Koordinaten x=100 und y=500
pageContents. Add(new ConcatenateMatrix(1, 0, 0, 1, 100, 500));
// Zeichnen Sie die XForm mit dem Do-Operator
pageContents.Add(new Do(form.Name));
pageContents. Add(new GRestore());

pageContents. Add(new GSave());
// Positionieren Sie die XForm an den Koordinaten x=100 und y=300
pageContents. Add(new ConcatenateMatrix(1, 0, 0, 1, 100, 300));
// Zeichnen Sie die XForm mit dem Do-Operator
pageContents.Add(new Do(form.Name));
pageContents. Add(new GRestore());

// Stellen Sie den Grafikstatus mit GRestore nach GSave wieder her
pageContents. Add(new GRestore());
doc.Save(outFile);
}
```

Geben Sie unbedingt die tatsächlichen Dateipfade an und passen Sie die Seitenzahl und XForm-Positionen nach Bedarf an.

### Beispielquellcode für Draw XForm On Page mit Aspose.PDF für .NET
 
```csharp

// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";
string imageFile = dataDir+ "aspose-logo.jpg";
string inFile = dataDir + "DrawXFormOnPage.pdf";
string outFile = dataDir + "blank-sample2_out.pdf";
using (Document doc = new Document(inFile))
{
	OperatorCollection pageContents = doc.Pages[1].Contents;
	// Das Beispiel zeigt
	// Verwendung der GSave/GRestore-Operatoren
	// Verwendung des ContatenateMatrix-Operators zur Positionierung von xForm
	// Verwenden Sie den Operator, um xForm auf der Seite zu zeichnen
	// Umschließen Sie vorhandene Inhalte mit dem GSave/GRestore-Operatorpaar
	// Dies dient dazu, den anfänglichen Grafikstatus am Ende vorhandener Inhalte zu erhalten
	// Andernfalls könnten am Ende der bestehenden Operatorkette einige unerwünschte Transformationen verbleiben
	pageContents.Insert(1, new Aspose.Pdf.Operators.GSave());
	pageContents.Add(new Aspose.Pdf.Operators.GRestore());
	// Fügen Sie den Operator „Grafikstatus speichern“ hinzu, um den Grafikstatus nach neuen Befehlen ordnungsgemäß zu löschen
	pageContents.Add(new Aspose.Pdf.Operators.GSave());
	#region create xForm
	// xForm erstellen
	XForm form = XForm.CreateNewForm(doc.Pages[1], doc);
	doc.Pages[1].Resources.Forms.Add(form);
	form.Contents.Add(new Aspose.Pdf.Operators.GSave());
	// Definieren Sie die Bildbreite und -höhe
	form.Contents.Add(new Aspose.Pdf.Operators.ConcatenateMatrix(200, 0, 0, 200, 0, 0));
	// Bild in Stream laden
	Stream imageStream = new FileStream(imageFile, FileMode.Open);
	//Bild zur Bildersammlung der XForm-Ressourcen hinzufügen
	form.Resources.Images.Add(imageStream);
	XImage ximage = form.Resources.Images[form.Resources.Images.Count];
	// Verwenden des Do-Operators: Dieser Operator zeichnet ein Bild
	form.Contents.Add(new Aspose.Pdf.Operators.Do(ximage.Name));
	form.Contents.Add(new Aspose.Pdf.Operators.GRestore());
	#endregion
	pageContents.Add(new Aspose.Pdf.Operators.GSave());
	// Platzieren Sie das Formular an den Koordinaten x=100 y=500
	pageContents.Add(new Aspose.Pdf.Operators.ConcatenateMatrix(1, 0, 0, 1, 100, 500));
	// Zeichnen Sie ein Formular mit dem Do-Operator
	pageContents.Add(new Aspose.Pdf.Operators.Do(form.Name));
	pageContents.Add(new Aspose.Pdf.Operators.GRestore());
	pageContents.Add(new Aspose.Pdf.Operators.GSave());
	// Platzieren Sie das Formular an den x=100 y=300-Koordinaten
	pageContents.Add(new Aspose.Pdf.Operators.ConcatenateMatrix(1, 0, 0, 1, 100, 300));
	// Zeichnen Sie ein Formular mit dem Do-Operator
	pageContents.Add(new Aspose.Pdf.Operators.Do(form.Name));
	pageContents.Add(new Aspose.Pdf.Operators.GRestore());
	// Stellen Sie den Grafikstatus mit GRestore nach dem GSave wieder her
	pageContents.Add(new Aspose.Pdf.Operators.GRestore());
	doc.Save(outFile);                
}

```

## Abschluss

In diesem Tutorial haben Sie gelernt, wie Sie mit Aspose.PDF für .NET ein XForm-Formular auf einer PDF-Seite zeichnen. Wenn Sie die beschriebenen Schritte befolgen, können Sie ein XForm-Formular auf einer vorhandenen Seite hinzufügen und positionieren und so Ihren PDF-Dokumenten mehr Flexibilität verleihen.

### FAQs zum Zeichnen von XForm auf Seite

#### F: Was ist ein XForm in Aspose.PDF?

A: Ein XForm ist ein wiederverwendbares grafisches Objekt in einem PDF-Dokument. Sie können damit komplexe Grafiken, Bilder oder Texte definieren und zeichnen, die auf verschiedenen Seiten mehrfach wiederverwendet werden können.

#### F: Wie importiere ich die erforderlichen Namespaces für Aspose.PDF?

 A: Verwenden Sie in Ihrer C#-Codedatei die`using` Direktive zum Importieren der erforderlichen Namespaces für den Zugriff auf die von Aspose.PDF bereitgestellten Klassen und Methoden:
```csharp
using System;
using System.IO;
using Aspose.Pdf;
using Aspose.Pdf.Operators;
```

#### F: Was ist der Zweck der GSave- und GRestore-Operatoren?

 A: Die`GSave` Und`GRestore`Operatoren in Aspose.PDF werden zum Speichern und Wiederherstellen des Grafikstatus verwendet. Sie tragen dazu bei, dass Transformationen und Einstellungen, die auf einen Abschnitt des Inhalts angewendet werden, keine Auswirkungen auf nachfolgende Abschnitte haben.

#### F: Wie definiere ich ein XForm mit Aspose.PDF?

 A: Um eine XForm zu erstellen, verwenden Sie die`XForm.CreateNewForm` Methode und fügen Sie sie der hinzu`Resources.Forms` Sammlung einer bestimmten Seite. Anschließend können Sie Inhalte zu den XForms hinzufügen`Contents` Eigentum.

#### F: Wie kann ich ein Bild innerhalb einer XForm zeichnen?

 A: Laden Sie das Bild in einen Stream und fügen Sie es hinzu`Resources.Images` Sammlung der XForm. Benutzen Sie die`Do` Operator innerhalb der XForm's`Contents` um das Bild zu zeichnen.

#### F: Wie positioniere ich ein XForm auf einer PDF-Seite?

 A: Um ein XForm auf einer Seite zu positionieren, verwenden Sie die`ConcatenateMatrix` Operator innerhalb der Seite`Contents`. Passen Sie die Matrixparameter an, um die Übersetzung (Position) und Skalierung der XForm festzulegen.

#### F: Kann ich mehrere XForms auf derselben Seite zeichnen?

 A: Ja, Sie können mehrere XForms auf derselben Seite zeichnen, indem Sie die anpassen`ConcatenateMatrix`Parameter, um jede XForm an unterschiedlichen Koordinaten zu positionieren.

#### F: Kann ich den Inhalt einer XForm ändern, nachdem sie erstellt wurde?

 A: Ja, Sie können den Inhalt einer XForm nach der Erstellung ändern, indem Sie ihr zusätzliche Operatoren hinzufügen`Contents` Eigentum.

#### F: Was passiert, wenn ich die Operatoren GSave und GRestore weglasse?

A: Das Weglassen der Operatoren GSave und GRestore kann dazu führen, dass unerwünschte Transformationen oder Einstellungen auf nachfolgende Inhalte angewendet werden. Ihre Verwendung trägt dazu bei, einen sauberen Grafikzustand aufrechtzuerhalten.

#### F: Kann ich XForms auf verschiedenen Seiten des PDF-Dokuments wiederverwenden?

 A: Ja, Sie können XForms auf mehreren Seiten wiederverwenden, indem Sie dasselbe XForm hinzufügen`Resources.Forms` Sammlung verschiedener Seiten.

#### F: Gibt es eine Begrenzung für die Anzahl der XForms, die ich erstellen kann?

A: Es gibt zwar keine strikte Beschränkung für die Anzahl der XForms, die Sie erstellen können. Beachten Sie jedoch, dass zu viele XForms die Leistung und Speichernutzung beeinträchtigen können. Setzen Sie sie mit Bedacht ein.

#### F: Kann ich eine XForm drehen oder andere Transformationen anwenden?

 A: Ja, Sie können das verwenden`ConcatenateMatrix`Operator zum Anwenden von Transformationen wie Rotation, Skalierung und Translation auf eine XForm.
