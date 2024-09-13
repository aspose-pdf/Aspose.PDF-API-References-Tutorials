---
title: Ενσωματωμένα στοιχεία δομής
linktitle: Ενσωματωμένα στοιχεία δομής
second_title: Aspose.PDF για Αναφορά API .NET
description: Οδηγός βήμα προς βήμα για τη χρήση ηλεκτρονικών δομικών στοιχείων με το Aspose.PDF για .NET. Οργανώστε τα PDF σας με επικεφαλίδες και παραγράφους.
type: docs
weight: 110
url: /el/net/programming-with-tagged-pdf/inline-structure-elements/
---
Σε αυτόν τον οδηγό βήμα προς βήμα, θα σας δείξουμε πώς να χρησιμοποιείτε στοιχεία ενσωματωμένης δομής με το Aspose.PDF για .NET. Το Aspose.PDF είναι μια ισχυρή βιβλιοθήκη που σας επιτρέπει να χειρίζεστε έγγραφα PDF μέσω προγραμματισμού. Τα στοιχεία ενσωματωμένης δομής σάς επιτρέπουν να δημιουργήσετε μια ιεραρχική δομή στο έγγραφο PDF σας χρησιμοποιώντας επικεφαλίδες διαφορετικών επιπέδων και παραγράφων.

Ας βουτήξουμε στον κώδικα και ας μάθουμε πώς να χρησιμοποιούμε στοιχεία ενσωματωμένης δομής με το Aspose.PDF για .NET.

## Προαπαιτούμενα

Πριν ξεκινήσετε, βεβαιωθείτε ότι έχετε τα ακόλουθα:

1. Εγκαταστάθηκε η βιβλιοθήκη Aspose.PDF για .NET.
2. Βασική γνώση της γλώσσας προγραμματισμού C#.

## Βήμα 1: Ρύθμιση περιβάλλοντος

Για να ξεκινήσετε, ανοίξτε το περιβάλλον ανάπτυξης C# και δημιουργήστε ένα νέο έργο. Βεβαιωθείτε ότι έχετε προσθέσει μια αναφορά στη βιβλιοθήκη Aspose.PDF για .NET στο έργο σας.

```csharp
// Η διαδρομή προς τον κατάλογο εγγράφων.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Βήμα 2: Δημιουργία του εγγράφου

 Το πρώτο βήμα είναι να δημιουργήσετε ένα νέο έγγραφο PDF χρησιμοποιώντας το`Document` τάξη.

```csharp
// Δημιουργήστε το έγγραφο PDF
Document document = new Document();
```

## Βήμα 3: Εργαστείτε με περιεχόμενο με ετικέτα

Στη συνέχεια, μπορούμε να εργαστούμε με το περιεχόμενο του εγγράφου με ετικέτα.

```csharp
// Λάβετε το περιεχόμενο του εγγράφου με ετικέτα
ITaggedContent taggedContent = document.TaggedContent;
```

## Βήμα 4: Ορίστε τον τίτλο και τη γλώσσα του εγγράφου

Μπορούμε τώρα να ορίσουμε τον τίτλο και τη γλώσσα του εγγράφου.

```csharp
// Καθορίστε τον τίτλο και τη γλώσσα του εγγράφου
taggedContent.SetTitle("Tagged PDF document");
taggedContent.SetLanguage("fr-FR");
```

## Βήμα 5: Προσθέστε δομικά στοιχεία στο διαδίκτυο

Τώρα θα προσθέσουμε στοιχεία ενσωματωμένης δομής, όπως επικεφαλίδες διαφορετικών επιπέδων και παραγράφων στο έγγραφό μας.

```csharp
// Λάβετε το στοιχείο δομής ρίζας
StructureElement rootElement = taggedContent.RootElement;

// Προσθέστε κεφαλίδες διαφορετικών επιπέδων
HeaderElement h1 = taggedContent.CreateHeaderElement(1);
HeaderElement h2 = taggedContent.CreateHeaderElement(2);
HeaderElement h3 = taggedContent.CreateHeaderElement(3);
HeaderElement h4 = taggedContent.CreateHeaderElement(4);
HeaderElement h5 = taggedContent.CreateHeaderElement(5);
HeaderElement h6 = taggedContent.CreateHeaderElement(6);
rootElement.AppendChild(h1);
rootElement.AppendChild(h2);
rootElement.AppendChild(h3);
rootElement.AppendChild(h4);
rootElement.AppendChild(h5);
rootElement.AppendChild(h6);

// Προσθέστε περιεχόμενο σε κάθε κεφαλίδα
SpanElement spanH11 = taggedContent.CreateSpanElement();
spanH11.SetText("H1.");
h1.AppendChild(spanH11);
SpanElement spanH12 = taggedContent.CreateSpanElement();
spanH12.SetText("Level 1 header");
h1.AppendChild(spanH12);

SpanElement spanH21 = taggedContent.CreateSpanElement();
spanH21.SetText("H2.");
h2.AppendChild(spanH21);
SpanElement spanH22 = taggedContent.CreateSpanElement();
spanH22.SetText("Level 2 header");
h2.AppendChild(spanH22);

SpanElement spanH31 = taggedContent.CreateSpanElement();
spanH31.SetText("H3.");
h3.AppendChild(spanH31);
SpanElement spanH32 = taggedContent.CreateSpanElement();
spanH32.SetText("Level 3 header");
h3.AppendChild(spanH32);

SpanElement spanH41 = taggedContent.CreateSpanElement();
spanH41.SetText("H4.");
h4.AppendChild(spanH41);
SpanElement spanH42 = taggedContent.CreateSpanElement();
spanH42.SetText("Level 4 header");
h4.AppendChild(spanH42);

SpanElement spanH51 = taggedContent.CreateSpanElement();
spanH51.SetText("H5.");
h5.AppendChild(spanH51);
SpanElement spanH52 = taggedContent.CreateSpanElement();
spanH52.SetText("Level 5 header");
h5.AppendChild(spanH52);

SpanElement spanH61 = taggedContent.CreateSpanElement();
spanH61.SetText("H6.");
h6.AppendChild(spanH61);
SpanElement spanH62 = taggedContent.CreateSpanElement();
spanH62.SetText("Heading level 6");
h6.AppendChild(spanH62);

// Προσθέστε μια παράγραφο
ParagraphElement p = taggedContent.CreateParagraphElement();
p.SetText("P.");
rootElement.AppendChild(p);

// Προσθέστε περιεχόμενο στην παράγραφο
SpanElement span1 = taggedContent.CreateSpanElement();
span1.SetText("Lorem ipsum dolor sit amet, consectetur adipiscing elit.");
p.AppendChild(span1);
SpanElement span2 = taggedContent.CreateSpanElement();
span2.SetText("Aenean nec lectus ac sem faucibus imperdiet.");
p.AppendChild(span2);
SpanElement span3 = taggedContent.CreateSpanElement();
span3.SetText("Sed ut erat ac magna ullamcorper hendrerit.");
p.AppendChild(span3);
SpanElement span4 = taggedContent.CreateSpanElement();
span4.SetText("Cras pellentesque libero semper, gravida magna sed, luctus leo.");
p.AppendChild(span4);
SpanElement span5 = taggedContent.CreateSpanElement();
span5.SetText("Fusce lectus odio, laoreet nec ullamcorper ut, molestie eu elit.");
p.AppendChild(span5);
SpanElement span6 = taggedContent.CreateSpanElement();
span6.SetText("Interdum et malesuada fames ac ante ipsum primis in faucibus. ");
p.AppendChild(span6);
SpanElement span7 = taggedContent.CreateSpanElement();
span7.SetText("Aliquam lacinia sit amet elit ac consectetur. So cursus condimentum ligula, vitae volutpat sem tristique eget. ");
p.AppendChild(span7);
SpanElement span8 = taggedContent.CreateSpanElement();
span8.SetText("Nulla in consectetur massa. Vestibulum vitae lobortis ante. Nulla ullamcorper pellentesque justo rhoncus accumsan. ");
p.AppendChild(span8);
SpanElement span9 = taggedContent.CreateSpanElement();
span9.SetText("Mauris ornare eu odio non lacinia. Aliquam massa leo, rhoncus ac iaculis eget, tempus et magna. Sed non consectetur elit.");
p.AppendChild(span9);
SpanElement span10 = taggedContent.CreateSpanElement();
span10.SetText("Sed vulputate, quam sed lacinia luctus, ipsum nibh fringilla purus, vitae posuere risus odio id massa. Cras sed venenatis lacus.");
p.AppendChild(span10);
```

Εδώ δημιουργούμε στοιχεία εσωτερικής δομής, όπως επικεφαλίδες διαφορετικών επιπέδων και μια παράγραφο, και προσθέτουμε περιεχόμενο σε αυτά.

## Βήμα 6: Αποθηκεύστε το έγγραφο PDF με ετικέτα

Τέλος, αποθηκεύουμε το έγγραφο PDF με ετικέτα.

```csharp
// Αποθηκεύστε το έγγραφο PDF με ετικέτα
document.Save(dataDir + "InlineStructureElements.pdf");
```

### Δείγμα πηγαίου κώδικα για Inline Structure Elements χρησιμοποιώντας Aspose.PDF για .NET 

```csharp

// Η διαδρομή προς τον κατάλογο εγγράφων.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Δημιουργία εγγράφου Pdf
Document document = new Document();

// Λάβετε Περιεχόμενο για εργασία με το TaggedPdf
ITaggedContent taggedContent = document.TaggedContent;

// Ορίστε τον τίτλο και τη γλώσσα για το Documnet
taggedContent.SetTitle("Tagged Pdf Document");
taggedContent.SetLanguage("en-US");

// Λήψη στοιχείου δομής ρίζας
StructureElement rootElement = taggedContent.RootElement;
HeaderElement h1 = taggedContent.CreateHeaderElement(1);
HeaderElement h2 = taggedContent.CreateHeaderElement(2);
HeaderElement h3 = taggedContent.CreateHeaderElement(3);
HeaderElement h4 = taggedContent.CreateHeaderElement(4);
HeaderElement h5 = taggedContent.CreateHeaderElement(5);
HeaderElement h6 = taggedContent.CreateHeaderElement(6);
rootElement.AppendChild(h1);
rootElement.AppendChild(h2);
rootElement.AppendChild(h3);
rootElement.AppendChild(h4);
rootElement.AppendChild(h5);
rootElement.AppendChild(h6);
SpanElement spanH11 = taggedContent.CreateSpanElement();
spanH11.SetText("H1. ");
h1.AppendChild(spanH11);
SpanElement spanH12 = taggedContent.CreateSpanElement();
spanH12.SetText("Level 1 Header");
h1.AppendChild(spanH12);
SpanElement spanH21 = taggedContent.CreateSpanElement();
spanH21.SetText("H2. ");
h2.AppendChild(spanH21);
SpanElement spanH22 = taggedContent.CreateSpanElement();
spanH22.SetText("Level 2 Header");
h2.AppendChild(spanH22);
SpanElement spanH31 = taggedContent.CreateSpanElement();
spanH31.SetText("H3. ");
h3.AppendChild(spanH31);
SpanElement spanH32 = taggedContent.CreateSpanElement();
spanH32.SetText("Level 3 Header");
h3.AppendChild(spanH32);
SpanElement spanH41 = taggedContent.CreateSpanElement();
spanH41.SetText("H4. ");
h4.AppendChild(spanH41);
SpanElement spanH42 = taggedContent.CreateSpanElement();
spanH42.SetText("Level 4 Header");
h4.AppendChild(spanH42);
SpanElement spanH51 = taggedContent.CreateSpanElement();
spanH51.SetText("H5. ");
h5.AppendChild(spanH51);
SpanElement spanH52 = taggedContent.CreateSpanElement();
spanH52.SetText("Level 5 Header");
h5.AppendChild(spanH52);
SpanElement spanH61 = taggedContent.CreateSpanElement();
spanH61.SetText("H6. ");
h6.AppendChild(spanH61);
SpanElement spanH62 = taggedContent.CreateSpanElement();
spanH62.SetText("Level 6 Header");
h6.AppendChild(spanH62);
ParagraphElement p = taggedContent.CreateParagraphElement();
p.SetText("P. ");
rootElement.AppendChild(p);
SpanElement span1 = taggedContent.CreateSpanElement();
span1.SetText("Lorem ipsum dolor sit amet, consectetur adipiscing elit. ");
p.AppendChild(span1);
SpanElement span2 = taggedContent.CreateSpanElement();
span2.SetText("Aenean nec lectus ac sem faucibus imperdiet. ");
p.AppendChild(span2);
SpanElement span3 = taggedContent.CreateSpanElement();
span3.SetText("Sed ut erat ac magna ullamcorper hendrerit. ");
p.AppendChild(span3);
SpanElement span4 = taggedContent.CreateSpanElement();
span4.SetText("Cras pellentesque libero semper, gravida magna sed, luctus leo. ");
p.AppendChild(span4);
SpanElement span5 = taggedContent.CreateSpanElement();
span5.SetText("Fusce lectus odio, laoreet nec ullamcorper ut, molestie eu elit. ");
p.AppendChild(span5);
SpanElement span6 = taggedContent.CreateSpanElement();
span6.SetText("Interdum et malesuada fames ac ante ipsum primis in faucibus. ");
p.AppendChild(span6);
SpanElement span7 = taggedContent.CreateSpanElement();
span7.SetText("Aliquam lacinia sit amet elit ac consectetur. Donec cursus condimentum ligula, vitae volutpat sem tristique eget. ");
p.AppendChild(span7);
SpanElement span8 = taggedContent.CreateSpanElement();
span8.SetText("Nulla in consectetur massa. Vestibulum vitae lobortis ante. Nulla ullamcorper pellentesque justo rhoncus accumsan. ");
p.AppendChild(span8);
SpanElement span9 = taggedContent.CreateSpanElement();
span9.SetText("Mauris ornare eu odio non lacinia. Aliquam massa leo, rhoncus ac iaculis eget, tempus et magna. Sed non consectetur elit. ");
p.AppendChild(span9);
SpanElement span10 = taggedContent.CreateSpanElement();
span10.SetText("Sed vulputate, quam sed lacinia luctus, ipsum nibh fringilla purus, vitae posuere risus odio id massa. Cras sed venenatis lacus.");
p.AppendChild(span10);

// Αποθήκευση εγγράφου Pdf με ετικέτα
document.Save(dataDir + "InlineStructureElements.pdf");

```

## Σύναψη

Συγχαρητήρια ! Έχετε μάθει πώς να χρησιμοποιείτε στοιχεία ενσωματωμένης δομής με το Aspose.PDF για .NET. Τώρα μπορείτε να δημιουργήσετε μια ιεραρχική δομή στο έγγραφο PDF σας χρησιμοποιώντας επικεφαλίδες διαφορετικών επιπέδων και παραγράφων. Εξερευνήστε περισσότερες δυνατότητες του Aspose.PDF για να ανακαλύψετε όλες τις δυνατότητές του.

### Συχνές ερωτήσεις

#### Ε: Ποια είναι τα στοιχεία ενσωματωμένης δομής σε ένα έγγραφο PDF και πώς συμβάλλουν στη δημιουργία μιας ιεραρχικής δομής;

Α: Τα στοιχεία ενσωματωμένης δομής σε ένα έγγραφο PDF, όπως επικεφαλίδες διαφορετικών επιπέδων και παραγράφων, χρησιμοποιούνται για τη δημιουργία μιας ιεραρχικής δομής που οργανώνει και παρουσιάζει το περιεχόμενο με δομημένο τρόπο. Αυτά τα στοιχεία σάς επιτρέπουν να δημιουργήσετε μια σαφή ιεραρχία και ροή πληροφοριών μέσα στο έγγραφο.

#### Ε: Πώς μπορούν τα στοιχεία ενσωματωμένης δομής να βελτιώσουν την αναγνωσιμότητα και την οργάνωση ενός εγγράφου PDF;

Α: Τα στοιχεία ενσωματωμένης δομής, ιδιαίτερα οι επικεφαλίδες και οι παράγραφοι, συμβάλλουν στη βελτίωση της αναγνωσιμότητας και της οργάνωσης ενός εγγράφου PDF παρέχοντας μια λογική δομή. Οι επικεφαλίδες υποδεικνύουν διαφορετικά επίπεδα σημασίας και βοηθούν τους αναγνώστες να περιηγηθούν στο περιεχόμενο, ενώ οι παράγραφοι ομαδοποιούν τις σχετικές πληροφορίες μαζί.

#### Ε: Πώς το Aspose.PDF για .NET διευκολύνει τη χρήση στοιχείων ενσωματωμένης δομής;

Α: Το Aspose.PDF για .NET προσφέρει κλάσεις και μεθόδους για τη δημιουργία και τον χειρισμό στοιχείων εσωτερικής δομής, όπως επικεφαλίδες και παραγράφους. Αυτά τα στοιχεία μπορούν να προσαρμοστούν, να οργανωθούν ιεραρχικά και να εμπλουτιστούν με περιεχόμενο για τη βελτίωση της οπτικής παρουσίασης και της προσβασιμότητας του εγγράφου.

####  Ε: Ποιος είναι ο σκοπός του`taggedContent` object in relation to inline structure elements?

 Α: Το`taggedContent` αντικείμενο, που λαμβάνεται από το`TaggedContent` ιδιοκτησία του α`Document`, σας επιτρέπει να εργάζεστε με δομημένα στοιχεία, συμπεριλαμβανομένων των στοιχείων ενσωματωμένης δομής. Σας δίνει τη δυνατότητα να δημιουργήσετε, να προσαρμόσετε και να οργανώσετε επικεφαλίδες και παραγράφους μέσα στο έγγραφο.

#### Ε: Πώς βοηθούν τα στοιχεία εσωτερικής δομής στη δημιουργία μιας ξεκάθαρης ιεραρχίας εγγράφων;

Α: Στοιχεία εσωτερικής δομής, όπως επικεφαλίδες διαφορετικών επιπέδων, συμβάλλουν στη δημιουργία μιας σαφούς και καλά καθορισμένης ιεραρχίας στο έγγραφο. Οι αναγνώστες μπορούν να αναγνωρίσουν γρήγορα τα κύρια θέματα, τα υποθέματα και το σχετικό περιεχόμενο, κάνοντας το έγγραφο πιο εύκολο στην πλοήγηση και κατανόηση.

#### Ε: Μπορώ να προσαρμόσω την εμφάνιση και τη μορφοποίηση των στοιχείων ενσωματωμένης δομής χρησιμοποιώντας το Aspose.PDF για .NET;

Α: Ναι, μπορείτε να προσαρμόσετε την εμφάνιση και τη μορφοποίηση των στοιχείων ενσωματωμένης δομής. Μπορείτε να ορίσετε ιδιότητες όπως στυλ γραμματοσειράς, μεγέθη, χρώματα, στοίχιση, εσοχή και διάστημα για να επιτύχετε την επιθυμητή οπτική παρουσίαση για επικεφαλίδες και παραγράφους.

#### Ε: Πώς μπορώ να δημιουργήσω και να προσθέσω επικεφαλίδες διαφορετικών επιπέδων σε ένα έγγραφο PDF χρησιμοποιώντας στοιχεία ενσωματωμένης δομής στο Aspose.PDF για .NET;

 Α: Μπορείτε να δημιουργήσετε επικεφαλίδες διαφορετικών επιπέδων χρησιμοποιώντας το`CreateHeaderElement`μέθοδο και στη συνέχεια προσαρτήστε τα στο στοιχείο δομής ρίζας. Στη συνέχεια, μπορείτε να προσθέσετε περιεχόμενο σε κάθε στοιχείο επικεφαλίδας χρησιμοποιώντας το`CreateSpanElement` μέθοδος δημιουργίας περιοχών κειμένου.

#### Ε: Μπορώ να χρησιμοποιήσω στοιχεία ενσωματωμένης δομής για να δημιουργήσω λίστες, κουκκίδες ή άλλους τύπους οργάνωσης περιεχομένου σε ένα έγγραφο PDF;

Α: Ενώ τα ίδια τα στοιχεία ενσωματωμένης δομής χρησιμοποιούνται κυρίως για επικεφαλίδες και παραγράφους, μπορείτε να τα χρησιμοποιήσετε σε συνδυασμό με άλλες δυνατότητες που προσφέρει το Aspose.PDF για .NET για να δημιουργήσετε λίστες, σημεία κουκκίδων, πίνακες και άλλους τύπους οργάνωσης περιεχομένου για μια ολοκληρωμένη δομή εγγράφου.

#### Ε: Πώς συμβάλλουν τα στοιχεία ενσωματωμένης δομής στην προσβασιμότητα των εγγράφων;

Α: Τα στοιχεία εσωτερικής δομής διαδραματίζουν κρίσιμο ρόλο στη βελτίωση της προσβασιμότητας των εγγράφων. Οι σωστά δομημένες επικεφαλίδες και παράγραφοι παρέχουν μια σαφή ιεραρχία εγγράφων που βοηθά τους αναγνώστες οθόνης και άλλες βοηθητικές τεχνολογίες να ερμηνεύουν με ακρίβεια και να μεταφέρουν το περιεχόμενο σε χρήστες με αναπηρίες.

#### Ε: Μπορώ να εξερευνήσω πιο προηγμένες χρήσεις στοιχείων εσωτερικής δομής, όπως η δημιουργία διαδραστικών στοιχείων ή η ενσωμάτωση πολυμέσων;

Α: Απολύτως! Ενώ αυτό το σεμινάριο εστιάζει στη δημιουργία επικεφαλίδων και παραγράφων, το Aspose.PDF για .NET προσφέρει προηγμένες δυνατότητες για τη δημιουργία διαδραστικών στοιχείων, την ενσωμάτωση πολυμέσων, την προσθήκη υπερσυνδέσμων και πολλά άλλα. Ελέγξτε την τεκμηρίωση και τα παραδείγματα της βιβλιοθήκης για να εμβαθύνετε σε αυτές τις προηγμένες δυνατότητες.