---
title: Abgerundeter Ecktisch
linktitle: Abgerundeter Ecktisch
second_title: Aspose.PDF für .NET API-Referenz
description: Erfahren Sie, wie Sie mit Aspose.PDF für .NET eine Tabelle mit abgerundeten Ecken in einem PDF-Dokument erstellen.
type: docs
weight: 190
url: /de/net/programming-with-tables/rounded-corner-table/
---

In diesem Tutorial führen wir Sie Schritt für Schritt durch die Erstellung einer Tabelle mit abgerundeten Ecken in einem PDF-Dokument mit Aspose.PDF für .NET. Wir erklären Ihnen den bereitgestellten C#-Quellcode und zeigen Ihnen, wie Sie ihn implementieren.

## Schritt 1: Erstellen der Tabelle
Zuerst erstellen wir die Tabelle mit dem folgenden Code:

```csharp
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();
```

## Schritt 2: Einrichtung des abgerundeten Eckenstils
Als Nächstes konfigurieren wir den Stil mit abgerundeten Ecken für die Tabelle:

```csharp
tab1.CornerStyle = Aspose.Pdf.BorderCornerStyle.Round;
```

## Schritt 3: Tabellenrahmen einrichten
Um der Tabelle einen Rand mit abgerundeten Ecken zu geben, müssen wir ein BorderInfo-Objekt erstellen und es mit den entsprechenden Parametern konfigurieren:

```csharp
//Erstellen Sie ein GraphInfo-Objekt, um die Rahmenfarbe festzulegen
GraphInfo graph = new GraphInfo();
graph.Color = Aspose.Pdf.Color.Red;

// Erstellen Sie ein leeres BorderInfo-Objekt
BorderInfo bInfo = new BorderInfo(BorderSide.All, graph);

// Stellen Sie den Radius des abgerundeten Randes auf 15 ein
bInfo.RoundedBorderRadius = 15;

// Wenden Sie Randinformationen auf die Tabelle an
tab1.Border = bInfo;
```

### Beispielquellcode für Rounded Corner Table mit Aspose.PDF für .NET

```csharp
// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();

GraphInfo graph = new GraphInfo();
graph.Color = Aspose.Pdf.Color.Red;
// Erstellen Sie ein leeres BorderInfo-Objekt
BorderInfo bInfo = new BorderInfo(BorderSide.All, graph);
// Stellen Sie den Rand auf einen runderen Rand ein, wobei der Rundungsradius 15 beträgt
bInfo.RoundedBorderRadius = 15;
// Stellen Sie den Eckstil der Tabelle auf „Rund“ ein.
tab1.CornerStyle = Aspose.Pdf.BorderCornerStyle.Round;
// Legen Sie die Informationen zum Tabellenrand fest
tab1.Border = bInfo;
```

## Abschluss
Herzlichen Glückwunsch! Sie haben jetzt gelernt, wie Sie mit Aspose.PDF für .NET eine Tabelle mit abgerundeten Ecken in einem PDF-Dokument erstellen. Diese Schritt-für-Schritt-Anleitung zeigte Ihnen, wie Sie den Stil mit abgerundeten Ecken und den Tischrand einrichten. Jetzt können Sie dieses Wissen auf Ihre eigenen Projekte anwenden.