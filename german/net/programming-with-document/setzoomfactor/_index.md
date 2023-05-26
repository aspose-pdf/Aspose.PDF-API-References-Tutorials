---
title: Stellen Sie den Zoomfaktor ein
linktitle: Stellen Sie den Zoomfaktor ein
second_title: Aspose.PDF für .NET API-Referenz
description: Erfahren Sie in unserer Schritt-für-Schritt-Anleitung, wie Sie den Zoomfaktor für PDF-Dateien mit Aspose.PDF für .NET festlegen.
type: docs
weight: 340
url: /de/net/programming-with-document/setzoomfactor/
---
Aspose.PDF für .NET ist eine leistungsstarke API, die es Entwicklern ermöglicht, mit PDF-Dokumenten in ihren .NET-Anwendungen zu arbeiten. Eine der Funktionen ist die Möglichkeit, den Zoomfaktor eines PDF-Dokuments festzulegen. In dieser Schritt-für-Schritt-Anleitung erklären wir, wie Sie mit Aspose.PDF für .NET den Zoomfaktor eines PDF-Dokuments mithilfe des bereitgestellten C#-Quellcodes festlegen.

## Schritt 1: Legen Sie den Pfad zum Dokumentverzeichnis fest

 Der erste Schritt besteht darin, den Pfad zu dem Verzeichnis festzulegen, in dem sich das PDF-Dokument befindet. Dies kann durch Einstellen der erfolgen`dataDir` Variable zum Verzeichnispfad. 

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

Ersetzen Sie „IHR DOKUMENTVERZEICHNIS“ durch den tatsächlichen Verzeichnispfad, in dem sich Ihr PDF-Dokument befindet.

## Schritt 2: Instanziieren Sie ein neues Document-Objekt

Um mit Aspose.PDF für .NET mit einem PDF-Dokument zu arbeiten, müssen wir ein neues erstellen`Document` Objekt und laden Sie die PDF-Datei hinein. 

```csharp
Document doc = new Document(dataDir + "SetZoomFactor.pdf");
```

 Dieser Code erstellt ein neues`Document` Objekt und laden Sie die PDF-Datei mit dem Namen „SetZoomFactor.pdf“ aus dem`dataDir` Verzeichnis hinein.

## Schritt 3: Stellen Sie den Zoomfaktor ein

 Sobald die`Document` Nachdem das Objekt erstellt wurde, können wir den Zoomfaktor des PDF-Dokuments festlegen. Im folgenden Code stellen wir den Zoomfaktor auf 50 % ein.

```csharp
GoToAction action = new GoToAction(new XYZExplicitDestination(1, 0, 0, .5));
doc.OpenAction = action;
```

 Dieser Code setzt den Zoomfaktor durch Erstellen eines neuen auf 50 %`GoToAction` Objekt und Übergabe von a`XYZExplicitDestination` Objekt mit einem Zoomfaktor von 50 % darauf. Der`OpenAction` Eigentum der`Document` Das Objekt wird dann auf dieses gesetzt`GoToAction` Objekt.

## Schritt 4: Speichern Sie das PDF-Dokument

 Schließlich können wir das geänderte PDF-Dokument in einer neuen Datei speichern. Im folgenden Code speichern wir das PDF-Dokument in einer neuen Datei mit dem Namen „Zoomed_pdf_out.pdf“.`dataDir` Verzeichnis.

```csharp
dataDir = dataDir + "Zoomed_pdf_out.pdf";
doc.Save(dataDir);
```

## Abschluss

Aspose.PDF für .NET bietet eine einfache und effiziente Möglichkeit, den Zoomfaktor eines PDF-Dokuments mithilfe von C#-Code festzulegen. Durch Befolgen der oben genannten Schritte können Sie den Zoomfaktor jedes PDF-Dokuments in Ihrer .NET-Anwendung problemlos ändern.

### Beispielquellcode für „Zoomfaktor festlegen“ mit Aspose.PDF für .NET

```csharp

	// Der Pfad zum Dokumentenverzeichnis.
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	// Instanziieren Sie ein neues Dokumentobjekt
	Document doc = new Document(dataDir + "SetZoomFactor.pdf");

	GoToAction action = new GoToAction(new XYZExplicitDestination(1, 0, 0, .5));
	doc.OpenAction = action;
	dataDir = dataDir + "Zoomed_pdf_out.pdf";
	// Speichern Sie das Dokument
	doc.Save(dataDir);

```
