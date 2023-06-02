---
title: Holen Sie sich den Zoomfaktor
linktitle: Holen Sie sich den Zoomfaktor
second_title: Aspose.PDF für .NET API-Referenz
description: Erfahren Sie in dieser Schritt-für-Schritt-Anleitung, wie Sie mit Aspose.PDF für .NET den Zoomfaktor einer PDF-Datei ermitteln.
type: docs
weight: 210
url: /de/net/programming-with-document/getzoomfactor/
---
Aspose.PDF für .NET ist eine PDF-Bearbeitungsbibliothek, die viele Funktionen zum Ausführen verschiedener Vorgänge an PDF-Dokumenten bietet. Eine dieser Funktionen ist die Möglichkeit, den Zoomfaktor einer PDF-Datei zu ermitteln. In diesem Tutorial erklären wir, wie Sie Aspose.PDF für .NET verwenden, um den Zoomfaktor einer PDF-Datei mithilfe von C#-Quellcode zu ermitteln.


## Schritt 1: Instanziieren Sie ein neues Dokumentobjekt

 Der erste Schritt zum Ermitteln des Zoomfaktors einer PDF-Datei mit Aspose.PDF für .NET besteht darin, eine neue zu instanziieren`Document` Objekt. Der`Document` Das Objekt stellt ein PDF-Dokument dar, das aus einer Datei oder einem Stream geladen werden kann.

```csharp
// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Instanziieren Sie ein neues Dokumentobjekt
Document doc = new Document(dataDir + "Zoomed_pdf.pdf");
```

 Im obigen Code haben wir eine erstellt`Document` Objekt, indem Sie den Pfad der PDF-Datei an den Konstruktor des übergeben`Document` Klasse. Sie müssen „IHR DOKUMENTVERZEICHNIS“ durch den tatsächlichen Pfad des Verzeichnisses ersetzen, in dem sich Ihre PDF-Datei befindet.

## Schritt 2: Erstellen Sie ein GoToAction-Objekt

 Der nächste Schritt besteht darin, eine zu erstellen`GoToAction` Objekt. A`GoToAction` Das Objekt stellt eine Aktion dar, die zu einem bestimmten Ziel in einem PDF-Dokument führt. In unserem Fall möchten wir den Zoomfaktor der PDF-Datei erhalten, also verwenden wir den`OpenAction` Eigentum der`Document` Objekt, um das zu bekommen`GoToAction` Objekt.

```csharp
// Erstellen Sie ein GoToAction-Objekt
GoToAction action = doc.OpenAction as GoToAction;
```

 Im obigen Code haben wir eine erstellt`GoToAction` Objekt durch Wirken des`OpenAction` Eigentum der`Document` widersprechen`GoToAction`.

## Schritt 3: Ermitteln Sie den Zoomfaktor der PDF-Datei

Der dritte Schritt besteht darin, den Zoomfaktor der PDF-Datei zu ermitteln. Wir können den Zoomfaktor der PDF-Datei ermitteln, indem wir auf zugreifen`Destination` Eigentum der`GoToAction` Objekt und wirf es dann darauf um`XYZExplicitDestination` . Der`XYZExplicitDestination` Die Klasse stellt ein Ziel in einem PDF-Dokument dar, das die Koordinaten und den Zoomfaktor angibt, zu dem es gehen soll.

```csharp
// Ermitteln Sie den Zoomfaktor der PDF-Datei
System.Console.WriteLine((action.Destination as XYZExplicitDestination).Zoom); // Zoomwert des Dokuments;
```

 Im obigen Code haben wir auf zugegriffen`Destination` Eigentum der`GoToAction` Objekt und wirf es dann darauf um`XYZExplicitDestination` . Danach haben wir auf die zugegriffen`Zoom` Eigentum der`XYZExplicitDestination` Objekt, um den Zoomfaktor der PDF-Datei zu erhalten.

## Schritt 4: Geben Sie den Zoomfaktor aus

 Im letzten Schritt wird der Zoomfaktor der PDF-Datei ausgegeben. Wir können das nutzen`System.Console.WriteLine`

```csharp
// Ermitteln Sie den Zoomfaktor der PDF-Datei
System.Console.WriteLine((action.Destination as XYZExplicitDestination).Zoom); // Zoomwert des Dokuments;
```        

### Beispielquellcode für „Zoomfaktor abrufen“ mit Aspose.PDF für .NET

Hier ist der vollständige Beispielquellcode für Get Zoom Factor mit Aspose.PDF für .NET:

```csharp
// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Instanziieren Sie ein neues Dokumentobjekt
Document doc = new Document(dataDir + "Zoomed_pdf.pdf");

// Erstellen Sie ein GoToAction-Objekt
GoToAction action = doc.OpenAction as GoToAction;

// Ermitteln Sie den Zoomfaktor der PDF-Datei
System.Console.WriteLine((action.Destination as XYZExplicitDestination).Zoom); // Zoomwert des Dokuments;
```
