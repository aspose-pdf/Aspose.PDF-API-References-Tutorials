---
title: XForm auf Seite zeichnen
linktitle: XForm auf Seite zeichnen
second_title: Aspose.PDF für .NET API-Referenz
description: Erfahren Sie in dieser umfassenden Schritt-für-Schritt-Anleitung, wie Sie mit Aspose.PDF für .NET XForms in PDF zeichnen.
type: docs
weight: 10
url: /de/net/programming-with-operators/draw-xform-on-page/
---
## Einführung

Das Erstellen dynamischer und optisch ansprechender PDF-Dokumente ist in der heutigen digitalen Welt zu einer wichtigen Fähigkeit geworden. Egal, ob Sie Entwickler sind, der an der Dokumenterstellung arbeitet, oder Designer, der sich auf Ästhetik konzentriert, das Verständnis der Bearbeitung von PDFs ist von unschätzbarem Wert. In diesem Tutorial erfahren Sie, wie Sie mithilfe der Aspose.PDF-Bibliothek für .NET ein XForm auf einer Seite zeichnen. Diese Schritt-für-Schritt-Anleitung führt Sie durch die Erstellung von XForms und deren effektive Platzierung auf Ihren PDF-Seiten.

## Voraussetzungen

Bevor wir beginnen, benötigen Sie einige Dinge, um einen reibungslosen Ablauf zu gewährleisten:

1.  Aspose.PDF für .NET-Bibliothek: Stellen Sie sicher, dass Sie die Aspose.PDF-Bibliothek installiert haben. Wenn Sie sie noch nicht installiert haben, laden Sie sie von herunter[Hier](https://releases.aspose.com/pdf/net/).
2. Entwicklungsumgebung: Eine funktionierende .NET-Entwicklungsumgebung (z. B. Visual Studio 2019 oder höher).
3. Beispiel-PDF- und Bilddateien: Sie benötigen eine Basis-PDF-Datei, in der wir das XForm und ein Bild zeichnen, um die Funktionalität zu demonstrieren. Sie können gerne das Beispiel-PDF und ein Bild verwenden, das in Ihrem Dokumentverzeichnis verfügbar ist.

## Pakete importieren

Sobald Sie die Voraussetzungen eingerichtet haben, müssen Sie die erforderlichen Namespaces in Ihr .NET-Projekt importieren. Dadurch können Sie auf die von Aspose.PDF bereitgestellten Klassen und Methoden zugreifen.

```csharp
using System.IO;
using Aspose.Pdf;
```

Diese Namespaces stellen die wesentlichen Komponenten bereit, die zum Bearbeiten von PDF-Dokumenten und Nutzen der Zeichenfunktionen erforderlich sind.

Lassen Sie uns den Prozess in leicht verständliche Schritte unterteilen. Jeder Schritt enthält klare Anweisungen, die Ihnen helfen, die Konzepte zu verstehen und effektiv anzuwenden.

## Schritt 1: Dokument initialisieren und Pfade festlegen

Die Grundlagen verstehen

In diesem Schritt richten wir unser Dokument ein und definieren die Dateipfade für das Eingabe-PDF, das Ausgabe-PDF und die Bilddatei, die im XForm verwendet wird.

```csharp
// Der Pfad zum Dokumentverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY"; // Ersetzen Sie es durch Ihren Pfad.
string imageFile = dataDir + "aspose-logo.jpg"; // Das zu zeichnende Bild
string inFile = dataDir + "DrawXFormOnPage.pdf"; // PDF-Eingabedatei
string outFile = dataDir + "blank-sample2_out.pdf"; // Ausgabe-PDF-Datei
```

 Hier,`dataDir`ist das Basisverzeichnis, in dem sich Ihre Dateien befinden. Ersetzen Sie daher`"YOUR DOCUMENT DIRECTORY"` mit dem tatsächlichen Pfad.

## Schritt 2: Erstellen einer neuen Dokumentinstanz

Laden des PDF-Dokuments

Als Nächstes erstellen wir eine Instanz der Document-Klasse, die unser Eingabe-PDF darstellt.

```csharp
using (Document doc = new Document(inFile))
{
    // Die weiteren Schritte erfolgen hier...
}
```

 Mit dem`using` Anweisung stellt sicher, dass die Ressourcen nach Abschluss der Vorgänge automatisch bereinigt werden.

## Schritt 3: Seiteninhalte aufrufen und mit dem Zeichnen beginnen

Einrichten für Zeichenvorgänge

Nun greifen wir auf den Inhalt der ersten Seite unseres Dokuments zu. Hier fügen wir unsere Zeichenbefehle ein.

```csharp
OperatorCollection pageContents = doc.Pages[1].Contents;
```

Dadurch erhalten wir Kontrolle über den Seiteninhalt und können grafische Operatoren einfügen, um unser XForm zu zeichnen.

## Schritt 4: Grafikstatus speichern und wiederherstellen

Beibehalten des Grafikzustands

Vor dem Zeichnen des XForms ist es wichtig, den aktuellen Grafikstatus zu speichern. Dadurch bleibt der Rendering-Kontext erhalten.

```csharp
pageContents.Insert(1, new GSave());
pageContents.Add(new GRestore());
pageContents.Add(new GSave());
```

 Der`GSave` Der Operator speichert den aktuellen Grafikzustand, während`GRestore`stellt es später wieder her und stellt sicher, dass wir nach dem Zeichnen zu unserem ursprünglichen Kontext zurückkehren.

## Schritt 5: Erstellen des XForm

Erstellen Ihres XForms

Hier erstellen wir unser XForm-Objekt. Dies ist der Container für unsere Zeichenvorgänge, der es uns ermöglicht, sie sauber zu kapseln.

```csharp
XForm form = XForm.CreateNewForm(doc.Pages[1], doc);
doc.Pages[1].Resources.Forms.Add(form);
form.Contents.Add(new GSave());
```

 Diese Zeile erstellt ein neues XForm und fügt es den Ressourcenformularen der Seite hinzu.`GSave` wird erneut verwendet, um den Grafikstatus innerhalb des XForms beizubehalten.

## Schritt 6: Bild hinzufügen und Abmessungen festlegen

Einbinden von Bildern

Als Nächstes laden wir ein Bild in unser XForm und legen seine Größe fest.

```csharp
form.Contents.Add(new ConcatenateMatrix(200, 0, 0, 200, 0, 0));
Stream imageStream = new FileStream(imageFile, FileMode.Open);
form.Resources.Images.Add(imageStream);
```

 Dieser Code setzt die Bildgröße mit`ConcatenateMatrix`, das definiert, wie das Bild transformiert wird. Der Bildstream wird den Ressourcen des XForms hinzugefügt.

## Schritt 7: Zeichnen Sie das Bild

Anzeigen des Bildes

 Nun verwenden wir die`Do` Operator, um das Bild, das wir dem XForm hinzugefügt haben, tatsächlich auf unserer Seite zu zeichnen.

```csharp
XImage ximage = form.Resources.Images[form.Resources.Images.Count];
form.Contents.Add(new Do(ximage.Name));
form.Contents.Add(new GRestore());
```

 Der`Do` Operator ist das Mittel, mit dem wir das Bild auf der PDF-Seite rendern. Danach stellen wir den Grafikzustand wieder her.

## Schritt 8: Positionieren Sie das XForm auf der Seite

Platzieren des XForms

 Um das XForm an bestimmten Koordinaten auf der Seite darzustellen, verwenden wir ein weiteres`ConcatenateMatrix` Betrieb.

```csharp
pageContents.Add(new ConcatenateMatrix(1, 0, 0, 1, 100, 500));
pageContents.Add(new Do(form.Name));
pageContents.Add(new GRestore());
```

 Dieses Snippet platziert das XForm an den Koordinaten`x=100`, `y=500`.

## Schritt 9: Zeichnen Sie es an einer anderen Stelle erneut

Wiederverwenden des XForms

Nutzen wir dasselbe XForm und zeichnen es an einer anderen Position auf der Seite.

```csharp
pageContents.Add(new ConcatenateMatrix(1, 0, 0, 1, 100, 300));
pageContents.Add(new Do(form.Name));
pageContents.Add(new GRestore());
```

Dadurch können Sie dasselbe XForm wiederverwenden und so die Effizienz Ihres Dokumentlayouts maximieren.

## Schritt 10: Dokument fertigstellen und speichern

Speichern Ihrer Arbeit

Zuletzt müssen wir die Änderungen speichern, die wir an unserem PDF-Dokument vorgenommen haben.

```csharp
doc.Save(outFile);
```

Diese Zeile schreibt Ihr geändertes Dokument in den angegebenen Ausgabedateipfad.

## Abschluss

Herzlichen Glückwunsch! Sie haben erfolgreich gelernt, wie Sie mithilfe der Aspose.PDF-Bibliothek für .NET ein XForm auf einer PDF-Seite zeichnen. Wenn Sie diese Schritte befolgen, können Sie Ihre PDFs nun mit dynamischen Formularen und visuellen Elementen erweitern. Ganz gleich, ob Sie Berichte, Marketingmaterial oder elektronische Dokumente erstellen, die Einbindung von Bild-XForms kann den Inhalt erheblich bereichern. Werden Sie also kreativ und entdecken Sie weitere Funktionen mit Aspose.PDF!

## Häufig gestellte Fragen

### Was ist ein XForm in Aspose.PDF?
Ein XForm ist ein wiederverwendbares Formular, das Grafiken und Inhalte kapseln kann, sodass diese auf mehreren Seiten oder an verschiedenen Stellen innerhalb eines PDF-Dokuments gezeichnet werden können.

### Wie ändere ich die Größe des Bildes im XForm?
 Sie können die Größe anpassen, indem Sie die Parameter im`ConcatenateMatrix` Operator, der die Skalierung des gezeichneten Inhalts festlegt.

### Kann ich in einem XForm neben Bildern auch Text hinzufügen?
Ja! Sie können mit den Textoperatoren der Aspose.PDF-Bibliothek auch Text hinzufügen. Dabei folgt man einem ähnlichen Ansatz wie beim Hinzufügen von Bildern.

### Ist die Nutzung von Aspose.PDF kostenlos?
 Obwohl Aspose.PDF eine kostenlose Testversion anbietet, ist für die weitere Nutzung nach Ablauf der Testphase eine Lizenz erforderlich. Sie können die Lizenzierungsoptionen erkunden[Hier](https://purchase.aspose.com/buy).

### Wo finde ich ausführlichere Dokumentation?
 Die komplette Aspose.PDF Dokumentation finden Sie[Hier](https://reference.aspose.com/pdf/net/).