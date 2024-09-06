---
title: Seitenzahl in Kopf- und Fußzeile mithilfe einer schwebenden Box
linktitle: Seitenzahl in Kopf- und Fußzeile mithilfe einer schwebenden Box
second_title: Aspose.PDF für .NET API-Referenz
description: Erfahren Sie, wie Sie mit Aspose.PDF für .NET die Seitenzahl in die Kopf- und Fußzeile eines PDF-Dokuments einfügen.
type: docs
weight: 150
url: /de/net/programming-with-stamps-and-watermarks/page-number-in-header-footer-using-floating-box/
---
In diesem Tutorial zeigen wir Ihnen Schritt für Schritt, wie Sie mithilfe von FloatingBox mit Aspose.PDF für .NET Seitenzahlen in Kopf- und Fußzeile eines PDF-Dokuments hinzufügen. Wir verwenden den bereitgestellten C#-Quellcode, um ein PDF-Dokument zu erstellen, eine Seite hinzuzufügen, eine FloatingBox zu erstellen, ihre Position festzulegen und die Seitenzahl hinzuzufügen. Anschließend speichern wir das geänderte PDF-Dokument.

## Schritt 1: Einrichten der Umgebung

Bevor Sie beginnen, stellen Sie sicher, dass Sie über Folgendes verfügen:

- Eine installierte .NET-Entwicklungsumgebung.
- Die Aspose.PDF-Bibliothek für .NET wurde heruntergeladen und in Ihrem Projekt referenziert.

## Schritt 2: PDF-Dokument erstellen und Seite hinzufügen

Der erste Schritt besteht darin, eine Instanz des PDF-Dokuments zu erstellen und ihr eine Seite hinzuzufügen. So geht's:

```csharp
// Der Pfad zum Dokumentverzeichnis.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Instanziieren des PDF-Dokuments
Aspose.Pdf.Document pdf = new Aspose.Pdf.Document();

// Dem PDF-Dokument eine Seite hinzufügen
Aspose.Pdf.Page page = pdf.Pages.Add();
```

Ersetzen Sie „IHR DOKUMENTVERZEICHNIS“ unbedingt durch den tatsächlichen Pfad zu dem Verzeichnis, in dem Sie das PDF-Dokument speichern möchten.

## Schritt 3: FloatingBox erstellen und Seitenzahl hinzufügen

Nachdem die Seite nun dem PDF-Dokument hinzugefügt wurde, können wir eine FloatingBox erstellen, ihre Position festlegen und ihr die Seitenzahl hinzufügen. So geht's:

```csharp
// Erstellen Sie eine FloatingBox mit einer Breite von 140 und einer Höhe von 80
Aspose.Pdf.FloatingBox box1 = new Aspose.Pdf.FloatingBox(140, 80);

// Legen Sie die linke Position des Absatzes fest
box1. Left = 2;

// Legen Sie die obere Position des Absatzes fest
box1. Top = 10;

// Seitenzahl zur FloatingBox hinzufügen
box1.Paragraphs.Add(new Aspose.Pdf.Text.TextFragment("Page: ($p/ $P )"));

// Fügen Sie die FloatingBox zur Seite hinzu
page.Paragraphs.Add(box1);
```

Der obige Code erstellt eine FloatingBox mit einer Breite von 140 und einer Höhe von 80. Als Nächstes legen wir ihre Position fest, indem wir die Werte für „left“ und „top“ angeben. Schließlich fügen wir der FloatingBox die Seitenzahl hinzu, indem wir ein TextFragment mit der Syntax „($p/ $P )“ verwenden, das durch die aktuelle Seitenzahl und die Gesamtzahl der Seiten ersetzt wird.

## Schritt 4: Speichern des geänderten PDF-Dokuments

Nachdem die Seitenzahl mithilfe der FloatingBox in die Kopf- oder Fußzeile eingefügt wurde, können wir das geänderte PDF-Dokument speichern. So geht's:

```csharp
// Speichern Sie das geänderte PDF-Dokument
pdf.Save(dataDir + "PageNumberinHeaderFooterUsingFloatingBox_out.pdf");
```

Der obige Code speichert das bearbeitete PDF-Dokument im angegebenen Verzeichnis.

### Beispielquellcode für Seitennummerierung in Kopf- und Fußzeile mithilfe einer Floating Box unter Verwendung von Aspose.PDF für .NET 
```csharp

// Der Pfad zum Dokumentverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Dokumentinstanz instantiieren
Aspose.Pdf.Document pdf = new Aspose.Pdf.Document();

// Fügen Sie dem PDF-Dokument eine Seite hinzu
Aspose.Pdf.Page page = pdf.Pages.Add();

// Initialisiert eine neue Instanz der FloatingBox-Klasse
Aspose.Pdf.FloatingBox box1 = new Aspose.Pdf.FloatingBox(140, 80);

// Float-Wert, der die linke Position des Absatzes angibt
box1.Left = 2;

// Float-Wert, der die obere Position des Absatzes angibt
box1.Top = 10;

// Fügen Sie die Makros zur Absatzsammlung der FloatingBox hinzu
box1.Paragraphs.Add(new Aspose.Pdf.Text.TextFragment("Page: ($p/ $P )"));

// Fügen Sie der Seite eine FloatingBox hinzu
page.Paragraphs.Add(box1);

// Speichern des Dokuments
pdf.Save(dataDir + "PageNumberinHeaderFooterUsingFloatingBox_out.pdf");

```

## Abschluss

Herzlichen Glückwunsch! Sie haben gelernt, wie Sie mithilfe von FloatingBox mit Aspose.PDF für .NET Seitenzahlen in Kopf- und Fußzeilen von PDF-Dokumenten einfügen. Sie können jetzt Ihre Kopf- und Fußzeilen anpassen, indem Sie dynamische Informationen wie Seitenzahlen hinzufügen.

### Häufig gestellte Fragen

#### F: Was ist eine FloatingBox und wie wird sie verwendet, um Seitenzahlen in die Kopf- oder Fußzeile eines PDF-Dokuments einzufügen?

A: Eine FloatingBox ist ein vielseitiges Layoutelement in Aspose.PDF, das verschiedene Inhalte, darunter Text und Bilder, enthalten kann. In diesem Tutorial wird es verwendet, um einen Container für die Seitenzahl zu erstellen, sodass Sie die aktuelle Seitenzahl und die Gesamtseitenzahl dynamisch in die Kopf- oder Fußzeile einfügen können.

#### F: Wie erreicht der bereitgestellte C#-Quellcode das Hinzufügen von Seitenzahlen mithilfe einer FloatingBox?

A: Der Codeausschnitt zeigt, wie man ein PDF-Dokument erstellt, eine Seite hinzufügt, eine FloatingBox erstellt, ihre Position innerhalb der Seite festlegt und die Seitenzahl mithilfe eines TextFragments einfügt. Die Syntax "($p/ $P )" im TextFragment wird durch die aktuelle Seitenzahl und die Gesamtseitenzahl ersetzt.

#### F: Kann ich das Aussehen und die Formatierung der mit der FloatingBox hinzugefügten Seitenzahl anpassen?

A: Ja, Sie können das Erscheinungsbild der Seitenzahl anpassen, indem Sie die Eigenschaften des TextFragments innerhalb der FloatingBox ändern. Sie können Schriftgröße, Farbe, Stil, Ausrichtung und andere Formatierungsoptionen ändern.

#### F: Ist es möglich, mit einem ähnlichen Ansatz verschiedene dynamische Elemente wie Datum und Uhrzeit zur Kopf- oder Fußzeile hinzuzufügen?

A: Absolut, Sie können verschiedene dynamische Elemente wie Datum, Uhrzeit, Dokumentmetadaten oder benutzerdefinierten Text hinzufügen, indem Sie den TextFragment-Inhalt innerhalb der FloatingBox ändern. Sie können Makros wie „($p/ $P )“ für Seitenzahlen oder „($date)“ für das aktuelle Datum verwenden.

#### F: Wie lege ich die Position der FloatingBox im Header- oder Footerbereich fest?
 A: Der bereitgestellte Code setzt die Position der FloatingBox mithilfe der`Left` Und`Top` Eigenschaften. Sie können diese Werte anpassen, um die FloatingBox wie gewünscht im Kopf- oder Fußzeilenbereich zu positionieren.

#### F: Kann ich für die Seitenzahl in der Kopf- oder Fußzeile eine andere Schriftart oder einen anderen Stil verwenden?

A: Ja, Sie können die Schriftart, den Stil und andere Formatierungseigenschaften des Seitenzahlentextes anpassen, indem Sie die TextFragment-Eigenschaften innerhalb der FloatingBox ändern.

#### F: Was passiert, wenn der Inhalt der FloatingBox deren Abmessungen überschreitet?

A: Wenn der Inhalt innerhalb der FloatingBox die Abmessungen überschreitet, kann er abgeschnitten werden oder es können Layoutprobleme auftreten. Stellen Sie sicher, dass die Abmessungen der FloatingBox für die Aufnahme des Inhalts geeignet sind, und passen Sie das Seitenlayout bei Bedarf an.

#### F: Ist es möglich, der Kopf- oder Fußzeile derselben Seite mehrere FloatingBoxen mit unterschiedlichem Inhalt hinzuzufügen?

A: Ja, Sie können der Kopf- oder Fußzeile derselben Seite mehrere FloatingBoxes mit unterschiedlichem Inhalt hinzufügen, indem Sie separate FloatingBox-Instanzen erstellen und diese der Paragraphs-Sammlung der Seite hinzufügen.

#### F: Kann ich den FloatingBox-Ansatz verwenden, um Inhalt zu anderen Abschnitten des PDF-Dokuments hinzuzufügen, beispielsweise zum Textkörper oder zu den Rändern?

A: FloatingBoxes werden zwar häufig für Kopf- und Fußzeilen verwendet, Sie können sie jedoch auch nutzen, um anderen Abschnitten des PDF-Dokuments, wie etwa dem Textkörper oder den Rändern, Inhalt hinzuzufügen, indem Sie sie entsprechend innerhalb der Seite positionieren.