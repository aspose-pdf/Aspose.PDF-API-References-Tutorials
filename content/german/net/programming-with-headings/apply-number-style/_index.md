---
title: Zahlenstil in PDF-Datei anwenden
linktitle: Zahlenstil in PDF-Datei anwenden
second_title: Aspose.PDF für .NET API-Referenz
description: Erfahren Sie, wie Sie mit Aspose.PDF für .NET einen Nummerierungsstil auf Überschriften in PDF-Dateien anwenden. Schritt-für-Schritt-Anleitung.
type: docs
weight: 10
url: /de/net/programming-with-headings/apply-number-style/
---
In diesem Tutorial führen wir Sie Schritt für Schritt durch den folgenden C#-Quellcode, um mit Aspose.PDF für .NET einen Nummerierungsstil in einer PDF-Datei anzuwenden.

Stellen Sie sicher, dass Sie die Aspose.PDF-Bibliothek installiert und Ihre Entwicklungsumgebung eingerichtet haben, bevor Sie beginnen. Sie benötigen außerdem Grundkenntnisse in der C#-Programmierung.

### Schritt 1: Einrichten des Dokumentverzeichnisses

Im bereitgestellten Quellcode müssen Sie das Verzeichnis angeben, in dem Sie die generierte PDF-Datei speichern möchten. Ändern Sie die Variable „dataDir“ in das gewünschte Verzeichnis.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

### Schritt 2: Erstellen des PDF-Dokuments

Wir erstellen ein neues PDF-Dokument mit angegebenen Abmessungen und Rändern.

```csharp
Document pdfDoc = new Document();
pdfDoc.PageInfo.Width = 612.0;
pdfDoc.PageInfo.Height = 792.0;
pdfDoc.PageInfo.Margin = new Aspose.Pdf.MarginInfo();
pdfDoc.PageInfo.Margin.Left = 72;
pdfDoc.PageInfo.Margin.Right = 72;
pdfDoc.PageInfo.Margin.Top = 72;
pdfDoc.PageInfo.Margin.Bottom = 72;
```

### Schritt 3: Erstellen einer Seite und eines schwebenden Containers

Wir fügen dem Dokument eine Seite hinzu und erstellen einen schwebenden Container, um den Inhalt zu organisieren.

```csharp
Aspose.Pdf.Page pdfPage = pdfDoc.Pages.Add();
pdfPage.PageInfo.Width = 612.0;
pdfPage.PageInfo.Height = 792.0;
pdfPage.PageInfo.Margin = new Aspose.Pdf.MarginInfo();
pdfPage.PageInfo.Margin.Left = 72;
pdfPage.PageInfo.Margin.Right = 72;
pdfPage.PageInfo.Margin.Top = 72;
pdfPage.PageInfo.Margin.Bottom = 72;
Aspose.Pdf.FloatingBox floatBox = new Aspose.Pdf.FloatingBox();
floatBox.Margin = pdfPage.PageInfo.Margin;
pdfPage.Paragraphs.Add(floatBox);
```

### Schritt 4: Überschriften mit Nummerierung hinzufügen

Wir erstellen Überschriften mit vorgegebener Nummerierung und fügen diese dem Floating-Container hinzu.

```csharp
Aspose.Pdf.Heading heading = new Aspose.Pdf.Heading(1);
heading. IsInList = true;
heading. StartNumber = 1;
heading.Text = "List 1";
heading.Style = NumberingStyle.NumeralsRomanLowercase;
heading. IsAutoSequence = true;
floatBox.Paragraphs.Add(heading);

Aspose.Pdf.Heading heading2 = new Aspose.Pdf.Heading(1);
heading2.IsInList = true;
heading2.StartNumber = 13;
heading2.Text = "Listing 2";
heading2.Style = NumberingStyle.NumeralsRomanLowercase;
heading2.IsAutoSequence = true;
floatBox.Paragraphs.Add(heading2);

Aspose.Pdf.Heading heading3 = new Aspose.Pdf.Heading(2);
heading3.IsInList = true;
heading3.StartNumber = 1;
heading3.Text = "The value, at the effective date of the plan, of the assets to be distributed under the plan

";
heading3.Style = NumberingStyle.LettersLowercase;
heading3.IsAutoSequence = true;
floatBox.Paragraphs.Add(heading3);
```

### Schritt 5: Speichern des PDF-Dokuments

Das erzeugte PDF-Dokument speichern wir im angegebenen Verzeichnis.

```csharp
dataDir = dataDir + "ApplyNumberStyle_out.pdf";
pdfDoc.Save(dataDir);
Console.WriteLine("\nNumbering style successfully applied to headers.\nFile saved as: " + dataDir);
```

### Beispielquellcode für „Apply Number Style“ mit Aspose.PDF für .NET 
```csharp

// Der Pfad zum Dokumentverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document pdfDoc = new Document();
pdfDoc.PageInfo.Width = 612.0;
pdfDoc.PageInfo.Height = 792.0;
pdfDoc.PageInfo.Margin = new Aspose.Pdf.MarginInfo();
pdfDoc.PageInfo.Margin.Left = 72;
pdfDoc.PageInfo.Margin.Right = 72;
pdfDoc.PageInfo.Margin.Top = 72;
pdfDoc.PageInfo.Margin.Bottom = 72;
Aspose.Pdf.Page pdfPage = pdfDoc.Pages.Add();
pdfPage.PageInfo.Width = 612.0;
pdfPage.PageInfo.Height = 792.0;
pdfPage.PageInfo.Margin = new Aspose.Pdf.MarginInfo();
pdfPage.PageInfo.Margin.Left = 72;
pdfPage.PageInfo.Margin.Right = 72;
pdfPage.PageInfo.Margin.Top = 72;
pdfPage.PageInfo.Margin.Bottom = 72;
Aspose.Pdf.FloatingBox floatBox = new Aspose.Pdf.FloatingBox();
floatBox.Margin = pdfPage.PageInfo.Margin;
pdfPage.Paragraphs.Add(floatBox);
TextFragment textFragment = new TextFragment();
TextSegment segment = new TextSegment();
Aspose.Pdf.Heading heading = new Aspose.Pdf.Heading(1);
heading.IsInList = true;
heading.StartNumber = 1;
heading.Text = "List 1";
heading.Style = NumberingStyle.NumeralsRomanLowercase;
heading.IsAutoSequence = true;
floatBox.Paragraphs.Add(heading);
Aspose.Pdf.Heading heading2 = new Aspose.Pdf.Heading(1);
heading2.IsInList = true;
heading2.StartNumber = 13;
heading2.Text = "List 2";
heading2.Style = NumberingStyle.NumeralsRomanLowercase;
heading2.IsAutoSequence = true;
floatBox.Paragraphs.Add(heading2);
Aspose.Pdf.Heading heading3 = new Aspose.Pdf.Heading(2);
heading3.IsInList = true;
heading3.StartNumber = 1;
heading3.Text = "the value, as of the effective date of the plan, of property to be distributed under the plan onaccount of each allowed";
heading3.Style = NumberingStyle.LettersLowercase;
heading3.IsAutoSequence = true;
floatBox.Paragraphs.Add(heading3);
dataDir = dataDir + "ApplyNumberStyle_out.pdf";
pdfDoc.Save(dataDir);
Console.WriteLine("\nNumber style applied successfully in headings.\nFile saved at " + dataDir);  
          
```

## Abschluss

In diesem Tutorial haben wir erklärt, wie Sie mit Aspose.PDF für .NET einen Nummerierungsstil auf Überschriften in einem PDF-Dokument anwenden. Dieses Wissen können Sie nun nutzen, um PDF-Dokumente mit benutzerdefinierten Nummerierungen für Überschriften zu erstellen.

### FAQs zum Anwenden von Nummerierungsstilen in PDF-Dateien

#### F: Was ist der Nummerierungsstil in einem PDF-Dokument?

A: Der Nummerierungsstil bezieht sich auf das Format, in dem Überschriften oder Abschnitte in einem PDF-Dokument nummeriert werden. Er kann Ziffern, Buchstaben oder andere Zeichen enthalten, um eine hierarchische Struktur bereitzustellen.

#### F: Warum muss ich auf Überschriften in einem PDF-Dokument einen Nummerierungsstil anwenden?

A: Durch die Anwendung eines Nummerierungsstils auf Überschriften wird die Lesbarkeit und Organisation Ihres PDF-Dokuments verbessert. Es hilft den Lesern, einfach zu navigieren und die hierarchische Struktur des Inhalts zu verstehen.

#### F: Was ist Aspose.PDF für .NET?

A: Aspose.PDF für .NET ist eine Bibliothek, die es Entwicklern ermöglicht, programmgesteuert in .NET-Anwendungen mit PDF-Dateien zu arbeiten. Sie bietet eine breite Palette an Funktionen zum Erstellen, Bearbeiten, Konvertieren und Manipulieren von PDF-Dokumenten.

#### F: Wie importiere ich die erforderlichen Bibliotheken für mein C#-Projekt?

A: Um die erforderlichen Bibliotheken für Ihr C#-Projekt zu importieren, schließen Sie die folgenden Importanweisungen ein:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.InteractiveFeatures;
```

Diese Anweisungen ermöglichen Ihnen den Zugriff auf die Klassen und Methoden, die zum Arbeiten mit PDF-Dokumenten und Anwenden von Nummerierungsstilen erforderlich sind.

#### F: Wie gebe ich das Verzeichnis zum Speichern der generierten PDF-Datei an?

A: Ändern Sie im bereitgestellten Quellcode die Variable „dataDir“, um das Verzeichnis anzugeben, in dem Sie die generierte PDF-Datei speichern möchten.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

 Ersetzen`"YOUR DOCUMENTS DIRECTORY"` durch den tatsächlichen Verzeichnispfad.

#### F: Wie erstelle ich ein PDF-Dokument mit festgelegten Abmessungen und Rändern?

A: Um ein PDF-Dokument mit angegebenen Abmessungen und Rändern zu erstellen, verwenden Sie den folgenden Code:

```csharp
Document pdfDoc = new Document();
pdfDoc.PageInfo.Width = 612.0;
pdfDoc.PageInfo.Height = 792.0;
pdfDoc.PageInfo.Margin = new Aspose.Pdf.MarginInfo();
pdfDoc.PageInfo.Margin.Left = 72;
pdfDoc.PageInfo.Margin.Right = 72;
pdfDoc.PageInfo.Margin.Top = 72;
pdfDoc.PageInfo.Margin.Bottom = 72;
```

#### F: Wie füge ich dem PDF-Dokument Überschriften im Nummerierungsstil hinzu?

A: Um dem PDF-Dokument Überschriften mit Nummerierungsstil hinzuzufügen, verwenden Sie die bereitgestellten Codebeispiele, um Überschriften zu erstellen und ihre Nummerierungsstile anzupassen. Passen Sie Eigenschaften wie Text, Nummerierungsstil, Startnummer und automatische Sequenz nach Bedarf an.

#### F: Wie speichere ich das generierte PDF-Dokument?

 A: Um das generierte PDF-Dokument zu speichern, verwenden Sie die`Save` Methode der`pdfDoc` Objekt:

```csharp
dataDir = dataDir + "ApplyNumberStyle_out.pdf";
pdfDoc.Save(dataDir);
Console.WriteLine("\nNumbering style applied to headers.\nFile saved as: " + dataDir);
```

#### F: Wie kann ich bestätigen, dass der Nummerierungsstil angewendet wurde?

A: Öffnen Sie die generierte PDF-Datei, um zu überprüfen, ob der angegebene Nummerierungsstil auf die Überschriften angewendet wurde.

#### F: Kann ich den Nummerierungsstil weiter anpassen?

 A: Ja, Sie können den Nummerierungsstil weiter anpassen, indem Sie die Eigenschaften des`Heading` Objekte, wie etwa Nummerierungsstiltyp, Startnummer und automatische Sequenz.

#### F: Kann ich auf verschiedene Abschnitte des Dokuments unterschiedliche Nummerierungsstile anwenden?

 A: Ja, Sie können verschiedene Nummerierungsstile auf verschiedene Abschnitte des Dokuments anwenden, indem Sie mehrere`Heading` Objekte mit unterschiedlichen Stilen und Sequenzen.