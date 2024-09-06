---
title: Zoomfaktor in PDF-Datei festlegen
linktitle: Zoomfaktor in PDF-Datei festlegen
second_title: Aspose.PDF für .NET API-Referenz
description: Erfahren Sie in unserer Schritt-für-Schritt-Anleitung, wie Sie mit Aspose.PDF für .NET den Zoomfaktor in einer PDF-Datei einstellen.
type: docs
weight: 340
url: /de/net/programming-with-document/setzoomfactor/
---
Aspose.PDF für .NET ist eine leistungsstarke API, die es Entwicklern ermöglicht, in ihren .NET-Anwendungen mit PDF-Dokumenten zu arbeiten. Eine der Funktionen, die es bietet, ist die Möglichkeit, den Zoomfaktor eines PDF-Dokuments einzustellen. In dieser Schritt-für-Schritt-Anleitung erklären wir, wie Sie mit Aspose.PDF für .NET den Zoomfaktor eines PDF-Dokuments mithilfe des bereitgestellten C#-Quellcodes einstellen.

## Schritt 1: Pfad zum Dokumentverzeichnis festlegen

 Der erste Schritt besteht darin, den Pfad zum Verzeichnis festzulegen, in dem sich das PDF-Dokument befindet. Dies kann durch Festlegen der`dataDir` Variable zum Verzeichnispfad. 

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

Ersetzen Sie „IHR DOKUMENTVERZEICHNIS“ durch den tatsächlichen Verzeichnispfad, in dem sich Ihr PDF-Dokument befindet.

## Schritt 2: Instanziieren eines neuen Dokumentobjekts

 Um mit einem PDF-Dokument mit Aspose.PDF für .NET zu arbeiten, müssen wir ein neues erstellen`Document` Objekt und laden Sie die PDF-Datei hinein. 

```csharp
Document doc = new Document(dataDir + "SetZoomFactor.pdf");
```

 Dieser Code erstellt eine neue`Document` Objekt und laden Sie die PDF-Datei mit dem Namen "SetZoomFactor.pdf" aus dem`dataDir` Verzeichnis hinein.

## Schritt 3: Zoomfaktor einstellen

 Sobald das`Document`Objekt erstellt wird, können wir den Zoomfaktor des PDF-Dokuments festlegen. Im folgenden Code setzen wir den Zoomfaktor auf 50 %.

```csharp
GoToAction action = new GoToAction(new XYZExplicitDestination(1, 0, 0, .5));
doc.OpenAction = action;
```

 Dieser Code setzt den Zoomfaktor auf 50%, indem er ein neues`GoToAction` Objekt und Übergabe eines`XYZExplicitDestination` Objekt mit einem Zoomfaktor von 50%. Die`OpenAction` Eigentum der`Document` Objekt wird dann auf diesen Wert gesetzt`GoToAction` Objekt.

## Schritt 4: Speichern Sie das PDF-Dokument

 Schließlich können wir das geänderte PDF-Dokument in einer neuen Datei speichern. Im folgenden Code speichern wir das PDF-Dokument in einer neuen Datei mit dem Namen "Zoomed_pdf_out.pdf" im`dataDir` Verzeichnis.

```csharp
dataDir = dataDir + "Zoomed_pdf_out.pdf";
doc.Save(dataDir);
```

### Beispielquellcode zum Festlegen des Zoomfaktors mit Aspose.PDF für .NET

```csharp
// Der Pfad zum Dokumentverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Neues Dokumentobjekt instanziieren
Document doc = new Document(dataDir + "SetZoomFactor.pdf");

GoToAction action = new GoToAction(new XYZExplicitDestination(1, 0, 0, .5));
doc.OpenAction = action;
dataDir = dataDir + "Zoomed_pdf_out.pdf";
// Speichern des Dokuments
doc.Save(dataDir);
```

## Abschluss

Aspose.PDF für .NET bietet eine einfache und effiziente Möglichkeit, den Zoomfaktor eines PDF-Dokuments mithilfe von C#-Code festzulegen. Indem Sie die obigen Schritte befolgen, können Sie den Zoomfaktor jedes PDF-Dokuments in Ihrer .NET-Anwendung problemlos ändern.

### FAQs

#### F: Was ist der Zoomfaktor in einem PDF-Dokument und wie wirkt er sich auf die Anzeige aus?

A: Der Zoomfaktor in einem PDF-Dokument bestimmt den Vergrößerungsgrad beim Anzeigen des Dokuments. Er gibt den Maßstab an, in dem das Dokument angezeigt wird, und beeinflusst, wie groß oder klein der Inhalt auf dem Bildschirm erscheint. Ein Zoomfaktor von 1,0 entspricht einem Zoom von 100 % (tatsächliche Größe), während ein Faktor größer als 1,0 vergrößert und ein Faktor kleiner als 1,0 verkleinert.

#### F: Kann ich für verschiedene Seiten desselben PDF-Dokuments einen bestimmten Zoomfaktor festlegen?

 A: Ja, mit Aspose.PDF für .NET können Sie verschiedene Zoomfaktoren für verschiedene Seiten innerhalb desselben PDF-Dokuments festlegen. Der bereitgestellte Beispielquellcode zeigt, wie Sie den Zoomfaktor für die erste Seite mithilfe des`GoToAction` Objekt. Sie können den Code ändern, um bei Bedarf unterschiedliche Zoomfaktoren für andere Seiten festzulegen.

#### F: Welche Auswirkungen hat die Änderung des Zoomfaktors auf das Drucken und Speichern des PDF-Dokuments?

A: Das Ändern des Zoomfaktors mit Aspose.PDF für .NET wirkt sich nicht auf den eigentlichen Inhalt des PDF-Dokuments selbst aus. Es wirkt sich nur auf das Anzeigeerlebnis aus, wenn das Dokument in einem PDF-Viewer geöffnet wird. Der programmgesteuert eingestellte Zoomfaktor hat keine Auswirkungen auf die Druckausgabe oder die gespeicherte PDF-Datei.