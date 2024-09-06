---
title: Strichtext in PDF-Datei füllen
linktitle: Strichtext in PDF-Datei füllen
second_title: Aspose.PDF für .NET API-Referenz
description: Erfahren Sie, wie Sie mit Aspose.PDF für .NET einfach Text in PDF-Dateien ausfüllen und skizzieren.
type: docs
weight: 90
url: /de/net/programming-with-stamps-and-watermarks/fill-stroke-text/
---
In diesem Tutorial zeigen wir Ihnen Schritt für Schritt, wie Sie mit Aspose.PDF für .NET Text in einer PDF-Datei ausfüllen und umranden. Wir zeigen Ihnen, wie Sie mit dem bereitgestellten C#-Quellcode Füll- und Umrandungsfarben auf Text in der PDF-Datei anwenden.

## Schritt 1: Einrichten der Umgebung

Bevor Sie beginnen, stellen Sie sicher, dass Sie über Folgendes verfügen:

- Eine installierte .NET-Entwicklungsumgebung.
- Die Aspose.PDF-Bibliothek für .NET wurde heruntergeladen und in Ihrem Projekt referenziert.

## Schritt 2: Erstellen des TextState-Objekts

Der erste Schritt besteht darin, ein TextState-Objekt zu erstellen, um die erweiterten Eigenschaften zu übergeben. So geht's:

```csharp
// Erstellen Sie ein TextState-Objekt, um erweiterte Eigenschaften zu übertragen
TextState ts = new TextState();

// Umrissfarbe festlegen
ts.StrokingColor = Color.Gray;

// Definieren des Textwiedergabemodus
ts.RenderingMode = TextRenderingMode.StrokeText;
```

Der obige Code erstellt ein neues TextState-Objekt und legt die Umrissfarbe sowie die Art und Weise der Textdarstellung fest.

## Schritt 3: Laden des PDF-Dokuments

Nachdem das TextState-Objekt nun bereit ist, können wir das PDF-Dokument laden, in dem wir die Textfüllung und den Umriss anwenden möchten. So geht's:

```csharp
// Laden Sie das PDF-Dokument als Eingabe
Facades.PdfFileStamp fileStamp = new Facades.PdfFileStamp(new Aspose.Pdf.Document(dataDir + "input.pdf"));
```

Der obige Code lädt das vorhandene PDF-Dokument mithilfe der Klasse PdfFileStamp aus der Bibliothek Aspose.PDF.Facades.

## Schritt 4: Dem Text Füllung und Kontur hinzufügen

Nachdem das PDF-Dokument geladen ist, können wir dem Text Füllung und Umriss hinzufügen. So geht's:

```csharp
// Erstellen Sie einen Stempel (Stempel) mit dem definierten Text und den Eigenschaften
Aspose.Pdf.Facades.Stamp stamp = new Aspose.Pdf.Facades.Stamp();
stamp.BindLogo(new Facades.FormattedText("PAID IN FULL", System.Drawing.Color.Gray, "Arial", Facades.EncodingType.Winansi, true, 78));

// Binden des TextState-Objekts
stamp.BindTextState(ts);

// Ursprung X, Y festlegen
stamp.SetOrigin(100, 100);
stamp. Opacity = 5;
stamp.BlendingSpace = Facades.BlendingColorSpace.DeviceRGB;
stamp.Rotation = 45.0F;
stamp. IsBackground = false;

// Fügen Sie dem Dokument den Stempel hinzu
fileStamp.AddStamp(stamp);
```

Der obige Code erstellt einen Stempel mit dem angegebenen Text und den definierten Füll- und Stricheigenschaften.

## Schritt 5: Speichern des Ausgabedokuments

Sobald der Textstempel hinzugefügt wurde, können wir das geänderte PDF-Dokument speichern. So geht's:

```csharp
// Speichern des geänderten Dokuments
fileStamp.Save(dataDir + "output_out.pdf");
fileStamp.Close();
```

Der obige Code speichert das bearbeitete PDF-Dokument im angegebenen Verzeichnis.

### Beispielquellcode für Fill Stroke Text mit Aspose.PDF für .NET 
```csharp

// Der Pfad zum Dokumentverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Erstellen Sie ein TextState-Objekt, um erweiterte Eigenschaften zu übertragen
TextState ts = new TextState();

// Farbe für Strich festlegen
ts.StrokingColor = Color.Gray;

// Textwiedergabemodus festlegen
ts.RenderingMode = TextRenderingMode.StrokeText;

// Laden eines PDF-Eingabedokuments
Facades.PdfFileStamp fileStamp = new Facades.PdfFileStamp(new Aspose.Pdf.Document(dataDir + "input.pdf"));
Aspose.Pdf.Facades.Stamp stamp = new Aspose.Pdf.Facades.Stamp();
stamp.BindLogo(new Facades.FormattedText("PAID IN FULL", System.Drawing.Color.Gray, "Arial", Facades.EncodingType.Winansi, true, 78));

// TextState binden
stamp.BindTextState(ts);

// X,Y-Ursprung festlegen
stamp.SetOrigin(100, 100);
stamp.Opacity = 5;
stamp.BlendingSpace = Facades.BlendingColorSpace.DeviceRGB;
stamp.Rotation = 45.0F;
stamp.IsBackground = false;

// Stempel hinzufügen
fileStamp.AddStamp(stamp);
fileStamp.Save(dataDir + "ouput_out.pdf");
fileStamp.Close();

```

## Abschluss

Herzlichen Glückwunsch! Sie haben gelernt, wie Sie mit Aspose.PDF für .NET Text in einem PDF-Dokument ausfüllen und umreißen. Jetzt können Sie dieses Wissen anwenden, um Füll- und Umrissfarben in Ihren PDF-Dokumenten anzupassen.

### FAQs zum Füllen von Strichtext in PDF-Dateien

#### F: Was bedeutet es, Text in einem PDF-Dokument auszufüllen und zu skizzieren, und wann muss ich dies möglicherweise tun?

A: Beim Füllen und Konturieren von Text in einem PDF-Dokument werden Farben auf das Innere der Textzeichen (Füllen) und auf die Ränder um den Text (Kontur) angewendet. Dies kann verwendet werden, um das visuelle Erscheinungsbild des Textes zu verbessern, Hervorhebungen vorzunehmen oder bestimmte Inhalte im PDF hervorzuheben.

#### F: Wie ermöglicht der bereitgestellte C#-Quellcode das Ausfüllen und Umreißen von Text in einer PDF-Datei?

 A: Der bereitgestellte Quellcode zeigt, wie man ein`TextState` Objekt, um erweiterte Texteigenschaften wie Umrissfarbe und Rendering-Modus zu definieren. Anschließend wird Aspose.PDF.Facades verwendet, um ein vorhandenes PDF-Dokument zu laden, einen Stempel mit dem Text mit angegebenen Füll- und Stricheigenschaften zu erstellen und den Stempel dem Dokument hinzuzufügen.

####  F: Was ist der Zweck der`TextState` object in the code?

 A: Die`TextState`Das Objekt wird verwendet, um erweiterte Texteigenschaften zu definieren, einschließlich der Farbe der Textkontur (Strich) und des Rendering-Modus. Sie können damit anpassen, wie der Text in Bezug auf Strich und Füllung angezeigt wird.

#### F: Kann ich auf verschiedene Teile desselben Textes unterschiedliche Füll- und Umrissfarben anwenden?

 A: Ja, Sie können den Code ändern, um verschiedene`TextState` Objekte mit unterschiedlichen Füll- und Umrissfarben und wenden Sie diese auf bestimmte Teile des Textes an, indem Sie separate`Stamp` Objekte.

#### F: Kann ich Füll- und Umrissfarben auf Text anwenden, der bereits im PDF-Dokument vorhanden ist?

 A: Ja, Sie können ähnliche Prinzipien verwenden, um Füll- und Umrissfarben auf vorhandenen Text im PDF-Dokument anzuwenden, indem Sie die entsprechenden Textobjekte auswählen und sie als Stempel mit den gewünschten`TextState` Eigenschaften.

#### F: Wie kann ich die Deckkraft und Mischung des ausgefüllten und umrissenen Textes anpassen?

 A: Mit dem bereitgestellten Code können Sie die Deckkraft und die Mischeigenschaften des Stempels mithilfe der`Opacity` Und`BlendingSpace`Eigenschaften. Sie können diese Werte anpassen, um den gewünschten visuellen Effekt zu erzielen.

#### F: Wie kann ich mehreren Stempeln im selben PDF-Dokument unterschiedliche Füll- und Umrissfarben zuweisen?

 A: Sie können mehrere`TextState` Objekte mit unterschiedlichen Füll- und Umrissfarben und erstellen Sie dann separate`Stamp` Objekte für jeden Textsatz mit unterschiedlichen Farben. Fügen Sie diese Stempel zum selben PDF-Dokument hinzu, indem Sie`PdfFileStamp` Klasse.

#### F: Kann ich für den umrandeten und ausgefüllten Text andere Schriftarten als Arial verwenden?

 A: Ja, Sie können die Schriftart ändern, indem Sie den Parameter für den Schriftartnamen im`FormattedText` Konstruktor beim Erstellen des Stempels. Sie können jede auf Ihrem System verfügbare Schriftart verwenden.

#### F: Wie kann ich den Drehwinkel des umrandeten und ausgefüllten Textes ändern?

 A: Mit dem bereitgestellten Code können Sie den Drehwinkel des Stempels mithilfe der`Rotation` Eigenschaft. Sie können diese Eigenschaft anpassen, um den gewünschten Drehwinkel für den Text anzugeben.

#### F: Wie kann ich die Position und Größe des umrandeten und ausgefüllten Textes auf der Seite steuern?

 A: Sie können die`SetOrigin` Methode der`Stamp` Objekt, um die X- und Y-Koordinaten der Position des Stempels auf der Seite festzulegen. Darüber hinaus können Sie die Schriftgröße im`FormattedText` Konstruktor zur Steuerung der Textgröße.