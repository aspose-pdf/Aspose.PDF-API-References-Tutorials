---
title: Zahlenstil in PDF-Datei anwenden
linktitle: Zahlenstil in PDF-Datei anwenden
second_title: Aspose.PDF für .NET API-Referenz
description: Erfahren Sie, wie Sie mit Aspose.PDF für .NET einen Nummerierungsstil auf Überschriften in einer PDF-Datei anwenden. Schritt für Schritt Anleitung.
type: docs
weight: 10
url: /de/net/programming-with-headings/apply-number-style/
---
In diesem Tutorial führen wir Sie Schritt für Schritt durch den folgenden C#-Quellcode, um mit Aspose.PDF für .NET den Nummerierungsstil in einer PDF-Datei anzuwenden.

Stellen Sie sicher, dass Sie die Aspose.PDF-Bibliothek installiert und Ihre Entwicklungsumgebung eingerichtet haben, bevor Sie beginnen. Außerdem verfügen Sie über Grundkenntnisse der C#-Programmierung.

### Schritt 1: Einrichten des Dokumentenverzeichnisses

Im bereitgestellten Quellcode müssen Sie das Verzeichnis angeben, in dem Sie die generierte PDF-Datei speichern möchten. Ändern Sie die Variable „dataDir“ in das gewünschte Verzeichnis.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

### Schritt 2: Erstellen des PDF-Dokuments

Wir erstellen ein neues PDF-Dokument mit den angegebenen Abmessungen und Rändern.

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

Wir erstellen Header mit vorgegebener Nummerierung und fügen sie dem Floating-Container hinzu.

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

Wir speichern das generierte PDF-Dokument im angegebenen Verzeichnis.

```csharp
dataDir = dataDir + "ApplyNumberStyle_out.pdf";
pdfDoc.Save(dataDir);
Console.WriteLine("\nNumbering style successfully applied to headers.\nFile saved as: " + dataDir);
```

### Beispielquellcode für „Anwenden des Zahlenstils“ mit Aspose.PDF für .NET 
```csharp

// Der Pfad zum Dokumentenverzeichnis.
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

### FAQs zum Anwenden des Zahlenstils in einer PDF-Datei

#### F: Was ist der Nummerierungsstil in einem PDF-Dokument?

A: Der Nummerierungsstil bezieht sich auf das Format, in dem Überschriften oder Abschnitte in einem PDF-Dokument nummeriert werden. Es kann Ziffern, Buchstaben oder andere Zeichen enthalten, um eine hierarchische Struktur bereitzustellen.

#### F: Warum sollte ich den Nummerierungsstil auf Überschriften in einem PDF-Dokument anwenden?

A: Das Anwenden eines Nummerierungsstils auf Überschriften verbessert die Lesbarkeit und Organisation Ihres PDF-Dokuments. Es hilft den Lesern, sich leicht zurechtzufinden und die hierarchische Struktur des Inhalts zu verstehen.

#### F: Was ist Aspose.PDF für .NET?

A: Aspose.PDF für .NET ist eine Bibliothek, die es Entwicklern ermöglicht, programmgesteuert mit PDF-Dateien in .NET-Anwendungen zu arbeiten. Es bietet eine breite Palette von Funktionen zum Erstellen, Bearbeiten, Konvertieren und Bearbeiten von PDF-Dokumenten.

#### F: Wie importiere ich die erforderlichen Bibliotheken für mein C#-Projekt?

A: Um die erforderlichen Bibliotheken für Ihr C#-Projekt zu importieren, schließen Sie die folgenden Importanweisungen ein:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.InteractiveFeatures;
```

Mit diesen Anweisungen können Sie auf die Klassen und Methoden zugreifen, die zum Arbeiten mit PDF-Dokumenten und zum Anwenden von Nummerierungsstilen erforderlich sind.

#### F: Wie lege ich das Verzeichnis zum Speichern der generierten PDF-Datei fest?

A: Ändern Sie im bereitgestellten Quellcode die Variable „dataDir“, um das Verzeichnis anzugeben, in dem Sie die generierte PDF-Datei speichern möchten.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

 Ersetzen`"YOUR DOCUMENTS DIRECTORY"` mit dem tatsächlichen Verzeichnispfad.

#### F: Wie erstelle ich ein PDF-Dokument mit bestimmten Abmessungen und Rändern?

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

#### F: Wie füge ich Überschriften mit Nummerierungsstil zum PDF-Dokument hinzu?

A: Um dem PDF-Dokument Überschriften mit Nummerierungsstil hinzuzufügen, verwenden Sie die bereitgestellten Codebeispiele, um Überschriften zu erstellen und deren Nummerierungsstile anzupassen. Passen Sie Eigenschaften wie Text, Nummerierungsstil, Startnummer und automatische Reihenfolge nach Bedarf an.

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

 A: Ja, Sie können den Nummerierungsstil weiter anpassen, indem Sie die Eigenschaften anpassen`Heading` Objekte wie Nummerierungsstiltyp, Startnummer und automatische Reihenfolge.

#### F: Kann ich unterschiedliche Nummerierungsstile auf verschiedene Abschnitte des Dokuments anwenden?

A: Ja, Sie können verschiedene Nummerierungsstile auf verschiedene Abschnitte des Dokuments anwenden, indem Sie mehrere erstellen`Heading` Objekte mit unterschiedlichen Stilen und Sequenzen.