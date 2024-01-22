---
title: Προσθήκη σχολιασμού lnk
linktitle: Προσθήκη σχολιασμού lnk
second_title: Aspose.PDF για Αναφορά API .NET
description: Μάθετε πώς να προσθέτετε τη δυνατότητα Ink Annotation σε έγγραφα PDF σε C# χρησιμοποιώντας το Aspose.PDF για .NET με οδηγό βήμα προς βήμα και πλήρη πηγαίο κώδικα.
type: docs
weight: 20
url: /el/net/annotations/addlnkannotation/
---
Το Aspose.PDF για .NET είναι μια ισχυρή βιβλιοθήκη που επιτρέπει στους προγραμματιστές να εκτελούν διάφορες λειτουργίες PDF. Μια τέτοια λειτουργία είναι η προσθήκη Ink Annotation σε έγγραφα PDF. Σε αυτό το άρθρο, θα παρέχουμε έναν οδηγό βήμα προς βήμα για να εξηγήσουμε τον πηγαίο κώδικα C# για την προσθήκη σχολιασμού μελανιού χρησιμοποιώντας το Aspose.PDF για .NET. Ας αρχίσουμε!

## Κατανόηση της δυνατότητας σχολιασμού μελανιού του Aspose.PDF για .NET

Πριν βουτήξουμε στον πηγαίο κώδικα C#, ας καταλάβουμε πρώτα τι είναι το Ink Annotation και τις χρήσεις του.

Το Ink Annotation είναι ένας τρόπος για να σχεδιάσετε σχολιασμούς μελάνης ελεύθερης μορφής σε έγγραφα PDF. Σας επιτρέπει να δημιουργείτε σχολιασμούς με μια γραφίδα ή ένα ποντίκι. Αυτή η δυνατότητα είναι χρήσιμη σε περιπτώσεις όπου χρειάζεται να σχεδιάσετε διαγράμματα, σκίτσα ή άλλους τύπους σχολιασμών.

## Βήμα 1: Δημιουργία νέου εγγράφου

Το πρώτο βήμα για την προσθήκη του Ink Annotation σε ένα έγγραφο PDF είναι η δημιουργία μιας νέας παρουσίας της κλάσης Document. Αυτό επιτυγχάνεται χρησιμοποιώντας το ακόλουθο απόσπασμα κώδικα:

```csharp
string dataDir = "YOUR DATA DIRECTORY";
Document doc = new Document();
Page pdfPage = doc.Pages.Add();
```

Εδώ, δημιουργούμε μια νέα παρουσία της κλάσης Document και προσθέτουμε μια νέα σελίδα σε αυτήν.

## Βήμα 2: Δημιουργία σχολιασμού μελανιού

Το επόμενο βήμα είναι να δημιουργήσετε μια παρουσία της κλάσης InkAnnotation. Αυτό γίνεται χρησιμοποιώντας το ακόλουθο απόσπασμα κώδικα:

```csharp
System.Drawing.Rectangle drect = new System.Drawing.Rectangle();
drect.Height = (int)pdfPage.Rect.Height;
drect.Width = (int)pdfPage.Rect.Width;
drect.X = 0;
drect.Y = 0;
Aspose.Pdf.Rectangle arect = Aspose.Pdf.Rectangle.FromRect(drect);
IList<Point[]> inkList = new List<Point[]>();
Aspose.Pdf.Point[] arrpt = new Aspose.Pdf.Point[3];
inkList.Add(arrpt);
arrpt[0] = new Aspose.Pdf.Point(100, 800);
arrpt[1] = new Aspose.Pdf.Point(200, 800);
arrpt[2] = new Aspose.Pdf.Point(200, 700);
InkAnnotation ia = new InkAnnotation(pdfPage, arect, inkList);
ia.Title = "XXX";
ia.Color = Aspose.Pdf.Color.LightBlue; // (GetColorFromString(stroke.InkColor));
ia.CapStyle = CapStyle.Rounded;
Border border = new Border(ia);
border.Width = 25;
ia.Opacity = 0.5;
pdfPage.Annotations.Add(ia);
```

Εδώ, δημιουργούμε πρώτα ένα ορθογώνιο χρησιμοποιώντας την κλάση System.Drawing.Rectangle και το μετατρέπουμε σε Aspose.Pdf.Rectangle χρησιμοποιώντας τη μέθοδο FromRect. Στη συνέχεια, δημιουργούμε μια παρουσία της κλάσης InkAnnotation χρησιμοποιώντας το ορθογώνιο, μια λίστα σημείων και τη σελίδα όπου προστίθεται ο σχολιασμός.

Στη συνέχεια, ορίσαμε διάφορες ιδιότητες του InkAnnotation, όπως τον τίτλο, το χρώμα, το στυλ κεφαλαίων, το περίγραμμα και την αδιαφάνεια. Τέλος, προσθέτουμε τον σχολιασμό στη σελίδα χρησιμοποιώντας τη μέθοδο Annotations.Add.

## Βήμα 3: Αποθήκευση του εγγράφου

Το τελευταίο βήμα είναι να αποθηκεύσετε το έγγραφο PDF με την προσθήκη του σχολιασμού μελανιού. Αυτό επιτυγχάνεται χρησιμοποιώντας το ακόλουθο απόσπασμα κώδικα:

```csharp
dataDir = dataDir + "AddlnkAnnotation_out.pdf";
doc.Save(dataDir);
```

Εδώ, ενώνουμε το όνομα του αρχείου εξόδου στον κατάλογο δεδομένων και αποθηκεύουμε το έγγραφο χρησιμοποιώντας τη μέθοδο Save.

### Παράδειγμα πηγαίου κώδικα για Προσθήκη σχολιασμού μελανιού χρησιμοποιώντας Aspose.PDF για .NET

```csharp
// Η διαδρομή προς τον κατάλογο εγγράφων.
string dataDir = "YOUR DATA DIRECTORY";


Document doc = new Document();
Page pdfPage = doc.Pages.Add();
System.Drawing.Rectangle drect = new System.Drawing.Rectangle();
drect.Height = (int)pdfPage.Rect.Height;
drect.Width = (int)pdfPage.Rect.Width;
drect.X = 0;
drect.Y = 0;
Aspose.Pdf.Rectangle arect = Aspose.Pdf.Rectangle.FromRect(drect);
IList<Point[]> inkList = new List<Point[]>();
Aspose.Pdf.Point[] arrpt = new Aspose.Pdf.Point[3];
inkList.Add(arrpt);
arrpt[0] = new Aspose.Pdf.Point(100, 800);
arrpt[1] = new Aspose.Pdf.Point(200, 800);
arrpt[2] = new Aspose.Pdf.Point(200, 700);
InkAnnotation ia = new InkAnnotation(pdfPage, arect, inkList);
ia.Title = "XXX";
ia.Color = Aspose.Pdf.Color.LightBlue; // (GetColorFromString(stroke.InkColor));
ia.CapStyle = CapStyle.Rounded;
Border border = new Border(ia);
border.Width = 25;
ia.Opacity = 0.5;
pdfPage.Annotations.Add(ia);

dataDir = dataDir + "AddlnkAnnotation_out.pdf";
// Αποθήκευση αρχείου εξόδου
doc.Save(dataDir);
```

## συμπέρασμα

Σε αυτό το σεμινάριο, εξερευνήσαμε τον τρόπο προσθήκης σχολιασμών μελανιού σε ένα έγγραφο PDF χρησιμοποιώντας το Aspose.PDF για .NET. Ακολουθώντας τον οδηγό βήμα προς βήμα και τον πηγαίο κώδικα C# που παρέχεται, οι προγραμματιστές μπορούν εύκολα να εφαρμόσουν τη λειτουργία Ink Annotation στις εφαρμογές επεξεργασίας PDF τους.

### Συχνές ερωτήσεις

#### Ε: Τι είναι το Ink Annotation σε ένα έγγραφο PDF;

Α: Ένας σχολιασμός μελάνης σε ένα έγγραφο PDF επιτρέπει στους χρήστες να σχεδιάζουν σχολιασμούς μελάνης ελεύθερης μορφής χρησιμοποιώντας γραφίδα ή ποντίκι. Χρησιμοποιείται συνήθως για την προσθήκη σκίτσων, διαγραμμάτων ή άλλων ελεύθερων σχολιασμών σε ένα PDF.

#### Ε: Μπορώ να προσαρμόσω την εμφάνιση του σχολιασμού μελανιού;

Α: Ναι, το Aspose.PDF για .NET παρέχει διάφορες ιδιότητες για την προσαρμογή της εμφάνισης του σχολιασμού μελανιού, όπως χρώμα, αδιαφάνεια, στυλ καπακιού, πλάτος περιγράμματος και άλλα. Οι προγραμματιστές μπορούν να προσαρμόσουν αυτές τις ιδιότητες για να καλύψουν τις συγκεκριμένες απαιτήσεις τους.

#### Ε: Είναι δυνατή η προσθήκη πολλών σχολιασμών μελανιού σε μία σελίδα PDF;

Α: Ναι, μπορείτε να προσθέσετε πολλαπλούς σχολιασμούς μελανιού σε μια σελίδα PDF χρησιμοποιώντας το Aspose.PDF για .NET. Κάθε σχολιασμός μελανιού μπορεί να έχει το δικό του σύνολο σημείων και προσαρμοσμένη εμφάνιση.

#### Ε: Μπορώ να προσθέσω σχολιασμούς μελανιού σε υπάρχοντα έγγραφα PDF;

Α: Ναι, το Aspose.PDF για .NET σάς επιτρέπει να προσθέτετε σχολιασμούς μελανιού τόσο στα πρόσφατα δημιουργημένα έγγραφα PDF όσο και στα υπάρχοντα αρχεία PDF. Μπορείτε να ανοίξετε ένα υπάρχον PDF, να προσθέσετε σχολιασμούς μελανιού και να αποθηκεύσετε το ενημερωμένο έγγραφο.

#### Ε: Ποιες είναι μερικές συνήθεις περιπτώσεις χρήσης για τους σχολιασμούς μελανιού σε έγγραφα PDF;

Α: Οι σχολιασμοί μελανιού είναι χρήσιμοι για ένα ευρύ φάσμα εφαρμογών, συμπεριλαμβανομένης της προσθήκης υπογραφών ή χειρόγραφων σημειώσεων σε φόρμες PDF, σχολιασμού αρχιτεκτονικών σχεδίων ή μηχανικών σχεδίων και επισήμανσης εγγράφων για συλλογική αναθεώρηση.