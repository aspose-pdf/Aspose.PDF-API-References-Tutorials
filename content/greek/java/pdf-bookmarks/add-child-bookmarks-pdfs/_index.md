---
title: Προσθήκη παιδικών σελιδοδεικτών σε αρχεία PDF
linktitle: Προσθήκη παιδικών σελιδοδεικτών σε αρχεία PDF
second_title: Aspose.PDF Java PDF Processing API
description: Μάθετε πώς να βελτιώνετε έγγραφα PDF με θυγατρικούς σελιδοδείκτες χρησιμοποιώντας το Aspose.PDF για Java. Οδηγός βήμα προς βήμα με παραδείγματα κώδικα για βελτιωμένη πλοήγηση και οργάνωση.
type: docs
weight: 11
url: /el/java/pdf-bookmarks/add-child-bookmarks-pdfs/
---

## Εισαγωγή στην προσθήκη παιδικών σελιδοδεικτών σε αρχεία PDF

Σε αυτό το άρθρο, θα διερευνήσουμε πώς να προσθέσετε θυγατρικούς σελιδοδείκτες σε έγγραφα PDF χρησιμοποιώντας το Aspose.PDF για Java. Οι θυγατρικοί σελιδοδείκτες είναι ένας βολικός τρόπος οργάνωσης και πλοήγησης στο περιεχόμενο ενός εγγράφου PDF, διευκολύνοντας τους χρήστες να βρίσκουν συγκεκριμένες ενότητες ή θέματα μέσα στο έγγραφο.

## Προαπαιτούμενα

Πριν προχωρήσουμε στην υλοποίηση, βεβαιωθείτε ότι έχετε τις ακόλουθες προϋποθέσεις:

- Το περιβάλλον ανάπτυξης Java είναι εγκατεστημένο στο σύστημά σας.
-  Aspose.PDF για βιβλιοθήκη Java. Μπορείτε να το κατεβάσετε από[εδώ](https://releases.aspose.com/pdf/java/).

## Ρύθμιση του περιβάλλοντος

1. Κατεβάστε τη βιβλιοθήκη Aspose.PDF για Java από τον παρεχόμενο σύνδεσμο.
2. Προσθέστε τη βιβλιοθήκη στο έργο σας Java.

Τώρα, ας ξεκινήσουμε δημιουργώντας ένα νέο έγγραφο PDF και προσθέτοντας θυγατρικούς σελιδοδείκτες σε αυτό βήμα προς βήμα.

## Δημιουργία νέου εγγράφου PDF

Για να ξεκινήσουμε, πρέπει να αρχικοποιήσουμε ένα έγγραφο PDF και να προσθέσουμε σελίδες σε αυτό. Ακολουθεί το απόσπασμα κώδικα για να ξεκινήσετε:

```java
// Αρχικοποιήστε ένα έγγραφο PDF
Document pdfDocument = new Document();

// Προσθήκη σελίδων στο PDF
pdfDocument.getPages().add();
pdfDocument.getPages().add();
```

Σε αυτό το παράδειγμα, δημιουργήσαμε ένα νέο έγγραφο PDF και προσθέσαμε δύο σελίδες σε αυτό.

## Προσθήκη γονικών σελιδοδεικτών

Οι γονικοί σελιδοδείκτες χρησιμεύουν ως οι κύριες ενότητες ή κατηγορίες στο έγγραφό σας PDF. Ας δημιουργήσουμε μερικούς γονικούς σελιδοδείκτες:

```java
// Δημιουργία γονικών σελιδοδεικτών
OutlineItemCollection outline = pdfDocument.getOutlines();
OutlineItemCollection parentBookmark = new OutlineItemCollection(outline);
parentBookmark.setTitle("Parent Bookmark 1");
outline.add(parentBookmark);

parentBookmark = new OutlineItemCollection(outline);
parentBookmark.setTitle("Parent Bookmark 2");
outline.add(parentBookmark);
```

Προσθέσαμε δύο γονικούς σελιδοδείκτες, τον "Γονικό σελιδοδείκτη 1" και τον "Γονικό σελιδοδείκτη 2".

## Προσθήκη παιδικών σελιδοδεικτών

Τώρα, ήρθε η ώρα να προσθέσουμε θυγατρικούς σελιδοδείκτες στους γονικούς σελιδοδείκτες που δημιουργήσαμε νωρίτερα. Οι θυγατρικοί σελιδοδείκτες αντιπροσωπεύουν συγκεκριμένα θέματα ή υποενότητες σε κάθε γονικό σελιδοδείκτη. Δείτε πώς μπορείτε να το κάνετε:

```java
// Προσθήκη θυγατρικών σελιδοδεικτών στον Γονικό σελιδοδείκτη 1
OutlineItemCollection childBookmark = new OutlineItemCollection(outline);
childBookmark.setTitle("Child Bookmark 1.1");
parentBookmark.add(childBookmark);

childBookmark = new OutlineItemCollection(outline);
childBookmark.setTitle("Child Bookmark 1.2");
parentBookmark.add(childBookmark);

//Προσθήκη θυγατρικών σελιδοδεικτών στο Γονικό σελιδοδείκτη 2
childBookmark = new OutlineItemCollection(outline);
childBookmark.setTitle("Child Bookmark 2.1");
parentBookmark.add(childBookmark);
```

Προσθέσαμε θυγατρικούς σελιδοδείκτες τόσο στον "Γονικό σελιδοδείκτη 1" και στον "Γονικό σελιδοδείκτη 2".

## Προσαρμογή της εμφάνισης σελιδοδεικτών

Μπορείτε να προσαρμόσετε την εμφάνιση των σελιδοδεικτών αλλάζοντας το κείμενο και το στυλ τους. Επιπλέον, μπορείτε να προσθέσετε εικονίδια σε σελιδοδείκτες για καλύτερη οπτική αναπαράσταση. Ακολουθεί ένα παράδειγμα για το πώς να το κάνετε:

```java
// Προσαρμόστε την εμφάνιση σελιδοδεικτών
parentBookmark.setItalic(true);
childBookmark.setForegroundColor(Color.getGreen());
childBookmark.setIcon(OutlineItemCollection.getItalicIcon());
```

Σε αυτό το παράδειγμα, κάναμε τον γονικό σελιδοδείκτη πλάγιο, αλλάξαμε το χρώμα κειμένου του θυγατρικού σελιδοδείκτη σε πράσινο και προσθέσαμε ένα πλάγιο εικονίδιο στον θυγατρικό σελιδοδείκτη.

## Χειρισμός συμβάντων

Οι σελιδοδείκτες μπορούν επίσης να έχουν ενέργειες που σχετίζονται με αυτούς. Για παράδειγμα, μπορείτε να προσθέσετε ενέργειες που ενεργοποιούνται όταν ένας χρήστης κάνει κλικ σε έναν σελιδοδείκτη. Δείτε πώς μπορείτε να χειριστείτε τα συμβάντα κλικ σελιδοδεικτών:

```java
// Προσθήκη ενέργειας σε σελιδοδείκτη
GoToAction action = new GoToAction(pdfDocument.getPages().get_Item(1));
childBookmark.setAction(action);
```

Σε αυτόν τον κώδικα, έχουμε προσθέσει μια ενέργεια "Μετάβαση" σε έναν θυγατρικό σελιδοδείκτη που θα μεταφέρει τον χρήστη στη δεύτερη σελίδα του PDF όταν κάνει κλικ.

## Αποθήκευση του PDF

Αφού προσθέσετε όλους τους απαραίτητους σελιδοδείκτες και προσαρμόσετε την εμφάνιση και τις ενέργειές τους, μπορείτε να αποθηκεύσετε το τροποποιημένο έγγραφο PDF:

```java
// Αποθηκεύστε το έγγραφο PDF
pdfDocument.save("output.pdf");
```

Το έγγραφο PDF με θυγατρικούς σελιδοδείκτες είναι τώρα έτοιμο.

## Πλήρης Πηγαίος Κώδικας

Ακολουθεί ο πλήρης πηγαίος κώδικας για την προσθήκη θυγατρικών σελιδοδεικτών σε ένα έγγραφο PDF χρησιμοποιώντας το Aspose.PDF για Java:

```java
// Αρχικοποιήστε ένα έγγραφο PDF
Document pdfDocument = new Document();

// Προσθήκη σελίδων στο PDF
pdfDocument.getPages().add();
pdfDocument.getPages().add();

// Δημιουργία γονικών σελιδοδεικτών
OutlineItemCollection outline = pdfDocument.getOutlines();
OutlineItemCollection parentBookmark = new OutlineItemCollection(outline);
parentBookmark.setTitle("Parent Bookmark 1");
outline.add(parentBookmark);

parentBookmark = new OutlineItemCollection(outline);
parentBookmark.setTitle("Parent Bookmark 2");
outline.add(parentBookmark);

// Προσθήκη θυγατρικών σελιδοδεικτών στον Γονικό σελιδοδείκτη 1
OutlineItemCollection childBookmark = new OutlineItemCollection(outline);
childBookmark.setTitle("Child Bookmark 1.1");
parentBookmark.add(childBookmark);

childBookmark = new OutlineItemCollection(outline);
childBookmark.setTitle("Child Bookmark 1.2");
parentBookmark.add(childBookmark);

//Προσθήκη θυγατρικών σελιδοδεικτών στο Γονικό σελιδοδείκτη 2
childBookmark = new OutlineItemCollection(outline);
childBookmark.setTitle("Child Bookmark 2.1");
parentBookmark.add(childBookmark);

// Προσαρμόστε την εμφάνιση σελιδοδεικτών
parentBookmark.setItalic(true);
childBookmark.setForegroundColor(Color.getGreen());
childBookmark.setIcon(OutlineItemCollection.getItalicIcon());

// Προσθήκη ενέργειας σε σελιδοδείκτη
GoToAction action = new GoToAction(pdfDocument.getPages().get_Item(1));
childBookmark.setAction(action);

// Αποθηκεύστε το έγγραφο PDF
pdfDocument.save("output.pdf");
```

## Σύναψη

Η προσθήκη θυγατρικών σελιδοδεικτών σε αρχεία PDF χρησιμοποιώντας το Aspose.PDF για Java είναι μια ισχυρή δυνατότητα που βελτιώνει την πλοήγηση και την οργάνωση των εγγράφων σας. Ακολουθώντας τα βήματα που περιγράφονται σε αυτό το άρθρο, μπορείτε να δημιουργήσετε καλά δομημένα αρχεία PDF με γονικούς και θυγατρικούς σελιδοδείκτες, να προσαρμόσετε την εμφάνισή τους και ακόμη και να προσθέσετε ενέργειες για τη βελτίωση της εμπειρίας χρήστη.

## Συχνές ερωτήσεις

### Πώς μπορώ να κατεβάσω το Aspose.PDF για Java;

 Μπορείτε να κάνετε λήψη του Aspose.PDF για Java από τον ιστότοπο[εδώ](https://releases.aspose.com/pdf/java/).

### Υποστηρίζονται οι θυγατρικοί σελιδοδείκτες σε όλα τα προγράμματα προβολής PDF;

Ναι, οι παιδικοί σελιδοδείκτες υποστηρίζονται στα περισσότερα σύγχρονα προγράμματα προβολής PDF και παρέχουν μια βελτιωμένη εμπειρία χρήστη για πλοήγηση στα έγγραφα PDF.

### Μπορώ να προσαρμόσω περαιτέρω την εμφάνιση των σελιδοδεικτών;

Ναι, μπορείτε να προσαρμόσετε την εμφάνιση των σελιδοδεικτών προσαρμόζοντας στυλ κειμένου, χρώματα και εικονίδια ώστε να ταιριάζουν με τη σχεδίαση του εγγράφου σας.

### Ποιες άλλες ενέργειες μπορώ να προσθέσω στους σελιδοδείκτες;

Εκτός από τις ενέργειες "GoTo", μπορείτε να προσθέσετε ενέργειες όπως ενέργειες "URI" για να ανοίξετε συνδέσμους ιστού ή ενέργειες "JavaScript" για να εκτελέσετε προσαρμοσμένα σενάρια όταν γίνεται κλικ σε έναν σελιδοδείκτη.

### Είναι το Aspose.PDF για Java κατάλληλο για εμπορικά έργα;

Ναι, το Aspose.PDF για Java είναι κατάλληλο τόσο για προσωπικά όσο και για εμπορικά έργα και προσφέρει ένα ευρύ φάσμα δυνατοτήτων για χειρισμό και δημιουργία PDF.