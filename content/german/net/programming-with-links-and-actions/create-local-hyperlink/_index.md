---
title: Erstellen Sie einen lokalen Hyperlink in einer PDF-Datei
linktitle: Erstellen Sie einen lokalen Hyperlink in einer PDF-Datei
second_title: Aspose.PDF für .NET API-Referenz
description: Erstellen Sie mit Aspose.PDF für .NET ganz einfach lokale Hyperlinks in einer PDF-Datei.
type: docs
weight: 40
url: /de/net/programming-with-links-and-actions/create-local-hyperlink/
---
Durch das Erstellen lokaler Hyperlinks in einer PDF-Datei können Sie anklickbare Links erstellen, die Benutzer zu anderen Seiten im selben PDF-Dokument führen. Mit Aspose.PDF für .NET können Sie solche Links ganz einfach erstellen, indem Sie dem folgenden Quellcode folgen:

## Schritt 1: Erforderliche Bibliotheken importieren

Bevor Sie beginnen, müssen Sie die erforderlichen Bibliotheken für Ihr C#-Projekt importieren. Hier ist die notwendige Importanweisung:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
using Aspose.Pdf.InteractiveFeatures;
```

## Schritt 2: Legen Sie den Pfad zum Dokumentenordner fest

 In diesem Schritt müssen Sie den Pfad zu dem Ordner angeben, in dem Sie die resultierende PDF-Datei speichern möchten. Ersetzen`"YOUR DOCUMENT DIRECTORY"`Geben Sie im folgenden Code den tatsächlichen Pfad zu Ihrem Dokumentenordner ein:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Schritt 3: Erstellen Sie eine Instanz von Document

 Wir werden eine Instanz davon erstellen`Document` Klasse zur Darstellung unseres PDF-Dokuments. Hier ist der entsprechende Code:

```csharp
Document doc = new Document();
```

## Schritt 4: Seite und Text mit Hyperlinks hinzufügen

In diesem Schritt fügen wir unserem PDF-Dokument eine Seite hinzu und fügen Text hinzu, der lokale Hyperlinks enthält. Wir definieren die Zielseiten für jeden Link. Hier ist der entsprechende Code:

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

 Speichern wir nun die aktualisierte PDF-Datei mit`Save` Methode der`doc` Objekt. Hier ist der entsprechende Code:

```csharp
dataDir = dataDir + "CreateLocalHyperlink_out.pdf";
doc.Save(dataDir);
```

### Beispielquellcode für „Lokalen Hyperlink erstellen“ mit Aspose.PDF für .NET 
```csharp
// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Dokumentinstanz erstellen
Document doc = new Document();
// Seite zur Seitensammlung der PDF-Datei hinzufügen
Page page = doc.Pages.Add();
// Erstellen Sie eine Textfragment-Instanz
Aspose.Pdf.Text.TextFragment text = new Aspose.Pdf.Text.TextFragment("link page number test to page 7");
// Erstellen Sie eine lokale Hyperlink-Instanz
Aspose.Pdf.LocalHyperlink link = new Aspose.Pdf.LocalHyperlink();
// Zielseite für Linkinstanz festlegen
link.TargetPageNumber = 7;
// Legen Sie den TextFragment-Hyperlink fest
text.Hyperlink = link;
//Fügen Sie Text zur Absatzsammlung der Seite hinzu
page.Paragraphs.Add(text);
// Erstellen Sie eine neue TextFragment-Instanz
text = new TextFragment("link page number test to page 1");
// TextFragment sollte über einer neuen Seite hinzugefügt werden
text.IsInNewPage = true;
// Erstellen Sie eine weitere lokale Hyperlink-Instanz
link = new LocalHyperlink();
// Legen Sie die Zielseite für den zweiten Hyperlink fest
link.TargetPageNumber = 1;
// Link für zweites TextFragment festlegen
text.Hyperlink = link;
// Fügen Sie Text zur Absatzsammlung des Seitenobjekts hinzu
page.Paragraphs.Add(text);    
dataDir = dataDir + "CreateLocalHyperlink_out.pdf";
// Aktualisiertes Dokument speichern
doc.Save(dataDir);
Console.WriteLine("\nLocal hyperlink created successfully.\nFile saved at " + dataDir);            
```

## Abschluss

Herzlichen Glückwunsch! Jetzt haben Sie eine Schritt-für-Schritt-Anleitung zum Erstellen lokaler Hyperlinks in einer PDF-Datei mit Aspose.PDF für .NET. Mit diesem Code können Sie anklickbare Links erstellen, die Benutzer zu anderen Seiten im selben Dokument führen.

Weitere Informationen zu erweiterten Hyperlink-Funktionen finden Sie unbedingt in der offiziellen Aspose.PDF-Dokumentation.

### FAQs zum Erstellen eines lokalen Hyperlinks in einer PDF-Datei

#### F: Was sind lokale Hyperlinks in einer PDF-Datei?

A: Lokale Hyperlinks in einer PDF-Datei sind anklickbare Links, die Benutzer zu verschiedenen Seiten innerhalb desselben Dokuments führen. Diese Links verbessern die Navigation und ermöglichen den Lesern einen schnellen Zugriff auf relevante Abschnitte.

#### F: Wie können lokale Hyperlinks meinem PDF-Dokument zugute kommen?

A: Lokale Hyperlinks bieten eine effiziente Möglichkeit, verwandte Inhalte innerhalb desselben PDF-Dokuments zu verbinden. Sie verbessern die Benutzererfahrung, indem sie es den Lesern ermöglichen, schnell zu bestimmten Abschnitten zu springen, ohne durch das gesamte Dokument scrollen zu müssen.

#### F: Wie unterstützt Aspose.PDF für .NET die Erstellung lokaler Hyperlinks?
A: Aspose.PDF für .NET bietet umfassende Unterstützung für die Erstellung lokaler Hyperlinks. Das in diesem Handbuch bereitgestellte Schritt-für-Schritt-Tutorial zeigt, wie Sie mit C# lokale Hyperlinks zu Ihrem PDF-Dokument hinzufügen.

#### F: Kann ich das Erscheinungsbild lokaler Hyperlinks anpassen?

A: Ja, Sie können das Erscheinungsbild lokaler Hyperlinks, einschließlich Textfarbe und -stil, anpassen, um sicherzustellen, dass sie zum Design Ihres Dokuments passen und ein einheitliches visuelles Erlebnis bieten.

#### F: Ist es möglich, mehrere lokale Hyperlinks innerhalb einer einzelnen PDF-Seite zu erstellen?

A: Auf jeden Fall! Sie können innerhalb einer einzelnen PDF-Seite mehrere lokale Hyperlinks erstellen, sodass Leser bei Bedarf zu verschiedenen Abschnitten oder Seiten springen können. Jeder lokale Hyperlink kann auf sein jeweiliges Ziel zugeschnitten werden.

#### F: Kann ich über lokale Hyperlinks auf bestimmte Abschnitte einer Seite verlinken?

A: Während lokale Hyperlinks normalerweise zu ganzen Seiten führen, können Sie Anker oder Lesezeichen in Ihrem PDF-Dokument erstellen, um eine gezielte Verlinkung zu erreichen. Aspose.PDF für .NET unterstützt verschiedene Hyperlink-Optionen.

#### F: Wie kann ich überprüfen, ob meine lokalen Hyperlinks ordnungsgemäß funktionieren?

A: Wenn Sie dem Tutorial und dem bereitgestellten Beispielcode folgen, können Sie sicher funktionierende lokale Hyperlinks erstellen. Sie können die Links testen, indem Sie das generierte PDF-Dokument öffnen und auf den Hyperlink-Text klicken.

#### F: Gibt es Einschränkungen bei der Verwendung lokaler Hyperlinks?

A: Lokale Hyperlinks sind eine wirksame Möglichkeit, die Dokumentnavigation zu verbessern. Es ist jedoch wichtig sicherzustellen, dass die Struktur des Dokuments klar und intuitiv bleibt. Richtig gekennzeichnete Hyperlinks und Anker tragen zu einer positiven Benutzererfahrung bei.

#### F: Kann ich lokale Hyperlinks innerhalb von Tabellen oder Bildern erstellen?

A: Ja, Sie können lokale Hyperlinks innerhalb verschiedener Elemente Ihres PDF-Dokuments erstellen, einschließlich Tabellen, Bildern und Text. Aspose.PDF für .NET bietet Flexibilität beim Hinzufügen von Hyperlinks zu verschiedenen Inhaltstypen.