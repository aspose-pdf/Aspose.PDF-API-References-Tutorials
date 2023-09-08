---
title: Markieren Sie Zeichen in der PDF-Datei
linktitle: Markieren Sie Zeichen in der PDF-Datei
second_title: Aspose.PDF für .NET API-Referenz
description: Erfahren Sie, wie Sie mit Aspose.PDF für .NET Zeichen in einer PDF-Datei hervorheben.
type: docs
weight: 240
url: /de/net/programming-with-text/highlight-character-in-pdf/
---
In diesem Tutorial erklären wir, wie Sie Zeichen in einer PDF-Datei mithilfe der Aspose.PDF-Bibliothek für .NET hervorheben. Wir werden den Prozess der Hervorhebung von Zeichen in einer PDF-Datei mithilfe des bereitgestellten C#-Quellcodes Schritt für Schritt durchgehen.

## Anforderungen

Bevor Sie beginnen, stellen Sie sicher, dass Sie über Folgendes verfügen:

- Die Aspose.PDF für .NET-Bibliothek installiert.
- Ein grundlegendes Verständnis der C#-Programmierung.

## Schritt 1: Richten Sie das Dokumentenverzeichnis ein

 Zuerst müssen Sie den Pfad zu dem Verzeichnis festlegen, in dem sich Ihre Eingabe-PDF-Datei befindet. Ersetzen`"YOUR DOCUMENT DIRECTORY"` im`dataDir` Variable mit dem Pfad zu Ihrer PDF-Datei.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Schritt 2: Laden Sie das PDF-Dokument

 Als nächstes laden wir das Eingabe-PDF-Dokument mit`Aspose.Pdf.Document` Klasse.

```csharp
Aspose.Pdf.Document pdfDocument = new Aspose.Pdf.Document(dataDir + "input.pdf");
```

## Schritt 3: PDF in Bild konvertieren

 Um Zeichen hervorzuheben, konvertieren wir das PDF-Dokument mit in ein Bild`PdfConverter` Klasse. Wir legen die Auflösung für die Konvertierung fest und rufen das Bild als ab`Bitmap` Objekt.

```csharp
int resolution = 150;
using (MemoryStream ms = new MemoryStream())
{
     PdfConverter conv = new PdfConverter(pdfDocument);
     conv. Resolution = new Resolution(resolution, resolution);
     conv. GetNextImage(ms, System.Drawing.Imaging.ImageFormat.Png);
     Bitmap bmp = (Bitmap)Bitmap.FromStream(ms);
```

## Schritt 4: Markieren Sie Zeichen

 Wir durchlaufen jede Seite des PDF-Dokuments und verwenden a`TextFragmentAbsorber` Objekt, um alle Wörter auf der Seite zu finden. Anschließend durchlaufen wir die Textfragmente, Segmente und Zeichen, um sie mithilfe von Rechtecken hervorzuheben.

```csharp
using (System.Drawing.Graphics gr = System.Drawing.Graphics.FromImage(bmp))
{
     //Maßstab festlegen und transformieren
     float scale = resolution / 72f;
     gr.Transform = new System.Drawing.Drawing2D.Matrix(scale, 0, 0, -scale, 0, bmp.Height);

     // Blättern Sie durch die Seiten
     for (int i = 0; i < pdfDocument.Pages.Count; i++)
     {
         Page page = pdfDocument.Pages[1];

         // Finden Sie alle Wörter auf der Seite
         TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber(@"[\S]+");
         textFragmentAbsorber.TextSearchOptions.IsRegularExpressionUsed = true;
         page. Accept(textFragmentAbsorber);
         TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;

         // Durchlaufen Sie Textfragmente
         foreach(TextFragment textFragment in textFragmentCollection)
         {
             if (i == 0)
             {
                 // Markieren Sie Zeichen
                 gr.DrawRectangle(
                     Think.Yellow,
                     (float)textFragment.Position.XIndent,
                     (float)textFragment.Position.YIndent,
                     (float)textFragment.Rectangle.Width,
                     (float)textFragment.Rectangle.Height);

                 // Durchlaufen Sie die Segmente
                 foreach(TextSegment segment in textFragment.Segments)
                 {
                     // Markieren Sie das Segment
                     gr.DrawRectangle(
                         Think Green,
                         (float)segment.Rectangle.LLX,
                         (float)segment.Rectangle.LLY,
                         (float)segment.Rectangle.Width,
                         (float)segment.Rectangle.Height);

                     // Durchlaufen Sie die Zeichen
                     foreach(CharInfo characterInfo in segment.Characters)
                     {
                         // Markieren Sie den Charakter
                         gr.DrawRectangle(
                             Think.Black,
                             (float)characterInfo.Rectangle.LLx,
                             (float)characterInfo.Rectangle.LLY,
                             (float)characterInfo.Rectangle.Width,
                             (float)characterInfo.Rectangle.Height);
                     }
                 }
             }
         }
     }
}
```

## Schritt 5: Speichern Sie das Ausgabebild

Abschließend speichern wir das geänderte Bild mit den hervorgehobenen Zeichen in der angegebenen Ausgabedatei.

```csharp
dataDir = dataDir + "HighlightCharacterInPDF_out.png";
bmp.Save(dataDir, System.Drawing.Imaging.ImageFormat.Png);
```

### Beispielquellcode zum Hervorheben von Zeichen in PDF mit Aspose.PDF für .NET 
```csharp
try
{
	// Der Pfad zum Dokumentenverzeichnis.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	int resolution = 150;
	Aspose.Pdf.Document pdfDocument = new Aspose.Pdf.Document(dataDir + "input.pdf");
	using (MemoryStream ms = new MemoryStream())
	{
		PdfConverter conv = new PdfConverter(pdfDocument);
		conv.Resolution = new Resolution(resolution, resolution);
		conv.GetNextImage(ms, System.Drawing.Imaging.ImageFormat.Png);
		Bitmap bmp = (Bitmap)Bitmap.FromStream(ms);
		using (System.Drawing.Graphics gr = System.Drawing.Graphics.FromImage(bmp))
		{
			float scale = resolution / 72f;
			gr.Transform = new System.Drawing.Drawing2D.Matrix(scale, 0, 0, -scale, 0, bmp.Height);
			for (int i = 0; i < pdfDocument.Pages.Count; i++)
			{
				Page page = pdfDocument.Pages[1];
				// Erstellen Sie ein TextAbsorber-Objekt, um alle Wörter zu finden
				TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber(@"[\S]+");
				textFragmentAbsorber.TextSearchOptions.IsRegularExpressionUsed = true;
				page.Accept(textFragmentAbsorber);
				// Holen Sie sich die extrahierten Textfragmente
				TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
				// Durchlaufe die Fragmente
				foreach (TextFragment textFragment in textFragmentCollection)
				{
					if (i == 0)
					{
						gr.DrawRectangle(
						Pens.Yellow,
						(float)textFragment.Position.XIndent,
						(float)textFragment.Position.YIndent,
						(float)textFragment.Rectangle.Width,
						(float)textFragment.Rectangle.Height);
						for (int segNum = 1; segNum <= textFragment.Segments.Count; segNum++)
						{
							TextSegment segment = textFragment.Segments[segNum];
							for (int charNum = 1; charNum <= segment.Characters.Count; charNum++)
							{
								CharInfo characterInfo = segment.Characters[charNum];
								Aspose.Pdf.Rectangle rect = page.GetPageRect(true);
								Console.WriteLine("TextFragment = " + textFragment.Text + "    Page URY = " + rect.URY +
												  "   TextFragment URY = " + textFragment.Rectangle.URY);
								gr.DrawRectangle(
								Pens.Black,
								(float)characterInfo.Rectangle.LLX,
								(float)characterInfo.Rectangle.LLY,
								(float)characterInfo.Rectangle.Width,
								(float)characterInfo.Rectangle.Height);
							}
							gr.DrawRectangle(
							Pens.Green,
							(float)segment.Rectangle.LLX,
							(float)segment.Rectangle.LLY,
							(float)segment.Rectangle.Width,
							(float)segment.Rectangle.Height);
						}
					}
				}
			}
		}
		dataDir = dataDir + "HighlightCharacterInPDF_out.png";
		bmp.Save(dataDir, System.Drawing.Imaging.ImageFormat.Png);
	}
	Console.WriteLine("\nCharacters highlighted successfully in pdf document.\nFile saved at " + dataDir);
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message + "\nThis example will only work if you apply a valid Aspose License. You can purchase full license or get 30 day temporary license from http:// Www.aspose.com/purchase/default.aspx.");
}
```

## Abschluss

In diesem Tutorial haben Sie gelernt, wie Sie mithilfe der Aspose.PDF-Bibliothek für .NET Zeichen in einem PDF-Dokument hervorheben. Indem Sie der Schritt-für-Schritt-Anleitung folgen und den bereitgestellten C#-Code ausführen, können Sie Zeichen in einer PDF-Datei hervorheben und die Ausgabe als Bild speichern.

### FAQs

#### F: Was ist der Zweck des Tutorials „Zeichen in PDF-Datei hervorheben“?

A: Das Tutorial „Zeichen in PDF-Datei hervorheben“ erklärt, wie Sie die Aspose.PDF-Bibliothek für .NET verwenden, um Zeichen in einem PDF-Dokument hervorzuheben. Das Tutorial bietet eine Schritt-für-Schritt-Anleitung und C#-Quellcode, um dies zu erreichen.

#### F: Warum sollte ich Zeichen in einem PDF-Dokument hervorheben?

A: Das Hervorheben von Zeichen in einem PDF-Dokument kann für verschiedene Zwecke nützlich sein, beispielsweise um bestimmte Inhalte hervorzuheben oder bestimmte Texte besser sichtbar und unterscheidbar zu machen.

#### F: Wie richte ich das Dokumentenverzeichnis ein?

A: So richten Sie das Dokumentenverzeichnis ein:

1.  Ersetzen`"YOUR DOCUMENT DIRECTORY"` im`dataDir` Variable mit dem Pfad zu dem Verzeichnis, in dem sich Ihre Eingabe-PDF-Datei befindet.

#### F: Wie lade ich das PDF-Dokument und konvertiere es in ein Bild?

 A: Im Tutorial ist das`Aspose.Pdf.Document` Die Klasse wird zum Laden des Eingabe-PDF-Dokuments verwendet. Dann ist die`PdfConverter` Die Klasse wird verwendet, um das PDF-Dokument in ein Bild zu konvertieren. Die Auflösung des Bildes wird eingestellt und das Bild wird als abgerufen`Bitmap` Objekt.

#### F: Wie hebe ich Zeichen im PDF-Dokumentbild hervor?

A: Das Tutorial führt Sie durch den Prozess des Durchgehens jeder Seite des PDF-Dokuments und der Suche nach Wörtern mithilfe von a`TextFragmentAbsorber`und Durchlaufen von Textfragmenten, Segmenten und Zeichen, um sie mithilfe von Rechtecken hervorzuheben.

#### F: Kann ich das Erscheinungsbild der hervorgehobenen Zeichen und Segmente anpassen?

A: Ja, Sie können das Erscheinungsbild der hervorgehobenen Zeichen und Segmente anpassen, indem Sie die Farben und Stile ändern, die bei den Zeichenvorgängen verwendet werden.

#### F: Wie speichere ich das geänderte Bild mit den hervorgehobenen Zeichen?

 A: Das Tutorial zeigt, wie Sie das geänderte Bild mit den hervorgehobenen Zeichen mithilfe von in der angegebenen Ausgabedatei speichern`Save` Methode der`Bitmap` Klasse.

#### F: Ist für dieses Tutorial eine gültige Aspose-Lizenz erforderlich?

A: Ja, eine gültige Aspose-Lizenz ist erforderlich, damit dieses Tutorial ordnungsgemäß funktioniert. Sie können eine Volllizenz erwerben oder eine 30-tägige temporäre Lizenz auf der Aspose-Website erwerben.