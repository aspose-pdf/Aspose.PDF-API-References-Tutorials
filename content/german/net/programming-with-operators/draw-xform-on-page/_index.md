---
title: XForm auf Seite zeichnen
linktitle: XForm auf Seite zeichnen
second_title: Aspose.PDF für .NET API-Referenz
description: Schritt-für-Schritt-Anleitung zum Zeichnen eines XForm-Formulars auf einer PDF-Seite mit Aspose.PDF für .NET. Fügen Sie das Formular hinzu und positionieren Sie es auf der Seite.
type: docs
weight: 10
url: /de/net/programming-with-operators/draw-xform-on-page/
---
In diesem Tutorial erhalten Sie eine Schritt-für-Schritt-Anleitung zum Zeichnen eines XForms auf einer Seite mit Aspose.PDF für .NET. Aspose.PDF ist eine leistungsstarke Bibliothek, mit der Sie PDF-Dokumente programmgesteuert erstellen, bearbeiten und konvertieren können. Mit den von Aspose.PDF bereitgestellten Operatoren können Sie ein XForm-Formular auf einer vorhandenen PDF-Seite hinzufügen und positionieren.

## Voraussetzungen

Stellen Sie zunächst sicher, dass die folgenden Voraussetzungen erfüllt sind:

1. Visual Studio mit .NET Framework installiert.
2. Die Aspose.PDF-Bibliothek für .NET.

## Schritt 1: Projekt-Setup

Erstellen Sie zunächst ein neues Projekt in Visual Studio und fügen Sie einen Verweis auf die Aspose.PDF-Bibliothek für .NET hinzu. Sie können die Bibliothek von der offiziellen Aspose-Website herunterladen und auf Ihrem Computer installieren.

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
// Der folgende Code verwendet die Operatoren GSave/GRestore
// Der Code verwendet den ContatenateMatrix-Operator, um das XForm zu positionieren
// Der Code verwendet den Do-Operator, um das XForm auf der Seite zu zeichnen
// GSave/GRestore-Operatoren umschließen vorhandenen Inhalt
//Dies geschieht, um den anfänglichen Grafikzustand am Ende des vorhandenen Inhalts zu erhalten
// Andernfalls könnten am Ende der Kette der vorhandenen Operatoren unerwünschte Transformationen übrig bleiben
pageContents. Insert(1, new GSave());
pageContents. Add(new GRestore());
// Fügen Sie den GSave-Operator hinzu, um den Grafikstatus nach neuen Befehlen ordnungsgemäß zurückzusetzen
pageContents. Add(new GSave());

// Erstellen des XForms
XForm form = XForm.CreateNewForm(doc.Pages[1], doc);
doc.Pages[1].Resources.Forms.Add(form);
form.Contents.Add(new GSave());
// Legen Sie die Breite und Höhe des Bildes fest
form.Contents.Add(new ConcatenateMatrix(200, 0, 0, 200, 0, 0));
// Laden Sie das Bild in einen Stream
Stream imageStream = new FileStream(imageFile, FileMode.Open);
// Fügen Sie das Bild zur XForm-Ressourcenbildsammlung hinzu
form.Resources.Images.Add(imageStream);
XImage ximage = form.Resources.Images[form.Resources.Images.Count];
// Verwendung des Do-Operators: Dieser Operator zeichnet das Bild
form.Contents.Add(new Do(ximage.Name));
form.Contents.Add(new GRestore());

pageContents. Add(new GSave());
// Positionieren Sie das XForm bei den Koordinaten x=100 und y=500
pageContents. Add(new ConcatenateMatrix(1, 0, 0, 1, 100, 500));
// Zeichnen Sie das XForm mit dem Do-Operator
pageContents.Add(new Do(form.Name));
pageContents. Add(new GRestore());

pageContents. Add(new GSave());
// Positionieren Sie das XForm bei den Koordinaten x=100 und y=300
pageContents. Add(new ConcatenateMatrix(1, 0, 0, 1, 100, 300));
// Zeichnen Sie das XForm mit dem Do-Operator
pageContents.Add(new Do(form.Name));
pageContents. Add(new GRestore());

// Stellen Sie den Grafikstatus mit GRestore nach GSave wieder her
pageContents. Add(new GRestore());
doc.Save(outFile);
}
```

Geben Sie unbedingt die tatsächlichen Dateipfade an und passen Sie die Seitenzahl und die XForm-Positionen nach Bedarf an.

### Beispielquellcode für Draw XForm On Page mit Aspose.PDF für .NET
 
```csharp

// Der Pfad zum Dokumentverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";
string imageFile = dataDir+ "aspose-logo.jpg";
string inFile = dataDir + "DrawXFormOnPage.pdf";
string outFile = dataDir + "blank-sample2_out.pdf";
using (Document doc = new Document(inFile))
{
	OperatorCollection pageContents = doc.Pages[1].Contents;
	// Das Beispiel zeigt
	// Verwendung der GSave/GRestore-Operatoren
	// Verwendung des ContatenateMatrix-Operators zum Positionieren von xForm
	//Verwenden Sie den Operator, um xForm auf der Seite zu zeichnen
	// Umschließen Sie vorhandene Inhalte mit dem Operatorpaar GSave/GRestore
	// Dies dient dazu, den anfänglichen Grafikzustand am Ende des vorhandenen Inhalts abzurufen.
	// Andernfalls könnten am Ende der Kette bestehender Operatoren unerwünschte Transformationen verbleiben.
	pageContents.Insert(1, new Aspose.Pdf.Operators.GSave());
	pageContents.Add(new Aspose.Pdf.Operators.GRestore());
	// Fügen Sie den Operator „Grafikstatus speichern“ hinzu, um den Grafikstatus nach neuen Befehlen ordnungsgemäß zu löschen
	pageContents.Add(new Aspose.Pdf.Operators.GSave());
	#region create xForm
	// xForm erstellen
	XForm form = XForm.CreateNewForm(doc.Pages[1], doc);
	doc.Pages[1].Resources.Forms.Add(form);
	form.Contents.Add(new Aspose.Pdf.Operators.GSave());
	// Bildbreite und -höhe definieren
	form.Contents.Add(new Aspose.Pdf.Operators.ConcatenateMatrix(200, 0, 0, 200, 0, 0));
	// Bild in Stream laden
	Stream imageStream = new FileStream(imageFile, FileMode.Open);
	// Bild zur Bildersammlung der XForm-Ressourcen hinzufügen
	form.Resources.Images.Add(imageStream);
	XImage ximage = form.Resources.Images[form.Resources.Images.Count];
	// Verwenden des Do-Operators: Dieser Operator zeichnet ein Bild
	form.Contents.Add(new Aspose.Pdf.Operators.Do(ximage.Name));
	form.Contents.Add(new Aspose.Pdf.Operators.GRestore());
	#endregion
	pageContents.Add(new Aspose.Pdf.Operators.GSave());
	// Platzieren Sie das Formular auf den Koordinaten x=100 y=500
	pageContents.Add(new Aspose.Pdf.Operators.ConcatenateMatrix(1, 0, 0, 1, 100, 500));
	// Zeichnen Sie ein Formular mit dem Do-Operator
	pageContents.Add(new Aspose.Pdf.Operators.Do(form.Name));
	pageContents.Add(new Aspose.Pdf.Operators.GRestore());
	pageContents.Add(new Aspose.Pdf.Operators.GSave());
	// Platzieren Sie das Formular auf den Koordinaten x=100 y=300
	pageContents.Add(new Aspose.Pdf.Operators.ConcatenateMatrix(1, 0, 0, 1, 100, 300));
	// Zeichnen Sie ein Formular mit dem Do-Operator
	pageContents.Add(new Aspose.Pdf.Operators.Do(form.Name));
	pageContents.Add(new Aspose.Pdf.Operators.GRestore());
	// Stellen Sie den Grafikzustand mit GRestore nach dem GSave wieder her
	pageContents.Add(new Aspose.Pdf.Operators.GRestore());
	doc.Save(outFile);                
}

```

## Abschluss

In diesem Tutorial haben Sie gelernt, wie Sie mit Aspose.PDF für .NET ein XForm-Formular auf einer PDF-Seite zeichnen. Wenn Sie die beschriebenen Schritte befolgen, können Sie ein XForm-Formular auf einer vorhandenen Seite hinzufügen und positionieren und so Ihren PDF-Dokumenten mehr Flexibilität verleihen.

### FAQs zum Zeichnen von XForms auf der Seite

#### F: Was ist ein XForm in Aspose.PDF?

A: Ein XForm ist ein wiederverwendbares grafisches Objekt in einem PDF-Dokument. Sie können damit komplexe Grafiken, Bilder oder Texte definieren und zeichnen, die mehrfach auf verschiedenen Seiten wiederverwendet werden können.

#### F: Wie importiere ich die erforderlichen Namespaces für Aspose.PDF?

 A: Verwenden Sie in Ihrer C#-Codedatei die`using` Direktive zum Importieren der erforderlichen Namespaces für den Zugriff auf die von Aspose.PDF bereitgestellten Klassen und Methoden:
```csharp
using System;
using System.IO;
using Aspose.Pdf;
using Aspose.Pdf.Operators;
```

#### F: Was ist der Zweck der Operatoren GSave und GRestore?

 A: Die`GSave` Und`GRestore` Operatoren in Aspose.PDF werden zum Speichern und Wiederherstellen des Grafikstatus verwendet. Sie tragen dazu bei, sicherzustellen, dass Transformationen und Einstellungen, die auf einen Abschnitt des Inhalts angewendet werden, nachfolgende Abschnitte nicht beeinflussen.

#### F: Wie definiere ich ein XForm mit Aspose.PDF?

 A: Um ein XForm zu erstellen, verwenden Sie das`XForm.CreateNewForm` -Methode und fügen Sie sie zur`Resources.Forms` Sammlung einer bestimmten Seite. Sie können dann Inhalt zur XForm hinzufügen`Contents` Eigentum.

#### F: Wie kann ich ein Bild in einem XForm zeichnen?

A: Laden Sie das Bild in einen Stream und fügen Sie es dem`Resources.Images` Sammlung des XForms. Verwenden Sie die`Do` Operator innerhalb des XForms`Contents` um das Bild zu zeichnen.

#### F: Wie positioniere ich ein XForm auf einer PDF-Seite?

 A: Um ein XForm auf einer Seite zu positionieren, verwenden Sie die`ConcatenateMatrix` Operator innerhalb der Seite`Contents`. Passen Sie die Matrixparameter an, um die Übersetzung (Position) und Skalierung des XForms festzulegen.

#### F: Kann ich mehrere XForms auf derselben Seite zeichnen?

 A: Ja, Sie können mehrere XForms auf derselben Seite zeichnen, indem Sie die`ConcatenateMatrix` Parameter, um jedes XForm an unterschiedlichen Koordinaten zu positionieren.

#### F: Kann ich den Inhalt eines XForms nach seiner Erstellung ändern?

 A: Ja, Sie können den Inhalt eines XForms nach der Erstellung ändern, indem Sie zusätzliche Operatoren hinzufügen.`Contents` Eigentum.

#### F: Was passiert, wenn ich die Operatoren GSave und GRestore weglasse?

A: Das Weglassen der Operatoren GSave und GRestore kann dazu führen, dass auf nachfolgende Inhalte unerwünschte Transformationen oder Einstellungen angewendet werden. Ihre Verwendung hilft dabei, einen sauberen Grafikzustand beizubehalten.

#### F: Kann ich XForms auf verschiedenen Seiten des PDF-Dokuments wiederverwenden?

 A: Ja, Sie können XForms auf mehreren Seiten wiederverwenden, indem Sie das gleiche XForm zum`Resources.Forms` Sammlung verschiedener Seiten.

#### F: Gibt es eine Begrenzung für die Anzahl der XForms, die ich erstellen kann?

A: Es gibt zwar keine strikte Begrenzung für die Anzahl der XForms, die Sie erstellen können, aber bedenken Sie, dass zu viele XForms die Leistung und den Speicherverbrauch beeinträchtigen können. Verwenden Sie sie mit Bedacht.

#### F: Kann ich ein XForm drehen oder andere Transformationen anwenden?

 A: Ja, Sie können die`ConcatenateMatrix` Operator zum Anwenden von Transformationen wie Drehung, Skalierung und Übersetzung auf ein XForm.
