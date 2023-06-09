---
title: Automatisch an Fenster anpassen
linktitle: Automatisch an Fenster anpassen
second_title: Aspose.PDF für .NET API-Referenz
description: Schritt-für-Schritt-Anleitung zur Verwendung von Aspose.PDF für .NET und zur automatischen Fensteranpassung bei der PDF-Generierung.
type: docs
weight: 50
url: /de/net/programming-with-tables/auto-fit-to-window/
---

Der folgende Artikel ist eine Schritt-für-Schritt-Anleitung zur Verwendung des bereitgestellten C#-Quellcodes, um mithilfe der Aspose.PDF-Bibliothek für .NET die Funktion „Automatisch an Fenster anpassen“ zu erreichen. Mit der Funktion „Auto Fit To Window“ können Sie PDF-Dateien mit einem an das Anzeigefenster angepassten Layout erstellen. Diese Funktion ist besonders nützlich, wenn Ihr PDF-Dokument automatisch an die Größe des vom Benutzer verwendeten PDF-Reader-Fensters angepasst werden soll.

## Schritt 1: Einrichten der Umgebung

Bevor Sie beginnen, müssen Sie die Aspose.PDF-Bibliothek für .NET auf Ihrem Computer installieren. Stellen Sie außerdem sicher, dass Sie die erforderlichen Namespaces in Ihr Projekt importieren.

```csharp
// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Schritt 2: Erstellen eines PDF-Dokuments

 Um zu beginnen, müssen Sie eine erstellen`Document` Objekt durch Aufrufen seines Standardkonstruktors.

```csharp
Document doc = new Document();
```

 Erstellen Sie als Nächstes einen Abschnitt im`Pdf` Objekt.

```csharp
Page sec1 = doc.Pages.Add();
```

## Schritt 3: Hinzufügen einer Tabelle zum Dokument

 In diesem Schritt fügen wir unserem PDF-Dokument eine Tabelle hinzu. Erstellen Sie zunächst eine`Table` Objekt.

```csharp
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();
```

Als nächstes fügen Sie die Tabelle zur Absatzsammlung des Abschnitts hinzu.

```csharp
sec1.Paragraphs.Add(tab1);
```

##  Schritt 4: Anpassen der Tabellendarstellung

Sie können das Erscheinungsbild der Tabelle anpassen, indem Sie Eigenschaften wie Zellränder und Ränder festlegen.

```csharp
tab1. ColumnWidths = "50 50 50";
tab1.ColumnAdjustment = ColumnAdjustment.AutoFitToWindow;

tab1.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.1F);
tab1.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 1F);

Aspose.Pdf.MarginInfo margin = new Aspose.Pdf.MarginInfo();
margin. Top = 5f;
margin. Left = 5f;
margin.Right = 5f;
margin. Bottom = 5f;

tab1. DefaultCellPadding = margin;
```

##  Schritt 4: Zeilen und Zellen zur Tabelle hinzufügen

Nun fügen wir unserer Tabelle Zeilen und Zellen hinzu. Erstellen Sie zunächst eine Zeile und fügen Sie dieser Zeile Zellen hinzu.

```csharp
Aspose.Pdf.Row row1 = tab1.Rows.Add();
row1.Cells.Add("col1");
row1.Cells.Add("col2");
row1.Cells.Add("col3");

Aspose.Pdf.Row row2 = tab1.Rows.Add();
row2.Cells.Add("item1");
row2.Cells.Add("item2");
row2.Cells.Add("item3");
```

## Schritt 5: Speichern des Dokuments

Geben Sie abschließend den Pfad der Ausgabedatei an und speichern Sie das Dokument.

```csharp
dataDir = dataDir + "AutoFitToWindow_out.pdf";
doc.Save(dataDir);
```

### Beispielquellcode für „Auto Fit To Window“ mit Aspose.PDF für .NET

```csharp
// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Instanziieren Sie das PDF-Objekt, indem Sie seinen leeren Konstruktor aufrufen
Document doc = new Document();
// Erstellen Sie den Abschnitt im PDF-Objekt
Page sec1 = doc.Pages.Add();

// Instanziieren Sie ein Tabellenobjekt
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();
// Fügen Sie die Tabelle in der Absatzsammlung des gewünschten Abschnitts hinzu
sec1.Paragraphs.Add(tab1);

// Mit den Spaltenbreiten der Tabelle festlegen
tab1.ColumnWidths = "50 50 50";
tab1.ColumnAdjustment = ColumnAdjustment.AutoFitToWindow;

// Legen Sie den Standardzellenrahmen mithilfe des BorderInfo-Objekts fest
tab1.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.1F);

// Legen Sie den Tabellenrand mithilfe eines anderen benutzerdefinierten BorderInfo-Objekts fest
tab1.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 1F);
// Erstellen Sie ein MarginInfo-Objekt und legen Sie dessen linken, unteren, rechten und oberen Rand fest
Aspose.Pdf.MarginInfo margin = new Aspose.Pdf.MarginInfo();
margin.Top = 5f;
margin.Left = 5f;
margin.Right = 5f;
margin.Bottom = 5f;

// Legen Sie den Standard-Zellenabstand für das MarginInfo-Objekt fest
tab1.DefaultCellPadding = margin;

// Erstellen Sie Zeilen in der Tabelle und dann Zellen in den Zeilen
Aspose.Pdf.Row row1 = tab1.Rows.Add();
row1.Cells.Add("col1");
row1.Cells.Add("col2");
row1.Cells.Add("col3");
Aspose.Pdf.Row row2 = tab1.Rows.Add();
row2.Cells.Add("item1");
row2.Cells.Add("item2");
row2.Cells.Add("item3");

dataDir = dataDir + "AutoFitToWindow_out.pdf";
// Speichern Sie das aktualisierte Dokument, das das Tabellenobjekt enthält
doc.Save(dataDir);
```

## Abschluss

In diesem Tutorial haben wir gelernt, wie man mit Aspose.PDF für .NET eine PDF-Datei mit der Funktion „Automatisch an Fenster anpassen“ generiert. Diese Funktion ist äußerst nützlich, wenn Ihr PDF-Dokument automatisch an die Größe des Anzeigefensters angepasst werden soll. Aspose.PDF für .NET bietet viele weitere leistungsstarke Funktionen zum Generieren und Bearbeiten von PDF-Dateien. Ich ermutige Sie, diese Bibliothek weiter zu erkunden, um alle ihre Möglichkeiten zu entdecken.