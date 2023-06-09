---
title: Java-Script zur Seite hinzufügen
linktitle: Java-Script zur Seite hinzufügen
second_title: Aspose.PDF für .NET API-Referenz
description: Erfahren Sie, wie Sie mit Aspose.PDF für .NET JavaScript zu PDF-Dateien hinzufügen. Schritt-für-Schritt-Anleitung mit Code-Tutorials für die Skripterstellung auf Dokument- und Seitenebene.
type: docs
weight: 10
url: /de/net/programming-with-document/addjavascripttopage/
---

Um JavaScript zu einer PDF-Datei hinzuzufügen, verwenden wir Aspose.PDF für .NET. Diese Bibliothek bietet eine einfache und effiziente Möglichkeit, mit PDF-Dateien in .NET-Anwendungen zu arbeiten. Die folgenden Schritte führen Sie durch den Prozess des Hinzufügens von JavaScript zu einer PDF-Datei mit Aspose.PDF für .NET.

## Schritt 1: Laden Sie die PDF-Datei

 Der erste Schritt besteht darin, die PDF-Datei zu laden, zu der Sie JavaScript hinzufügen möchten. Sie können dies mit dem tun`Document` Von Aspose.PDF für .NET bereitgestellte Klasse. Der`Document` Die Klasse stellt Methoden zum Laden, Speichern und Bearbeiten von PDF-Dateien bereit.

```csharp
// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Laden Sie eine vorhandene PDF-Datei
Document doc = new Document(dataDir + "input.pdf");
```

## Schritt 2: Fügen Sie JavaScript auf Dokumentebene hinzu

 Um JavaScript auf Dokumentebene hinzuzufügen, verwenden wir die`JavascriptAction` Von Aspose.PDF für .NET bereitgestellte Klasse. Mit dieser Klasse können Sie die JavaScript-Anweisung angeben, die Sie der PDF-Datei hinzufügen möchten.

```csharp
// JavaScript auf Dokumentebene hinzufügen
// Instanziieren Sie JavascriptAction mit der gewünschten JavaScript-Anweisung
JavascriptAction javaScript = new JavascriptAction("this.print({bUI:true,bSilent:false,bShrinkToFit:true});");

// Weisen Sie das JavascriptAction-Objekt der gewünschten Aktion des Dokuments zu
doc.OpenAction = javaScript;
```

In diesem Tutorial fügen wir eine JavaScript-Anweisung hinzu, die die PDF-Datei mit den angegebenen Optionen druckt, wenn das Dokument geöffnet wird.

## Schritt 3: Fügen Sie JavaScript auf Seitenebene hinzu

 Um JavaScript auf Seitenebene hinzuzufügen, verwenden wir die`JavascriptAction` Klasse und die`Actions`Eigenschaft, die von Aspose.PDF für .NET bereitgestellt wird. Mit dieser Eigenschaft können Sie JavaScript-Anweisungen angeben, die ausgeführt werden, wenn die Seite geöffnet oder geschlossen wird.

```csharp
// Hinzufügen von JavaScript auf Seitenebene
doc.Pages[2].Actions.OnOpen = new JavascriptAction("app.alert('page 1 opened')");
doc.Pages[2].Actions.OnClose = new JavascriptAction("app.alert('page 1 closed')");
```

In diesem Tutorial fügen wir JavaScript-Anweisungen hinzu, die eine Warnmeldung anzeigen, wenn die Seite geöffnet oder geschlossen wird.

## Schritt 4: Speichern Sie die PDF-Datei

 Nachdem Sie das JavaScript zur PDF-Datei hinzugefügt haben, müssen Sie die geänderte Datei speichern. Sie können dies mit dem tun`Save` Methode, die von der bereitgestellt wird`Document` Klasse.

```csharp
dataDir = dataDir + "JavaScript-Added_out.pdf";
// PDF-Dokument speichern
doc.Save(dataDir);

Console.WriteLine("\nJavascript added successfully to a page.\nFile saved at " + dataDir);
```

Dieser Code speichert die geänderte PDF-Datei im angegebenen Verzeichnis.

### Beispielquellcode für „Java Script To Page hinzufügen“ mit Aspose.PDF für .NET

```csharp
            
// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Laden Sie eine vorhandene PDF-Datei
Document doc = new Document(dataDir + "input.pdf");

// JavaScript auf Dokumentebene hinzufügen
// Instanziieren Sie JavascriptAction mit der gewünschten JavaScript-Anweisung
JavascriptAction javaScript = new JavascriptAction("this.print({bUI:true,bSilent:false,bShrinkToFit:true});");

// Weisen Sie das JavascriptAction-Objekt der gewünschten Aktion des Dokuments zu
doc.OpenAction = javaScript;

// Hinzufügen von JavaScript auf Seitenebene
doc.Pages[2].Actions.OnOpen = new JavascriptAction("app.alert('page 1 opened')");
doc.Pages[2].Actions.OnClose = new JavascriptAction("app.alert('page 1 closed')");

dataDir = dataDir + "JavaScript-Added_out.pdf";
// PDF-Dokument speichern
doc.Save(dataDir);

Console.WriteLine("\nJavascript added successfully to a page.\nFile saved at " + dataDir);     
```

## Abschluss

In diesem Artikel haben wir erklärt, wie Sie mit Aspose.PDF für .NET sowohl auf Dokumentebene als auch auf Seitenebene JavaScript zu einer PDF-Datei hinzufügen. Wir haben Schritt-für-Schritt-Anleitungen bereitgestellt und den vollständigen Quellcode für jedes Beispiel beigefügt. Mit diesem Wissen können Sie JavaScript zu Ihren PDF-Dateien hinzufügen und deren Verhalten an Ihre Bedürfnisse anpassen.


