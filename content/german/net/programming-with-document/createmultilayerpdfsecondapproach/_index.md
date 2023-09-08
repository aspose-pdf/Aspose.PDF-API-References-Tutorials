---
title: Zweiter Ansatz zum Erstellen mehrschichtiger PDF-Dateien
linktitle: Zweiter Ansatz zum Erstellen mehrschichtiger PDF-Dateien
second_title: Aspose.PDF für .NET API-Referenz
description: Erfahren Sie, wie Sie mit Aspose.PDF für .NET eine mehrschichtige PDF-Datei erstellen. Schritt-für-Schritt-Anleitung mit Quellcode zum Erstellen dynamischer PDFs mit Text und Bildern.
type: docs
weight: 80
url: /de/net/programming-with-document/createmultilayerpdfsecondapproach/
---
In diesem Tutorial erfahren Sie, wie Sie mit dem zweiten Ansatz in Aspose.PDF für .NET eine mehrschichtige PDF-Datei erstellen. Wir stellen Ihnen eine Schritt-für-Schritt-Anleitung mit detaillierten Erklärungen zur Verfügung und fügen den vollständigen Quellcode bei. Wenn Sie diesem Tutorial folgen, können Sie mithilfe der Aspose.PDF-Bibliothek in Ihren .NET-Anwendungen PDF-Dokumente mit mehreren Ebenen generieren.

Beginnen wir nun mit der Schritt-für-Schritt-Anleitung.

## Schritt 1: Richten Sie die Umgebung ein

Öffnen Sie zunächst Visual Studio und erstellen Sie ein neues C#-Projekt. Stellen Sie sicher, dass Sie in Ihrem Projekt auf die Aspose.PDF-Bibliothek verwiesen haben. Sobald Sie die Umgebung eingerichtet haben, können Sie mit dem nächsten Schritt fortfahren.

## Schritt 2: Variablen initialisieren

In diesem Schritt werden wir die notwendigen Variablen initialisieren. Wir müssen den Pfad zum Dokumentverzeichnis festlegen und Farbvariablen für die PDF-Ebenen definieren. Hier ist der Codeausschnitt:

```csharp
// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";

int alpha = 10;
int green = 0;
int red = 100;
int blue = 0;
Color alphaColor = Color.FromArgb(alpha, red, green, blue);
```

## Schritt 3: Erstellen Sie ein PDF-Dokument

Als Nächstes erstellen wir eine neue Instanz der Aspose.Pdf.Document-Klasse, die ein PDF-Dokument darstellt. Hier ist der Codeausschnitt:

```csharp
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
```

## Schritt 4: Fügen Sie dem Dokument eine Seite hinzu

In diesem Schritt fügen wir dem PDF-Dokument eine neue Seite hinzu. Hier ist der Codeausschnitt:

```csharp
Aspose.Pdf.Page page = doc.Pages.Add();
```

## Schritt 5: Text zur Seite hinzufügen

Jetzt fügen wir der Seite ein Textfragment hinzu. Der Text wird als Absatz-3-Segment mit roter Farbe angezeigt. Hier ist der Codeausschnitt:

```csharp
Aspose.Pdf.Text.TextFragment t1 = new Aspose.Pdf.Text.TextFragment("paragraph 3 segment");
t1.TextState.ForegroundColor = Color.Red;
t1.IsInLineParagraph = true;
t1.TextState.FontSize = 12;

Aspose.Pdf.FloatingBox TextFloatingBox1 = new Aspose.Pdf.FloatingBox(117, 21);
TextFloatingBox1.ZIndex = 1;
TextFloatingBox1.Left = -4;
TextFloatingBox1.Top = -4;
page.Paragraphs.Add(TextFloatingBox1);
TextFloatingBox1.Paragraphs.Add(t1);
```

## Schritt 6: Fügen Sie der Seite ein Bild hinzu

In diesem Schritt fügen wir der Seite ein Bild hinzu. Das Bild wird als schwebendes Feld mit einer bestimmten Größe positioniert. Hier ist der Codeausschnitt:

```csharp
Aspose.Pdf.Image image1 = new Aspose.Pdf.Image();
image1.File = dataDir + "test_image.png";

Aspose.Pdf.FloatingBox ImageFloatingBox = new Aspose.Pdf.FloatingBox(117, 21);
page.Paragraphs.Add(ImageFloatingBox);
ImageFloatingBox.Left = -4;
ImageFloatingBox.Top = -4;
ImageFloatingBox.ZIndex = 2;
ImageFloatingBox.Paragraphs.Add(image1);
```

## Schritt 7: Speichern Sie das PDF

In diesem Schritt speichern wir das PDF in einer Datei.

```
doc.Save(dataDir + @"Multilayer-2ndApproach_out.pdf");
```

### Beispielquellcode für die Erstellung eines mehrschichtigen PDF-Zweitansatzes mit Aspose.PDF für .NET.

```csharp   
// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";

int alpha = 10;
int green = 0;
int red = 100;
int blue = 0;
Color alphaColor = Color.FromArgb(alpha, red, green, blue);
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();

Aspose.Pdf.Page page = doc.Pages.Add();
Aspose.Pdf.Text.TextFragment t1 = new Aspose.Pdf.Text.TextFragment("paragraph 3 segment");
t1.TextState.ForegroundColor = Color.Red;
t1.IsInLineParagraph = true;
t1.TextState.FontSize = 12;
Aspose.Pdf.FloatingBox TextFloatingBox1 = new Aspose.Pdf.FloatingBox(117, 21);
TextFloatingBox1.ZIndex = 1;
TextFloatingBox1.Left = -4;
TextFloatingBox1.Top = -4;
page.Paragraphs.Add(TextFloatingBox1);
TextFloatingBox1.Paragraphs.Add(t1);
Aspose.Pdf.Image image1 = new Aspose.Pdf.Image();
image1.File = dataDir + "test_image.png";
Aspose.Pdf.FloatingBox ImageFloatingBox = new Aspose.Pdf.FloatingBox(117, 21);
page.Paragraphs.Add(ImageFloatingBox);

ImageFloatingBox.Left = -4;
ImageFloatingBox.Top = -4;
ImageFloatingBox.ZIndex = 2;
ImageFloatingBox.Paragraphs.Add(image1);

doc.Save(dataDir + @"Multilayer-2ndApproach_out.pdf");
```

## Abschluss

In diesem Artikel haben wir gelernt, wie man mit dem zweiten Ansatz von Aspose.PDF für .NET ein mehrschichtiges PDF erstellt. Wir haben Ihnen Schritt-für-Schritt-Anleitungen und den vollständigen Quellcode zur Verfügung gestellt, der zum Erstellen eines mehrschichtigen PDFs erforderlich ist.

### FAQs

#### F: Was ist der zweite Ansatz zum Erstellen einer mehrschichtigen PDF-Datei mit Aspose.PDF für .NET?

A: Der zweite Ansatz zum Erstellen einer mehrschichtigen PDF-Datei mit Aspose.PDF für .NET besteht darin, schwebende Boxen zu verwenden, um Inhaltselemente wie Text und Bilder auf verschiedenen Ebenen innerhalb des PDF-Dokuments zu positionieren und hinzuzufügen.

#### F: Kann ich mit dem zweiten Ansatz mehr als zwei Ebenen zum PDF-Dokument hinzufügen?

A: Ja, Sie können dem PDF-Dokument mit dem zweiten Ansatz mehrere Ebenen hinzufügen, indem Sie weitere schwebende Kästchen hinzufügen und diese entsprechend positionieren. Jede schwebende Box stellt eine separate Ebene dar, und Sie können jeder Box Inhaltselemente hinzufügen, um mehrere Ebenen zu erstellen.

#### F: Welche Vorteile bietet der zweite Ansatz zum Erstellen mehrschichtiger PDFs?

A: Der zweite Ansatz ermöglicht eine präzise Kontrolle über die Positionierung und Sichtbarkeit von Inhaltselementen im PDF-Dokument. Es bietet eine größere Flexibilität bei der Verwaltung von Ebenen und der Inhaltsanordnung und erleichtert so die Erstellung komplexer und interaktiver Dokumente.

#### F: Ist Aspose.PDF für .NET zum Erstellen komplexer und interaktiver PDF-Dokumente geeignet?

A: Ja, Aspose.PDF für .NET ist eine leistungsstarke Bibliothek, die umfangreiche Funktionen zum Erstellen komplexer und interaktiver PDF-Dokumente bietet. Es bietet eine breite Palette an Funktionen, wie das Hinzufügen von Text, Bildern, Tabellen, Hyperlinks und Formularfeldern sowie die Unterstützung erweiterter PDF-Vorgänge.

#### F: Kann ich das Erscheinungsbild und die Eigenschaften der schwebenden Boxen im zweiten Ansatz anpassen?

A: Ja, Sie können das Erscheinungsbild und die Eigenschaften der schwebenden Boxen anpassen, z. B. deren Größe, Position, Hintergrundfarbe und Deckkraft. Aspose.PDF für .NET bietet verschiedene Optionen zum Gestalten und Positionieren schwebender Boxen.