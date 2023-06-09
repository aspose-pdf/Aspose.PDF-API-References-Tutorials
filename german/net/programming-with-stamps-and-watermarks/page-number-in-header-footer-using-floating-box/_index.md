---
title: Seitenzahl in der Kopf- und Fußzeile mithilfe eines Schweberahmens
linktitle: Seitenzahl in der Kopf- und Fußzeile mithilfe eines Schweberahmens
second_title: Aspose.PDF für .NET API-Referenz
description: Erfahren Sie, wie Sie mit Aspose.PDF für .NET die Seitenzahl in die Kopf- und Fußzeile eines PDF-Dokuments einfügen.
type: docs
weight: 150
url: /de/net/programming-with-stamps-and-watermarks/page-number-in-header-footer-using-floating-box/
---
In diesem Tutorial führen wir Sie Schritt für Schritt durch das Hinzufügen von Seitenzahlen in der Kopf- und Fußzeile eines PDF-Dokuments mithilfe von FloatingBox mit Aspose.PDF für .NET. Wir werden den bereitgestellten C#-Quellcode verwenden, um ein PDF-Dokument zu erstellen, eine Seite hinzuzufügen, eine FloatingBox zu erstellen, ihre Position festzulegen und die Seitenzahl hinzuzufügen, und dann das geänderte PDF-Dokument zu speichern.

## Schritt 1: Einrichten der Umgebung

Bevor Sie beginnen, stellen Sie sicher, dass Sie über Folgendes verfügen:

- Eine installierte .NET-Entwicklungsumgebung.
- Die Aspose.PDF-Bibliothek für .NET wurde heruntergeladen und in Ihrem Projekt referenziert.

## Schritt 2: Erstellen des PDF-Dokuments und Hinzufügen einer Seite

Der erste Schritt besteht darin, eine Instanz des PDF-Dokuments zu erstellen und ihm eine Seite hinzuzufügen. Hier ist wie:

```csharp
// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Instanziieren Sie das PDF-Dokument
Aspose.Pdf.Document pdf = new Aspose.Pdf.Document();

// Fügen Sie dem PDF-Dokument eine Seite hinzu
Aspose.Pdf.Page page = pdf.Pages.Add();
```

Ersetzen Sie unbedingt „VERZEICHNIS IHRER DOKUMENTE“ durch den tatsächlichen Pfad zu dem Verzeichnis, in dem Sie das PDF-Dokument speichern möchten.

## Schritt 3: Erstellen der FloatingBox und Hinzufügen der Seitenzahl

Nachdem die Seite nun zum PDF-Dokument hinzugefügt wurde, können wir eine FloatingBox erstellen, ihre Position festlegen und ihr die Seitenzahl hinzufügen. Hier ist wie:

```csharp
// Erstellen Sie eine FloatingBox mit einer Breite von 140 und einer Höhe von 80
Aspose.Pdf.FloatingBox box1 = new Aspose.Pdf.FloatingBox(140, 80);

// Legen Sie die linke Position des Absatzes fest
box1. Left = 2;

// Legen Sie die oberste Position des Absatzes fest
box1. Top = 10;

// Fügen Sie die Seitenzahl zur FloatingBox hinzu
box1.Paragraphs.Add(new Aspose.Pdf.Text.TextFragment("Page: ($p/ $P )"));

// Fügen Sie die FloatingBox zur Seite hinzu
page.Paragraphs.Add(box1);
```

Der obige Code erstellt eine FloatingBox mit einer Breite von 140 und einer Höhe von 80. Als Nächstes legen wir ihre Position fest, indem wir die linken und oberen Werte angeben. Schließlich fügen wir der FloatingBox die Seitenzahl hinzu, indem wir ein TextFragment mit der Syntax „($p/ $P )“ verwenden, das durch die aktuelle Seitenzahl und die Gesamtzahl der Seiten ersetzt wird.

## Schritt 4: Speichern des geänderten PDF-Dokuments

Sobald die Seitenzahl mithilfe der FloatingBox zur Kopf- oder Fußzeile hinzugefügt wurde, können wir das geänderte PDF-Dokument speichern. Hier ist wie:

```csharp
// Speichern Sie das geänderte PDF-Dokument
pdf.Save(dataDir + "PageNumberinHeaderFooterUsingFloatingBox_out.pdf");
```

Der obige Code speichert das bearbeitete PDF-Dokument im angegebenen Verzeichnis.

### Beispielquellcode für Seitennummerierung in Kopf- und Fußzeile mit Floating Box unter Verwendung von Aspose.PDF für .NET 
```csharp

// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Dokumentinstanz instanziieren
Aspose.Pdf.Document pdf = new Aspose.Pdf.Document();

// Fügen Sie dem PDF-Dokument eine Seite hinzu
Aspose.Pdf.Page page = pdf.Pages.Add();

// Initialisiert eine neue Instanz der FloatingBox-Klasse
Aspose.Pdf.FloatingBox box1 = new Aspose.Pdf.FloatingBox(140, 80);

// Float-Wert, der die linke Position des Absatzes angibt
box1.Left = 2;

// Float-Wert, der die oberste Position des Absatzes angibt
box1.Top = 10;

// Fügen Sie die Makros zur Absatzsammlung der FloatingBox hinzu
box1.Paragraphs.Add(new Aspose.Pdf.Text.TextFragment("Page: ($p/ $P )"));

// Fügen Sie der Seite eine FloatingBox hinzu
page.Paragraphs.Add(box1);

// Speichern Sie das Dokument
pdf.Save(dataDir + "PageNumberinHeaderFooterUsingFloatingBox_out.pdf");

```

## Abschluss

Herzlichen Glückwunsch! Sie haben gelernt, wie Sie mithilfe von FloatingBox mit Aspose.PDF für .NET Seitenzahlen in die Kopf- und Fußzeile eines PDF-Dokuments einfügen. Sie können Ihre Kopf- und Fußzeilen jetzt anpassen, indem Sie dynamische Informationen wie die Seitenzahl hinzufügen.
