---
title: SVG-Dimensionen abrufen
linktitle: SVG-Dimensionen abrufen
second_title: Aspose.PDF für .NET API-Referenz
description: Erfahren Sie in dieser Schritt-für-Schritt-Anleitung, wie Sie mit Aspose.PDF für .NET SVG-Dateien in PDF konvertieren. Perfekt für Entwickler, die PDFs bearbeiten möchten.
type: docs
weight: 40
url: /de/net/document-conversion/get-svg-dimensions/
---
## Einführung

Willkommen in der Welt von Aspose.PDF für .NET! Wenn Sie PDF-Dateien programmgesteuert bearbeiten möchten, sind Sie hier genau richtig. Aspose.PDF ist eine leistungsstarke Bibliothek, mit der Entwickler PDF-Dokumente problemlos erstellen, bearbeiten und konvertieren können. Egal, ob Sie ein erfahrener Entwickler sind oder gerade erst anfangen, dieser Leitfaden führt Sie durch die Grundlagen der Verwendung von Aspose.PDF für .NET und konzentriert sich darauf, wie Sie SVG-Dimensionen erhalten und sie in das PDF-Format konvertieren.

## Voraussetzungen

Bevor wir uns in den Code stürzen, müssen einige Dinge bereitstehen:

1. Visual Studio: Stellen Sie sicher, dass Visual Studio auf Ihrem Computer installiert ist. Dies ist die IDE, die wir für dieses Tutorial verwenden werden.
2.  .NET Framework: Stellen Sie sicher, dass Sie das .NET Framework installiert haben. Aspose.PDF unterstützt verschiedene Versionen. Überprüfen Sie daher die[Dokumentation](https://reference.aspose.com/pdf/net/) aus Kompatibilitätsgründen.
3.  Aspose.PDF-Bibliothek: Sie können die neueste Version von Aspose.PDF für .NET herunterladen von der[Downloadlink](https://releases.aspose.com/pdf/net/) . Wenn Sie es erst einmal ausprobieren möchten, können Sie auch eine[Kostenlose Testversion](https://releases.aspose.com/).
4. Grundlegende C#-Kenntnisse: Wenn Sie mit der C#-Programmierung vertraut sind, verstehen Sie die Beispiele besser.

## Pakete importieren

Um zu beginnen, müssen Sie die erforderlichen Pakete importieren. So können Sie das tun:

1. Öffnen Sie Ihr Visual Studio-Projekt.
2. Klicken Sie im Projektmappen-Explorer mit der rechten Maustaste auf Ihr Projekt und wählen Sie „NuGet-Pakete verwalten“ aus.
3. Suchen Sie nach „Aspose.PDF“ und installieren Sie das Paket.

Sobald Sie das Paket installiert haben, können Sie mit der Codierung beginnen!

## Schritt 1: Richten Sie Ihr Projekt ein

### Neues Projekt erstellen

Lassen Sie uns zunächst ein neues C#-Projekt in Visual Studio erstellen.

- Öffnen Sie Visual Studio und wählen Sie „Neues Projekt erstellen“ aus.
- Wählen Sie „Konsolen-App (.NET Framework)“ und klicken Sie auf „Weiter“.
- Geben Sie Ihrem Projekt einen Namen (z. B. „AsposePDFExample“) und klicken Sie auf „Erstellen“.

### Using-Direktiven hinzufügen

 Nachdem Ihr Projekt nun eingerichtet ist, müssen Sie die erforderlichen using-Direktiven oben in Ihrem`Program.cs` Datei:

```csharp
using System.IO;
using System;
using Aspose.Pdf;
```

Dadurch können Sie auf die von der Aspose.PDF-Bibliothek bereitgestellten Klassen und Methoden zugreifen.

## Schritt 2: Laden Sie das SVG-Dokument

### Definieren des Dokumentverzeichnisses

Bevor Sie das SVG-Dokument laden, müssen Sie den Pfad zu Ihrem Dokumentenverzeichnis angeben. Ersetzen Sie`"YOUR DOCUMENT DIRECTORY"` durch den tatsächlichen Pfad, in dem sich Ihre SVG-Datei befindet.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

### Laden Sie das SVG-Dokument

 Laden wir nun das SVG-Dokument mit dem`SvgLoadOptions` Klasse. Mit dieser Klasse können Sie die Seitengröße basierend auf dem SVG-Inhalt anpassen.

```csharp
var loadopt = new SvgLoadOptions();
loadopt.AdjustPageSize = true;
var svgDoc = new Document(dataDir + "GetSVGDimensions.svg", loadopt);
```

## Schritt 3: Seitenränder anpassen

Um sicherzustellen, dass der SVG-Inhalt perfekt in das PDF passt, müssen Sie die Seitenränder auf Null setzen. Dieser Schritt ist entscheidend, um die Integrität der SVG-Abmessungen beizubehalten.

```csharp
svgDoc.Pages[1].PageInfo.Margin.Top = 0;
svgDoc.Pages[1].PageInfo.Margin.Left = 0;
svgDoc.Pages[1].PageInfo.Margin.Bottom = 0;
svgDoc.Pages[1].PageInfo.Margin.Right = 0;
```

## Schritt 4: Speichern Sie das Dokument als PDF

Zum Schluss ist es an der Zeit, das SVG-Dokument als PDF zu speichern. Den Namen und Pfad der Ausgabedatei können Sie wie folgt angeben:

```csharp
svgDoc.Save(dataDir + "GetSVGDimensions_out.pdf");
```

Und das war’s! Sie haben eine SVG-Datei mit Aspose.PDF für .NET erfolgreich in eine PDF-Datei konvertiert.

## Abschluss

Herzlichen Glückwunsch! Sie haben gerade eine einfache, aber leistungsstarke Aufgabe mit Aspose.PDF für .NET abgeschlossen. Indem Sie dieser Anleitung gefolgt sind, haben Sie gelernt, wie Sie ein SVG-Dokument laden, seine Ränder anpassen und es als PDF speichern. Die Möglichkeiten mit Aspose.PDF sind endlos, und dies ist nur die Spitze des Eisbergs. Egal, ob Sie komplexe PDFs erstellen, vorhandene bearbeiten oder zwischen Formaten konvertieren möchten, Aspose.PDF bietet Ihnen alles. Also, worauf warten Sie noch? Tauchen Sie tiefer ein in die[Dokumentation](https://reference.aspose.com/pdf/net/) und entdecken Sie alle Funktionen, die diese Bibliothek zu bieten hat!

## Häufig gestellte Fragen

### Was ist Aspose.PDF für .NET?
Aspose.PDF für .NET ist eine Bibliothek, mit der Entwickler PDF-Dokumente programmgesteuert erstellen, bearbeiten und konvertieren können.

### Wie installiere ich Aspose.PDF?
 Sie können Aspose.PDF über den NuGet Package Manager in Visual Studio installieren oder von der[Website](https://releases.aspose.com/pdf/net/).

### Kann ich Aspose.PDF kostenlos nutzen?
 Ja, Aspose bietet eine[Kostenlose Testversion](https://releases.aspose.com/) damit Sie die Bibliothek vor dem Kauf testen können.

### Wo finde ich Unterstützung für Aspose.PDF?
 Unterstützung erhalten Sie vom[Aspose-Forum](https://forum.aspose.com/c/pdf/10).

### Wie erhalte ich eine temporäre Lizenz für Aspose.PDF?
 Sie können eine[vorläufige Lizenz](https://purchase.aspose.com/temporary-license/) von der Aspose-Website.