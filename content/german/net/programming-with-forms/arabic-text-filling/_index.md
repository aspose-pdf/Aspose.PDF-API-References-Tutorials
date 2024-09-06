---
title: Arabische Textfüllung
linktitle: Arabische Textfüllung
second_title: Aspose.PDF für .NET API-Referenz
description: Füllen Sie PDF-Formularfelder mit Aspose.PDF für .NET ganz einfach mit arabischem Text.
type: docs
weight: 20
url: /de/net/programming-with-forms/arabic-text-filling/
---
In diesem Tutorial lernen wir, wie man mit Aspose.PDF für .NET ein PDF-Formularfeld mit arabischem Text füllt. Aspose.PDF ist eine leistungsstarke Bibliothek, mit der Entwickler PDF-Dokumente programmgesteuert bearbeiten können. Wir führen Sie Schritt für Schritt durch den Prozess und erklären den C#-Quellcode, der zum Ausführen dieser Aufgabe erforderlich ist.

## Schritt 1: PDF-Formularinhalt laden

Zuerst müssen wir das PDF-Formular laden, das das auszufüllende Feld enthält. Wir beginnen mit der Definition des Pfads zum Verzeichnis, in dem sich das Formular befindet:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Als nächstes erstellen wir eine`FileStream` Objekt zum Lesen und Schreiben der Formulardatei:

```csharp
FileStream fs = new FileStream(dataDir + "FillFormField.pdf", FileMode.Open, FileAccess.ReadWrite);
```

 Als nächstes instantiieren wir ein`Document` Objekt, das den Stream verwendet, der die Formulardatei enthält:

```csharp
Aspose.Pdf.Document pdfDocument = new Aspose.Pdf.Document(fs);
```

## Schritt 2: Auf das TextBoxField-Feld zugreifen

 Um das Formularfeld mit arabischem Text zu füllen, müssen wir auf die spezifische`TextBoxField` Feld, das wir ausfüllen möchten. In diesem Beispiel nehmen wir an, dass der Feldname "textbox1" ist. Wir können die Feldreferenz mithilfe des`Form` Eigentum der`pdfDocument` Objekt:

```csharp
TextBoxField txtFld = pdfDocument.Form["textbox1"] as TextBoxField;
```

## Schritt 3: Füllen Sie das Formularfeld mit arabischem Text

 Jetzt, da wir die`TextBoxField` Bezug können wir den arabischen Text seiner`Value` Eigentum:

```csharp
txtFld.Value = "يولد جميع الناس أحراراً متساوين في";
```

## Schritt 4: Speichern Sie das aktualisierte Dokument

Abschließend speichern wir das aktualisierte Dokument in einer neuen Datei:

```csharp
dataDir = dataDir + "ArabicTextFilling_out.pdf";
pdfDocument.Save(dataDir);
```

Wir zeigen außerdem eine Meldung an, die den Erfolg des Ausfüllens des arabischen Textes bestätigt:

```csharp
Console.WriteLine("\nArabic text successfully filled in the form field.\nFile saved in the following location: " + dataDir);
```

### Beispiel-Quellcode zum Ausfüllen arabischen Textes mit Aspose.PDF für .NET 
```csharp
// Der Pfad zum Dokumentverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";
//PDF-Formularinhalte laden
FileStream fs = new FileStream(dataDir + "FillFormField.pdf", FileMode.Open, FileAccess.ReadWrite);
// Instanziieren Sie eine Dokumentinstanz mit dem Stream, der die Formulardatei enthält
Aspose.Pdf.Document pdfDocument = new Aspose.Pdf.Document(fs);
// Holen Sie sich die Referenz eines bestimmten TextBoxField
TextBoxField txtFld = pdfDocument.Form["textbox1"] as TextBoxField;
// Formularfeld mit arabischem Text ausfüllen
txtFld.Value = "يولد جميع الناس أحراراً متساوين في";
dataDir = dataDir + "ArabicTextFilling_out.pdf";
// Aktualisiertes Dokument speichern
pdfDocument.Save(dataDir);
Console.WriteLine("\nArabic text filled successfully in form field.\nFile saved at " + dataDir);
```

## Abschluss

In diesem Tutorial haben wir untersucht, wie man mit Aspose.PDF für .NET ein PDF-Formularfeld mit arabischem Text füllt. Wir sind Schritt für Schritt durch den Prozess gegangen und haben den relevanten C#-Quellcode erklärt. Wenn Sie diese Anweisungen befolgen, können Sie die Funktion zum Füllen arabischen Textes ganz einfach in Ihre .NET-Anwendungen integrieren. Wenn Sie weitere Fragen haben oder weitere Informationen benötigen, können Sie sich gerne an das Aspose.PDF-Supportteam wenden oder sich die zusätzlichen Ressourcen unten ansehen.

### Häufig gestellte Fragen

#### F: Kann ich mit Aspose.PDF für .NET andere Arten von Formularfeldern mit arabischem Text füllen?

 A: Ja, Sie können Aspose.PDF für .NET verwenden, um andere Arten von Formularfeldern mit arabischem Text zu füllen, wie z. B. Kontrollkästchen, Optionsfelder, Kombinationsfelder und mehr. Der Vorgang ähnelt dem Ausfüllen eines`TextBoxField` . Greifen Sie einfach über den Namen oder die ID auf das jeweilige Feld zu und legen Sie`Value`-Eigenschaft auf den gewünschten arabischen Text.

#### F: Ist Aspose.PDF für .NET mit arabischem Text und Rechts-nach-Links-Schreibweise (RTL) kompatibel?

A: Ja, Aspose.PDF für .NET unterstützt arabischen Text und RTL-Schreiben vollständig. Es verarbeitet arabische Zeichen und Textausrichtung korrekt und stellt sicher, dass die generierten PDF-Dokumente das korrekte visuelle Layout für Sprachen mit Schreibrichtung von rechts nach links beibehalten.

#### F: Kann ich Aspose.PDF für .NET verwenden, um arabischen Text aus vorhandenen PDF-Dateien zu extrahieren?

A: Ja, Aspose.PDF für .NET bietet Textextraktionsfunktionen, mit denen Sie arabischen Text aus vorhandenen PDF-Dateien extrahieren können. Mithilfe der Bibliothek können Sie programmgesteuert Text aus bestimmten Seiten oder dem gesamten Dokument extrahieren, einschließlich arabischem Text.

#### F: Kann ich das Erscheinungsbild des ausgefüllten arabischen Textes im Formularfeld anpassen?

A: Ja, Sie können das Erscheinungsbild des ausgefüllten arabischen Textes im Formularfeld mit Aspose.PDF für .NET anpassen. Sie haben Kontrolle über Schriftarten, -größen, -farben und andere Textformatierungsoptionen. Sie können sicherstellen, dass der ausgefüllte arabische Text Ihrem gewünschten Erscheinungsbild im PDF-Formular entspricht.

#### F: Wie kann ich Support erhalten oder zusätzliche Ressourcen für Aspose.PDF für .NET finden?

A: Sie erhalten Support für Aspose.PDF für .NET, indem Sie das offizielle Aspose-Supportforum besuchen oder sich direkt an das Supportteam wenden. Darüber hinaus finden Sie auf der Aspose-Website hilfreiche Dokumentationen, Beispiele und API-Referenzen, die Sie bei der Implementierung verschiedener PDF-bezogener Aufgaben unterstützen.