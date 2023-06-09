---
title: Tabelle entfernen
linktitle: Tabelle entfernen
second_title: Aspose.PDF für .NET API-Referenz
description: Erfahren Sie, wie Sie mit Aspose.PDF für .NET eine Tabelle in einem PDF-Dokument entfernen.
type: docs
weight: 160
url: /de/net/programming-with-tables/remove-table/
---

In diesem Tutorial führen wir Sie Schritt für Schritt durch das Entfernen einer Tabelle in einem PDF-Dokument mit Aspose.PDF für .NET. Wir erklären Ihnen den bereitgestellten C#-Quellcode und zeigen Ihnen, wie Sie ihn implementieren.

## Schritt 1: Laden des vorhandenen PDF-Dokuments
Zuerst müssen Sie das vorhandene PDF-Dokument mit dem folgenden Code laden:

```csharp
// Pfad zum Dokumentenverzeichnis
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Laden Sie das vorhandene PDF-Dokument
Document pdfDocument = new Document(dataDir + "Table_input.pdf");
```

## Schritt 2: Erstellen des TableAbsorber-Objekts zum Suchen der Tabellen
Als Nächstes erstellen wir ein TableAbsorber-Objekt, um die Tabellen im PDF-Dokument zu finden:

```csharp
// Erstellen Sie ein TableAbsorber-Objekt, um die Tabellen zu finden
TableAbsorber absorber = new TableAbsorber();
```

## Schritt 3: Besuchen Sie die erste Seite mit dem Absorber
Wir besuchen nun die erste Seite des PDF-Dokuments mit dem Absorber:

```csharp
// Besuchen Sie die erste Seite mit dem Absorber
absorb.Visit(pdfDocument.Pages[1]);
```

## Schritt 4: Erste Tabelle auf der Seite erstellen
Um die Tabelle entfernen zu können, erhalten wir die erste Tabelle der Seite:

```csharp
// Holen Sie sich die erste Tabelle auf der Seite
AbsorbedTable table = absorb.TableList[0];
```

## Schritt 5: Tabelle löschen
Jetzt entfernen wir den Tisch mit dem Absorber:

```csharp
//Entfernen Sie den Tisch
absorb.Remove(table);
```

## Schritt 6: PDF speichern
Abschließend speichern wir das geänderte PDF-Dokument:

```csharp
// Speichern Sie das PDF
pdfDocument.Save(dataDir + "Table_out.pdf");
```

### Beispielquellcode für Remove Table mit Aspose.PDF für .NET

```csharp
// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Vorhandenes PDF-Dokument laden
Document pdfDocument = new Document(dataDir + "Table_input.pdf");

// Erstellen Sie ein TableAbsorber-Objekt, um Tabellen zu finden
TableAbsorber absorber = new TableAbsorber();

// Besuchen Sie die erste Seite mit Absorber
absorber.Visit(pdfDocument.Pages[1]);

// Holen Sie sich die erste Tabelle auf der Seite
AbsorbedTable table = absorber.TableList[0];

// Entfernen Sie den Tisch
absorber.Remove(table);

// PDF speichern
pdfDocument.Save(dataDir + "Table_out.pdf");
```

## Abschluss
Herzlichen Glückwunsch! Sie haben jetzt erfahren, wie Sie mit Aspose.PDF für .NET eine Tabelle in einem PDF-Dokument entfernen. Diese Schritt-für-Schritt-Anleitung zeigte Ihnen, wie Sie das Dokument laden, die Tabelle finden und entfernen. Jetzt können Sie dieses Wissen auf Ihre eigenen Projekte anwenden.