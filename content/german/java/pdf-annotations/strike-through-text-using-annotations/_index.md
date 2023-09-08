---
title: Text mit Anmerkungen durchstreichen
linktitle: Text mit Anmerkungen durchstreichen
second_title: Aspose.PDF Java PDF-Verarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.PDF für Java durchgestrichene Textanmerkungen zu PDF-Dokumenten hinzufügen. Befolgen Sie unsere Schritt-für-Schritt-Anleitung für eine präzise Dokumentbearbeitung.
type: docs
weight: 16
url: /de/java/pdf-annotations/strike-through-text-using-annotations/
---

## Einführung in das Durchstreichen von Text mithilfe von Anmerkungen

In der Welt der Dokumentenmanipulation sind Präzision und Klarheit von größter Bedeutung. Durchgestrichene Textanmerkungen sind ein wertvolles Werkzeug, um Änderungen hervorzuheben, auf Löschungen hinzuweisen oder bestimmte Inhalte in einem PDF-Dokument hervorzuheben. Aspose.PDF für Java bietet eine Reihe robuster Funktionen, um dies mühelos zu erreichen. In dieser Anleitung führen wir Sie durch den Prozess des Hinzufügens von durchgestrichenen Textanmerkungen zu Ihren PDF-Dokumenten mit Aspose.PDF für Java.

## Voraussetzungen

Bevor wir uns mit dem Code befassen, stellen Sie sicher, dass die folgenden Voraussetzungen erfüllt sind:

1. Java-Entwicklungsumgebung: Stellen Sie sicher, dass Java und eine geeignete IDE (Eclipse, IntelliJ IDEA oder eine andere) auf Ihrem System installiert sind.

2.  Aspose.PDF für Java-Bibliothek: Laden Sie die Aspose.PDF für Java-Bibliothek herunter und fügen Sie sie in Ihr Projekt ein. Den Download-Link finden Sie hier[Hier](https://releases.aspose.com/pdf/java/).

## Schritt 1: Einrichten Ihres Java-Projekts

Erstellen Sie zunächst ein neues Java-Projekt oder öffnen Sie ein vorhandenes in Ihrer bevorzugten IDE. Stellen Sie sicher, dass Sie die Aspose.PDF for Java-Bibliothek zum Klassenpfad Ihres Projekts hinzugefügt haben.

## Schritt 2: Initialisieren des PDF-Dokuments

Beginnen wir mit der Initialisierung eines PDF-Dokuments, dem wir eine durchgestrichene Anmerkung hinzufügen möchten.

```java
// Initialisieren Sie ein neues PDF-Dokument
com.aspose.pdf.Document pdfDocument = new com.aspose.pdf.Document();
```

## Schritt 3: Text zum Dokument hinzufügen

Als Nächstes fügen wir dem PDF-Dokument Text hinzu. Dieser Text dient als Inhalt, den wir durchstreichen wollen.

```java
// Erstellen Sie eine Seite im PDF-Dokument
com.aspose.pdf.Page page = pdfDocument.getPages().add();

// Fügen Sie der Seite Text hinzu
com.aspose.pdf.TextFragment textFragment = new com.aspose.pdf.TextFragment("This is a sample text to be struck through.");
page.getParagraphs().add(textFragment);
```

## Schritt 4: Hinzufügen einer durchgestrichenen Anmerkung

Jetzt kommt der spannende Teil – das Hinzufügen einer durchgestrichenen Anmerkung zum Text.

```java
// Erstellen Sie eine durchgestrichene Anmerkung
com.aspose.pdf.StrikeOutAnnotation strikeOutAnnotation = new com.aspose.pdf.StrikeOutAnnotation(page, textFragment.getRectangle());
strikeOutAnnotation.setColor(com.aspose.pdf.Color.getRed());

// Fügen Sie die Anmerkung zur Seite hinzu
page.getAnnotations().add(strikeOutAnnotation);
```

In diesem Codeausschnitt erstellen wir eine durchgestrichene Anmerkung, setzen ihre Farbe auf Rot (Sie können jede beliebige Farbe auswählen) und fügen sie dann der PDF-Seite hinzu.

## Schritt 5: Speichern des PDF-Dokuments

Abschließend speichern wir das geänderte PDF-Dokument in einer Datei.

```java
// Speichern Sie das PDF-Dokument
pdfDocument.save("output.pdf");
```

## Abschluss

Glückwunsch! Sie haben mit Aspose.PDF für Java erfolgreich eine durchgestrichene Textanmerkung zu einem PDF-Dokument hinzugefügt. Diese leistungsstarke Bibliothek vereinfacht die Arbeit mit PDF-Dokumenten und ist somit die ideale Wahl für Entwickler, die ihre Möglichkeiten zur Dokumentbearbeitung erweitern möchten.

## FAQs

### Wie ändere ich die Farbe der durchgestrichenen Anmerkung?

 Um die Farbe der durchgestrichenen Anmerkung zu ändern, können Sie Folgendes verwenden:`setColor` Methode und geben Sie die gewünschte Farbe an. Im bereitgestellten Beispiel haben wir es mit auf Rot gesetzt`setColor(com.aspose.pdf.Color.getRed())`.

### Kann ich einem einzelnen PDF-Dokument mehrere durchgestrichene Anmerkungen hinzufügen?

Ja, Sie können einem einzelnen PDF-Dokument mehrere durchgestrichene Anmerkungen hinzufügen. Wiederholen Sie einfach die Schritte in der Anleitung für jede Anmerkung, die Sie hinzufügen möchten.

### Ist Aspose.PDF für Java mit verschiedenen Java-Versionen kompatibel?

Aspose.PDF für Java ist mit verschiedenen Java-Versionen kompatibel. Stellen Sie sicher, dass Sie die richtige Version der Bibliothek auswählen, die zu Ihrer Java-Umgebung passt.

### Gibt es andere Arten von Anmerkungen, die ich mit Aspose.PDF für Java hinzufügen kann?

Ja, Aspose.PDF für Java unterstützt verschiedene Arten von Anmerkungen, einschließlich Text, Hervorhebung, Unterstreichung und mehr. Detaillierte Beispiele und Verwendungsmöglichkeiten finden Sie in der Dokumentation.

### Wo finde ich weitere Ressourcen und Dokumentation für Aspose.PDF für Java?

 Eine umfassende Dokumentation und weitere Ressourcen finden Sie auf der Dokumentationsseite zu Aspose.PDF für Java:[Hier](https://reference.aspose.com/pdf/java/).