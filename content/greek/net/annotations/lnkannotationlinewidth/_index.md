---
title: lnk Πλάτος γραμμής σχολιασμού
linktitle: lnk Πλάτος γραμμής σχολιασμού
second_title: Aspose.PDF για Αναφορά API .NET
description: Αυτό το άρθρο παρέχει έναν οδηγό βήμα προς βήμα για τη ρύθμιση του πλάτους γραμμής του σχολιασμού lnk χρησιμοποιώντας το Aspose.PDF για .NET.
type: docs
weight: 110
url: /el/net/annotations/lnkannotationlinewidth/
---
Το Aspose.PDF είναι ένα ισχυρό και ευρέως χρησιμοποιούμενο εργαλείο για εργασία με αρχεία PDF σε εφαρμογές .NET. Παρέχει μια ποικιλία λειτουργιών για τη δημιουργία, την επεξεργασία και τον χειρισμό αρχείων PDF, συμπεριλαμβανομένης της δυνατότητας προσθήκης σχολιασμών σε σελίδες. Σε αυτό το σεμινάριο, θα εξηγήσουμε πώς να ορίσετε το πλάτος γραμμής ενός σχολιασμού συνδέσμου χρησιμοποιώντας το Aspose.PDF για .NET.

Αφού έχετε αυτές τις προϋποθέσεις, δημιουργήστε ένα νέο έργο εφαρμογής κονσόλας στο Visual Studio. Στη συνέχεια, προσθέστε μια αναφορά στη βιβλιοθήκη Aspose.PDF για .NET κάνοντας δεξί κλικ στο έργο στην Εξερεύνηση λύσεων, επιλέγοντας "Διαχείριση πακέτων NuGet" και αναζητώντας "Aspose.PDF" στο NuGet Package Manager.

Για να προσθέσετε έναν σχολιασμό lnk σε ένα έγγραφο PDF, ακολουθήστε τα εξής βήματα:

##  Βήμα 1: Δημιουργήστε ένα νέο`Document` object.
```csharp
Document doc = new Document();
```
## Βήμα 2: Προσθέστε μια νέα σελίδα στο έγγραφο.
```csharp
doc.Pages.Add();
```
##  Βήμα 3: Δημιουργήστε μια λίστα με`Point` arrays that represent the ink gesture for the annotation.
```csharp
IList<Point[]> inkList = new List<Point[]>();
```
##  Βήμα 4: Δημιουργήστε ένα νέο`LineInfo` object that defines the properties of the ink gesture.
```csharp
LineInfo lineInfo = new LineInfo();
lineInfo.VerticeCoordinate = new float[] { 55, 55, 70, 70, 70, 90, 150, 60 };
lineInfo.Visibility = true;
lineInfo.LineColor = System.Drawing.Color.Red;
lineInfo.LineWidth = 2;
```
##  Βήμα 5: Δημιουργήστε ένα νέο`Aspose.Pdf.Point` array that represents the gesture from the `LineInfo` object.
```csharp
int length = lineInfo.VerticeCoordinate.Length / 2;
Aspose.Pdf.Point[] gesture = new Aspose.Pdf.Point[length];
for (int i = 0; i < length; i++)
{
    gesture[i] = new Aspose.Pdf.Point(lineInfo.VerticeCoordinate[2 * i], lineInfo.VerticeCoordinate[2 * i + 1]);
}
```
## Βήμα 6: Προσθέστε τη χειρονομία στη λίστα με τις κινήσεις μελανιού.
```csharp
inkList.Add(gesture);
```
##  Βήμα 7: Δημιουργήστε ένα νέο`InkAnnotation` object that represents the link annotation.
```csharp
InkAnnotation a1 = new InkAnnotation(doc.Pages[1], new Aspose.Pdf.Rectangle(100, 100, 300, 300), inkList);
```
## Βήμα 8: Ορίστε το θέμα και τον τίτλο του σχολιασμού.
```csharp
a1.Subject = "Test";
a1.Title = "Title";
```
## Βήμα 9: Ορίστε το χρώμα του σχολιασμού.
```csharp
a1.Color = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Green);
```
##  Βήμα 10: Δημιουργήστε ένα νέο`Border` object that defines the properties of the annotation's border.
```csharp
Border border = new Border(a1);
border.Width = 3;
border.Effect = BorderEffect.Cloudy;
border.Dash = new Dash(1, 1);
border.Style = BorderStyle.Solid;
```
## Βήμα 11: Προσθέστε τον σχολιασμό στη σελίδα.
```csharp
doc.Pages[1].Annotations.Add(a1);
```
## Βήμα 12: Αποθηκεύστε το έγγραφο σε αρχείο.
```csharp
// Αποθήκευση αρχείου εξόδου
doc.Save(dataDir);


```
### Το παράδειγμα δείχνει lnk πλάτος γραμμής σχολιασμού με Aspose.PDF για .NET

```csharp
// Η διαδρομή προς τον κατάλογο εγγράφων.
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
doc.Pages.Add();
IList<Point[]> inkList = new List<Point[]>();
LineInfo lineInfo = new LineInfo();
lineInfo.VerticeCoordinate = new float[] { 55, 55, 70, 70, 70, 90, 150, 60 };
lineInfo.Visibility = true;
lineInfo.LineColor = System.Drawing.Color.Red;
lineInfo.LineWidth = 2;
int length = lineInfo.VerticeCoordinate.Length / 2;
Aspose.Pdf.Point[] gesture = new Aspose.Pdf.Point[length];
for (int i = 0; i < length; i++)
{
gesture[i] = new Aspose.Pdf.Point(lineInfo.VerticeCoordinate[2 * i], lineInfo.VerticeCoordinate[2 * i + 1]);
}

inkList.Add(gesture);
InkAnnotation a1 = new InkAnnotation(doc.Pages[1], new Aspose.Pdf.Rectangle(100, 100, 300, 300), inkList);
a1.Subject = "Test";
a1.Title = "Title";
a1.Color = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Green);
Border border = new Border(a1);
border.Width = 3;
border.Effect = BorderEffect.Cloudy;
border.Dash = new Dash(1, 1);
border.Style = BorderStyle.Solid;
doc.Pages[1].Annotations.Add(a1);

dataDir = dataDir + "lnkAnnotationLineWidth_out.pdf";
// Αποθήκευση αρχείου εξόδου
doc.Save(dataDir);
```

## συμπέρασμα

Σε αυτό το σεμινάριο, μάθαμε πώς να ορίζουμε το πλάτος γραμμής ενός σχολιασμού συνδέσμου σε ένα έγγραφο PDF χρησιμοποιώντας το Aspose.PDF για .NET. Το Aspose.PDF για .NET παρέχει ένα ευρύ φάσμα εργαλείων και δυνατοτήτων για εργασία με έγγραφα PDF, συμπεριλαμβανομένης της δυνατότητας δημιουργίας και προσαρμογής σχολιασμών συνδέσμων. Ακολουθώντας τον οδηγό βήμα προς βήμα και χρησιμοποιώντας τον παρεχόμενο πηγαίο κώδικα C#, οι προγραμματιστές μπορούν εύκολα να προσθέσουν διαδραστικούς συνδέσμους στα έγγραφά τους PDF, βελτιώνοντας την εμπειρία χρήστη και τη διαδραστικότητα των εφαρμογών τους. Το Aspose.PDF για .NET είναι μια ευέλικτη βιβλιοθήκη που δίνει τη δυνατότητα στους προγραμματιστές .NET να εργάζονται με αρχεία PDF αποτελεσματικά και αποτελεσματικά.

### Συχνές ερωτήσεις

#### Ε: Τι είναι ο σχολιασμός συνδέσμου σε ένα έγγραφο PDF;

Α: Ένας σχολιασμός συνδέσμου σε ένα έγγραφο PDF είναι ένα διαδραστικό στοιχείο που σας επιτρέπει να δημιουργείτε υπερσυνδέσμους ή ενέργειες που κατευθύνουν τον χρήστη σε άλλη τοποθεσία εντός του ίδιου εγγράφου, σε εξωτερικό ιστότοπο ή σε διαφορετικό έγγραφο PDF.

#### Ε: Πώς μπορώ να ορίσω το πλάτος γραμμής ενός σχολιασμού συνδέσμου χρησιμοποιώντας το Aspose.PDF για .NET;

Α: Για να ορίσετε το πλάτος γραμμής ενός σχολιασμού συνδέσμου χρησιμοποιώντας το Aspose.PDF για .NET, μπορείτε να δημιουργήσετε ένα`InkAnnotation` αντικείμενο και καθορίστε την ιδιότητα πλάτους γραμμής.

#### Ε: Ποιες ιδιότητες μπορούν να προσαρμοστούν για έναν σχολιασμό συνδέσμου στο Aspose.PDF για .NET;

Α: Μπορείτε να προσαρμόσετε διάφορες ιδιότητες ενός σχολιασμού συνδέσμου στο Aspose.PDF για .NET, όπως η τοποθεσία, το μέγεθος, το χρώμα, οι ιδιότητες περιγράμματος (πλάτος, στυλ, μοτίβο παύλας και εφέ), θέμα, τίτλος και ορατότητα.

#### Ε: Μπορώ να δημιουργήσω έναν σχολιασμό συνδέσμου που περιέχει πολλές κινήσεις μελανιού;

 Α: Ναι, μπορείτε να δημιουργήσετε έναν σχολιασμό συνδέσμου που περιέχει πολλές κινήσεις μελανιού προσθέτοντας πολλές`Point` συστοιχίες στο`InkAnnotation` αντικείμενο.

#### Ε: Πώς μπορώ να προσθέσω έναν σχολιασμό συνδέσμου σε μια συγκεκριμένη σελίδα του εγγράφου PDF;

 Α: Για να προσθέσετε έναν σχολιασμό συνδέσμου σε μια συγκεκριμένη σελίδα του εγγράφου PDF, πρέπει να καθορίσετε τον αριθμό της σελίδας κατά τη δημιουργία του`InkAnnotation` αντικείμενο. Για παράδειγμα,`new InkAnnotation(doc.Pages[1], ...)` προσθέτει τον σχολιασμό του συνδέσμου στην πρώτη σελίδα.