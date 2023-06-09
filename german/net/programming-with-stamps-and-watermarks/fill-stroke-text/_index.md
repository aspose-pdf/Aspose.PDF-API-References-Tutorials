---
title: Füllstrichtext
linktitle: Füllstrichtext
second_title: Aspose.PDF für .NET API-Referenz
description: Erfahren Sie, wie Sie mit Aspose.PDF für .NET ganz einfach Text in Ihren PDF-Dokumenten füllen und umreißen.
type: docs
weight: 90
url: /de/net/programming-with-stamps-and-watermarks/fill-stroke-text/
---
In diesem Tutorial zeigen wir Ihnen Schritt für Schritt, wie Sie mit Aspose.PDF für .NET Text in einem PDF-Dokument füllen und umreißen. Wir zeigen Ihnen, wie Sie den bereitgestellten C#-Quellcode verwenden, um Füll- und Umrissfarben auf Text im PDF-Dokument anzuwenden.

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

//Laden Sie ein Eingabe-PDF-Dokument
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
