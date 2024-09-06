---
title: Z-Reihenfolge von Rechtecken in PDF-Dateien steuern
linktitle: Z-Reihenfolge von Rechtecken in PDF-Dateien steuern
second_title: Aspose.PDF für .NET API-Referenz
description: Erfahren Sie, wie Sie die Z-Reihenfolge von Rechtecken in einer PDF-Datei mit Aspose.PDF für .NET steuern.
type: docs
weight: 40
url: /de/net/programming-with-graphs/control-rectangle-z-order/
---
In diesem Tutorial führen wir Sie Schritt für Schritt durch den folgenden C#-Quellcode, um die Z-Reihenfolge von Rechtecken mit Aspose.PDF für .NET zu steuern.

Stellen Sie sicher, dass Sie die Aspose.PDF-Bibliothek installiert und Ihre Entwicklungsumgebung eingerichtet haben, bevor Sie beginnen. Sie benötigen außerdem Grundkenntnisse in der C#-Programmierung.

## Schritt 1: Einrichten des Dokumentverzeichnisses

Im bereitgestellten Quellcode müssen Sie das Verzeichnis angeben, in dem Sie die resultierende PDF-Datei speichern möchten. Ändern Sie die Variable „dataDir“ in das gewünschte Verzeichnis.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Schritt 2: Instanziieren eines Dokumentobjekts und Hinzufügen einer Seite

Wir erstellen eine Instanz der Dokumentklasse und fügen diesem Dokument eine Seite hinzu.

```csharp
Document doc1 = new Document();
Aspose.Pdf.Page page1 = doc1.Pages.Add();
```

## Schritt 3: Seitengröße festlegen

Wir legen die PDF-Seitengröße mit der Methode SetPageSize fest.

```csharp
page1.SetPageSize(375, 300);
```

## Schritt 4: Seitenränder festlegen

Wir können die Seitenränder mit den Eigenschaften des PageInfo-Objekts konfigurieren.

```csharp
page1.PageInfo.Margin.Left = 0;
page1.PageInfo.Margin.Top = 0;
```

## Schritt 5: Rechtecke mit angegebener Z-Reihenfolge hinzufügen

Wir erstellen und fügen der Seite Rechtecke mit unterschiedlichen Farben und angegebenen Z-Reihenfolgen hinzu.

```csharp
AddRectangle(page1, 50, 40, 60, 40, Aspose.Pdf.Color.Red, 2);
AddRectangle(page1, 20, 20, 30, 30, Aspose.Pdf.Color.Blue, 1);
AddRectangle(page1, 40, 40, 60, 30, Aspose.Pdf.Color.Green, 0);
```

## Schritt 6: Speichern der resultierenden PDF-Datei

Abschließend speichern wir die entstandene PDF-Datei unter dem Namen „ControlRectangleZOrder_out.pdf“ im angegebenen Verzeichnis ab.

```csharp
doc1.Save(dataDir);
```
### Beispiel-Quellcode für Control Rectangle Z Order mit Aspose.PDF für .NET 

```csharp

// Der Pfad zum Dokumentverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Instanziieren Sie das Objekt der Document-Klasse
Document doc1 = new Document();
/// Seite zur Seitensammlung der PDF-Datei hinzufügen
Aspose.Pdf.Page page1 = doc1.Pages.Add();
// Größe der PDF-Seite festlegen
page1.SetPageSize(375, 300);
// Linken Rand für Seitenobjekt auf 0 setzen
page1.PageInfo.Margin.Left = 0;
// Oberen Rand des Seitenobjekts auf 0 setzen
page1.PageInfo.Margin.Top = 0;
//Erstellen Sie ein neues Rechteck mit der Farbe Rot, der Z-Reihenfolge 0 und bestimmten Abmessungen
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

In diesem Tutorial haben wir erklärt, wie Sie die Z-Reihenfolge von Rechtecken mit Aspose.PDF für .NET steuern. Dieses Wissen können Sie nun nutzen, um Rechtecke in Ihren PDF-Dateien präzise anzuordnen und zu schichten.

### FAQs zur Z-Reihenfolge von Kontrollrechtecken in PDF-Dateien

#### F: Was ist der Zweck dieses Tutorials?

A: Dieses Tutorial führt Sie durch den Prozess der Steuerung der Z-Reihenfolge von Rechtecken mit Aspose.PDF für .NET und ermöglicht Ihnen das Anordnen und Überlagern von Rechtecken in Ihren PDF-Dateien.

#### F: Welche Voraussetzungen müssen vor dem Start erfüllt sein?

A: Stellen Sie vor dem Start sicher, dass Sie die Aspose.PDF-Bibliothek installiert und Ihre Entwicklungsumgebung eingerichtet haben. Darüber hinaus sind Grundkenntnisse in der C#-Programmierung empfehlenswert.

#### F: Wie gebe ich das Verzeichnis zum Speichern der PDF-Datei an?

A: Im bereitgestellten Quellcode können Sie die Variable „dataDir“ ändern, um das Verzeichnis anzugeben, in dem Sie die resultierende PDF-Datei speichern möchten.

#### F: Welchen Zweck hat das Festlegen von Seitengröße und Rändern?

A: Durch das Festlegen der Seitengröße und der Ränder können Sie das Layout der PDF-Seite konfigurieren und eine Leinwand bereitstellen, auf der Sie die Rechtecke anordnen können.

#### F: Wie füge ich Rechtecke mit angegebener Z-Reihenfolge hinzu?

A: Sie können Rechtecke erstellen und der Seite hinzufügen, indem Sie`AddRectangle` Methode, die die Position, Abmessungen, Farbe und Z-Reihenfolge für jedes Rechteck angibt.

#### F: Was ist die Z-Reihenfolge und warum ist sie wichtig?

A: Die Z-Reihenfolge bestimmt die Stapelreihenfolge von Objekten auf einer Seite. Objekte mit höheren Z-Order-Werten werden über Objekten mit niedrigeren Z-Order-Werten positioniert, was sich auf ihre Sichtbarkeit und Schichtung auswirkt.

#### F: Kann ich die Farben und Abmessungen der Rechtecke anpassen?

 A: Ja, Sie können die Farben, Positionen und Abmessungen der Rechtecke anpassen, indem Sie die an den`AddRectangle` Verfahren.

#### F: Wie speichere ich die resultierende PDF-Datei, nachdem ich die Rechtecke angeordnet habe?

 A: Nach dem Anordnen der Rechtecke können Sie die resultierende PDF-Datei mit dem`doc1.Save(dataDir);` Zeile im bereitgestellten Quellcode.