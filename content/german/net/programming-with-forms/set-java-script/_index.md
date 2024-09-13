---
title: Java Script festlegen
linktitle: Java Script festlegen
second_title: Aspose.PDF für .NET API-Referenz
description: Entfesseln Sie die Leistungsfähigkeit von Aspose.PDF für .NET. Erfahren Sie in unserer Schritt-für-Schritt-Anleitung, wie Sie JavaScript in Formularfeldern einrichten.
type: docs
weight: 270
url: /de/net/programming-with-forms/set-java-script/
---
## Einführung

Das Erstellen dynamischer und interaktiver PDFs kann das Benutzererlebnis erheblich verbessern, insbesondere wenn Formulare und Felder in ein Dokument integriert werden. Eine leistungsstarke Bibliothek, die dies ermöglicht, ist Aspose.PDF für .NET. In diesem Artikel werden wir uns eingehend mit der Einrichtung von JavaScript für Formularfelder mit Aspose.PDF befassen, um sicherzustellen, dass Ihre PDFs nicht nur gut aussehen, sondern auch einwandfrei funktionieren.

## Voraussetzungen

Bevor wir mit dem Programmieren beginnen, stellen wir sicher, dass Sie alles haben, was Sie brauchen, um reibungslos mitmachen zu können:

- Visual Studio (oder eine beliebige .NET IDE): Stellen Sie sicher, dass Sie es richtig installiert und eingerichtet haben.
  
-  Aspose.PDF-Bibliothek: Sie benötigen die neueste Version dieser Bibliothek. Sie können sie herunterladen[Hier](https://releases.aspose.com/pdf/net/).

- Grundkenntnisse in C#: Wenn Sie mit der C#-Programmierung vertraut sind, verstehen Sie die Codeausschnitte besser.

-  PDF-Dateien: Sie sollten eine PDF-Datei zum Testen bereit haben. In unserem Beispiel verwenden wir eine Datei mit dem Namen`SetJavaScript.pdf`.

- Ihr Dokumentverzeichnis: Erfahren Sie, wo Ihre Dokumentdateien gespeichert sind. Wir werden diesen Pfad in unserem Code referenzieren.

Wenn diese Voraussetzungen erfüllt sind, welche Tools werden wir dann nutzen? Sehen wir uns an, was Aspose.PDF kann.

## Pakete importieren

Um zu beginnen, müssen Sie die erforderlichen Namespaces in Ihr C#-Projekt einbinden. Öffnen Sie Ihre C#-Hauptdatei und fügen Sie die folgenden Importanweisungen hinzu:

```csharp
using System;
using System.IO;
using Aspose.Pdf.Forms;
using Aspose.Pdf.Annotations;
using Aspose.Pdf;
```

Diese Namespaces bieten Zugriff auf die PDF- und Formularfunktionen innerhalb der Aspose.PDF-Bibliothek.

Bereit, Ihr PDF interaktiv zu gestalten? Schnappen Sie sich Ihren Programmierhut und lassen Sie uns Schritt für Schritt vorgehen!

## Schritt 1: Dokumentpfad festlegen

Zuerst müssen wir den Speicherort unserer PDF-Datei angeben. Dies legt die Grundlage für alles Folgende. So geht's:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Ersetzen`"YOUR DOCUMENT DIRECTORY"` durch den tatsächlichen Pfad, in dem sich Ihre PDF-Datei befindet. Stellen Sie sich das so vor, als würden Sie die Koordinaten für eine Schatzkarte festlegen – Sie müssen wissen, wo das „X“ die Stelle markiert!

## Schritt 2: Laden Sie das PDF-Dokument

Sobald wir das Verzeichnis definiert haben, laden wir unsere PDF-Datei. 

```csharp
Document doc = new Document(dataDir + "SetJavaScript.pdf");
```

Diese Zeile öffnet Ihre angegebene PDF-Datei und bereitet sie für die Bearbeitung vor. 

## Schritt 3: Zugriff auf das Formularfeld

Als Nächstes möchten wir auf das Formularfeld zugreifen, in dem wir unser JavaScript anwenden. 

```csharp
TextBoxField field = (TextBoxField)doc.Form["textbox1"];
```

 Hier nehmen wir an, dass es in Ihrer PDF-Datei ein Textfeld mit dem Namen gibt:`textbox1`Solltest Du noch kein Feld mit diesem Namen haben, kannst Du es entweder umbenennen oder den Code entsprechend anpassen. 

## Schritt 4: JavaScript-Aktionen einrichten

Fügen wir nun unserem Textfeld einige Funktionen hinzu! Wir werden JavaScript-Aktionen einrichten, die bei bestimmten Ereignissen ausgelöst werden. 

```csharp
field.Actions.OnModifyCharacter = new JavascriptAction("AFNumber_Keystroke(2, 1, 1, 0, \"\", true)");
field.Actions.OnFormat = new JavascriptAction("AFNumber_Format(2, 1, 1, 0, \"\", true)");
```

Folgendes ist passiert:
- OnModifyCharacter: Diese JavaScript-Funktion gibt an, wie sich das Feld verhalten soll, wenn ein Zeichen geändert wird. In diesem Fall sind zwei Dezimalpunkte nach der Zahl ohne Trennzeichen zulässig.
- OnFormat: Dadurch wird sichergestellt, dass beim Formatieren der Nummer durch den Benutzer die gleiche Regel eingehalten wird.

Indem wir diese Aktionen einrichten, verleihen wir unserem Textfeld im Wesentlichen eine Persönlichkeit – als würden wir ihm eine Tanzbewegung beibringen!

## Schritt 5: Initialisieren des Feldwertes

Als Nächstes geben wir unserem Textfeld einen Startpunkt, indem wir einen Anfangswert festlegen. 

```csharp
field.Value = "123";
```

Diese Zeile legt „123“ als voreingestellten Wert im Textfeld fest. Es ist, als würde man eine Bühne für eine Aufführung vorbereiten.

## Schritt 6: Speichern Sie die geänderte PDF-Datei

Schließlich müssen wir unser Dokument speichern, nachdem wir alle Änderungen vorgenommen haben.

```csharp
dataDir = dataDir + "Restricted_out.pdf";
doc.Save(dataDir);
```

 Dadurch wird die Originaldatei mit Ihren Änderungen aktualisiert und gespeichert als`Restricted_out.pdf`Betrachten Sie dies als Besiegelung des Schicksals Ihrer PDF-Datei – sobald sie gespeichert ist, ist sie bereit für die Welt!

## Schritt 7: Erfolg bestätigen

Lassen Sie uns zum Schluss überprüfen, ob alles reibungslos verlaufen ist. 

```csharp
Console.WriteLine("\nJavaScript on form field setup successfully.\nFile saved at " + dataDir);
```

Das Ausführen dieser Meldung beruhigt Sie, da der Vorgang erfolgreich abgeschlossen wurde – genauso wie der Applaus des Publikums nach einer großartigen Vorstellung.

## Abschluss

Herzlichen Glückwunsch! Sie haben JavaScript für Formularfelder in einer PDF-Datei mit Aspose.PDF für .NET erfolgreich eingerichtet. Dieses Tutorial hat Ihnen nicht nur die Tools zur Verbesserung der Benutzerinteraktion gegeben, sondern Sie auch in die Lage versetzt, Ihre Dokumente wie ein Profi zu personalisieren. Egal, ob Sie mit Formularen in Rechnungen, Umfragen oder anderen interaktiven PDF-Dateien arbeiten, die Möglichkeiten sind wirklich endlos.

### Häufig gestellte Fragen

### Was ist Aspose.PDF für .NET?  
Aspose.PDF ist eine Bibliothek zum Erstellen, Bearbeiten und Manipulieren von PDF-Dateien in .NET-Anwendungen und bietet leistungsstarke PDF-Funktionen.

### Benötige ich eine Lizenz, um Aspose.PDF zu verwenden?  
 Obwohl eine kostenlose Testversion verfügbar ist, ist für die uneingeschränkte Nutzung eine Lizenz erforderlich. Sie können eine Lizenz erwerben[Hier](https://purchase.aspose.com/buy).

### Kann ich JavaScript auf andere Arten von Formularfeldern anwenden?  
Auf jeden Fall! Aspose.PDF ermöglicht JavaScript-Aktionen für verschiedene Formularfelder wie Kontrollkästchen, Optionsfelder und Dropdown-Menüs.

### Wie erhalte ich Support bei Problemen mit Aspose.PDF?  
 Sie erhalten Support über deren[Forum](https://forum.aspose.com/c/pdf/10) für alle Fragen oder Probleme.

### Gibt es eine Möglichkeit, Aspose.PDF zu testen, ohne es zu kaufen?  
Ja! Aspose bietet eine[Kostenlose Testversion](https://releases.aspose.com/) um die Funktionen der Bibliothek zu testen, bevor Sie einen Kauf tätigen.