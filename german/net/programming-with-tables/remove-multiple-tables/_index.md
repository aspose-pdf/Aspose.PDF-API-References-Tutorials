---
title: Mehrere Tabellen entfernen
linktitle: Mehrere Tabellen entfernen
second_title: Aspose.PDF für .NET API-Referenz
description: Erfahren Sie, wie Sie mit Aspose.PDF für .NET mehrere Tabellen in einem PDF-Dokument entfernen.
type: docs
weight: 150
url: /de/net/programming-with-tables/remove-multiple-tables/
---

In diesem Tutorial führen wir Sie Schritt für Schritt durch das Entfernen mehrerer Tabellen in einem PDF-Dokument mit Aspose.PDF für .NET. Wir erklären Ihnen den bereitgestellten C#-Quellcode und zeigen Ihnen, wie Sie ihn implementieren.

## Schritt 1: Laden des vorhandenen PDF-Dokuments
Zuerst müssen Sie das vorhandene PDF-Dokument mit dem folgenden Code laden:

```csharp
// Pfad zum Dokumentenverzeichnis
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Laden Sie das vorhandene PDF-Dokument
Document pdfDocument = new Document(dataDir + "Table_input2.pdf");
```

## Schritt 2: Erstellen des TableAbsorber-Objekts zum Suchen der Tabellen
Als Nächstes erstellen wir ein TableAbsorber-Objekt, um die Tabellen im PDF-Dokument zu finden:

```csharp
// Erstellen Sie ein TableAbsorber-Objekt, um die Tabellen zu finden
TableAbsorber absorber = new TableAbsorber();
```

## Schritt 3: Besuchen Sie die zweite Seite mit dem Absorber
Wir besuchen nun die zweite Seite des PDF-Dokuments mit dem Absorber:

```csharp
// Besuchen Sie die zweite Seite mit dem Absorber
absorb.Visit(pdfDocument.Pages[1]);
```

## Schritt 4: Erhalten einer Kopie der Tabellensammlung
Um die Tabellen löschen zu können, benötigen wir eine Kopie der Tabellensammlung:

```csharp
// Holen Sie sich eine Kopie der Tabellensammlung
AbsorbedTable[] tables = new AbsorbedTable[absorb.TableList.Count];
absorb.TableList.CopyTo(tables, 0);
```

## Schritt 5: Durchsuchen Sie die Kopie der Sammlung und entfernen Sie die Tabellen
Lassen Sie uns nun die Kopie der Tabellensammlung durchlaufen und sie nacheinander entfernen:

```csharp
// Durchsuchen Sie die Kopie der Sammlung und entfernen Sie die Tabellen
foreach(AbsorbedTable table in tables)
     absorb.Remove(table);
```

## Schritt 6: Speichern des Dokuments
Abschließend speichern wir das geänderte PDF-Dokument:

```csharp
// Speichern Sie das Dokument
pdfDocument.Save(dataDir + "Table2_out.pdf");
```

### Beispielquellcode zum Entfernen mehrerer Tabellen mit Aspose.Words für .NET

```csharp
// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Vorhandenes PDF-Dokument laden
Document pdfDocument = new Document(dataDir + "Table_input2.pdf");

// Erstellen Sie ein TableAbsorber-Objekt, um Tabellen zu finden
TableAbsorber absorber = new TableAbsorber();

// Besuchen Sie die zweite Seite mit Absorber
absorber.Visit(pdfDocument.Pages[1]);

// Holen Sie sich eine Kopie der Tabellensammlung
AbsorbedTable[] tables = new AbsorbedTable[absorber.TableList.Count];
absorber.TableList.CopyTo(tables, 0);

// Durchlaufen Sie die Kopie der Sammlung und entfernen Sie Tabellen
foreach (AbsorbedTable table in tables)
	absorber.Remove(table);

// Dokument speichern
pdfDocument.Save(dataDir + "Table2_out.pdf");
```

## Abschluss
Herzlichen Glückwunsch! Sie haben jetzt gelernt, wie Sie mit Aspose.PDF für .NET mehrere Tabellen in einem PDF-Dokument entfernen. Diese Schritt-für-Schritt-Anleitung zeigte Ihnen, wie Sie das Dokument hochladen, die Tabellen finden und entfernen. Jetzt können Sie dieses Wissen auf Ihre eigenen Projekte anwenden.