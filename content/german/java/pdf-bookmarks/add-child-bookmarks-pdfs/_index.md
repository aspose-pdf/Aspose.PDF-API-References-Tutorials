---
title: Untergeordnete Lesezeichen zu PDFs hinzufügen
linktitle: Untergeordnete Lesezeichen zu PDFs hinzufügen
second_title: Aspose.PDF Java PDF-Verarbeitungs-API
description: Erfahren Sie, wie Sie PDF-Dokumente mit Aspose.PDF für Java mit untergeordneten Lesezeichen verbessern. Schritt-für-Schritt-Anleitung mit Codebeispielen für verbesserte Navigation und Organisation.
type: docs
weight: 11
url: /de/java/pdf-bookmarks/add-child-bookmarks-pdfs/
---

## Einführung zum Hinzufügen untergeordneter Lesezeichen zu PDFs

In diesem Artikel erfahren Sie, wie Sie mit Aspose.PDF für Java untergeordnete Lesezeichen zu PDF-Dokumenten hinzufügen. Untergeordnete Lesezeichen sind eine praktische Möglichkeit, den Inhalt eines PDF-Dokuments zu organisieren und darin zu navigieren. So können Benutzer leichter bestimmte Abschnitte oder Themen im Dokument finden.

## Voraussetzungen

Bevor wir mit der Implementierung beginnen, stellen Sie sicher, dass die folgenden Voraussetzungen erfüllt sind:

- Auf Ihrem System installierte Java-Entwicklungsumgebung.
-  Aspose.PDF für Java-Bibliothek. Sie können es herunterladen von[Hier](https://releases.aspose.com/pdf/java/).

## Einrichten der Umgebung

1. Laden Sie die Aspose.PDF-Bibliothek für Java über den bereitgestellten Link herunter.
2. Fügen Sie die Bibliothek zu Ihrem Java-Projekt hinzu.

Beginnen wir nun mit der Erstellung eines neuen PDF-Dokuments und fügen diesem Schritt für Schritt untergeordnete Lesezeichen hinzu.

## Erstellen eines neuen PDF-Dokuments

Zu Beginn müssen wir ein PDF-Dokument initialisieren und Seiten hinzufügen. Hier ist der Codeausschnitt zum Einstieg:

```java
// Initialisieren eines PDF-Dokuments
Document pdfDocument = new Document();

// Seiten zum PDF hinzufügen
pdfDocument.getPages().add();
pdfDocument.getPages().add();
```

In diesem Beispiel haben wir ein neues PDF-Dokument erstellt und ihm zwei Seiten hinzugefügt.

## Übergeordnete Lesezeichen hinzufügen

Übergeordnete Lesezeichen dienen als Hauptabschnitte oder -kategorien in Ihrem PDF-Dokument. Lassen Sie uns einige übergeordnete Lesezeichen erstellen:

```java
// Übergeordnete Lesezeichen erstellen
OutlineItemCollection outline = pdfDocument.getOutlines();
OutlineItemCollection parentBookmark = new OutlineItemCollection(outline);
parentBookmark.setTitle("Parent Bookmark 1");
outline.add(parentBookmark);

parentBookmark = new OutlineItemCollection(outline);
parentBookmark.setTitle("Parent Bookmark 2");
outline.add(parentBookmark);
```

Wir haben zwei übergeordnete Lesezeichen hinzugefügt: „Übergeordnetes Lesezeichen 1“ und „Übergeordnetes Lesezeichen 2“.

## Untergeordnete Lesezeichen hinzufügen

Jetzt ist es an der Zeit, den übergeordneten Lesezeichen, die wir zuvor erstellt haben, untergeordnete Lesezeichen hinzuzufügen. Untergeordnete Lesezeichen stellen bestimmte Themen oder Unterabschnitte innerhalb jedes übergeordneten Lesezeichens dar. So können Sie das tun:

```java
// Untergeordnete Lesezeichen zum übergeordneten Lesezeichen 1 hinzufügen
OutlineItemCollection childBookmark = new OutlineItemCollection(outline);
childBookmark.setTitle("Child Bookmark 1.1");
parentBookmark.add(childBookmark);

childBookmark = new OutlineItemCollection(outline);
childBookmark.setTitle("Child Bookmark 1.2");
parentBookmark.add(childBookmark);

//Untergeordnete Lesezeichen zum übergeordneten Lesezeichen 2 hinzufügen
childBookmark = new OutlineItemCollection(outline);
childBookmark.setTitle("Child Bookmark 2.1");
parentBookmark.add(childBookmark);
```

Wir haben sowohl zu „Übergeordnetes Lesezeichen 1“ als auch zu „Übergeordnetes Lesezeichen 2“ untergeordnete Lesezeichen hinzugefügt.

## Anpassen des Erscheinungsbilds von Lesezeichen

Sie können das Erscheinungsbild von Lesezeichen anpassen, indem Sie deren Text und Stil ändern. Darüber hinaus können Sie Lesezeichen Symbole hinzufügen, um sie optisch besser darzustellen. Hier ist ein Beispiel dafür:

```java
// Anpassen des Erscheinungsbilds von Lesezeichen
parentBookmark.setItalic(true);
childBookmark.setForegroundColor(Color.getGreen());
childBookmark.setIcon(OutlineItemCollection.getItalicIcon());
```

In diesem Beispiel haben wir das übergeordnete Lesezeichen kursiv gemacht, die Textfarbe des untergeordneten Lesezeichens in Grün geändert und dem untergeordneten Lesezeichen ein Kursivsymbol hinzugefügt.

## Behandeln von Ereignissen

Mit Lesezeichen können auch Aktionen verknüpft sein. Sie können beispielsweise Aktionen hinzufügen, die ausgelöst werden, wenn ein Benutzer auf ein Lesezeichen klickt. So können Sie Klickereignisse für Lesezeichen behandeln:

```java
// Einem Lesezeichen eine Aktion hinzufügen
GoToAction action = new GoToAction(pdfDocument.getPages().get_Item(1));
childBookmark.setAction(action);
```

In diesem Code haben wir einem untergeordneten Lesezeichen eine „Gehe zu“-Aktion hinzugefügt, die den Benutzer beim Anklicken zur zweiten Seite der PDF-Datei führt.

## Speichern der PDF

Nachdem Sie alle erforderlichen Lesezeichen hinzugefügt und deren Aussehen und Aktionen angepasst haben, können Sie das geänderte PDF-Dokument speichern:

```java
// Speichern des PDF-Dokuments
pdfDocument.save("output.pdf");
```

Ihr PDF-Dokument mit untergeordneten Lesezeichen ist jetzt fertig.

## Vollständiger Quellcode

Hier ist der vollständige Quellcode zum Hinzufügen untergeordneter Lesezeichen zu einem PDF-Dokument mit Aspose.PDF für Java:

```java
// Initialisieren eines PDF-Dokuments
Document pdfDocument = new Document();

// Seiten zum PDF hinzufügen
pdfDocument.getPages().add();
pdfDocument.getPages().add();

// Übergeordnete Lesezeichen erstellen
OutlineItemCollection outline = pdfDocument.getOutlines();
OutlineItemCollection parentBookmark = new OutlineItemCollection(outline);
parentBookmark.setTitle("Parent Bookmark 1");
outline.add(parentBookmark);

parentBookmark = new OutlineItemCollection(outline);
parentBookmark.setTitle("Parent Bookmark 2");
outline.add(parentBookmark);

// Untergeordnete Lesezeichen zum übergeordneten Lesezeichen 1 hinzufügen
OutlineItemCollection childBookmark = new OutlineItemCollection(outline);
childBookmark.setTitle("Child Bookmark 1.1");
parentBookmark.add(childBookmark);

childBookmark = new OutlineItemCollection(outline);
childBookmark.setTitle("Child Bookmark 1.2");
parentBookmark.add(childBookmark);

//Untergeordnete Lesezeichen zum übergeordneten Lesezeichen 2 hinzufügen
childBookmark = new OutlineItemCollection(outline);
childBookmark.setTitle("Child Bookmark 2.1");
parentBookmark.add(childBookmark);

// Anpassen des Erscheinungsbilds von Lesezeichen
parentBookmark.setItalic(true);
childBookmark.setForegroundColor(Color.getGreen());
childBookmark.setIcon(OutlineItemCollection.getItalicIcon());

// Einem Lesezeichen eine Aktion hinzufügen
GoToAction action = new GoToAction(pdfDocument.getPages().get_Item(1));
childBookmark.setAction(action);

// Speichern des PDF-Dokuments
pdfDocument.save("output.pdf");
```

## Abschluss

Das Hinzufügen untergeordneter Lesezeichen zu PDFs mit Aspose.PDF für Java ist eine leistungsstarke Funktion, die die Navigation und Organisation Ihrer Dokumente verbessert. Indem Sie die in diesem Artikel beschriebenen Schritte befolgen, können Sie gut strukturierte PDFs mit übergeordneten und untergeordneten Lesezeichen erstellen, deren Erscheinungsbild anpassen und sogar Aktionen hinzufügen, um das Benutzererlebnis zu verbessern.

## Häufig gestellte Fragen

### Wie kann ich Aspose.PDF für Java herunterladen?

 Sie können Aspose.PDF für Java von der Website herunterladen[Hier](https://releases.aspose.com/pdf/java/).

### Werden untergeordnete Lesezeichen in allen PDF-Viewern unterstützt?

Ja, untergeordnete Lesezeichen werden in den meisten modernen PDF-Viewern unterstützt und bieten ein verbessertes Benutzererlebnis beim Navigieren durch PDF-Dokumente.

### Kann ich das Erscheinungsbild der Lesezeichen weiter anpassen?

Ja, Sie können das Erscheinungsbild von Lesezeichen anpassen, indem Sie Textstile, Farben und Symbole an das Design Ihres Dokuments anpassen.

### Welche anderen Aktionen kann ich zu Lesezeichen hinzufügen?

Neben „Gehe zu“-Aktionen können Sie Aktionen wie „URI“-Aktionen zum Öffnen von Weblinks oder „JavaScript“-Aktionen zum Ausführen benutzerdefinierter Skripts beim Klicken auf ein Lesezeichen hinzufügen.

### Ist Aspose.PDF für Java für kommerzielle Projekte geeignet?

Ja, Aspose.PDF für Java eignet sich sowohl für persönliche als auch für kommerzielle Projekte und bietet eine breite Palette an Funktionen zur PDF-Bearbeitung und -Erstellung.