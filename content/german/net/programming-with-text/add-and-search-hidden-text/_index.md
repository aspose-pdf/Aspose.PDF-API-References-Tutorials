---
title: Hinzufügen und Suchen von verstecktem Text in einer PDF-Datei
linktitle: Hinzufügen und Suchen von verstecktem Text in einer PDF-Datei
second_title: Aspose.PDF für .NET API-Referenz
description: Erfahren Sie, wie Sie mit Aspose.PDF für .NET versteckten Text in PDF-Dokumenten hinzufügen und suchen. Schritt-für-Schritt-Anleitung mit Codebeispielen.
type: docs
weight: 20
url: /de/net/programming-with-text/add-and-search-hidden-text/
---
## Einführung

In diesem Tutorial führen wir Sie Schritt für Schritt durch das Hinzufügen und Suchen von verstecktem Text in einer PDF-Datei mit Aspose.PDF für .NET. Egal, ob Sie ein erfahrener Entwickler oder ein Neuling sind, der seine Programmierkenntnisse verbessern möchte, dieser Artikel bietet Ihnen die Einblicke, die Sie benötigen, um die Funktion für versteckten Text in Ihre Anwendungen zu integrieren.

## Voraussetzungen

Bevor Sie mit der Codierung beginnen, müssen Sie einige Voraussetzungen erfüllen:

### Anforderungs-Checkliste
- Visual Studio: Stellen Sie sicher, dass Sie Visual Studio installiert haben. Dieses Tutorial setzt voraus, dass Sie .NET Framework verwenden.
-  Aspose.PDF für .NET: Sie benötigen die Bibliothek Aspose.PDF für .NET. Sie können sie herunterladen[Hier](https://releases.aspose.com/pdf/net/).
- Grundkenntnisse in C#: Wenn Sie mit der C#-Programmierung vertraut sind, verstehen Sie die Codeausschnitte besser.

## Pakete importieren

Bevor Sie mit Ihrem Code beginnen können, müssen Sie sicherstellen, dass Sie die erforderlichen Aspose.PDF-Namespaces importieren. So geht's:

### Richten Sie Ihr Projekt ein
1. Öffnen Sie Visual Studio und erstellen Sie ein neues C#-Projekt oder verwenden Sie ein vorhandenes.
2.  Installieren Sie Aspose.PDF, indem Sie das NuGet-Paket hinzufügen. Sie können dies tun, indem Sie zum NuGet-Paketmanager navigieren und nach`Aspose.PDF`. 
3.  Alternativ können Sie die Bibliothek auch direkt herunterladen von[Hier](https://releases.aspose.com/pdf/net/) und fügen Sie es als Referenz in Ihr Projekt ein.

### Erforderliche Namespaces importieren
Importieren Sie oben in Ihre C#-Datei die folgenden Namespaces:

```csharp
using Aspose.Pdf.Text;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

Dieser Schritt ist entscheidend, da diese Namespaces die zur Bearbeitung von PDF-Dokumenten erforderlichen Klassen und Methoden enthalten.

## Erstellen eines PDF-Dokuments mit verstecktem Text

Nachdem Sie nun eingerichtet sind, gehen wir die Schritte zum Erstellen eines PDF-Dokuments durch, das sowohl sichtbaren als auch unsichtbaren Text enthält.

### Schritt 1: Dokumentverzeichnis definieren
Zuerst müssen Sie den Pfad festlegen, in dem die PDF-Datei gespeichert wird. Hier beginnt die Magie!

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY"; // Ändern Sie dies in Ihr Verzeichnis
```

 Diese Zeile definiert, wo Ihr generiertes PDF gespeichert wird. Vergessen Sie nicht,`YOUR DOCUMENT DIRECTORY` mit Ihrem tatsächlichen Pfad.

### Schritt 2: Erstellen Sie ein PDF-Dokument
Als Nächstes erstellen wir ein neues PDF-Dokument und fügen ihm Seiten hinzu.

```csharp
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
Page page = doc.Pages.Add();
```

Hier initialisieren wir ein neues Dokument und fügen eine Seite hinzu, auf der wir unsere Textfragmente platzieren.

### Schritt 3: Sichtbaren und versteckten Text hinzufügen
Jetzt fügen wir unserem PDF sowohl sichtbaren als auch unsichtbaren Text hinzu.

```csharp
TextFragment frag1 = new TextFragment("This is common text.");
TextFragment frag2 = new TextFragment("This is invisible text.");
```

 In diesem Snippet`frag1` sichtbar sein wird, während`frag2` wird als nächstes auf unsichtbar gesetzt.

### Schritt 4: Setzen Sie den Text auf Unsichtbar
 Um den Text von`frag2` unsichtbar, ändern Sie einfach seine`TextState`.

```csharp
frag2.TextState.Invisible = true;
```

 Durch das Setzen dieser Eigenschaft wird jeder Text, der mit`frag2` wird beim Anzeigen der PDF-Datei nicht gerendert.

### Schritt 5: Textfragmente zur Seite hinzufügen
Abschließend fügen wir diese Textfragmente der Seite hinzu und speichern das PDF.

```csharp
page.Paragraphs.Add(frag1);
page.Paragraphs.Add(frag2);
doc.Save(dataDir + "39400_out.pdf");
doc.Dispose();
```

Dieser Teil des Codes fügt unsere Textfragmente zur Seite hinzu. Danach speichern und entsorgen wir das Dokument ordnungsgemäß.

## Suchen nach verstecktem Text im PDF

Nachdem wir nun unsere PDF-Datei mit sichtbarem und verstecktem Text erstellt haben, stellt sich die Frage, wie wir nach diesem versteckten Text suchen können. Lassen Sie uns das Ganze aufschlüsseln.

### Schritt 1: Laden Sie das PDF-Dokument
Um im PDF nach Text zu suchen, müssen wir zuerst das gerade erstellte Dokument laden.

```csharp
doc = new Aspose.Pdf.Document(dataDir + "39400_out.pdf");
```

### Schritt 2: Erstellen Sie einen Textfragmentabsorber
 Wir verwenden`TextFragmentAbsorber` um alle Textfragmente im PDF zu erfassen.

```csharp
TextFragmentAbsorber absorber = new TextFragmentAbsorber();
absorber.Visit(doc.Pages[1]);
```

Hier geben wir an, dass wir alle Textfragmente der ersten Seite übernehmen möchten.

### Schritt 3: Durch die Fragmente iterieren
Jetzt können wir die gesammelten Textfragmente durchgehen, um herauszufinden, welche sichtbar und welche ausgeblendet sind.

```csharp
foreach (TextFragment fragment in absorber.TextFragments)
{
    Console.WriteLine("Text '{0}' on pos {1} invisibility: {2}",
        fragment.Text, fragment.Position.ToString(), fragment.TextState.Invisible);
}
```

 Diese Schleife prüft jedes Textfragment und gibt dessen Inhalt zusammen mit seiner Position und seinem Sichtbarkeitsstatus aus. Wenn`fragment.TextState.Invisible` auf „true“ gesetzt ist, bedeutet dies, dass der Text ausgeblendet ist!

### Schritt 4: Dokument entsorgen
Denken Sie abschließend daran, das Dokument nach Abschluss der Bearbeitung wieder zu entsorgen.

```csharp
doc.Dispose();
```

## Abschluss

In diesem Tutorial haben wir den spannenden Prozess des Hinzufügens und Suchens nach verstecktem Text in PDF-Dateien mit Aspose.PDF für .NET durchgegangen. Wir haben gelernt, wie man ein PDF-Dokument mit sichtbarem und verstecktem Text erstellt und wie man programmgesteuert nach diesem versteckten Text sucht. Diese Funktion kann in verschiedenen Anwendungen unglaublich nützlich sein, egal ob Sie vertrauliche Informationen speichern oder eine einzigartige Benutzererfahrung in Ihren Dokumenten bieten müssen.

Je besser Sie sich mit ASPose.PDF auskennen, desto mehr Möglichkeiten eröffnen sich. Experimentieren Sie weiter und erweitern Sie die Grenzen dessen, was Sie mit Ihren PDF-Dokumenten erreichen können!

## Häufig gestellte Fragen

### Kann Aspose.PDF verschlüsselte PDF-Dateien verarbeiten?  
Ja, Aspose.PDF unterstützt die Verschlüsselung und Entschlüsselung von PDF-Dokumenten. Sie können Ihre PDFs ganz einfach mit Passwörtern sichern.

### Gibt es eine Testversion für Aspose.PDF?  
 Auf jeden Fall! Sie können die kostenlose Testversion herunterladen unter[Hier](https://releases.aspose.com/).

### Welche Programmiersprachen unterstützt Aspose.PDF?  
Aspose.PDF bietet Unterstützung für mehrere Sprachen, darunter C#, Java und Python.

### Wo finde ich die Dokumentation für Aspose.PDF?  
 Sie können auf die Dokumentation zugreifen[Hier](https://reference.aspose.com/pdf/net/).

### Wie kann ich Unterstützung erhalten, wenn ich auf Probleme stoße?  
 Für Support können Sie die Aspose-Foren besuchen[Hier](https://forum.aspose.com/c/pdf/10).