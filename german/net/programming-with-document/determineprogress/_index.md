---
title: Bestimmen Sie den Fortschritt
linktitle: Bestimmen Sie den Fortschritt
second_title: Aspose.PDF für .NET API-Referenz
description: Erfahren Sie mit dieser Schritt-für-Schritt-Anleitung und dem Codebeispiel, wie Sie den Fortschritt des Konvertierungsprozesses eines PDF-Dokuments mit Aspose.PDF für .NET ermitteln können.
type: docs
weight: 110
url: /de/net/programming-with-document/determineprogress/
---

Aspose.PDF für .NET bietet eine Funktion, mit der Sie den Fortschritt des Konvertierungsprozesses eines PDF-Dokuments bestimmen können. In diesem Tutorial stellen wir eine Schritt-für-Schritt-Anleitung zur Implementierung dieser Funktion mit C# und Aspose.PDF für .NET bereit.

## Schritt 1: Laden des PDF-Dokuments

Der erste Schritt besteht darin, das PDF-Dokument zu laden, das Sie konvertieren möchten. Für dieses Tutorial verwenden wir die Datei „AddTOC.pdf“. Ersetzen Sie den Pfad zu dieser Datei durch den Pfad zu Ihrem eigenen PDF-Dokument.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document pdfDocument = new Document(dataDir + "AddTOC.pdf");
```

## Schritt 2: Einrichten des benutzerdefinierten Fortschrittshandlers

 Als Nächstes müssen wir den benutzerdefinierten Fortschrittshandler einrichten, der während des Konvertierungsprozesses aufgerufen wird. In diesem Tutorial verwenden wir die`ConversionProgressEventHandler` Delegierter, bereitgestellt von Aspose.PDF für .NET.

```csharp
DocSaveOptions saveOptions = new DocSaveOptions();
saveOptions.CustomProgressHandler = new UnifiedSaveOptions.ConversionProgressEventHandler(ShowProgressOnConsole);
```

## Schritt 3: Speichern des PDF-Dokuments

 Schließlich müssen wir das PDF-Dokument mit speichern`Save()` Methode der`Document`Objekt. Wir übergeben den benutzerdefinierten Fortschrittshandler, den wir im vorherigen Schritt eingerichtet haben, als Parameter.

```csharp
dataDir = dataDir + "DetermineProgress_out.pdf";
pdfDocument.Save(dataDir, saveOptions);
```

## Schritt 4: Implementierung des Fortschrittshandlers

 Um den Fortschrittshandler zu implementieren, müssen wir eine Methode definieren, die einen einzelnen Parameter vom Typ akzeptiert`ConversionProgressEventArgs`. Diese Methode wird während des Konvertierungsprozesses aufgerufen, um den Fortschritt der Konvertierung zu melden.

```csharp
private void ShowProgressOnConsole(ConversionProgressEventArgs args)
{
    Console.WriteLine("Conversion progress: {0}%", args.Percent);
}
```

### Beispielquellcode für Determine Progress mit Aspose.PDF für .NET

```csharp
// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Dokument öffnen
Document pdfDocument = new Document(dataDir + "AddTOC.pdf");
DocSaveOptions saveOptions = new DocSaveOptions();
saveOptions.CustomProgressHandler = new UnifiedSaveOptions.ConversionProgressEventHandler(ShowProgressOnConsole);

dataDir = dataDir + "DetermineProgress_out.pdf";
pdfDocument.Save(dataDir, saveOptions);
Console.ReadLine();

private void ShowProgressOnConsole(ConversionProgressEventArgs args)
{
    Console.WriteLine("Conversion progress: {0}%", args.Percent);
}
```

## Abschluss

In diesem Tutorial haben wir eine Schritt-für-Schritt-Anleitung bereitgestellt, wie Sie den Fortschritt des Konvertierungsprozesses eines PDF-Dokuments mit Aspose.PDF für .NET ermitteln können. Wir haben außerdem ein Codebeispiel bereitgestellt, das Sie als Referenz bei der Implementierung dieser Funktion in Ihrer eigenen Anwendung verwenden können.