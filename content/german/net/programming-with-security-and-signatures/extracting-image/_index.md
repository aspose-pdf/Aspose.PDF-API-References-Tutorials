---
title: Bild extrahieren
linktitle: Bild extrahieren
second_title: Aspose.PDF für .NET API-Referenz
description: Erfahren Sie ganz einfach, wie Sie mit Aspose.PDF für .NET Bilder aus PDFs extrahieren. Folgen Sie unserer Schritt-für-Schritt-Anleitung zur nahtlosen Bildextraktion.
type: docs
weight: 70
url: /de/net/programming-with-security-and-signatures/extracting-image/
---
## Einführung

In der digitalen Welt sind PDFs zu einem der am häufigsten verwendeten Dateiformate geworden. Ob für Berichte, eBooks oder Vertragsdokumente, PDFs haben sich eine eigene Nische geschaffen. Mussten Sie schon einmal Bilder aus einer PDF-Datei extrahieren? Vielleicht für ein Projekt oder einfach, weil das Bild besonders beeindruckend ist? Nun, Sie haben Glück! In diesem Tutorial zeigen wir Ihnen, wie Sie mit Aspose.PDF für .NET nahtlos Bilder aus einer PDF-Datei extrahieren.

## Voraussetzungen

Bevor wir uns mit den Einzelheiten der Bildextraktion befassen, müssen Sie einige Dinge einrichten. Stellen wir sicher, dass Sie alles vorbereitet haben!

### .NET-Entwicklungsumgebung

Zunächst müssen Sie eine Entwicklungsumgebung mit .NET einrichten. Dies umfasst normalerweise Folgendes:

-  Visual Studio: Es ist eine leistungsstarke IDE für .NET-Anwendungen. Wenn Sie es noch nicht heruntergeladen haben, können Sie es von der[Visual Studio-Website](https://visualstudio.microsoft.com/).
- .NET Framework: Stellen Sie sicher, dass .NET Framework 4.5 oder höher auf Ihrem Computer installiert ist.

### Aspose.PDF für .NET-Bibliothek

Um mit PDFs arbeiten zu können, benötigen Sie die Bibliothek Aspose.PDF. Mit dieser Bibliothek können Sie PDF-Dateien frei bearbeiten, einschließlich der Extraktion von Bildern. So erhalten Sie sie:

-  Du kannst[Laden Sie die neueste Version herunter](https://releases.aspose.com/pdf/net/) von Aspose.PDF für .NET.
-  Wenn Sie es vor dem Kauf ausprobieren möchten,[Kostenlose Testversion](https://releases.aspose.com/) ist verfügbar.
-  Wenn Sie sich für eine langfristige Nutzung entscheiden, können Sie[eine Lizenz kaufen](https://purchase.aspose.com/buy) oder auch[Fordern Sie eine temporäre Lizenz an](https://purchase.aspose.com/temporary-license/) zu Testzwecken.

### Grundkenntnisse in C#

Grundlegende Kenntnisse in C# sind hilfreich. Wenn Sie mit dem Schreiben einfacher C#-Skripte vertraut sind, werden Sie dies problemlos bewältigen.

## Pakete importieren

Nachdem wir nun alles eingerichtet haben, beginnen wir mit dem Importieren der erforderlichen Pakete. Sie beginnen damit, den Aspose.PDF-Namespace oben in Ihrer C#-Datei einzubinden. So geht's:

```csharp
using System;
using System.IO;
using Aspose.Pdf;
using Aspose.Pdf.Forms;
using System.Drawing;
```

- Aspose.Pdf: Dies ist der Hauptnamespace für die Arbeit mit PDF-Dateien.
- Aspose.Pdf.Form: Dieser Namespace befasst sich speziell mit der Handhabung von Formularen in PDF-Dokumenten, einschließlich aller Felder wie Textfelder und Signaturfelder.
- System.Drawing: Dieser Namespace wird zur Handhabung der Grafikprogrammierung in .NET verwendet.
- System.IO: Dieser Namespace bietet Funktionen zur Verarbeitung von Dateien und Datenströmen.

Okay, kommen wir zum Kern der Sache: dem Extrahieren von Bildern! Wir verwenden den folgenden Code als Grundlage.

## Schritt 1: Definieren Sie den PDF-Dokumentpfad

Zunächst müssen wir definieren, wo sich Ihr PDF-Dokument befindet. Mithilfe einer Zeichenfolgenvariable geben Sie den Pfad Ihrer Eingabedatei an. So geht's:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY"; // Ersetzen Sie es durch Ihr Dokumentenverzeichnis.
string input = dataDir + @"ExtractingImage.pdf"; // PDF-Eingabedatei
```
 Ersetzen`"YOUR DOCUMENTS DIRECTORY"` mit dem Pfad zum Ordner, in dem Ihre PDF-Datei gespeichert ist. Dies ist wichtig, da das Programm wissen muss, wo sich Ihre PDF-Datei befindet.

## Schritt 2: Laden Sie das PDF-Dokument

Als nächstes müssen wir Ihr PDF-Dokument in das Programm laden. Dazu verwenden wir die Document-Klasse von Aspose.Pdf.

```csharp
using (Document pdfDocument = new Document(input))
{
    // Dadurch wird sichergestellt, dass die PDF-Datei ordnungsgemäß geschlossen wird, wenn wir fertig sind.
}
```
 Der`using` Anweisung stellt sicher, dass das PDF-Dokument ordnungsgemäß entsorgt wird, sobald wir mit der Arbeit daran fertig sind, und verhindert so Speicherlecks.

## Schritt 3: Durch die Signaturfelder iterieren

Nun durchlaufen wir alle Felder im PDF-Dokument und suchen gezielt nach Signaturfeldern (da hier normalerweise Bilder eingebettet sind).

```csharp
foreach (Field field in pdfDocument.Form)
{
    SignatureField sf = field as SignatureField;
    if (sf != null)
    {
        // Wenn es sich bei dem Feld um eine Signatur handelt, können wir deren Bild extrahieren.
    }
}
```
 Hier verwenden wir eine`foreach` Schleife, um jedes Feld im PDF-Formular zu überprüfen. Wenn wir ein Signaturfeld finden, können wir mit dem Extrahieren des Bildes fortfahren.

## Schritt 4: Extrahieren Sie das Bild

Jetzt kommt der spannende Teil: das Extrahieren des Bildes! Wenn das Signaturfeld nicht null ist, können wir sein Bild mit dem folgenden Code extrahieren:

```csharp
string outFile = dataDir + @"output_out.jpg"; // Pfad für das extrahierte Bild
using (Stream imageStream = sf.ExtractImage())
{
    if (imageStream != null)
    {
        using (System.Drawing.Image image = Bitmap.FromStream(imageStream))
        {
            image.Save(outFile, System.Drawing.Imaging.ImageFormat.Jpeg);
        }
    }
}
```

- Wir definieren einen Ausgabedateipfad, in dem das extrahierte Bild gespeichert wird.
-  Wir verwenden`sf.ExtractImage()` um den Bildstrom aus dem Signaturfeld abzurufen.
-  Wir prüfen, ob die`imageStream` ist nicht null, um sicherzustellen, dass tatsächlich ein zu extrahierendes Bild vorhanden ist.
- Abschließend wandeln wir den Stream in ein Bitmap um und speichern ihn als JPEG-Datei.

## Abschluss

Das Extrahieren von Bildern aus PDFs mit Aspose.PDF für .NET ist ein unkomplizierter Vorgang, wenn Sie die Schritte kennen. Mit nur wenigen Codezeilen können Sie auf die verborgenen Schätze in Ihren Dokumenten zugreifen. Egal, ob Sie nach einem unvergesslichen Foto oder einer wichtigen Grafik aus einem Bericht suchen, dieses Tool ist von unschätzbarem Wert. Viel Spaß beim Codieren und mögen Ihre PDFs immer voller Bilder sein!

## Häufig gestellte Fragen

### Kann ich mit Aspose.PDF Bilder aus jeder PDF-Datei extrahieren?  
Ja, Sie können Bilder aus jeder PDF-Datei extrahieren, vorausgesetzt, die PDF-Datei enthält eingebettete Bilder oder Signaturfelder.

### Benötige ich eine kostenpflichtige Lizenz, um Aspose.PDF zu verwenden?  
Sie können es mit einer kostenlosen Testversion ausprobieren, für die langfristige oder kommerzielle Nutzung ist jedoch eine kostenpflichtige Lizenz erforderlich.

### Ist es möglich, mehrere Bilder gleichzeitig zu extrahieren?  
Ja, Sie können den Code so ändern, dass er mehrere Felder durchläuft und alle Bilder extrahiert.

### In welchen Bildformaten kann ich die extrahierten Bilder speichern?  
Sie können extrahierte Bilder je nach Ihren Anforderungen in verschiedenen Formaten speichern, darunter JPEG, PNG, BMP usw.

### Wo finde ich weitere Ressourcen für Aspose.PDF?  
 Sie können die[Aspose.PDF Dokumentation](https://reference.aspose.com/pdf/net/) für weitere Ressourcen und Beispiele.