---
title: Automatisch an Fenster anpassen
linktitle: Automatisch an Fenster anpassen
second_title: Aspose.PDF für .NET API-Referenz
description: Schritt-für-Schritt-Anleitung zur Verwendung von Aspose.PDF für .NET und zur automatischen Fensteranpassung bei der PDF-Generierung.
type: docs
weight: 50
url: /de/net/programming-with-tables/auto-fit-to-window/
---
Der folgende Artikel ist eine Schritt-für-Schritt-Anleitung zur Verwendung des bereitgestellten C#-Quellcodes, um die Funktion „Automatisch an Fenster anpassen“ mithilfe der Aspose.PDF-Bibliothek für .NET zu erreichen. Mit der Funktion „Automatisch an Fenster anpassen“ können Sie PDF-Dateien mit einem an das Anzeigefenster angepassten Layout erstellen. Diese Funktion ist besonders nützlich, wenn Sie möchten, dass sich Ihr PDF-Dokument automatisch an die Größe des vom Benutzer verwendeten PDF-Reader-Fensters anpasst.

## Schritt 1: Einrichten der Umgebung

Bevor Sie beginnen, müssen Sie die Aspose.PDF-Bibliothek für .NET auf Ihrem Computer installieren. Stellen Sie außerdem sicher, dass Sie die erforderlichen Namespaces in Ihr Projekt importieren.

```csharp
// Der Pfad zum Dokumentverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Schritt 2: Erstellen eines PDF-Dokuments

 Um zu beginnen, müssen Sie eine`Document` -Objekt, indem Sie seinen Standardkonstruktor aufrufen.

```csharp
Document doc = new Document();
```

 Erstellen Sie als nächstes einen Abschnitt im`Pdf` Objekt.

```csharp
Page sec1 = doc.Pages.Add();
```

## Schritt 3: Dem Dokument eine Tabelle hinzufügen

 In diesem Schritt fügen wir unserem PDF-Dokument eine Tabelle hinzu. Erstellen Sie zunächst eine`Table` Objekt.

```csharp
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();
```

Fügen Sie als Nächstes die Tabelle zur Absatzsammlung des Abschnitts hinzu.

```csharp
sec1.Paragraphs.Add(tab1);
```

##  Schritt 4: Anpassen des Tabellenaussehens

Sie können das Erscheinungsbild der Tabelle anpassen, indem Sie Eigenschaften wie Zellenränder und Ränder festlegen.

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

Fügen wir nun unserer Tabelle Zeilen und Zellen hinzu. Beginnen Sie mit dem Erstellen einer Zeile und dem Hinzufügen von Zellen zu dieser Zeile.

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

Geben Sie abschließend den Ausgabedateipfad an und speichern Sie das Dokument.

```csharp
dataDir = dataDir + "AutoFitToWindow_out.pdf";
doc.Save(dataDir);
```

### Beispielquellcode für Auto Fit To Window mit Aspose.PDF für .NET

```csharp
// Der Pfad zum Dokumentverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Instanziieren Sie das PDF-Objekt, indem Sie seinen leeren Konstruktor aufrufen
Document doc = new Document();
// Erstellen Sie den Abschnitt im PDF-Objekt
Page sec1 = doc.Pages.Add();

// Instanziieren eines Tabellenobjekts
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();
// Fügen Sie die Tabelle in die Absatzsammlung des gewünschten Abschnitts ein
sec1.Paragraphs.Add(tab1);

// Mit Spaltenbreiten der Tabelle festlegen
tab1.ColumnWidths = "50 50 50";
tab1.ColumnAdjustment = ColumnAdjustment.AutoFitToWindow;

// Festlegen des Standardzellenrahmens mithilfe des BorderInfo-Objekts
tab1.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.1F);

// Festlegen des Tabellenrahmens mithilfe eines anderen benutzerdefinierten BorderInfo-Objekts
tab1.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 1F);
// Erstellen Sie ein MarginInfo-Objekt und legen Sie dessen linken, unteren, rechten und oberen Rand fest.
Aspose.Pdf.MarginInfo margin = new Aspose.Pdf.MarginInfo();
margin.Top = 5f;
margin.Left = 5f;
margin.Right = 5f;
margin.Bottom = 5f;

// Festlegen der Standardzellenpolsterung auf das MarginInfo-Objekt
tab1.DefaultCellPadding = margin;

//Erstellen Sie Zeilen in der Tabelle und dann Zellen in den Zeilen
Aspose.Pdf.Row row1 = tab1.Rows.Add();
row1.Cells.Add("col1");
row1.Cells.Add("col2");
row1.Cells.Add("col3");
Aspose.Pdf.Row row2 = tab1.Rows.Add();
row2.Cells.Add("item1");
row2.Cells.Add("item2");
row2.Cells.Add("item3");

dataDir = dataDir + "AutoFitToWindow_out.pdf";
// Aktualisiertes Dokument mit Tabellenobjekt speichern
doc.Save(dataDir);
```

## Abschluss

In diesem Tutorial haben wir gelernt, wie man mit Aspose.PDF für .NET eine PDF-Datei mit der Funktion „Automatisch an Fenster anpassen“ generiert. Diese Funktion ist äußerst nützlich, wenn Sie möchten, dass Ihr PDF-Dokument automatisch an die Größe des Anzeigefensters angepasst wird. Aspose.PDF für .NET bietet viele weitere leistungsstarke Funktionen zum Generieren und Bearbeiten von PDF-Dateien. Ich empfehle Ihnen, diese Bibliothek weiter zu erkunden, um alle ihre Funktionen zu entdecken.

### Häufig gestellte Fragen

#### F: Was ist der Zweck der Funktion „Automatisch an Fenster anpassen“ bei der PDF-Generierung?

A: Die Funktion „Automatisch an Fenster anpassen“ bei der PDF-Generierung sorgt dafür, dass sich das Layout des PDF-Dokuments automatisch an die Größe des vom Benutzer verwendeten PDF-Reader-Fensters anpasst. Dies ermöglicht eine bessere Anzeige und stellt sicher, dass der Inhalt perfekt in den verfügbaren Anzeigebereich passt.

#### F: Kann ich das Erscheinungsbild der Tabelle, beispielsweise Schriftgröße und Farben, anpassen?

A: Ja, Sie können das Erscheinungsbild der Tabelle im PDF-Dokument mit Aspose.PDF für .NET anpassen. Der bereitgestellte Codeausschnitt zeigt, wie Sie Eigenschaften wie Zellränder, Ränder und Spaltenbreiten festlegen. Sie können außerdem die Schriftgröße, Farben und andere Gestaltungsaspekte der Tabelle und ihres Inhalts anpassen.

#### F: Wie integriere ich Aspose.PDF für .NET in mein C#-Projekt?

A: Um Aspose.PDF für .NET in Ihrem C#-Projekt zu verwenden, müssen Sie zuerst die Aspose.PDF-Bibliothek für .NET auf Ihrem Computer installieren. Anschließend können Sie in Ihrem C#-Projekt einen Verweis auf die Bibliothek hinzufügen. Importieren Sie abschließend die erforderlichen Namespaces, um auf die von Aspose.PDF für .NET bereitgestellten Klassen und Methoden zuzugreifen.

#### F: Ist Aspose.PDF für .NET mit .NET Core-Anwendungen kompatibel?

A: Ja, Aspose.PDF für .NET ist mit .NET Core-Anwendungen kompatibel. Es unterstützt verschiedene .NET-Plattformen, darunter .NET Framework, .NET Core und .NET 5.0+.

#### F: Kann ich dem PDF-Dokument weitere Tabellen hinzufügen?

A: Ja, Sie können einem PDF-Dokument mehrere Tabellen hinzufügen, indem Sie die gleichen Schritte wie im Codeausschnitt beschrieben durchführen. Erstellen Sie einfach neue Instanzen der`Aspose.Pdf.Table` Klasse und fügen Sie sie verschiedenen Abschnitten oder Seiten des PDF-Dokuments hinzu.