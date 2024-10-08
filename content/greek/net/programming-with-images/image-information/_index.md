---
title: Πληροφορίες εικόνας σε αρχείο PDF
linktitle: Πληροφορίες εικόνας σε αρχείο PDF
second_title: Aspose.PDF για Αναφορά API .NET
description: Μάθετε να εξάγετε πληροφορίες εικόνας από αρχεία PDF χρησιμοποιώντας το Aspose.PDF για .NET με τον αναλυτικό οδηγό μας βήμα προς βήμα.
type: docs
weight: 160
url: /el/net/programming-with-images/image-information/
---
## Εισαγωγή

Τα αρχεία PDF είναι παντού αυτές τις μέρες—σχεδόν κάθε επαγγελματικό και προσωπικό έγγραφο βρίσκει το δρόμο του σε αυτήν τη μορφή κάποια στιγμή. Είτε πρόκειται για μια αναφορά, ένα φυλλάδιο ή ένα eBook, η κατανόηση του τρόπου αλληλεπίδρασης με αυτά τα αρχεία μέσω προγραμματισμού προσφέρει μυριάδες δυνατότητες. Μια κοινή απαίτηση είναι η εξαγωγή πληροφοριών εικόνας από αρχεία PDF. Σε αυτόν τον οδηγό, θα εξετάσουμε πώς να χρησιμοποιήσετε τη βιβλιοθήκη Aspose.PDF για .NET για να εξαγάγετε σημαντικές λεπτομέρειες σχετικά με εικόνες που είναι ενσωματωμένες σε ένα έγγραφο PDF.

## Προαπαιτούμενα

Προτού περάσουμε στη λεπτομέρεια της κωδικοποίησης, υπάρχουν μερικές προϋποθέσεις που θα πρέπει να έχετε:

1. Περιβάλλον ανάπτυξης: Θα χρειαστείτε να ρυθμίσετε ένα περιβάλλον ανάπτυξης .NET. Αυτό θα μπορούσε να είναι το Visual Studio ή οποιοδήποτε άλλο IDE συμβατό με .NET.
2.  Aspose.PDF Library: Βεβαιωθείτε ότι έχετε πρόσβαση στη βιβλιοθήκη Aspose.PDF. Μπορείτε να το κατεβάσετε από το[Aspose website](https://releases.aspose.com/pdf/net/). 
3. Βασικές γνώσεις C#: Η εξοικείωση με την C# και τις αντικειμενοστρεφείς έννοιες προγραμματισμού θα σας βοηθήσει να ακολουθήσετε το σεμινάριο χωρίς κόπο.
4. Έγγραφο PDF: Έχετε ένα δείγμα εγγράφου PDF που περιέχει εικόνες για να δοκιμάσετε τον κώδικά σας. 

## Εισαγωγή πακέτων

Για να ξεκινήσετε με τη χρήση της βιβλιοθήκης Aspose.PDF, θα χρειαστεί να εισαγάγετε τους απαραίτητους χώρους ονομάτων στο αρχείο C#. Ακολουθεί μια γρήγορη σύνοψη:

```csharp
using System.IO;
using Aspose.Pdf;
using System;
```

Αυτοί οι χώροι ονομάτων θα σας παρέχουν πρόσβαση στις απαιτούμενες κλάσεις και μεθόδους για τον χειρισμό αρχείων PDF και την εξαγωγή δεδομένων εικόνας.

Τώρα που έχετε ρυθμίσει τα πάντα, ήρθε η ώρα να το αναλύσετε σε διαχειρίσιμα βήματα. Θα γράψουμε ένα πρόγραμμα C# που φορτώνει ένα έγγραφο PDF, περνά από κάθε σελίδα και εξάγει τις διαστάσεις και την ανάλυση κάθε εικόνας στο έγγραφο.

## Βήμα 1: Αρχικοποιήστε το έγγραφο

 Σε αυτό το βήμα, θα αρχικοποιήσουμε το έγγραφο PDF χρησιμοποιώντας τη διαδρομή προς το αρχείο PDF σας. Θα πρέπει να αντικαταστήσετε`"YOUR DOCUMENT DIRECTORY"` με την πραγματική διαδρομή όπου βρίσκεται το αρχείο PDF σας.

```csharp
// Η διαδρομή προς τον κατάλογο εγγράφων.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Φορτώστε το αρχείο προέλευσης PDF
Document doc = new Document(dataDir + "ImageInformation.pdf");
```
 Δημιουργούμε α`Document` αντικείμενο που φορτώνει το PDF από τον καθορισμένο κατάλογο. Αυτό θα μας επιτρέψει να εργαστούμε με τα περιεχόμενα του αρχείου.

## Βήμα 2: Ορίστε την προεπιλεγμένη ανάλυση και αρχικοποιήστε τις δομές δεδομένων

Στη συνέχεια, ορίζουμε μια προεπιλεγμένη ανάλυση για τις εικόνες, η οποία είναι χρήσιμη για τους υπολογισμούς. Θα ετοιμάσουμε επίσης έναν πίνακα για τη διατήρηση των ονομάτων εικόνων και μια στοίβα για τη διαχείριση των καταστάσεων γραφικών.

```csharp
// Ορίστε την προεπιλεγμένη ανάλυση για την εικόνα
int defaultResolution = 72;
System.Collections.Stack graphicsState = new System.Collections.Stack();
// Καθορίστε το αντικείμενο λίστας πίνακα που θα περιέχει ονόματα εικόνων
System.Collections.ArrayList imageNames = new System.Collections.ArrayList(doc.Pages[1].Resources.Images.Names);
```
 Ο`defaultResolution` Η μεταβλητή μας βοηθά να υπολογίσουμε σωστά την ανάλυση των εικόνων. Ο`graphicsState`Η στοίβα χρησιμεύει ως μέσο αποθήκευσης της τρέχουσας γραφικής κατάστασης του εγγράφου όταν συναντάμε τελεστές μετασχηματισμού.

## Βήμα 3: Επεξεργασία κάθε χειριστή στη σελίδα

Τώρα κάνουμε βρόχο σε όλους τους τελεστές στην πρώτη σελίδα του εγγράφου. Εδώ συμβαίνει η άρση βαρέων. 

```csharp
foreach (Operator op in doc.Pages[1].Contents)
{
    // Οι χειριστές διεργασιών...
}
```
Κάθε χειριστής σε ένα αρχείο PDF είναι μια εντολή που λέει στον αποδέκτη πώς να διαχειρίζεται γραφικά στοιχεία, συμπεριλαμβανομένων εικόνων.

## Βήμα 4: Χειριστείτε τους χειριστές GSave/GRestore

Μέσα στον βρόχο, θα χειριστούμε εντολές αποθήκευσης και επαναφοράς γραφικών για να παρακολουθούμε τις αλλαγές που έγιναν στην κατάσταση γραφικών.

```csharp
if (opSaveState != null) 
{
    // Αποθήκευση προηγούμενης κατάστασης
    graphicsState.Push(((Matrix)graphicsState.Peek()).Clone());
} 
else if (opRestoreState != null) 
{
    // Επαναφορά της προηγούμενης κατάστασης
    graphicsState.Pop();
}
```
`GSave` αποθηκεύει την τρέχουσα κατάσταση γραφικών, ενώ`GRestore` επαναφέρει την τελευταία αποθηκευμένη κατάσταση, επιτρέποντάς μας να επαναφέρουμε τυχόν μετασχηματισμούς κατά την επεξεργασία εικόνων.

## Βήμα 5: Διαχείριση μητρών μετασχηματισμού

Στη συνέχεια, χειριζόμαστε τη συνένωση των πινάκων μετασχηματισμού κατά την εφαρμογή μετασχηματισμών σε εικόνες.

```csharp
else if (opCtm != null) 
{
    Matrix cm = new Matrix(
        (float)opCtm.Matrix.A,
        (float)opCtm.Matrix.B,
        (float)opCtm.Matrix.C,
        (float)opCtm.Matrix.D,
        (float)opCtm.Matrix.E,
        (float)opCtm.Matrix.F);
    
    ((Matrix)graphicsState.Peek()).Multiply(cm);
    continue;
}
```
Όταν εφαρμόζεται ένας πίνακας μετασχηματισμού, τον πολλαπλασιάζουμε με τον τρέχοντα πίνακα που είναι αποθηκευμένος στην κατάσταση γραφικών, έτσι ώστε να μπορούμε να παρακολουθούμε τυχόν κλιμάκωση ή μετάφραση που εφαρμόζεται στην εικόνα.

## Βήμα 6: Εξαγωγή πληροφοριών εικόνας

Τέλος, επεξεργαζόμαστε τον τελεστή σχεδίασης για εικόνες και εξάγουμε τις απαραίτητες πληροφορίες, όπως διαστάσεις και αναλύσεις.

```csharp
else if (opDo != null) 
{
    // Χειριστείτε τον τελεστή Do που σχεδιάζει αντικείμενα
    if (imageNames.Contains(opDo.Name)) 
    {
        Matrix lastCTM = (Matrix)graphicsState.Peek();
        XImage image = doc.Pages[1].Resources.Images[opDo.Name];
        double scaledWidth = Math.Sqrt(Math.Pow(lastCTM.Elements[0], 2) + Math.Pow(lastCTM.Elements[1], 2));
        double scaledHeight = Math.Sqrt(Math.Pow(lastCTM.Elements[2], 2) + Math.Pow(lastCTM.Elements[3], 2));
        double originalWidth = image.Width;
        double originalHeight = image.Height;
        
        double resHorizontal = originalWidth * defaultResolution / scaledWidth;
        double resVertical = originalHeight * defaultResolution / scaledHeight;
        
        // Εξαγωγή των πληροφοριών
        Console.Out.WriteLine(string.Format(dataDir + "image {0} ({1:.##}:{2:.##}): res {3:.##} x {4:.##}",
                         opDo.Name, scaledWidth, scaledHeight, resHorizontal, resVertical));
    }
}
```
Εδώ, ελέγχουμε αν ο χειριστής είναι υπεύθυνος για τη σχεδίαση μιας εικόνας. Εάν είναι, παίρνουμε το αντίστοιχο αντικείμενο XImage, υπολογίζουμε τις κλιμακούμενες διαστάσεις και την ανάλυσή του και εκτυπώνουμε τις απαραίτητες πληροφορίες.

## Σύναψη

Συγχαρητήρια! Μόλις δημιουργήσατε ένα λειτουργικό παράδειγμα του τρόπου εξαγωγής πληροφοριών εικόνας από ένα αρχείο PDF χρησιμοποιώντας το Aspose.PDF για .NET. Αυτή η δυνατότητα μπορεί να είναι απίστευτα χρήσιμη για προγραμματιστές που πρέπει να αναλύουν ή να χειρίζονται έγγραφα PDF για διάφορες εφαρμογές, όπως αναφορές, εξαγωγή δεδομένων ή ακόμα και προσαρμοσμένα προγράμματα προβολής PDF. 


## Συχνές ερωτήσεις

### Τι είναι η βιβλιοθήκη Aspose.PDF;
Η βιβλιοθήκη Aspose.PDF είναι ένα ισχυρό εργαλείο για τη δημιουργία, το χειρισμό και τη μετατροπή αρχείων PDF σε εφαρμογές .NET.

### Μπορώ να χρησιμοποιήσω τη βιβλιοθήκη δωρεάν;
 Ναι, το Aspose προσφέρει δωρεάν δοκιμή. Μπορείτε να το κατεβάσετε[εδώ](https://releases.aspose.com/).

### Ποιοι τύποι μορφών εικόνας μπορούν να εξαχθούν;
Η βιβλιοθήκη υποστηρίζει διάφορες μορφές εικόνας, συμπεριλαμβανομένων των JPEG, PNG και TIFF, αρκεί να είναι ενσωματωμένες στο PDF.

### Το Aspose χρησιμοποιείται για εμπορικούς σκοπούς;
 Ναι, μπορείτε να χρησιμοποιήσετε τα προϊόντα Aspose στο εμπόριο. Για αδειοδότηση, επισκεφθείτε το[σελίδα αγοράς](https://purchase.aspose.com/buy).

### Πώς μπορώ να λάβω υποστήριξη για το Aspose;
 Μπορείτε να αποκτήσετε πρόσβαση στο φόρουμ υποστήριξης[εδώ](https://forum.aspose.com/c/pdf/10).