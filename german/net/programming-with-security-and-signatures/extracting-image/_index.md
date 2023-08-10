---
title: Bild extrahieren
linktitle: Bild extrahieren
second_title: Aspose.PDF für .NET API-Referenz
description: Extrahieren Sie ganz einfach Bilder aus PDF-Dokumenten mit Aspose.PDF für .NET.
type: docs
weight: 70
url: /de/net/programming-with-security-and-signatures/extracting-image/
---
Das Extrahieren von Bildern aus einem PDF-Dokument kann in vielen Fällen nützlich sein. Mit Aspose.PDF für .NET können Sie Bilder einfach mit dem folgenden Quellcode extrahieren:

## Schritt 1: Erforderliche Bibliotheken importieren

Bevor Sie beginnen, müssen Sie die erforderlichen Bibliotheken für Ihr C#-Projekt importieren. Hier sind die notwendigen Importanweisungen:

```csharp
using Aspose.Pdf;
using System.Drawing;
using System.Drawing.Imaging;
```

## Schritt 2: Legen Sie den Pfad zum Dokumentenordner fest

 In diesem Schritt müssen Sie den Pfad zu dem Ordner angeben, der die PDF-Datei enthält, aus der Sie das Bild extrahieren möchten. Ersetzen`"YOUR DOCUMENTS DIRECTORY"`Geben Sie im folgenden Code den tatsächlichen Pfad zu Ihrem Dokumentenordner ein:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
string input = dataDir + @"ExtractingImage.pdf";
```

## Schritt 3: Bild aus PDF-Dokument extrahieren

Jetzt extrahieren wir das Bild aus dem PDF-Dokument mit dem folgenden Code:

```csharp
using (Document pdfDocument = new Document(input))
{
foreach(Field field in pdfDocument.Form)
{
SignatureField sf = field as SignatureField;
if (sf != null)
{
string outFile = dataDir + @"output_out.jpg";
using (Stream imageStream = sf.ExtractImage())
{
if (imageStream != null)
{
using (Image image = Bitmap.FromStream(imageStream))
{
image.Save(outFile, ImageFormat.Jpeg);
}
}
}
}
}
}
```

In diesem Beispiel durchlaufen wir jedes Feld des Formulars im PDF-Dokument. Wird ein Signaturfeld gefunden, extrahieren wir das zugehörige Bild und speichern es in einer JPEG-Datei.

### Beispielquellcode zum Extrahieren von Bildern mit Aspose.PDF für .NET 
```csharp
// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
string input = dataDir+ @"ExtractingImage.pdf";
using (Document pdfDocument = new Document(input))
{
	foreach (Field field in pdfDocument.Form)
	{
		SignatureField sf = field as SignatureField;
		if (sf != null)
		{
			string outFile = dataDir+ @"output_out.jpg";
			using (Stream imageStream = sf.ExtractImage())
			{
				if (imageStream != null)
				{
					using (System.Drawing.Image image = Bitmap.FromStream(imageStream))
					{
						image.Save(outFile, System.Drawing.Imaging.ImageFormat.Jpeg);
					}
				}
			}
		}
	}
}
```

## Abschluss

Herzlichen Glückwunsch! Jetzt haben Sie eine Schritt-für-Schritt-Anleitung zum Extrahieren von Bildern aus einem PDF-Dokument mit Aspose.PDF für .NET. Sie können diesen Code in Ihre eigenen Projekte integrieren, um Bilder zu extrahieren und bei Bedarf zu verwenden.

Weitere Informationen zu erweiterten Bildextraktions- und PDF-Dokumentbearbeitungsfunktionen finden Sie unbedingt in der offiziellen Aspose.PDF-Dokumentation.


### FAQs

#### F: Ist Aspose.PDF für .NET für Anfänger geeignet?

A: Während eine gewisse Vertrautheit mit der C#-Programmierung hilfreich ist, ist unser Tutorial so konzipiert, dass es anfängerfreundlich ist und Sie durch jeden Schritt führt.

#### F: Kann ich mehrere Bilder gleichzeitig extrahieren?

A: Auf jeden Fall! Durch die Implementierung von Schleifen und die Anpassung des bereitgestellten Codes können Sie mehrere Bilder aus einem einzigen PDF-Dokument extrahieren.

#### F: Ist Aspose.PDF für .NET die einzige Lösung für die Bildextraktion?

A: Obwohl andere Tools verfügbar sind, ist Aspose.PDF für .NET für seine Effizienz und umfassenden Funktionen bekannt.

#### F: Kann ich die extrahierten Bilder für kommerzielle Zwecke verwenden?

A: Ja, nach dem Extrahieren können Sie die Bilder nach Bedarf verwenden, auch für kommerzielle Projekte.

#### F: Wo finde ich weitere Ressourcen zur PDF-Bearbeitung mit Aspose.PDF?

A: Besuchen Sie unsere offizielle Dokumentation für eine Fülle von Ressourcen und Einblicken in die erweiterte PDF-Bearbeitung mit Aspose.PDF für .NET.