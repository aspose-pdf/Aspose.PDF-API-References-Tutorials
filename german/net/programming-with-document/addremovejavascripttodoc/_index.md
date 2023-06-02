---
title: Hinzufügen und Entfernen von Javascript zum Dokument
linktitle: Hinzufügen und Entfernen von Javascript zum Dokument
second_title: Aspose.PDF für .NET API-Referenz
description: Erfahren Sie, wie Sie mit Aspose.PDF für .NET JavaScript zu PDF-Dokumenten hinzufügen und entfernen. Schritt-für-Schritt-Anleitung mit Code-Tutorials für die Skripterstellung auf Dokumentebene.
type: docs
weight: 30
url: /de/net/programming-with-document/addremovejavascripttodoc/
---

Um JavaScript aus PDF-Dokumenten hinzuzufügen und zu entfernen, verwenden wir die Bibliothek Aspose.PDF für .NET. Mit dieser leistungsstarken Bibliothek können wir PDF-Dateien in .NET-Anwendungen bearbeiten. Befolgen Sie die nachstehenden Schritt-für-Schritt-Anleitungen, um JavaScript mit Aspose.PDF für .NET hinzuzufügen und zu entfernen.

## Schritt 1: Erstellen Sie ein neues PDF-Dokument

 Beginnen Sie mit der Erstellung einer neuen Instanz von`Document`Von Aspose.PDF für .NET bereitgestellte Klasse. Dies dient als PDF-Dokument, in das wir das JavaScript einfügen.

```csharp
// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
doc.Pages.Add();
```

## Schritt 2: Fügen Sie JavaScript auf Dokumentebene hinzu

 Um JavaScript auf Dokumentebene hinzuzufügen, verwenden Sie die`JavaScript` Eigentum der`Document` Klasse. Weisen Sie den Tasten im JavaScript-Wörterbuch JavaScript-Funktionen zu.

```csharp
doc.JavaScript["func1"] = "function func1() { hello(); }";
doc.JavaScript["func2"] = "function func2() { hello(); }";
doc.Save(dataDir + "AddJavascript.pdf");
```

 In diesem Tutorial haben wir zwei JavaScript-Funktionen hinzugefügt:`func1` Und`func2`, zum PDF-Dokument.

## Schritt 3: Entfernen Sie JavaScript auf Dokumentebene

 Um JavaScript auf Dokumentebene zu entfernen, laden Sie das PDF-Dokument und greifen Sie auf zu`JavaScript` Wörterbuch. Durchlaufen Sie die Schlüssel und entfernen Sie die gewünschte JavaScript-Funktion.

```csharp
Document doc1 = new Document(dataDir + "AddJavascript.pdf");
IList keys = (System.Collections.IList)doc1.JavaScript.Keys;

foreach (string key in keys)
{
    Console.WriteLine(key + " ==> " + doc1.JavaScript[key]);
}

doc1.JavaScript.Remove("func1");
Console.WriteLine("Key 'func1' removed");
```

 In diesem Tutorial entfernen wir die`func1` JavaScript-Funktion aus dem PDF-Dokument.

## Schritt 4: Änderungen speichern und überprüfen

Speichern Sie das geänderte PDF-Dokument und überprüfen Sie die Änderungen.

```csharp
Console.WriteLine("\nJavascript added/removed successfully to a document.");
```

Dieser Code speichert das geänderte PDF-Dokument und zeigt die Erfolgsmeldung an.

### Beispielquellcode für das Hinzufügen und Entfernen von Javascript aus PDF-Dokumenten mit Aspose.PDF für .NET

```csharp
// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
doc.Pages.Add();
doc.JavaScript["func1"] = "function func1() { hello(); }";
doc.JavaScript["func2"] = "function func2() { hello(); }";
doc.Save(dataDir + "AddJavascript.pdf");

// Entfernen Sie JavaScript auf Dokumentebene
Document doc1 = new Document(dataDir + "AddJavascript.pdf");
IList keys = (System.Collections.IList)doc1.JavaScript.Keys;
Console.WriteLine("=============================== ");
foreach (string key in keys)
{
	Console.WriteLine(key + " ==> " + doc1.JavaScript[key]);
}

doc1.JavaScript.Remove("func1");
Console.WriteLine("Key 'func1' removed ");
Console.WriteLine("=============================== ");

Console.WriteLine("\nJavascript added/removed successfully to a document.");
```

## Abschluss

In diesem Artikel haben wir eine Schritt-für-Schritt-Anleitung zum Hinzufügen und Entfernen von JavaScript aus PDF-Dokumenten mit Aspose.PDF für .NET bereitgestellt. Indem Sie den Anweisungen folgen und die bereitgestellten Code-Tutorials nutzen, können Sie JavaScript problemlos in Ihre PDF-Dokumente integrieren und bei Bedarf entfernen. JavaScript ermöglicht dynamische Funktionalität und Interaktivität in Ihren PDF-Dateien und verbessert so das Benutzererlebnis.