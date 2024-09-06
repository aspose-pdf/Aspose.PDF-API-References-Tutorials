---
title: Lokalen Hyperlink in PDF-Datei erstellen
linktitle: Lokalen Hyperlink in PDF-Datei erstellen
second_title: Aspose.PDF für .NET API-Referenz
description: Erstellen Sie mit Aspose.PDF für .NET ganz einfach lokale Hyperlinks in PDF-Dateien.
type: docs
weight: 40
url: /de/net/programming-with-links-and-actions/create-local-hyperlink/
---
Durch das Erstellen lokaler Hyperlinks in PDF-Dateien können Sie anklickbare Links erstellen, die Benutzer zu anderen Seiten im selben PDF-Dokument führen. Mit Aspose.PDF für .NET können Sie solche Links ganz einfach erstellen, indem Sie dem folgenden Quellcode folgen:

## Schritt 1: Erforderliche Bibliotheken importieren

Bevor Sie beginnen, müssen Sie die erforderlichen Bibliotheken für Ihr C#-Projekt importieren. Hier ist die erforderliche Importanweisung:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
using Aspose.Pdf.InteractiveFeatures;
```

## Schritt 2: Pfad zum Dokumentenordner festlegen

 In diesem Schritt müssen Sie den Pfad zu dem Ordner angeben, in dem Sie die resultierende PDF-Datei speichern möchten. Ersetzen Sie`"YOUR DOCUMENT DIRECTORY"` ersetzen Sie den folgenden Code durch den tatsächlichen Pfad zu Ihrem Dokumentordner:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Schritt 3: Erstellen Sie eine Instanz von Document

 Wir erstellen eine Instanz des`Document` Klasse zur Darstellung unseres PDF-Dokuments. Hier ist der entsprechende Code:

```csharp
Document doc = new Document();
```

## Schritt 4: Seite und Text mit Hyperlinks hinzufügen

In diesem Schritt fügen wir unserem PDF-Dokument eine Seite hinzu und fügen einen Text mit lokalen Hyperlinks hinzu. Wir definieren die Zielseiten für jeden Link. Hier ist der entsprechende Code:

```csharp
Page page = doc.Pages.Add();

TextFragment text = new TextFragment("Link to page 7");
LocalHyperlink link = new LocalHyperlink();
link.TargetPageNumber = 7;
text. Hyperlink = link;
page.Paragraphs.Add(text);

text = new TextFragment("Link to page 1");
text. IsInNewPage = true;
link = new LocalHyperlink();
link.TargetPageNumber = 1;
text. Hyperlink = link;
page.Paragraphs.Add(text);
```

## Schritt 5: Speichern Sie das aktualisierte Dokument

Speichern wir nun die aktualisierte PDF-Datei mit dem`Save` Methode der`doc` Objekt. Hier ist der entsprechende Code:

```csharp
dataDir = dataDir + "CreateLocalHyperlink_out.pdf";
doc.Save(dataDir);
```

### Beispielquellcode zum Erstellen eines lokalen Hyperlinks mit Aspose.PDF für .NET 
```csharp
// Der Pfad zum Dokumentverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Dokumentinstanz erstellen
Document doc = new Document();
// Seite zur Seitensammlung der PDF-Datei hinzufügen
Page page = doc.Pages.Add();
// Textfragmentinstanz erstellen
Aspose.Pdf.Text.TextFragment text = new Aspose.Pdf.Text.TextFragment("link page number test to page 7");
// Lokale Hyperlink-Instanz erstellen
Aspose.Pdf.LocalHyperlink link = new Aspose.Pdf.LocalHyperlink();
// Zielseite für Linkinstanz festlegen
link.TargetPageNumber = 7;
// TextFragment-Hyperlink festlegen
text.Hyperlink = link;
// Text zur Absatzsammlung der Seite hinzufügen
page.Paragraphs.Add(text);
// Neue TextFragment-Instanz erstellen
text = new TextFragment("link page number test to page 1");
// TextFragment sollte über der neuen Seite hinzugefügt werden
text.IsInNewPage = true;
// Erstellen einer weiteren lokalen Hyperlinkinstanz
link = new LocalHyperlink();
// Zielseite für zweiten Hyperlink festlegen
link.TargetPageNumber = 1;
// Link für zweites TextFragment festlegen
text.Hyperlink = link;
// Text zur Absatzsammlung des Seitenobjekts hinzufügen
page.Paragraphs.Add(text);    
dataDir = dataDir + "CreateLocalHyperlink_out.pdf";
// Aktualisiertes Dokument speichern
doc.Save(dataDir);
Console.WriteLine("\nLocal hyperlink created successfully.\nFile saved at " + dataDir);            
```

## Abschluss

Herzlichen Glückwunsch! Jetzt haben Sie eine Schritt-für-Schritt-Anleitung zum Erstellen lokaler Hyperlinks in einer PDF-Datei mit Aspose.PDF für .NET. Mit diesem Code können Sie anklickbare Links erstellen, die Benutzer zu anderen Seiten im selben Dokument führen.

Weitere Informationen zu erweiterten Hyperlink-Funktionen finden Sie in der offiziellen Aspose.PDF-Dokumentation.

### FAQs zum Erstellen eines lokalen Hyperlinks in einer PDF-Datei

#### F: Was sind lokale Hyperlinks in einer PDF-Datei?

A: Lokale Hyperlinks in einer PDF-Datei sind anklickbare Links, die Benutzer zu verschiedenen Seiten innerhalb desselben Dokuments führen. Diese Links verbessern die Navigation und ermöglichen Lesern den schnellen Zugriff auf relevante Abschnitte.

#### F: Welche Vorteile bieten lokale Hyperlinks für mein PDF-Dokument?

A: Lokale Hyperlinks bieten eine effiziente Möglichkeit, verwandte Inhalte innerhalb desselben PDF-Dokuments zu verknüpfen. Sie verbessern die Benutzererfahrung, indem sie es den Lesern ermöglichen, schnell zu bestimmten Abschnitten zu springen, ohne durch das gesamte Dokument scrollen zu müssen.

#### F: Wie unterstützt Aspose.PDF für .NET die Erstellung lokaler Hyperlinks?
A: Aspose.PDF für .NET bietet umfassende Unterstützung zum Erstellen lokaler Hyperlinks. Das in diesem Handbuch enthaltene Schritt-für-Schritt-Tutorial zeigt, wie Sie mit C# lokale Hyperlinks zu Ihrem PDF-Dokument hinzufügen.

#### F: Kann ich das Erscheinungsbild lokaler Hyperlinks anpassen?

A: Ja, Sie können das Erscheinungsbild lokaler Hyperlinks, einschließlich Textfarbe und -stil, anpassen, um sicherzustellen, dass sie zum Design Ihres Dokuments passen und ein einheitliches visuelles Erlebnis bieten.

#### F: Ist es möglich, mehrere lokale Hyperlinks innerhalb einer einzelnen PDF-Seite zu erstellen?

A: Absolut! Sie können mehrere lokale Hyperlinks innerhalb einer einzelnen PDF-Seite erstellen, sodass Leser je nach Bedarf zu verschiedenen Abschnitten oder Seiten springen können. Jeder lokale Hyperlink kann auf sein jeweiliges Ziel zugeschnitten werden.

#### F: Kann ich mit lokalen Hyperlinks auf bestimmte Abschnitte einer Seite verlinken?

A: Während lokale Hyperlinks normalerweise zu ganzen Seiten navigieren, können Sie in Ihrem PDF-Dokument Anker oder Lesezeichen erstellen, um eine gezielte Verlinkung zu erreichen. Aspose.PDF für .NET unterstützt verschiedene Hyperlink-Optionen.

#### F: Wie kann ich überprüfen, ob meine lokalen Hyperlinks ordnungsgemäß funktionieren?

A: Wenn Sie dem bereitgestellten Tutorial und Beispielcode folgen, können Sie problemlos funktionsfähige lokale Hyperlinks erstellen. Sie können die Links testen, indem Sie das generierte PDF-Dokument öffnen und auf den Hyperlink-Text klicken.

#### F: Gibt es Einschränkungen bei der Verwendung lokaler Hyperlinks?

A: Lokale Hyperlinks sind eine effektive Möglichkeit, die Dokumentnavigation zu verbessern. Dabei muss jedoch sichergestellt werden, dass die Struktur des Dokuments klar und intuitiv bleibt. Richtig beschriftete Hyperlinks und Anker tragen zu einer positiven Benutzererfahrung bei.

#### F: Kann ich lokale Hyperlinks innerhalb von Tabellen oder Bildern erstellen?

A: Ja, Sie können lokale Hyperlinks innerhalb verschiedener Elemente Ihres PDF-Dokuments erstellen, einschließlich Tabellen, Bildern und Text. Aspose.PDF für .NET bietet Flexibilität beim Hinzufügen von Hyperlinks zu verschiedenen Inhaltstypen.