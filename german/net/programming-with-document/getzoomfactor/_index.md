---
title: Holen Sie sich den Zoomfaktor in eine PDF-Datei
linktitle: Holen Sie sich den Zoomfaktor in eine PDF-Datei
second_title: Aspose.PDF für .NET API-Referenz
description: Erfahren Sie in dieser Schritt-für-Schritt-Anleitung, wie Sie Aspose.PDF für .NET verwenden, um den Zoomfaktor in einer PDF-Datei zu ermitteln.
type: docs
weight: 210
url: /de/net/programming-with-document/getzoomfactor/
---
Aspose.PDF für .NET ist eine PDF-Bearbeitungsbibliothek, die viele Funktionen zum Ausführen verschiedener Vorgänge an PDF-Dokumenten bietet. Eine dieser Funktionen ist die Möglichkeit, den Zoomfaktor in einer PDF-Datei abzurufen. In diesem Tutorial erklären wir, wie Sie Aspose.PDF für .NET verwenden, um den Zoomfaktor in einer PDF-Datei mithilfe von C#-Quellcode zu ermitteln.


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

 Der nächste Schritt besteht darin, eine zu erstellen`GoToAction` Objekt. A`GoToAction`Das Objekt stellt eine Aktion dar, die zu einem bestimmten Ziel in einem PDF-Dokument führt. In unserem Fall möchten wir den Zoomfaktor der PDF-Datei erhalten, also verwenden wir den`OpenAction` Eigentum der`Document` Objekt, um das zu bekommen`GoToAction` Objekt.

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

## Abschluss

In diesem Tutorial haben wir untersucht, wie Sie Aspose.PDF für .NET verwenden, um den Zoomfaktor einer PDF-Datei zu ermitteln. Der Zoomfaktor ist ein entscheidender Aspekt eines PDF-Dokuments, da er die anfängliche Anzeigegröße beim Öffnen in einem Viewer bestimmt. Durch Zugriff auf und Nutzung des Zoomfaktors können Entwickler das Seherlebnis für Endbenutzer anpassen. Aspose.PDF für .NET bietet eine einfache und effektive API zum Abrufen des Zoomfaktors und anderer navigationsbezogener Informationen aus einem PDF-Dokument und ermöglicht Entwicklern so die Erstellung funktionsreicher und interaktiver PDF-Anwendungen.

### FAQs zum Abrufen des Zoomfaktors in einer PDF-Datei

#### F: Wie groß ist der Zoomfaktor in einer PDF-Datei?

A: Der Zoomfaktor in einer PDF-Datei bezieht sich auf die Vergrößerungsstufe, die auf das Dokument angewendet wird, wenn es angezeigt wird. Es bestimmt die anfängliche Anzeigegröße der PDF-Datei auf dem Bildschirm. Ein Zoomfaktor von 1,0 stellt die tatsächliche Größe dar (100 % Zoom), während ein Zoomfaktor größer als 1,0 eine Vergrößerung und ein Zoomfaktor kleiner als 1,0 eine Verkleinerung darstellt.

#### F: Wie kann ich die Informationen zum Zoomfaktor in meiner Anwendung verwenden?

A: Mithilfe der Informationen zum Zoomfaktor können Sie die anfängliche Anzeigegröße eines PDF-Dokuments anpassen, wenn es in einem Viewer geöffnet wird. Sie können beispielsweise einen bestimmten Zoomfaktor festlegen, um sicherzustellen, dass das PDF in einer bestimmten Größe angezeigt wird, oder um die gesamte Seite an das Fenster des Betrachters anzupassen.

#### F: Kann ich den Zoomfaktor eines PDF-Dokuments programmgesteuert mit Aspose.PDF für .NET ändern?

 A: Ja, Sie können den Zoomfaktor eines PDF-Dokuments programmgesteuert mit Aspose.PDF für .NET ändern. Sie können den Zoomfaktor für bestimmte Aktionen festlegen, z`GoToAction` oder`GoToRemoteAction`um zu steuern, wie das Dokument angezeigt wird, wenn der Benutzer mit Links oder Lesezeichen interagiert.

#### F: Gibt es andere Möglichkeiten, mit Aspose.PDF für .NET zu bestimmten Stellen in einem PDF-Dokument zu navigieren?

 A: Ja, Aspose.PDF für .NET bietet verschiedene Funktionen zum Navigieren zu bestimmten Stellen in einem PDF-Dokument. Neben der Verwendung`GoToAction` , Sie können andere Aktionen verwenden wie`GoToURIAction` um eine URL zu öffnen,`GoToEmbeddedAction` um zu eingebetteten Dateien zu navigieren und`GoToNamedAction` um zu benannten Zielen im PDF-Dokument zu gelangen.