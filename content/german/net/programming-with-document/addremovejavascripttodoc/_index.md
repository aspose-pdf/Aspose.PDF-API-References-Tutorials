---
title: Javascript zum PDF-Dokument hinzufügen/entfernen
linktitle: Hinzufügen und Entfernen von Javascript zum Dokument
second_title: Aspose.PDF für .NET API-Referenz
description: Erfahren Sie, wie Sie mit Aspose.PDF für .NET JavaScript zu PDF-Dokumenten hinzufügen und daraus entfernen. Schritt-für-Schritt-Anleitung mit Code-Tutorials für Skripting auf Dokumentebene.
type: docs
weight: 30
url: /de/net/programming-with-document/addremovejavascripttodoc/
---
## Einführung

In dieser Anleitung zeigen wir Ihnen, wie Sie mit Aspose.PDF für .NET JavaScript in eine PDF-Datei einfügen und es bei Bedarf entfernen. Am Ende dieses Tutorials wissen Sie genau, wie Sie JavaScript in PDFs mühelos bearbeiten können.

## Voraussetzungen

Bevor wir uns in den Code vertiefen, müssen Sie einige Dinge eingerichtet haben:

1.  Aspose.PDF für .NET: Sie müssen die Bibliothek Aspose.PDF für .NET in Ihrem Projekt installiert haben. Wenn Sie sie noch nicht haben, holen Sie sich die Bibliothek aus dem[Aspose.PDF für .NET-Downloadseite](https://releases.aspose.com/pdf/net/).
2. IDE oder Texteditor: Sie können jede .NET-kompatible IDE wie Visual Studio verwenden.
3. Grundlegende C#-Kenntnisse: Dieses Tutorial setzt voraus, dass Sie mit C# vertraut sind und sich mit der PDF-Bearbeitung auskennen.
4. Lizenz: Stellen Sie sicher, dass Sie eine gültige Lizenz verwenden, um Einschränkungen zu vermeiden. Sie erhalten eine temporäre Lizenz von[Hier](https://purchase.aspose.com/temporary-license/).

## Pakete importieren

Um Aspose.PDF für .NET verwenden zu können, müssen Sie die erforderlichen Namespaces in Ihr Projekt importieren. So geht's:

```csharp
using System.IO;
using System;
using Aspose.Pdf;
using Aspose.Pdf.Annotations;
using Aspose.Pdf.Text;
using System.Collections;
```

 Diese beiden Namespaces sind wichtig.`Aspose.Pdf` ermöglicht Ihnen die Arbeit mit PDF-Dokumenten, während`System.Collections` wird zur Verarbeitung von JavaScript-Schlüsseln verwendet.

Lassen Sie uns den gesamten Vorgang des Hinzufügens und Entfernens von JavaScript aus einer PDF-Datei in leicht verständliche Schritte aufschlüsseln.

## Schritt 1: Initialisieren Sie ein neues PDF-Dokument

Als Erstes müssen Sie ein neues PDF-Dokument erstellen. Dieses Dokument dient uns als leere Leinwand zum Hinzufügen von JavaScript.

```csharp
Document doc = new Document();
doc.Pages.Add();
```

 Hier initialisieren wir ein neues`Document` Objekt und fügen Sie ihm eine leere Seite hinzu. Betrachten Sie dies als die Grundlage Ihres PDFs.

## Schritt 2: JavaScript zum PDF hinzufügen

Jetzt, da wir ein Dokument haben, ist es an der Zeit, etwas JavaScript hinzuzufügen. JavaScript in PDFs kann verwendet werden, um benutzerdefiniertes Verhalten hinzuzufügen, wie z. B. Warnungen oder Formularvalidierung.

```csharp
doc.JavaScript["func1"] = "function func1() { hello(); }";
doc.JavaScript["func2"] = "function func2() { hello(); }";
```

In diesem Codeausschnitt fügen wir zwei JavaScript-Funktionen hinzu (`func1` Und`func2` ) in das PDF. Diese Funktionen können je nach Bedarf verschiedene Aufgaben ausführen. Hier rufen wir nur eine Platzhalterfunktion namens`hello()`.

## Schritt 3: Speichern Sie das PDF mit JavaScript

Nachdem Sie das gewünschte JavaScript hinzugefügt haben, ist es Zeit, das PDF zu speichern.

```csharp
doc.Save(dataDir + "AddJavascript.pdf");
```

 Dadurch wird das Dokument mit JavaScript unter dem Namen gespeichert`AddJavascript.pdf` im angegebenen Verzeichnis (`dataDir`).

## Schritt 4: JavaScript in das vorhandene PDF laden und anzeigen

Angenommen, Sie müssen die JavaScript-Funktionen in einer vorhandenen PDF-Datei überprüfen oder ändern. Der erste Schritt besteht darin, die PDF-Datei zu laden und auf die JavaScript-Schlüssel zuzugreifen.

```csharp
Document doc1 = new Document(dataDir + "AddJavascript.pdf");
IList keys = (System.Collections.IList)doc1.JavaScript.Keys;
```

 Wir laden die bestehenden`AddJavascript.pdf` und die JavaScript-Schlüssel in einer Liste speichern.`Keys` Die Eigenschaft gibt die Namen aller an das Dokument angehängten JavaScript-Funktionen zurück.

## Schritt 5: JavaScript-Funktionen anzeigen

Als Nächstes können wir die JavaScript-Funktionen durchlaufen, um zu sehen, was im Dokument verfügbar ist.

```csharp
Console.WriteLine("=============================== ");
foreach (string key in keys)
{
    Console.WriteLine(key + " ==> " + doc1.JavaScript[key]);
}
```

Dadurch werden alle JavaScript-Funktionsnamen und der entsprechende Code auf der Konsole ausgegeben. Dies ist nützlich, wenn Sie überprüfen möchten, welche Funktionen derzeit im Dokument vorhanden sind.

## Schritt 6: JavaScript aus der PDF entfernen

 Nehmen wir nun an, Sie möchten eine bestimmte JavaScript-Funktion entfernen, wie`func1`So können Sie das tun:

```csharp
doc1.JavaScript.Remove("func1");
Console.WriteLine("Key 'func1' removed ");
```

 Der`Remove` Methode nimmt den Namen der JavaScript-Funktion als Argument und löscht sie aus dem Dokument.

## Schritt 7: Überprüfen Sie, ob JavaScript entfernt wurde

 Nach dem Entfernen des JavaScripts können Sie die verbleibenden Funktionen erneut drucken, um zu bestätigen, dass`func1` wurde erfolgreich gelöscht.

```csharp
Console.WriteLine("=============================== ");
foreach (string key in keys)
{
    Console.WriteLine(key + " ==> " + doc1.JavaScript[key]);
}
Console.WriteLine("Javascript added/removed successfully.");
```

Dieser letzte Teil des Codes stellt sicher, dass alles an seinem Platz ist und die JavaScript-Funktionen korrekt aktualisiert werden.

## Abschluss

Herzlichen Glückwunsch! Sie haben gerade gelernt, wie Sie mit Aspose.PDF für .NET JavaScript zu einem PDF-Dokument hinzufügen und daraus entfernen. Diese leistungsstarke Funktion kann für eine Vielzahl von Aufgaben genutzt werden, vom Hinzufügen dynamischer Nachrichten bis hin zur Durchführung benutzerdefinierter Berechnungen oder Validierungen. Durch die Bearbeitung von JavaScript in einem PDF können Sie das Benutzererlebnis erheblich verbessern.

## Häufig gestellte Fragen

### Kann ich einer einzelnen PDF mehrere JavaScript-Funktionen hinzufügen?
 Auf jeden Fall! Sie können so viele JavaScript-Funktionen hinzufügen, wie Sie benötigen, indem Sie`doc.JavaScript` Sammlung.

### Was passiert, wenn ich versuche, eine nicht vorhandene JavaScript-Funktion zu entfernen?
 Wenn die Funktion nicht existiert,`Remove` Die Methode löst keinen Fehler aus, entfernt aber auch nichts.

### Ist es möglich, JavaScript auszuführen, sobald das PDF geöffnet wird?
Ja! Sie können JavaScript so konfigurieren, dass es bei bestimmten Auslösern ausgeführt wird, z. B. beim Öffnen des Dokuments oder beim Klicken auf eine Schaltfläche.

### Kann ich das JavaScript bearbeiten, nachdem es zum PDF hinzugefügt wurde?
Ja, Sie können eine vorhandene PDF-Datei laden, auf ihr JavaScript zugreifen, den Code ändern und das Dokument erneut speichern.

### Hat das Entfernen von JavaScript Auswirkungen auf den restlichen PDF-Inhalt?
Nein, das Entfernen von JavaScript wirkt sich nur auf das Skript aus. Der Inhalt des PDFs bleibt unverändert.