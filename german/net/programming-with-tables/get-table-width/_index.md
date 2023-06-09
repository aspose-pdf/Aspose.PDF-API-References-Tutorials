---
title: Tabellenbreite ermitteln
linktitle: Tabellenbreite ermitteln
second_title: Aspose.PDF für .NET API-Referenz
description: Erfahren Sie, wie Sie mit Aspose.PDF für .NET die Breite einer Tabelle in einem PDF-Dokument ermitteln.
type: docs
weight: 90
url: /de/net/programming-with-tables/get-table-width/
---

In diesem Tutorial erfahren Sie, wie Sie mit Aspose.PDF für .NET die Breite einer Tabelle in einem PDF-Dokument ermitteln. Wir erklären Ihnen Schritt für Schritt den Quellcode in C#. Am Ende dieses Tutorials erfahren Sie, wie Sie die Breite einer Tabelle in einem PDF-Dokument ermitteln. Lasst uns beginnen!

## Schritt 1: Einrichten der Umgebung
Stellen Sie zunächst sicher, dass Sie Ihre C#-Entwicklungsumgebung mit Aspose.PDF für .NET eingerichtet haben. Fügen Sie den Verweis zur Bibliothek hinzu und importieren Sie die erforderlichen Namespaces.

## Schritt 2: Erstellen eines neuen Dokuments und einer neuen Seite
Wir erstellen ein neues PDF-Dokument und fügen eine Seite in dieses Dokument ein.

```csharp
Document doc = new Document();
Page page = doc.Pages.Add();
```

## Schritt 3: Initialisieren einer neuen Tabelle
Wir initialisieren eine neue Tabelle und setzen die Spaltenanpassung auf „AutoFitToContent“.

```csharp
Table table = new Table
{
ColumnAdjustment = ColumnAdjustment.AutoFitToContent
};
```

## Schritt 4: Fügen Sie Zeilen und Zellen zur Tabelle hinzu
Wir fügen eine Zeile in der Tabelle hinzu und fügen Zellen in dieser Zeile hinzu.

```csharp
Row row = table.Rows.Add();
Cell cell = row.Cells.Add("Text of cell 1");
cell = row.Cells.Add("Text from cell 2");
```

## Schritt 5: Tischbreite ermitteln
Wir verwenden die Methode „GetWidth()“, um die Breite der Tabelle zu ermitteln.

```csharp
Console.WriteLine(table.GetWidth());
```

### Beispielquellcode zum Abrufen der Tabellenbreite mit Aspose.PDF für .NET

```csharp
// Erstellen Sie ein neues Dokument
Document doc = new Document();
// Seite im Dokument hinzufügen
Page page = doc.Pages.Add();
// Neue Tabelle initialisieren
Table table = new Table
{
	ColumnAdjustment = ColumnAdjustment.AutoFitToContent
};
// Zeile zur Tabelle hinzufügen
Row row = table.Rows.Add();
// Zelle zur Tabelle hinzufügen
Cell cell = row.Cells.Add("Cell 1 text");
cell = row.Cells.Add("Cell 2 text");
// Tabellenbreite ermitteln
Console.WriteLine(table.GetWidth());

System.Console.WriteLine("Extracted table width succesfully!");
```

## Abschluss
In diesem Tutorial haben wir gelernt, wie man mit Aspose.PDF für .NET die Breite einer Tabelle in einem PDF-Dokument ermittelt. Mit dieser Schritt-für-Schritt-Anleitung können Sie Tabellenbreiten in Ihren eigenen C#-Projekten ermitteln.