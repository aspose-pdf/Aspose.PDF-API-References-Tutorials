---
title: Grafikobjekte entfernen
linktitle: Grafikobjekte entfernen
second_title: Aspose.PDF für .NET API-Referenz
description: Schritt-für-Schritt-Anleitung zum Entfernen von Grafikobjekten aus einem PDF-Dokument mit Aspose.PDF für .NET. Passen Sie Ihre PDFs an und bereinigen Sie sie.
type: docs
weight: 30
url: /de/net/programming-with-operators/remove-graphics-objects/
---
In diesem Tutorial stellen wir Ihnen eine Schritt-für-Schritt-Anleitung zum Entfernen von Grafikobjekten aus einem PDF-Dokument mit Aspose.PDF für .NET zur Verfügung. Aspose.PDF ist eine leistungsstarke Bibliothek, mit der Sie PDF-Dokumente programmgesteuert erstellen, bearbeiten und konvertieren können. Mit den von Aspose.PDF bereitgestellten Operatoren können Sie bestimmte Grafikobjekte auf einer PDF-Seite gezielt auswählen und daraus entfernen.

## Voraussetzungen

Bevor Sie beginnen, stellen Sie sicher, dass die folgenden Voraussetzungen erfüllt sind:

1. Visual Studio mit .NET Framework installiert.
2. Die Aspose.PDF-Bibliothek für .NET.

## Schritt 1: Projekteinrichtung

Erstellen Sie zunächst ein neues Projekt in Visual Studio und fügen Sie einen Verweis auf die Aspose.PDF für .NET-Bibliothek hinzu. Sie können die Bibliothek von der offiziellen Website von Aspose herunterladen und auf Ihrem Computer installieren.

## Schritt 2: Importieren Sie die erforderlichen Namespaces

Importieren Sie in Ihre C#-Codedatei die Namespaces, die für den Zugriff auf die von Aspose.PDF bereitgestellten Klassen und Methoden erforderlich sind:

```csharp
using System;
using Aspose.Pdf;
using Aspose.Pdf.Operators;
```

## Schritt 3: Laden des PDF-Dokuments

Verwenden Sie den folgenden Code, um das PDF-Dokument zu laden:

```csharp
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";
Document doc = new Document(dataDir + "RemoveGraphicsObjects.pdf");
Page page = doc.Pages[2];
OperatorCollection oc = page.Contents;
```

Geben Sie unbedingt den tatsächlichen Pfad der PDF-Datei auf Ihrem Computer an und passen Sie die Seitenzahl nach Bedarf an.

## Schritt 4: Grafikobjekte löschen

Verwenden Sie den folgenden Code, um Grafikobjekte von der PDF-Seite zu entfernen:

```csharp
Operator[] operators = new Operator[] {
newStroke(),
new ClosePathStroke(),
newFill()
};
oc.Delete(operators);
```

Der obige Code entfernt grafische Objekte, die durch die Operatoren „Stroke“, „Path Close“ und „Fill“ identifiziert werden.

### Beispielquellcode zum Entfernen von Grafikobjekten mit Aspose.PDF für .NET
 
```csharp

// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir+ "RemoveGraphicsObjects.pdf");
Page page = doc.Pages[2];
OperatorCollection oc = page.Contents;
// Verwendete Path-Painting-Operatoren
Operator[] operators = new Operator[] {
		new Aspose.Pdf.Operators.Stroke(),
		new Aspose.Pdf.Operators.ClosePathStroke(),
		new Aspose.Pdf.Operators.Fill()
};
oc.Delete(operators);
doc.Save(dataDir+ "No_Graphics_out.pdf");

```

## Abschluss

In diesem Tutorial haben Sie gelernt, wie Sie mit Aspose.PDF für .NET grafische Objekte aus einem PDF-Dokument entfernen. Mit den von Aspose.PDF bereitgestellten Operatoren können Sie bestimmte Grafikobjekte auf einer PDF-Seite gezielt auswählen und daraus entfernen. Dadurch können Sie den Inhalt Ihrer PDF-Dokumente Ihren Bedürfnissen entsprechend anpassen und bereinigen.
