---
title: Text aus Stempelanmerkung extrahieren
linktitle: Text aus Stempelanmerkung extrahieren
second_title: Aspose.PDF für .NET API-Referenz
description: Erfahren Sie in diesem Schritt-für-Schritt-Tutorial mit einem ausführlichen Codebeispiel, wie Sie mit Aspose.PDF für .NET Text aus einer Stempelanmerkung in PDF extrahieren.
type: docs
weight: 80
url: /de/net/programming-with-stamps-and-watermarks/extract-text-from-stamp-annotation/
---
## Einführung

Beim Arbeiten mit PDF-Dateien kann das Extrahieren bestimmter Daten wie Text aus Anmerkungen sehr praktisch sein. In diesem Tutorial zeigen wir Ihnen Schritt für Schritt, wie Sie mit Aspose.PDF für .NET Text aus einer Stempelanmerkung in einem PDF-Dokument extrahieren. Mit dieser leistungsstarken Bibliothek können Entwickler PDF-Dateien bearbeiten und Aufgaben wie Textextraktion, Anmerkungsverwaltung und vieles mehr durchführen. Lassen Sie uns in die Details eintauchen und alles aufschlüsseln!

## Voraussetzungen

Bevor wir mit dem Tutorial beginnen, benötigen Sie einige Dinge:

-  Aspose.PDF für .NET: Sie müssen Aspose.PDF für .NET installiert haben. Sie können[Laden Sie hier die neueste Version herunter](https://releases.aspose.com/pdf/net/).
- Visual Studio: Dieses Handbuch setzt voraus, dass Sie Visual Studio als Ihre integrierte Entwicklungsumgebung (IDE) verwenden.
- Grundkenntnisse in C#: Sie sollten über grundlegende Kenntnisse der C#-Programmierung verfügen.

Stellen Sie sicher, dass Sie diese Tools eingerichtet haben, damit Sie dem Tutorial folgen können.

## Pakete importieren

Der erste Schritt in jedem .NET-Projekt ist das Importieren der erforderlichen Namespaces. Mit Aspose.PDF benötigen Sie zum Einstieg nur einige wenige wichtige Importe:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Annotations;
using Aspose.Pdf.Text;
```

Diese Importe bringen die Funktionalität mit, die für die Arbeit mit PDF-Dokumenten, Anmerkungen und Textextraktion erforderlich ist.

Lassen Sie uns den Vorgang zum Extrahieren von Text aus einer Stempelanmerkung durchgehen. Dazu müssen Sie ein PDF-Dokument laden, die Stempelanmerkung identifizieren und den Textinhalt extrahieren.

## Schritt 1: Laden Sie das PDF-Dokument

Als Erstes müssen Sie die PDF-Datei laden, in der sich die Stempelanmerkung befindet. In diesem Beispiel laden wir eine Beispiel-PDF-Datei aus Ihrem lokalen Verzeichnis.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "test.pdf");
```

 Hier verwenden wir die`Document` Klasse, die von Aspose.PDF bereitgestellt wird, um die PDF-Datei zu öffnen und mit ihr zu interagieren. Die`dataDir` Variable stellt den Pfad zu Ihrer Datei dar. Ersetzen Sie`"YOUR DOCUMENT DIRECTORY"` durch den tatsächlichen Pfad, in dem Ihr PDF gespeichert ist.

## Schritt 2: Identifizieren der Stempelanmerkung

PDF-Anmerkungen werden anhand ihres Typs und ihrer Position im Dokument identifiziert. In unserem Fall möchten wir eine Stempelanmerkung auf einer bestimmten Seite finden. So geht's:

```csharp
StampAnnotation annot = doc.Pages[1].Annotations[3] as StampAnnotation;
```

In dieser Codezeile:
- `doc.Pages[1]`: Greift auf die erste Seite des Dokuments zu.
- `Annotations[3]`: Bezieht sich auf die vierte Anmerkung auf der Seite (da die Indizierung bei 0 beginnt).
- `as StampAnnotation` : Wandelt die Annotation in eine`StampAnnotation` Objekt. Dabei handelt es sich um den spezifischen Typ der Anmerkung, mit der wir es zu tun haben.

## Schritt 3: Erstellen Sie einen Textabsorber

Um Text aus der Stempelanmerkung zu extrahieren, müssen wir einen Text Absorber verwenden. Dieses Tool hilft uns, den Text aus einem bestimmten Bereich der PDF-Datei, in diesem Fall der Anmerkung, zu absorbieren oder zu erfassen.

```csharp
TextAbsorber ta = new TextAbsorber();
```

 Der`TextAbsorber` Die Klasse ist für das Extrahieren von Text aus beliebigen Teilen des Dokuments konzipiert und wir werden sie verwenden, um das Erscheinungsbild der Anmerkung gezielt festzulegen.

## Schritt 4: Das Erscheinungsbild der Stempelanmerkung extrahieren

Stempelanmerkungen in PDFs haben ein zugeordnetes Erscheinungsbild, das normalerweise in Form eines XForms gespeichert ist. Wir müssen dieses Erscheinungsbild abrufen, um auf den eigentlichen Text im Stempel zuzugreifen.

```csharp
XForm ap = annot.Appearance["N"];
```

Hier:
- `annot.Appearance["N"]`: Ruft den Erscheinungsstrom mit dem Namen „N“ ab (der das normale Erscheinungsbild der Anmerkung darstellt).

## Schritt 5: Extrahieren Sie den Textinhalt

 Jetzt, da wir das Aussehen haben, können wir die`TextAbsorber` um das Erscheinungsbild zu besuchen und den Text zu erfassen.

```csharp
ta.Visit(ap);
```

 Der`Visit` Methode ermöglicht die`TextAbsorber` um das Erscheinungsbild zu analysieren und darin eingebetteten Textinhalt zu extrahieren.

## Schritt 6: Den extrahierten Text anzeigen

Sobald der Text extrahiert ist, können wir ihn auf der Konsole ausgeben oder zur weiteren Verwendung speichern.

```csharp
Console.WriteLine(ta.Text);
```

Diese einfache Codezeile zeigt den extrahierten Text im Konsolenfenster an. Sie können ihn auch in einer Datei speichern oder je nach Bedarf weiter bearbeiten.

## Abschluss

Das Arbeiten mit Anmerkungen in PDF-Dokumenten, insbesondere Stempelanmerkungen, kann Ihren Anwendungen erhebliche Funktionalität verleihen. Mit Aspose.PDF für .NET verfügen Sie über einen robusten Satz von Tools, mit denen Sie ganz einfach Daten extrahieren, Anmerkungen bearbeiten und auf sinnvolle Weise mit PDFs interagieren können. In diesem Tutorial haben wir Ihnen gezeigt, wie Sie in nur wenigen einfachen Schritten Text aus einer Stempelanmerkung extrahieren. Jetzt sind Sie an der Reihe, mit diesen Funktionen in Ihren Projekten zu experimentieren!

## Häufig gestellte Fragen

### Kann ich mit Aspose.PDF Text aus anderen Arten von Anmerkungen extrahieren?  
Ja, mit Aspose.PDF können Sie Text aus verschiedenen Arten von Anmerkungen extrahieren, beispielsweise Textanmerkungen, Freitextanmerkungen und mehr, nicht nur Stempelanmerkungen.

### Unterstützt Aspose.PDF das Hinzufügen benutzerdefinierter Anmerkungen?  
Auf jeden Fall! Aspose.PDF unterstützt das Erstellen und Hinzufügen benutzerdefinierter Anmerkungen zu PDF-Dokumenten und bietet Ihnen Flexibilität bei der Verwaltung und Präsentation von Daten.

### Kann ich Bilder aus Stempelanmerkungen extrahieren?  
Ja, Sie können mit ähnlichen Methoden Bilder aus Stempelanmerkungen extrahieren, indem Sie auf das Erscheinungsbild zugreifen und Bilddaten abrufen.

### Welche weiteren Funktionen bietet Aspose.PDF für .NET?  
Aspose.PDF für .NET bietet eine breite Palette an Funktionen, darunter Textbearbeitung, Formularfeldverwaltung, Dokumentkonvertierung und vieles mehr.

### Ist Aspose.PDF für .NET kostenlos?  
 Aspose.PDF für .NET bietet eine kostenlose Testversion, aber um auf den vollen Funktionsumfang zugreifen zu können, müssen Sie eine Lizenz erwerben. Sie können auch eine[vorläufige Lizenz](https://purchase.aspose.com/temporary-license/).