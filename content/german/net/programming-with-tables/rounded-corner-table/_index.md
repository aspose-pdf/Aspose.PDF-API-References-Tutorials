---
title: Tisch mit abgerundeten Ecken im PDF-Dokument
linktitle: Tisch mit abgerundeten Ecken im PDF-Dokument
second_title: Aspose.PDF für .NET API-Referenz
description: Erfahren Sie, wie Sie mit Aspose.PDF für .NET eine Tabelle mit abgerundeten Ecken in einem PDF-Dokument erstellen.
type: docs
weight: 190
url: /de/net/programming-with-tables/rounded-corner-table/
---
In diesem Tutorial führen wir Sie Schritt für Schritt durch die Erstellung einer Tabelle mit abgerundeten Ecken in einem PDF-Dokument mit Aspose.PDF für .NET. Wir erklären den bereitgestellten C#-Quellcode und zeigen Ihnen, wie Sie ihn implementieren.

## Schritt 1: Erstellen der Tabelle
Zuerst erstellen wir die Tabelle mit dem folgenden Code:

```csharp
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();
```

## Schritt 2: Einrichtung des Stils mit abgerundeten Ecken
Als Nächstes konfigurieren wir den abgerundeten Eckenstil für die Tabelle:

```csharp
tab1.CornerStyle = Aspose.Pdf.BorderCornerStyle.Round;
```

## Schritt 3: Einrichten der Tabellenränder
Um der Tabelle einen abgerundeten Rahmen zu geben, müssen wir ein BorderInfo-Objekt erstellen und es mit den entsprechenden Parametern konfigurieren:

```csharp
// Erstellen Sie ein GraphInfo-Objekt, um die Rahmenfarbe festzulegen
GraphInfo graph = new GraphInfo();
graph.Color = Aspose.Pdf.Color.Red;

// Erstellen Sie ein leeres BorderInfo-Objekt
BorderInfo bInfo = new BorderInfo(BorderSide.All, graph);

// Stellen Sie den Radius der abgerundeten Kante auf 15 ein
bInfo.RoundedBorderRadius = 15;

// Anwenden von Rahmeninformationen auf die Tabelle
tab1.Border = bInfo;
```

### Beispiel-Quellcode für Rounded Corner Table mit Aspose.PDF für .NET

```csharp
// Der Pfad zum Dokumentverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();

GraphInfo graph = new GraphInfo();
graph.Color = Aspose.Pdf.Color.Red;
// Erstellen Sie ein leeres BorderInfo-Objekt
BorderInfo bInfo = new BorderInfo(BorderSide.All, graph);
// Setzen Sie den Rand runder, mit einem Radius von 15
bInfo.RoundedBorderRadius = 15;
// Stellen Sie den Eckenstil der Tabelle auf „Rund“ ein.
tab1.CornerStyle = Aspose.Pdf.BorderCornerStyle.Round;
// Festlegen der Tabellenrahmeninformationen
tab1.Border = bInfo;
```

## Abschluss
Herzlichen Glückwunsch! Sie haben jetzt gelernt, wie Sie mit Aspose.PDF für .NET eine Tabelle mit abgerundeten Ecken in einem PDF-Dokument erstellen. Diese Schritt-für-Schritt-Anleitung hat Ihnen gezeigt, wie Sie den Stil mit abgerundeten Ecken und den Tabellenrahmen einrichten. Jetzt können Sie dieses Wissen in Ihren eigenen Projekten anwenden.

### FAQs zum Tisch mit abgerundeten Ecken im PDF-Dokument

#### F: Kann ich den Radius der abgerundeten Ecken des Tisches anpassen?

A: Ja, Sie können den Radius der abgerundeten Ecken für die Tabelle anpassen, indem Sie den Wert des`bInfo.RoundedBorderRadius` -Eigenschaft im bereitgestellten C#-Quellcode. Legen Sie einfach den gewünschten Radiuswert (in Punkten) fest, um das gewünschte abgerundete Eckenaussehen zu erzielen.

#### F: Kann ich einzelnen Zellen in der Tabelle abgerundete Ecken zuweisen?

A: Nein, der Stil mit abgerundeten Ecken wird auf die gesamte Tabelle als Ganzes angewendet. Aspose.PDF für .NET bietet derzeit keine integrierte Unterstützung für die Anwendung abgerundeter Ecken auf einzelne Zellen innerhalb der Tabelle.

#### F: Kann ich die Farbe der abgerundeten Ecken ändern?

 A: Ja, Sie können die Farbe der abgerundeten Ecken ändern, indem Sie den Wert des`graph.Color` Eigenschaft im C#-Quellcode. Geben Sie einfach die gewünschte Farbe an, beispielsweise`Aspose.Pdf.Color.Red` oder jede andere gültige Farbdarstellung.

#### F: Ist es möglich, verschiedenen Tabellen im selben PDF-Dokument unterschiedliche Eckenstile (z. B. eckig und abgerundet) zuzuweisen?

A: Ja, es ist möglich, verschiedene Eckenstile auf verschiedene Tabellen im selben PDF-Dokument anzuwenden. Sie können mehrere Tabellen erstellen und deren Eckenstile individuell nach Ihren Anforderungen konfigurieren.

#### F: Kann ich die Dicke des abgerundeten Eckrahmens anpassen?

 A: Ja, Sie können die Dicke der abgerundeten Ecken anpassen, indem Sie die`BorderInfo` Objekteigenschaften im C#-Quellcode. Sie können beispielsweise die`bInfo.Width` Eigenschaft, um die Dicke des Rahmens anzupassen.