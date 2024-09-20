---
title: Automatisch an Fenster anpassen
linktitle: Automatisch an Fenster anpassen
second_title: Aspose.PDF für .NET API-Referenz
description: In dieser ausführlichen Schritt-für-Schritt-Anleitung erfahren Sie, wie Sie mit Aspose.PDF für .NET eine Tabelle automatisch an das Fenster anpassen. Perfekt zum Erstellen eleganter und gut angepasster Tabellen in PDFs.
type: docs
weight: 50
url: /de/net/programming-with-tables/auto-fit-to-window/
---
## Einführung

Beim Arbeiten mit PDFs hat man häufig mit Tabellen zu tun, und manchmal müssen diese Tabellen perfekt in die Breite einer Seite passen. In diesem Tutorial erfahren Sie, wie Sie mit Aspose.PDF für .NET eine Tabelle automatisch an ein Fenster anpassen. Dadurch können Ihre Tabellen elegant und übersichtlich aussehen und Probleme wie überlaufende oder ungleichmäßige Spalten werden vermieden. Bereit zu lernen? Dann legen wir los!

## Voraussetzungen

Bevor wir mit der Schritt-für-Schritt-Anleitung beginnen, benötigen Sie einige Dinge:

1. Aspose.PDF für .NET in Ihrem Projekt installiert. Wenn Sie es noch nicht haben, können Sie[Laden Sie es hier herunter](https://releases.aspose.com/pdf/net/) oder erkunden Sie ihre[kostenlose Testversion](https://releases.aspose.com/).
2. Grundlegende Kenntnisse der .NET-Programmierung.
3. Visual Studio oder eine beliebige .NET-unterstützte IDE, die auf Ihrem System installiert ist.

>  PS Vergessen Sie nicht, dass Sie eine Lizenz benötigen, um Aspose.PDF uneingeschränkt nutzen zu können. Sie können entweder eine kaufen[Hier](https://purchase.aspose.com/buy) oder erhalten Sie eine[vorläufige Lizenz](https://purchase.aspose.com/temporary-license/) um alle Funktionen auszuprobieren.

## Pakete importieren

Bevor Sie in den Code eintauchen, müssen Sie die erforderlichen Namespaces importieren:

```csharp
using System.IO;
using System;
using Aspose.Pdf;
```

Jetzt, da wir alles vorbereitet haben, wollen wir die Sache in einfache, leicht verständliche Schritte aufteilen, um zu verstehen, wie Sie mit Aspose.PDF für .NET eine Tabelle automatisch an ein Fenster anpassen können.

## Schritt 1: Initialisieren Sie das Dokumentobjekt

Zuerst müssen Sie ein PDF-Dokument erstellen. Stellen Sie sich dieses Dokument als leeres Blatt vor, in das Sie Seiten und Tabellen einfügen.

```csharp
// Der Pfad zum Dokumentverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Instanziieren Sie das PDF-Objekt, indem Sie seinen leeren Konstruktor aufrufen
Document doc = new Document();
```
  
 Hier erstellen wir ein neues Dokument mit dem`Document` Klasse von Aspose.PDF. Die`dataDir` ist der Speicherort, an dem Ihre PDF-Datei gespeichert wird, wenn Sie fertig sind.

## Schritt 2: Dem Dokument eine Seite hinzufügen

Ein PDF-Dokument braucht Seiten, oder? Fügen wir eine hinzu.

```csharp
// Erstellen Sie einen Abschnitt (Seite) im PDF-Objekt
Page sec1 = doc.Pages.Add();
```
  
 Wir haben dem Dokument eine neue Seite hinzugefügt, indem wir den`Pages.Add()` Methode. Sie können sich das so vorstellen, als ob Sie Ihrem Dokument ein neues Blatt hinzufügen, in das Sie die Tabelle einfügen.

## Schritt 3: Erstellen und Konfigurieren einer Tabelle

Jetzt ist es an der Zeit, eine Tabelle zu erstellen und sie so anzupassen, dass sie in das Fenster passt.

```csharp
// Instanziieren eines Tabellenobjekts
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();
// Fügen Sie die Tabelle in die Absatzsammlung des gewünschten Abschnitts ein
sec1.Paragraphs.Add(tab1);
```
  
 Wir initialisierten ein neues`Table` Objekt und fügte es der Absatzsammlung der Seite hinzu. Jede PDF-Seite kann unterschiedliche Absätze haben, und hier behandeln wir die Tabelle als einen Absatz.

## Schritt 4: Spaltenbreiten definieren und automatisch an Fenster anpassen

Als nächstes stellen wir die Spaltenbreiten ein und sorgen dafür, dass sich die Tabelle an die Fenstergröße anpasst.

```csharp
// Spaltenbreiten für die Tabelle festlegen
tab1.ColumnWidths = "50 50 50";
tab1.ColumnAdjustment = ColumnAdjustment.AutoFitToWindow;
```
  
 Wir haben feste Spaltenbreiten für die Tabelle festgelegt, aber auch`ColumnAdjustment.AutoFitToWindow`, das dafür sorgt, dass die Tabelle ihre Größe dem zur Verfügung stehenden Fenster anpasst.

## Schritt 5: Rahmen und Ränder für Tabelle und Zellen festlegen

Tabellen ohne Rahmen sind oft unleserlich. Damit die Tabellen ordentlich aussehen, definieren wir Rahmen und Ränder.

```csharp
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
```
  
 Rahmen werden sowohl der Tabelle als auch den Zellen hinzugefügt mit dem`BorderInfo` Klasse, in der Sie die Dicke definieren. Ränder werden so festgelegt, dass den Zellen etwas Platz zum Auffüllen bleibt.

## Schritt 6: Zeilen und Zellen zur Tabelle hinzufügen

Eine Tabelle ohne Inhalt? Das ist nicht gut! Fügen wir einige Zeilen und Zellen hinzu.

```csharp
//Erstellen Sie Zeilen in der Tabelle und dann Zellen in den Zeilen
Aspose.Pdf.Row row1 = tab1.Rows.Add();
row1.Cells.Add("col1");
row1.Cells.Add("col2");
row1.Cells.Add("col3");

Aspose.Pdf.Row row2 = tab1.Rows.Add();
row2.Cells.Add("item1");
row2.Cells.Add("item2");
row2.Cells.Add("item3");
```
  
Wir erstellen zwei Zeilen und fügen jeder Zeile drei Zellen hinzu. Hier geben Sie Ihre eigentlichen Daten ein (das können alles sein, von Zeichenfolgen bis hin zu komplexeren Elementen).

## Schritt 7: Speichern Sie das Dokument

Sobald alles eingestellt ist, möchten Sie Ihr neu erstelltes PDF-Dokument speichern.

```csharp
dataDir = dataDir + "AutoFitToWindow_out.pdf";
// Aktualisiertes Dokument mit Tabellenobjekt speichern
doc.Save(dataDir);
```
  
 Der`doc.Save()` Methode speichert das PDF im angegebenen Verzeichnis. In diesem Fall wird das Dokument gespeichert als`AutoFitToWindow_out.pdf` in Ihrem definierten Verzeichnis.

## Abschluss

Und da haben Sie es! Sie haben gerade eine Tabelle erstellt, die mit Aspose.PDF für .NET automatisch in das Fenster passt. Dies stellt nicht nur sicher, dass Ihre Tabelle professionell und gut angepasst aussieht, sondern gibt Ihnen auch Flexibilität beim Arbeiten mit unterschiedlichen Datengrößen. Egal, ob Sie Berichte, Rechnungen oder andere Dokumente erstellen, die Tabellen erfordern, diese Methode ist eine großartige Möglichkeit, saubere und lesbare Layouts beizubehalten.

## Häufig gestellte Fragen

### Kann ich dynamisch weitere Zeilen hinzufügen?  
 Ja, Sie können weiterhin Zeilen hinzufügen, indem Sie`tab1.Rows.Add()` Methode, dynamisch basierend auf dem Inhalt.

### Wie passe ich die Tabelle an, wenn ich keine automatische Anpassung möchte?  
 Sie können die`ColumnWidths` ohne Verwendung`ColumnAdjustment.AutoFitToWindow` um eine feste Tabellenbreite beizubehalten.

### Kann ich in die Zellen Bilder oder andere Inhalte einfügen?  
Ja, mit Aspose.PDF können Sie Bilder, Text und sogar andere Tabellen in Zellen einfügen!

### Was ist, wenn ich komplexere Tabellenstile benötige?  
Sie können die Tabellen- und Zellenstile mithilfe von Eigenschaften wie Hintergrundfarbe, Textausrichtung und Schriftarteinstellungen weiter anpassen.

### Ist es möglich, diese Tabelle in andere Formate als PDF zu exportieren?  
Absolut! Aspose.PDF unterstützt den Export in verschiedene Formate wie HTML, DOCX und mehr.