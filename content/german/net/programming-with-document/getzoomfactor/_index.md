---
title: Zoomfaktor in PDF-Datei abrufen
linktitle: Zoomfaktor in PDF-Datei abrufen
second_title: Aspose.PDF für .NET API-Referenz
description: Erfahren Sie in dieser Schritt-für-Schritt-Anleitung, wie Sie mit Aspose.PDF für .NET den Zoomfaktor in einer PDF-Datei erhalten.
type: docs
weight: 210
url: /de/net/programming-with-document/getzoomfactor/
---
Aspose.PDF für .NET ist eine PDF-Bearbeitungsbibliothek, die viele Funktionen zum Ausführen verschiedener Vorgänge an PDF-Dokumenten bietet. Eine dieser Funktionen ist die Möglichkeit, den Zoomfaktor in einer PDF-Datei abzurufen. In diesem Tutorial erklären wir, wie Sie Aspose.PDF für .NET verwenden, um den Zoomfaktor in einer PDF-Datei mithilfe von C#-Quellcode abzurufen.


## Schritt 1: Neues Dokumentobjekt instanziieren

 Der erste Schritt zum Ermitteln des Zoomfaktors einer PDF-Datei mit Aspose.PDF für .NET besteht in der Instanziierung eines neuen`Document` Objekt. Das`Document` Das Objekt stellt ein PDF-Dokument dar, das aus einer Datei oder einem Stream geladen werden kann.

```csharp
// Der Pfad zum Dokumentverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Neues Dokumentobjekt instanziieren
Document doc = new Document(dataDir + "Zoomed_pdf.pdf");
```

 Im obigen Code haben wir ein`Document` Objekt, indem Sie den Pfad der PDF-Datei an den Konstruktor des`Document` Klasse. Sie müssen „IHR DOKUMENTVERZEICHNIS“ durch den tatsächlichen Pfad des Verzeichnisses ersetzen, in dem sich Ihre PDF-Datei befindet.

## Schritt 2: GoToAction-Objekt erstellen

 Der nächste Schritt besteht in der Erstellung eines`GoToAction` Objekt. Ein`GoToAction`Objekt stellt eine Aktion dar, die zu einem bestimmten Ziel in einem PDF-Dokument führt. In unserem Fall möchten wir den Zoomfaktor der PDF-Datei ermitteln, also verwenden wir das`OpenAction` Eigentum der`Document` Objekt, um die`GoToAction` Objekt.

```csharp
// GoToAction-Objekt erstellen
GoToAction action = doc.OpenAction as GoToAction;
```

 Im obigen Code haben wir ein`GoToAction` Objekt durch das Werfen des`OpenAction` Eigentum der`Document` Einwände erheben gegen`GoToAction`.

## Schritt 3: Den Zoomfaktor der PDF-Datei ermitteln

 Der dritte Schritt besteht darin, den Zoomfaktor der PDF-Datei zu ermitteln. Wir können den Zoomfaktor der PDF-Datei ermitteln, indem wir auf die`Destination` Eigentum der`GoToAction` Objekt und dann werfen Sie es auf`XYZExplicitDestination` . Der`XYZExplicitDestination` Die Klasse stellt ein Ziel in einem PDF-Dokument dar, das die zu erreichenden Koordinaten und den Zoomfaktor angibt.

```csharp
// Den Zoomfaktor einer PDF-Datei ermitteln
System.Console.WriteLine((action.Destination as XYZExplicitDestination).Zoom); // Dokument-Zoomwert;
```

 Im obigen Code haben wir auf die`Destination` Eigentum der`GoToAction` Objekt und wende es dann an`XYZExplicitDestination` . Danach haben wir den`Zoom` Eigentum der`XYZExplicitDestination` Objekt, um den Zoomfaktor der PDF-Datei zu erhalten.

## Schritt 4: Zoomfaktor ausgeben

 Der letzte Schritt ist die Ausgabe des Zoomfaktors der PDF-Datei. Wir können den`System.Console.WriteLine`

```csharp
// Den Zoomfaktor einer PDF-Datei ermitteln
System.Console.WriteLine((action.Destination as XYZExplicitDestination).Zoom); // Dokument-Zoomwert;
```        

### Beispiel-Quellcode zum Abrufen des Zoomfaktors mit Aspose.PDF für .NET

Hier ist der vollständige Beispielquellcode für „Get Zoom Factor“ mit Aspose.PDF für .NET:

```csharp
// Der Pfad zum Dokumentverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Neues Dokumentobjekt instanziieren
Document doc = new Document(dataDir + "Zoomed_pdf.pdf");

// GoToAction-Objekt erstellen
GoToAction action = doc.OpenAction as GoToAction;

// Den Zoomfaktor einer PDF-Datei ermitteln
System.Console.WriteLine((action.Destination as XYZExplicitDestination).Zoom); // Dokument-Zoomwert;
```

## Abschluss

In diesem Tutorial haben wir untersucht, wie man mit Aspose.PDF für .NET den Zoomfaktor einer PDF-Datei ermittelt. Der Zoomfaktor ist ein entscheidender Aspekt eines PDF-Dokuments, da er die anfängliche Anzeigegröße beim Öffnen in einem Viewer bestimmt. Durch Zugriff auf und Verwendung des Zoomfaktors können Entwickler das Anzeigeerlebnis für Endbenutzer anpassen. Aspose.PDF für .NET bietet eine einfache und effektive API zum Abrufen des Zoomfaktors und anderer navigationsbezogener Informationen aus einem PDF-Dokument und ermöglicht Entwicklern die Erstellung funktionsreicher und interaktiver PDF-Anwendungen.

### FAQs zum Zoomfaktor in PDF-Dateien

#### F: Was ist der Zoomfaktor in einer PDF-Datei?

A: Der Zoomfaktor in einer PDF-Datei bezieht sich auf den Vergrößerungsgrad, der beim Anzeigen des Dokuments angewendet wird. Er bestimmt die anfängliche Anzeigegröße der PDF-Datei auf dem Bildschirm. Ein Zoomfaktor von 1,0 stellt die tatsächliche Größe dar (100 % Zoom), während ein Zoomfaktor größer als 1,0 eine Vergrößerung und ein Zoomfaktor kleiner als 1,0 eine Verkleinerung darstellt.

#### F: Wie kann ich die Zoomfaktor-Informationen in meiner Anwendung verwenden?

A: Sie können die Zoomfaktorinformationen verwenden, um die anfängliche Anzeigegröße eines PDF-Dokuments anzupassen, wenn es in einem Viewer geöffnet wird. Sie können beispielsweise einen bestimmten Zoomfaktor festlegen, um sicherzustellen, dass das PDF in einer bestimmten Größe angezeigt wird oder die gesamte Seite in das Fenster des Viewers passt.

#### F: Kann ich den Zoomfaktor eines PDF-Dokuments programmgesteuert mit Aspose.PDF für .NET ändern?

 A: Ja, Sie können den Zoomfaktor eines PDF-Dokuments programmgesteuert mit Aspose.PDF für .NET ändern. Sie können den Zoomfaktor für bestimmte Aktionen festlegen, wie zum Beispiel`GoToAction` oder`GoToRemoteAction`um zu steuern, wie das Dokument angezeigt wird, wenn der Benutzer mit Links oder Lesezeichen interagiert.

#### F: Gibt es andere Möglichkeiten, mit Aspose.PDF für .NET zu bestimmten Stellen in einem PDF-Dokument zu navigieren?

 A: Ja, Aspose.PDF für .NET bietet verschiedene Funktionen, um zu bestimmten Stellen in einem PDF-Dokument zu navigieren. Neben der Verwendung`GoToAction` können Sie andere Aktionen verwenden wie`GoToURIAction` um eine URL zu öffnen,`GoToEmbeddedAction` um zu eingebetteten Dateien zu navigieren und`GoToNamedAction` um zu benannten Zielen innerhalb des PDF-Dokuments zu gelangen.