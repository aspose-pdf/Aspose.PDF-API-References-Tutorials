---
title: Steuern Sie die Z-Reihenfolge des Rechtecks
linktitle: Steuern Sie die Z-Reihenfolge des Rechtecks
second_title: Aspose.PDF für .NET API-Referenz
description: Erfahren Sie, wie Sie die Z-Reihenfolge von Rechtecken in einer PDF-Datei mit Aspose.PDF für .NET steuern.
type: docs
weight: 40
url: /de/net/programming-with-graphs/control-rectangle-z-order/
---

In diesem Tutorial führen wir Sie Schritt für Schritt durch den folgenden C#-Quellcode, um die Z-Reihenfolge von Rechtecken mithilfe von Aspose.PDF für .NET zu steuern.

Stellen Sie sicher, dass Sie die Aspose.PDF-Bibliothek installiert und Ihre Entwicklungsumgebung eingerichtet haben, bevor Sie beginnen. Außerdem verfügen Sie über Grundkenntnisse der C#-Programmierung.

## Schritt 1: Einrichten des Dokumentenverzeichnisses

Im bereitgestellten Quellcode müssen Sie das Verzeichnis angeben, in dem Sie die resultierende PDF-Datei speichern möchten. Ändern Sie die Variable „dataDir“ in das gewünschte Verzeichnis.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Schritt 2: Instanziieren eines Dokumentobjekts und Hinzufügen einer Seite

Wir erstellen eine Instanz der Document-Klasse und fügen diesem Dokument eine Seite hinzu.

```csharp
Document doc1 = new Document();
Aspose.Pdf.Page page1 = doc1.Pages.Add();
```

## Schritt 3: Einrichten der Seitengröße

Wir legen die PDF-Seitengröße mit der SetPageSize-Methode fest.

```csharp
page1.SetPageSize(375, 300);
```

## Schritt 4: Seitenränder festlegen

Wir können die Seitenränder mithilfe der Eigenschaften des PageInfo-Objekts konfigurieren.

```csharp
page1.PageInfo.Margin.Left = 0;
page1.PageInfo.Margin.Top = 0;
```

## Schritt 5: Fügen Sie Rechtecke mit der angegebenen Z-Reihenfolge hinzu

Wir erstellen und fügen der Seite Rechtecke mit unterschiedlichen Farben und bestimmten Z-Reihenfolgen hinzu.

```csharp
AddRectangle(page1, 50, 40, 60, 40, Aspose.Pdf.Color.Red, 2);
AddRectangle(page1, 20, 20, 30, 30, Aspose.Pdf.Color.Blue, 1);
AddRectangle(page1, 40, 40, 60, 30, Aspose.Pdf.Color.Green, 0);
```

## Schritt 6: Speichern der resultierenden PDF-Datei

Abschließend speichern wir die resultierende PDF-Datei mit dem Namen „ControlRectangleZOrder_out.pdf“ im angegebenen Verzeichnis.

```csharp
doc1.Save(dataDir);
```
### Beispielquellcode für die Z-Reihenfolge des Steuerrechtecks mit Aspose.Words für .NET 

```csharp

// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Instanziieren Sie ein Document-Klassenobjekt
Document doc1 = new Document();
/// Seite zur Seitensammlung der PDF-Datei hinzufügen
Aspose.Pdf.Page page1 = doc1.Pages.Add();
// Legen Sie die Größe der PDF-Seite fest
page1.SetPageSize(375, 300);
// Legen Sie den linken Rand für das Seitenobjekt auf 0 fest
page1.PageInfo.Margin.Left = 0;
// Legen Sie den oberen Rand des Seitenobjekts auf 0 fest
page1.PageInfo.Margin.Top = 0;
// Erstellen Sie ein neues Rechteck mit der Farbe Rot, der Z-Reihenfolge 0 und bestimmten Abmessungen
AddRectangle(page1, 50, 40, 60, 40, Aspose.Pdf.Color.Red, 2);
// Erstellen Sie ein neues Rechteck mit der Farbe Blau, der Z-Reihenfolge 0 und bestimmten Abmessungen
AddRectangle(page1, 20, 20, 30, 30, Aspose.Pdf.Color.Blue, 1);
// Erstellen Sie ein neues Rechteck mit der Farbe Grün, der Z-Reihenfolge 0 und bestimmten Abmessungen
AddRectangle(page1, 40, 40, 60, 30, Aspose.Pdf.Color.Green, 0);
dataDir = dataDir + "ControlRectangleZOrder_out.pdf";
// Speichern Sie die resultierende PDF-Datei
doc1.Save(dataDir);

```

## Abschluss

In diesem Tutorial haben wir erklärt, wie Sie die Z-Reihenfolge von Rechtecken mithilfe von Aspose.PDF für .NET steuern. Mit diesem Wissen können Sie nun Rechtecke in Ihren PDF-Dateien präzise anordnen und schichten.
