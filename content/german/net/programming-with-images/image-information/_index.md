---
title: Bildinformationen in PDF-Datei
linktitle: Bildinformationen in PDF-Datei
second_title: Aspose.PDF für .NET API-Referenz
description: Extrahieren Sie Bildinformationen in einer PDF-Datei mit Aspose.PDF für .NET.
type: docs
weight: 160
url: /de/net/programming-with-images/image-information/
---
In dieser Anleitung erfahren Sie Schritt für Schritt, wie Sie mit Aspose.PDF für .NET Informationen zu Bildern in eine PDF-Datei extrahieren. Stellen Sie sicher, dass Sie Ihre Umgebung bereits eingerichtet haben, und führen Sie die folgenden Schritte aus:

## Schritt 1: Definieren Sie das Dokumentenverzeichnis

 Stellen Sie sicher, dass Sie das richtige Dokumentenverzeichnis festlegen. Ersetzen`"YOUR DOCUMENT DIRECTORY"` Geben Sie im Code den Pfad zu dem Verzeichnis ein, in dem sich Ihr PDF-Dokument befindet.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Schritt 2: Laden Sie die Quell-PDF-Datei

 In diesem Schritt laden wir die Quell-PDF-Datei mit`Document` Klasse von Aspose.PDF. Benutzen Sie die`Document` Konstruktor und übergeben Sie den Pfad zum PDF-Dokument.

```csharp
Document doc = new Document(dataDir + "ImageInformation.pdf");
```

## Schritt 3: Standardauflösung festlegen

In diesem Schritt legen wir die Standardauflösung für Bilder fest. Im Beispiel ist die Standardauflösung auf 72 eingestellt.

```csharp
int defaultResolution = 72;
```

## Schritt 4: Objekte und Zähler initialisieren

In diesem Schritt initialisieren wir die Objekte und Zähler, die zum Abrufen der Bildinformationen erforderlich sind.

```csharp
System.Collections.Stack graphicsState = new System.Collections.Stack();
System.Collections.ArrayList imageNames = new System.Collections.ArrayList(doc.Pages[1].Resources.Images.Names);
```

## Schritt 5: Durchlaufen Sie die Operatoren auf der ersten Seite des Dokuments

In diesem Schritt gehen wir die Operatoren auf der ersten Seite des Dokuments durch, um bildbezogene Vorgänge zu identifizieren.

```csharp
foreach(Operator op in doc.Pages[1].Contents)
{
```

## Schritt 6: Operatoren verwalten und Bildinformationen extrahieren

In diesem Schritt verwalten wir die verschiedenen Arten von Operatoren und extrahieren die Informationen zu den Bildern.

```csharp
Aspose.Pdf.Operators.GSave opSaveState = op as Aspose.Pdf.Operators.GSave;
Aspose.Pdf.Operators.GRestore opRestoreState = op as Aspose.Pdf.Operators.GRestore;
Aspose.Pdf.Operators.ConcatenateMatrix opCtm = op as Aspose.Pdf.Operators.ConcatenateMatrix;
Aspose.Pdf.Operators.Do opDo = op as Aspose.Pdf.Operators.Do;

//Behandeln Sie GSave- und GRestore-Vorgänge für Transformationen
if (opSaveState != null)
{
     graphicsState.Push(((System.Drawing.Drawing2D.Matrix)graphicsState.Peek()).Clone());
}
else if (opRestoreState != null)
{
     graphicsState. Pop();
}
// Behandeln Sie den ConcatenateMatrix-Vorgang für Transformationen
else if (opCtm != null)
{
     // Wenden Sie die Transformationsmatrix an
     System.Drawing.Drawing2D.Matrix cm = new System.Drawing.Drawing2D.Matrix(
        (float)opCtm.Matrix.A,
        (float)opCtm.Matrix.B,
        (float)opCtm.Matrix.C,
        (float)opCtm.Matrix.D,
        (float)opCtm.Matrix.E,
        (float)opCtm.Matrix.F);


     ((System.Drawing.Drawing2D.Matrix)graphicsState.Peek()).Multiply(cm);
     keep on going;
}
// Behandeln Sie den Do-Vorgang für Bilder
else if (opDo != null)
{
     if (imageNames.Contains(opDo.Name))
     {
         // Rufen Sie das Bild ab
         XImage image = doc.Pages[1].Resources.Images[opDo.Name];
         // Rufen Sie die Abmessungen des Bildes ab
         double scaledWidth = Math.Sqrt(Math.Pow(lastCTM.Elements[0], 2) + Math.Pow(lastCTM.Elements[1], 2));
         double scaledHeight = Math.Sqrt(Math.Pow(lastCTM.Elements[2], 2) + Math.Pow(lastCTM.Elements[3], 2));
         // Berechnen Sie die Auflösung anhand der oben genannten Informationen
         double resHorizontal = originalWidth * defaultResolution / scaledWidth;
         double resVertical = originalHeight * defaultResolution / scaledHeight;
         // Bildinformationen anzeigen
         Console.Out.WriteLine(
                 string.Format(dataDir + "image {0} ({1:.##}:{2:.##}): res {3:.##} x {4:.##}",
								 opDo.Name, scaledWidth, scaledHeight, resHorizontal,
								 resVertical));
     }
}
```

### Beispielquellcode für Bildinformationen mit Aspose.PDF für .NET 
```csharp
// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Laden Sie die Quell-PDF-Datei
Document doc = new Document(dataDir+ "ImageInformation.pdf");
// Definieren Sie die Standardauflösung für das Bild
int defaultResolution = 72;
System.Collections.Stack graphicsState = new System.Collections.Stack();
// Definieren Sie ein Array-Listenobjekt, das Bildnamen enthält
System.Collections.ArrayList imageNames = new System.Collections.ArrayList(doc.Pages[1].Resources.Images.Names);
// Fügen Sie ein Objekt zum Stapeln ein
graphicsState.Push(new System.Drawing.Drawing2D.Matrix(1, 0, 0, 1, 0, 0));
// Holen Sie sich alle Operatoren auf der ersten Seite des Dokuments
foreach (Operator op in doc.Pages[1].Contents)
{
	// Verwenden Sie die GSave/GRestore-Operatoren, um die Transformationen auf den zuvor festgelegten Wert zurückzusetzen
	Aspose.Pdf.Operators.GSave opSaveState = op as Aspose.Pdf.Operators.GSave;
	Aspose.Pdf.Operators.GRestore opRestoreState = op as Aspose.Pdf.Operators.GRestore;
	// Instanziieren Sie das ConcatenateMatrix-Objekt, während es die aktuelle Transformationsmatrix definiert.
	Aspose.Pdf.Operators.ConcatenateMatrix opCtm = op as Aspose.Pdf.Operators.ConcatenateMatrix;
	// Erstellen Sie einen Do-Operator, der Objekte aus Ressourcen zieht. Es zeichnet Formobjekte und Bildobjekte
	Aspose.Pdf.Operators.Do opDo = op as Aspose.Pdf.Operators.Do;
	if (opSaveState != null)
	{
		//Vorherigen Status speichern und aktuellen Status an die Spitze des Stapels verschieben
		graphicsState.Push(((System.Drawing.Drawing2D.Matrix)graphicsState.Peek()).Clone());
	}
	else if (opRestoreState != null)
	{
		// Den aktuellen Zustand verwerfen und den vorherigen wiederherstellen
		graphicsState.Pop();
	}
	else if (opCtm != null)
	{
		System.Drawing.Drawing2D.Matrix cm = new System.Drawing.Drawing2D.Matrix(
		   (float)opCtm.Matrix.A,
		   (float)opCtm.Matrix.B,
		   (float)opCtm.Matrix.C,
		   (float)opCtm.Matrix.D,
		   (float)opCtm.Matrix.E,
		   (float)opCtm.Matrix.F);
		// Aktuelle Matrix mit der Zustandsmatrix multiplizieren
		((System.Drawing.Drawing2D.Matrix)graphicsState.Peek()).Multiply(cm);
		continue;
	}
	else if (opDo != null)
	{
		// Falls es sich um einen Bildzeichnungsoperator handelt
		if (imageNames.Contains(opDo.Name))
		{
			System.Drawing.Drawing2D.Matrix lastCTM = (System.Drawing.Drawing2D.Matrix)graphicsState.Peek();
			// Erstellen Sie ein XImage-Objekt, um Bilder der ersten PDF-Seite zu speichern
			XImage image = doc.Pages[1].Resources.Images[opDo.Name];
			// Bildabmessungen abrufen
			double scaledWidth = Math.Sqrt(Math.Pow(lastCTM.Elements[0], 2) + Math.Pow(lastCTM.Elements[1], 2));
			double scaledHeight = Math.Sqrt(Math.Pow(lastCTM.Elements[2], 2) + Math.Pow(lastCTM.Elements[3], 2));
			// Informationen zur Höhe und Breite des Bildes abrufen
			double originalWidth = image.Width;
			double originalHeight = image.Height;
			// Berechnen Sie die Auflösung basierend auf den oben genannten Informationen
			double resHorizontal = originalWidth * defaultResolution / scaledWidth;
			double resVertical = originalHeight * defaultResolution / scaledHeight;
			// Zeigt Informationen zur Größe und Auflösung jedes Bildes an
			Console.Out.WriteLine(
					string.Format(dataDir + "image {0} ({1:.##}:{2:.##}): res {3:.##} x {4:.##}",
								 opDo.Name, scaledWidth, scaledHeight, resHorizontal,
								 resVertical));
		}
	}
}
```

## Abschluss

Herzlichen Glückwunsch! Sie haben jetzt gelernt, wie Sie mit Aspose.PDF für .NET Bildinformationen in einer PDF-Datei extrahieren. Sie können diese Informationen für verschiedene Bildverarbeitungsaufgaben in Ihren Anwendungen nutzen.

### FAQs zu Bildinformationen in PDF-Dateien

#### F: Was ist der Zweck des Extrahierens von Bildinformationen aus einem PDF-Dokument mit Aspose.PDF für .NET?

A: Das Extrahieren von Bildinformationen aus einem PDF-Dokument bietet Einblicke in die Abmessungen, die Auflösung und andere Attribute von Bildern im Dokument. Diese Informationen können für Bildverarbeitungs-, Analyse- oder Optimierungsaufgaben verwendet werden.

#### F: Wie hilft Aspose.PDF für .NET beim Extrahieren von Bildinformationen aus einem PDF-Dokument?

A: Aspose.PDF für .NET bietet Tools zum Zugriff und zur Analyse des Inhalts eines PDF-Dokuments, einschließlich seiner Bilder. Der bereitgestellte Code zeigt, wie Bildinformationen mithilfe verschiedener Operatoren extrahiert und angezeigt werden.

#### F: Welche Bildinformationen können mit dieser Methode extrahiert werden?

A: Mit dieser Methode können Sie Informationen wie skalierte Abmessungen, Auflösung und Bildnamen für Bilder in einem PDF-Dokument extrahieren und anzeigen.

#### F: Wie identifiziert und verarbeitet der Code bildbezogene Operatoren in einem PDF-Dokument?

A: Der Code durchläuft die Operatoren auf einer bestimmten Seite des PDF-Dokuments. Es identifiziert und verarbeitet Operatoren im Zusammenhang mit Bildoperationen, Transformationen und Rendering.

#### F: Welche Bedeutung hat die Standardauflösung und wie wird sie im Code verwendet?

A: Die Standardauflösung wird als Referenzpunkt zur Berechnung der tatsächlichen Auflösung von Bildern verwendet. Der Code berechnet die Auflösung jedes Bildes basierend auf seinen Abmessungen und der Standardauflösungseinstellung.

#### F: Wie können die extrahierten Bildinformationen in realen Szenarien genutzt werden?

A: Die extrahierten Bildinformationen können für Aufgaben wie die Beurteilung der Bildqualität, die Bildoptimierung, die Erstellung von Miniaturansichten von Bildern und die Erleichterung bildbezogener Entscheidungsprozesse verwendet werden.

#### F: Kann ich den Code ändern, um zusätzliche bildbezogene Attribute zu extrahieren?

A: Ja, Sie können den Code anpassen, um zusätzliche Bildattribute wie Farbraum, Pixeltiefe oder Bildtyp zu extrahieren.

#### F: Ist der Prozess der Bildinformationsextraktion ressourcenintensiv oder zeitaufwändig?

A: Der Bildinformationsextraktionsprozess ist effizient und leistungsoptimiert, sodass die Auswirkungen auf den Ressourcenverbrauch und die Verarbeitungszeit minimal sind.

#### F: Wie können Entwickler von der Identifizierung und Extraktion von Bildinformationen aus PDF-Dokumenten profitieren?

A: Entwickler können Einblicke in die Eigenschaften von Bildern in PDF-Dokumenten gewinnen und so fundierte Entscheidungen hinsichtlich der Bildbearbeitung, -verarbeitung und -optimierung treffen.

#### F: Kann diese Methode für die Stapelverarbeitung von PDF-Dokumenten mit Bildern verwendet werden?

A: Ja, diese Methode kann für die Stapelverarbeitung erweitert werden, indem mehrere Seiten oder Dokumente durchlaufen, Bildinformationen extrahiert und bildbezogene Aufgaben ausgeführt werden.