---
title: Füllen Sie Strichtext in eine PDF-Datei
linktitle: Füllen Sie Strichtext in eine PDF-Datei
second_title: Aspose.PDF für .NET API-Referenz
description: Erfahren Sie, wie Sie mit Aspose.PDF für .NET ganz einfach Text in einer PDF-Datei füllen und umreißen.
type: docs
weight: 90
url: /de/net/programming-with-stamps-and-watermarks/fill-stroke-text/
---
In diesem Tutorial zeigen wir Ihnen Schritt für Schritt, wie Sie mit Aspose.PDF für .NET Text in einer PDF-Datei füllen und umreißen. Wir zeigen Ihnen, wie Sie den bereitgestellten C#-Quellcode verwenden, um Füll- und Umrissfarben auf Text in der PDF-Datei anzuwenden.

## Schritt 1: Einrichten der Umgebung

Bevor Sie beginnen, stellen Sie sicher, dass Sie über Folgendes verfügen:

- Eine installierte .NET-Entwicklungsumgebung.
- Die Aspose.PDF-Bibliothek für .NET wurde heruntergeladen und in Ihrem Projekt referenziert.

## Schritt 2: Erstellen des TextState-Objekts

Der erste Schritt besteht darin, ein TextState-Objekt zu erstellen, um die erweiterten Eigenschaften zu übergeben. Hier ist wie:

```csharp
// Erstellen Sie ein TextState-Objekt, um erweiterte Eigenschaften zu übertragen
TextState ts = new TextState();

// Umrissfarbe festlegen
ts.StrokingColor = Color.Gray;

// Definieren Sie den Textwiedergabemodus
ts.RenderingMode = TextRenderingMode.StrokeText;
```

Der obige Code erstellt ein neues TextState-Objekt und legt die Umrissfarbe sowie die Art und Weise fest, wie der Text gerendert wird.

## Schritt 3: Laden des PDF-Dokuments

Da das TextState-Objekt nun fertig ist, können wir das PDF-Dokument dort laden, wo wir die Textfüllung und -kontur anwenden möchten. Hier ist wie:

```csharp
// Laden Sie das PDF-Dokument als Eingabe
Facades.PdfFileStamp fileStamp = new Facades.PdfFileStamp(new Aspose.Pdf.Document(dataDir + "input.pdf"));
```

Der obige Code lädt das vorhandene PDF-Dokument mithilfe der PdfFileStamp-Klasse aus der Aspose.PDF.Facades-Bibliothek.

## Schritt 4: Fügen Sie dem Text Füllung und Kontur hinzu

Nachdem das PDF-Dokument geladen ist, können wir dem Text Füllung und Umriss hinzufügen. Hier ist wie:

```csharp
// Erstellen Sie einen Stempel (Stempel) mit dem definierten Text und den definierten Eigenschaften
Aspose.Pdf.Facades.Stamp stamp = new Aspose.Pdf.Facades.Stamp();
stamp.BindLogo(new Facades.FormattedText("PAID IN FULL", System.Drawing.Color.Gray, "Arial", Facades.EncodingType.Winansi, true, 78));

// Binden Sie das TextState-Objekt
stamp.BindTextState(ts);

// Legen Sie den Ursprung X, Y fest
stamp.SetOrigin(100, 100);
stamp. Opacity = 5;
stamp.BlendingSpace = Facades.BlendingColorSpace.DeviceRGB;
stamp.Rotation = 45.0F;
stamp. IsBackground = false;

// Fügen Sie dem Dokument den Stempel hinzu
fileStamp.AddStamp(stamp);
```

Der obige Code erstellt einen Stempel mit dem angegebenen Text und den definierten Füll- und Kontureigenschaften.

## Schritt 5: Speichern Sie das Ausgabedokument

Sobald der Textstempel hinzugefügt wurde, können wir das geänderte PDF-Dokument speichern. Hier ist wie:

```csharp
// Speichern Sie das geänderte Dokument
fileStamp.Save(dataDir + "output_out.pdf");
fileStamp.Close();
```

Der obige Code speichert das bearbeitete PDF-Dokument im angegebenen Verzeichnis.

### Beispielquellcode für Füllstrichtext mit Aspose.PDF für .NET 
```csharp

// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Erstellen Sie ein TextState-Objekt, um erweiterte Eigenschaften zu übertragen
TextState ts = new TextState();

// Legen Sie die Farbe für den Strich fest
ts.StrokingColor = Color.Gray;

// Legen Sie den Textwiedergabemodus fest
ts.RenderingMode = TextRenderingMode.StrokeText;

// Laden Sie ein Eingabe-PDF-Dokument
Facades.PdfFileStamp fileStamp = new Facades.PdfFileStamp(new Aspose.Pdf.Document(dataDir + "input.pdf"));
Aspose.Pdf.Facades.Stamp stamp = new Aspose.Pdf.Facades.Stamp();
stamp.BindLogo(new Facades.FormattedText("PAID IN FULL", System.Drawing.Color.Gray, "Arial", Facades.EncodingType.Winansi, true, 78));

// TextState binden
stamp.BindTextState(ts);

// Legen Sie den X- und Y-Ursprung fest
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

Herzlichen Glückwunsch! Sie haben gelernt, wie Sie mit Aspose.PDF für .NET Text in einem PDF-Dokument füllen und umreißen. Jetzt können Sie dieses Wissen anwenden, um Füll- und Umrissfarben in Ihren PDF-Dokumenten anzupassen.

### FAQs zum Füllstrichtext in PDF-Dateien

#### F: Was bedeutet es, Text in einem PDF-Dokument auszufüllen und zu umreißen, und wann muss ich das möglicherweise tun?

A: Das Füllen und Umreißen von Text in einem PDF-Dokument erfordert das Anwenden von Farben auf das Innere der Textzeichen (Füllung) und auf die Ränder um den Text (Umriss). Dies kann verwendet werden, um das visuelle Erscheinungsbild des Textes zu verbessern, Hervorhebungen zu schaffen oder bestimmte Inhalte innerhalb der PDF-Datei hervorzuheben.

#### F: Wie ermöglicht der bereitgestellte C#-Quellcode das Ausfüllen und Gliedern von Text in einer PDF-Datei?

 A: Der bereitgestellte Quellcode zeigt, wie ein erstellt wird`TextState` -Objekt, um erweiterte Texteigenschaften wie Umrissfarbe und Rendering-Modus zu definieren. Anschließend wird Aspose.PDF.Facades verwendet, um ein vorhandenes PDF-Dokument zu laden, einen Stempel zu erstellen, der den Text mit angegebenen Füll- und Stricheigenschaften enthält, und den Stempel dem Dokument hinzuzufügen.

####  F: Was ist der Zweck des`TextState` object in the code?

 A: Die`TextState`Das Objekt wird verwendet, um erweiterte Texteigenschaften zu definieren, einschließlich der Farbe der Textkontur (Strich) und des Rendering-Modus. Sie können damit anpassen, wie der Text in Bezug auf Strich und Füllung angezeigt wird.

#### F: Kann ich auf verschiedene Teile desselben Textes unterschiedliche Füll- und Umrissfarben anwenden?

 A: Ja, Sie können den Code ändern, um einen anderen zu erstellen`TextState` Erstellen Sie Objekte mit unterschiedlichen Füll- und Umrissfarben und wenden Sie diese mit separaten Farben auf bestimmte Teile des Textes an`Stamp` Objekte.

#### F: Kann ich Füll- und Umrissfarben auf Text anwenden, der bereits im PDF-Dokument vorhanden ist?

 A: Ja, Sie können ähnliche Prinzipien verwenden, um Füll- und Umrissfarben auf vorhandenen Text im PDF-Dokument anzuwenden, indem Sie die entsprechenden Textobjekte auswählen und sie mit den gewünschten Stempeln hinzufügen`TextState` Eigenschaften.

#### F: Wie kann ich die Deckkraft und Mischung des gefüllten und umrandeten Textes anpassen?

 A: Mit dem bereitgestellten Code können Sie die Deckkraft und Mischeigenschaften des Stempels mithilfe von festlegen`Opacity` Und`BlendingSpace`Eigenschaften bzw. Sie können diese Werte anpassen, um den gewünschten visuellen Effekt zu erzielen.

#### F: Wie kann ich auf mehrere Stempel innerhalb desselben PDF-Dokuments unterschiedliche Füll- und Umrissfarben anwenden?

 A: Sie können mehrere erstellen`TextState` Objekte mit unterschiedlichen Füll- und Umrissfarben und erstellen Sie dann separate`Stamp` Objekte für jeden Textsatz mit unterschiedlichen Farben. Fügen Sie diese Stempel mit dem zum selben PDF-Dokument hinzu`PdfFileStamp` Klasse.

#### F: Kann ich für den umrandeten und ausgefüllten Text andere Schriftarten als Arial verwenden?

 A: Ja, Sie können die Schriftart ändern, indem Sie den Parameter „Schriftartname“ im ändern`FormattedText` Konstruktor beim Erstellen des Stempels. Sie können jede auf Ihrem System verfügbare Schriftart verwenden.

#### F: Wie kann ich den Drehwinkel des umrandeten und gefüllten Textes ändern?

 A: Mit dem bereitgestellten Code können Sie den Drehwinkel des Stempels einstellen`Rotation` Eigentum. Sie können diese Eigenschaft anpassen, um den gewünschten Drehwinkel für den Text festzulegen.

#### F: Wie kann ich die Position und Größe des umrandeten und gefüllten Texts auf der Seite steuern?

A: Sie können das verwenden`SetOrigin` Methode der`Stamp` -Objekt, um die X- und Y-Koordinaten der Position des Stempels auf der Seite festzulegen. Darüber hinaus können Sie die Schriftgröße im anpassen`FormattedText` Konstruktor zur Steuerung der Textgröße.