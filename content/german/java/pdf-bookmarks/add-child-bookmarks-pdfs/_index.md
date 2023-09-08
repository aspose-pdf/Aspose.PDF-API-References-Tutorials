---
title: Fügen Sie untergeordnete Lesezeichen zu PDFs hinzu
linktitle: Fügen Sie untergeordnete Lesezeichen zu PDFs hinzu
second_title: Aspose.PDF Java PDF-Verarbeitungs-API
description: Erfahren Sie, wie Sie PDF-Dokumente mit Aspose.PDF für Java mit untergeordneten Lesezeichen erweitern. Schritt-für-Schritt-Anleitung mit Codebeispielen für eine verbesserte Navigation und Organisation.
type: docs
weight: 11
url: /de/java/pdf-bookmarks/add-child-bookmarks-pdfs/
---

## Einführung in das Hinzufügen untergeordneter Lesezeichen zu PDFs

In diesem Artikel erfahren Sie, wie Sie mit Aspose.PDF für Java untergeordnete Lesezeichen zu PDF-Dokumenten hinzufügen. Untergeordnete Lesezeichen sind eine praktische Möglichkeit, den Inhalt eines PDF-Dokuments zu organisieren und durch ihn zu navigieren, sodass Benutzer bestimmte Abschnitte oder Themen im Dokument leichter finden können.

## Voraussetzungen

Bevor wir uns mit der Implementierung befassen, stellen Sie sicher, dass die folgenden Voraussetzungen erfüllt sind:

- Auf Ihrem System installierte Java-Entwicklungsumgebung.
-  Aspose.PDF für Java-Bibliothek. Sie können es herunterladen unter[Hier](https://releases.aspose.com/pdf/java/).

## Einrichten der Umgebung

1. Laden Sie die Aspose.PDF für Java-Bibliothek über den bereitgestellten Link herunter.
2. Fügen Sie die Bibliothek Ihrem Java-Projekt hinzu.

Beginnen wir nun damit, ein neues PDF-Dokument zu erstellen und ihm Schritt für Schritt untergeordnete Lesezeichen hinzuzufügen.

## Erstellen eines neuen PDF-Dokuments

Zunächst müssen wir ein PDF-Dokument initialisieren und ihm Seiten hinzufügen. Hier ist der Codeausschnitt für den Einstieg:

```java
// Initialisieren Sie ein PDF-Dokument
Document pdfDocument = new Document();

// Fügen Sie Seiten zum PDF hinzu
pdfDocument.getPages().add();
pdfDocument.getPages().add();
```

In diesem Beispiel haben wir ein neues PDF-Dokument erstellt und ihm zwei Seiten hinzugefügt.

## Übergeordnete Lesezeichen hinzufügen

Übergeordnete Lesezeichen dienen als Hauptabschnitte oder Kategorien in Ihrem PDF-Dokument. Lassen Sie uns einige übergeordnete Lesezeichen erstellen:

```java
// Erstellen Sie übergeordnete Lesezeichen
OutlineItemCollection outline = pdfDocument.getOutlines();
OutlineItemCollection parentBookmark = new OutlineItemCollection(outline);
parentBookmark.setTitle("Parent Bookmark 1");
outline.add(parentBookmark);

parentBookmark = new OutlineItemCollection(outline);
parentBookmark.setTitle("Parent Bookmark 2");
outline.add(parentBookmark);
```

Wir haben zwei übergeordnete Lesezeichen hinzugefügt, „Übergeordnetes Lesezeichen 1“ und „Übergeordnetes Lesezeichen 2“.

## Untergeordnete Lesezeichen hinzufügen

Jetzt ist es an der Zeit, den übergeordneten Lesezeichen, die wir zuvor erstellt haben, untergeordnete Lesezeichen hinzuzufügen. Untergeordnete Lesezeichen repräsentieren bestimmte Themen oder Unterabschnitte innerhalb jedes übergeordneten Lesezeichens. So können Sie es machen:

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

## Anpassen der Lesezeichendarstellung

Sie können das Erscheinungsbild von Lesezeichen anpassen, indem Sie deren Text und Stil ändern. Darüber hinaus können Sie Lesezeichen zur besseren visuellen Darstellung Symbole hinzufügen. Hier ist ein Beispiel dafür:

```java
// Passen Sie das Erscheinungsbild des Lesezeichens an
parentBookmark.setItalic(true);
childBookmark.setForegroundColor(Color.getGreen());
childBookmark.setIcon(OutlineItemCollection.getItalicIcon());
```

In diesem Beispiel haben wir das übergeordnete Lesezeichen kursiv formatiert, die Textfarbe des untergeordneten Lesezeichens in Grün geändert und dem untergeordneten Lesezeichen ein kursives Symbol hinzugefügt.

## Umgang mit Ereignissen

Mit Lesezeichen können auch Aktionen verknüpft sein. Sie können beispielsweise Aktionen hinzufügen, die ausgelöst werden, wenn ein Benutzer auf ein Lesezeichen klickt. So können Sie mit Lesezeichen-Klickereignissen umgehen:

```java
// Fügen Sie einem Lesezeichen eine Aktion hinzu
GoToAction action = new GoToAction(pdfDocument.getPages().get_Item(1));
childBookmark.setAction(action);
```

In diesem Code haben wir einem untergeordneten Lesezeichen die Aktion „Gehe zu“ hinzugefügt, die den Benutzer beim Klicken zur zweiten Seite der PDF-Datei weiterleitet.

## Speichern des PDF

Nachdem Sie alle erforderlichen Lesezeichen hinzugefügt und deren Aussehen und Aktionen angepasst haben, können Sie das geänderte PDF-Dokument speichern:

```java
// Speichern Sie das PDF-Dokument
pdfDocument.save("output.pdf");
```

Ihr PDF-Dokument mit untergeordneten Lesezeichen ist jetzt fertig.

## Vollständiger Quellcode

Hier ist der vollständige Quellcode zum Hinzufügen untergeordneter Lesezeichen zu einem PDF-Dokument mit Aspose.PDF für Java:

```java
// Initialisieren Sie ein PDF-Dokument
Document pdfDocument = new Document();

// Fügen Sie Seiten zum PDF hinzu
pdfDocument.getPages().add();
pdfDocument.getPages().add();

// Erstellen Sie übergeordnete Lesezeichen
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

// Passen Sie das Erscheinungsbild des Lesezeichens an
parentBookmark.setItalic(true);
childBookmark.setForegroundColor(Color.getGreen());
childBookmark.setIcon(OutlineItemCollection.getItalicIcon());

// Fügen Sie einem Lesezeichen eine Aktion hinzu
GoToAction action = new GoToAction(pdfDocument.getPages().get_Item(1));
childBookmark.setAction(action);

// Speichern Sie das PDF-Dokument
pdfDocument.save("output.pdf");
```

## Abschluss

Das Hinzufügen untergeordneter Lesezeichen zu PDFs mit Aspose.PDF für Java ist eine leistungsstarke Funktion, die die Navigation und Organisation Ihrer Dokumente verbessert. Indem Sie die in diesem Artikel beschriebenen Schritte befolgen, können Sie gut strukturierte PDFs mit übergeordneten und untergeordneten Lesezeichen erstellen, deren Erscheinungsbild anpassen und sogar Aktionen hinzufügen, um die Benutzererfahrung zu verbessern.

## FAQs

### Wie kann ich Aspose.PDF für Java herunterladen?

 Sie können Aspose.PDF für Java von der Website herunterladen[Hier](https://releases.aspose.com/pdf/java/).

### Werden untergeordnete Lesezeichen in allen PDF-Viewern unterstützt?

Ja, untergeordnete Lesezeichen werden in den meisten modernen PDF-Viewern unterstützt und bieten eine verbesserte Benutzererfahrung beim Navigieren durch PDF-Dokumente.

### Kann ich das Erscheinungsbild von Lesezeichen weiter anpassen?

Ja, Sie können das Erscheinungsbild von Lesezeichen anpassen, indem Sie Textstile, Farben und Symbole an das Design Ihres Dokuments anpassen.

### Welche anderen Aktionen kann ich zu Lesezeichen hinzufügen?

Neben „GoTo“-Aktionen können Sie Aktionen wie „URI“-Aktionen zum Öffnen von Weblinks oder „JavaScript“-Aktionen zum Ausführen benutzerdefinierter Skripts hinzufügen, wenn auf ein Lesezeichen geklickt wird.

### Ist Aspose.PDF für Java für kommerzielle Projekte geeignet?

Ja, Aspose.PDF für Java eignet sich sowohl für private als auch für kommerzielle Projekte und bietet eine breite Palette an Funktionen zur PDF-Bearbeitung und -Generierung.