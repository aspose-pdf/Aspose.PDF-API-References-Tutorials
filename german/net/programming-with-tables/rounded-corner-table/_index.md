---
title: Abgerundeter Ecktisch im PDF-Dokument
linktitle: Abgerundeter Ecktisch im PDF-Dokument
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
// Erstellen Sie ein GraphInfo-Objekt, um die Rahmenfarbe festzulegen
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

### FAQs zum Tisch mit abgerundeten Ecken im PDF-Dokument

#### F: Kann ich den Radius der abgerundeten Ecken für den Tisch anpassen?

A: Ja, Sie können den Radius der abgerundeten Ecken für den Tisch anpassen, indem Sie den Wert ändern`bInfo.RoundedBorderRadius` -Eigenschaft im bereitgestellten C#-Quellcode. Stellen Sie einfach den gewünschten Radiuswert (in Punkten) ein, um das gewünschte Erscheinungsbild abgerundeter Ecken zu erzielen.

#### F: Kann ich abgerundete Ecken auf einzelne Zellen in der Tabelle anwenden?

A: Nein, der Stil mit abgerundeten Ecken wird auf die gesamte Tabelle angewendet. Aspose.PDF für .NET bietet derzeit keine integrierte Unterstützung für die Anwendung abgerundeter Ecken auf einzelne Zellen in der Tabelle.

#### F: Kann ich die Farbe des Randes mit abgerundeten Ecken ändern?

 A: Ja, Sie können die Farbe des abgerundeten Eckrahmens ändern, indem Sie den Wert von ändern`graph.Color` Eigenschaft im C#-Quellcode. Geben Sie einfach die gewünschte Farbe an, z`Aspose.Pdf.Color.Red` oder eine andere gültige Farbdarstellung.

#### F: Ist es möglich, verschiedene Eckenstile (z. B. quadratisch und abgerundet) auf verschiedene Tabellen innerhalb desselben PDF-Dokuments anzuwenden?

A: Ja, es ist möglich, unterschiedliche Eckenstile auf verschiedene Tabellen innerhalb desselben PDF-Dokuments anzuwenden. Sie können mehrere Tische erstellen und deren Eckstile individuell nach Ihren Anforderungen konfigurieren.

#### F: Kann ich die Dicke des Randes mit abgerundeten Ecken anpassen?

 A: Ja, Sie können die Dicke des Randes mit abgerundeten Ecken anpassen, indem Sie die ändern`BorderInfo` Objekteigenschaften im C#-Quellcode. Sie können beispielsweise Folgendes festlegen:`bInfo.Width` Eigenschaft, um die Dicke des Rahmens anzupassen.