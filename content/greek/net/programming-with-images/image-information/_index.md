---
title: Πληροφορίες εικόνας σε αρχείο PDF
linktitle: Πληροφορίες εικόνας σε αρχείο PDF
second_title: Aspose.PDF για Αναφορά API .NET
description: Εξαγωγή πληροφοριών εικόνας σε αρχείο PDF χρησιμοποιώντας το Aspose.PDF για .NET.
type: docs
weight: 160
url: /el/net/programming-with-images/image-information/
---
Αυτός ο οδηγός θα σας καθοδηγήσει βήμα προς βήμα πώς να εξάγετε πληροφορίες για εικόνες σε αρχείο PDF χρησιμοποιώντας το Aspose.PDF για .NET. Βεβαιωθείτε ότι έχετε ήδη ρυθμίσει το περιβάλλον σας και ακολουθήστε τα παρακάτω βήματα:

## Βήμα 1: Ορίστε τον κατάλογο εγγράφων

 Βεβαιωθείτε ότι έχετε ορίσει τον σωστό κατάλογο εγγράφων. Αντικαθιστώ`"YOUR DOCUMENT DIRECTORY"` στον κώδικα με τη διαδρομή προς τον κατάλογο όπου βρίσκεται το έγγραφο PDF σας.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Βήμα 2: Φορτώστε το αρχείο προέλευσης PDF

 Σε αυτό το βήμα, θα φορτώσουμε το αρχείο προέλευσης PDF χρησιμοποιώντας το`Document` κλάση του Aspose.PDF. Χρησιμοποιήστε το`Document` κατασκευαστή και περάστε τη διαδρομή προς το έγγραφο PDF.

```csharp
Document doc = new Document(dataDir + "ImageInformation.pdf");
```

## Βήμα 3: Ορίστε την προεπιλεγμένη ανάλυση

Σε αυτό το βήμα, θα ορίσουμε την προεπιλεγμένη ανάλυση για τις εικόνες. Στο παράδειγμα, η προεπιλεγμένη ανάλυση έχει οριστεί στο 72.

```csharp
int defaultResolution = 72;
```

## Βήμα 4: Αρχικοποίηση αντικειμένων και μετρητών

Σε αυτό το βήμα, θα αρχικοποιήσουμε τα αντικείμενα και τους μετρητές που απαιτούνται για την ανάκτηση των πληροφοριών εικόνας.

```csharp
System.Collections.Stack graphicsState = new System.Collections.Stack();
System.Collections.ArrayList imageNames = new System.Collections.ArrayList(doc.Pages[1].Resources.Images.Names);
```

## Βήμα 5: Περιηγηθείτε στους τελεστές στην πρώτη σελίδα του εγγράφου

Σε αυτό το βήμα, θα περιηγηθούμε στους τελεστές στην πρώτη σελίδα του εγγράφου για να εντοπίσουμε λειτουργίες που σχετίζονται με την εικόνα.

```csharp
foreach(Operator op in doc.Pages[1].Contents)
{
```

## Βήμα 6: Διαχείριση τελεστών και εξαγωγή πληροφοριών εικόνας

Σε αυτό το βήμα, θα διαχειριστούμε τους διαφορετικούς τύπους τελεστών και θα εξαγάγουμε τις πληροφορίες σχετικά με τις εικόνες.

```csharp
Aspose.Pdf.Operators.GSave opSaveState = op as Aspose.Pdf.Operators.GSave;
Aspose.Pdf.Operators.GRestore opRestoreState = op as Aspose.Pdf.Operators.GRestore;
Aspose.Pdf.Operators.ConcatenateMatrix opCtm = op as Aspose.Pdf.Operators.ConcatenateMatrix;
Aspose.Pdf.Operators.Do opDo = op as Aspose.Pdf.Operators.Do;

//Χειριστείτε τις λειτουργίες GSave και GRestore για μετασχηματισμούς
if (opSaveState != null)
{
     graphicsState.Push(((System.Drawing.Drawing2D.Matrix)graphicsState.Peek()).Clone());
}
else if (opRestoreState != null)
{
     graphicsState. Pop();
}
// Χειριστείτε τη λειτουργία ConcatenateMatrix για μετασχηματισμούς
else if (opCtm != null)
{
     // Εφαρμόστε τον πίνακα μετασχηματισμού
     System.Drawing.Drawing2D.Matrix cm = new System.Drawing.Drawing2D.Matrix(
        (float)opCtm.Matrix.A,
        (float)opCtm.Matrix.B,
        (float)opCtm.Matrix.C,
        (float)opCtm.Matrix.D,
        (float)opCtm.Matrix.E,
        (float)opCtm.Matrix.F);


     ((System.Drawing.Drawing2D.Matrix)graphicsState.Peek()).Multiply(cm);
     keep on going;
}
// Χειριστείτε τη λειτουργία Do για εικόνες
else if (opDo != null)
{
     if (imageNames.Contains(opDo.Name))
     {
         // Ανακτήστε την εικόνα
         XImage image = doc.Pages[1].Resources.Images[opDo.Name];
         // Ανακτήστε τις διαστάσεις της εικόνας
         double scaledWidth = Math.Sqrt(Math.Pow(lastCTM.Elements[0], 2) + Math.Pow(lastCTM.Elements[1], 2));
         double scaledHeight = Math.Sqrt(Math.Pow(lastCTM.Elements[2], 2) + Math.Pow(lastCTM.Elements[3], 2));
         // Υπολογίστε την ανάλυση με βάση τις παραπάνω πληροφορίες
         double resHorizontal = originalWidth * defaultResolution / scaledWidth;
         double resVertical = originalHeight * defaultResolution / scaledHeight;
         // Εμφάνιση πληροφοριών εικόνας
         Console.Out.WriteLine(
                 string.Format(dataDir + "image {0} ({1:.##}:{2:.##}): res {3:.##} x {4:.##}",
								 opDo.Name, scaledWidth, scaledHeight, resHorizontal,
								 resVertical));
     }
}
```

### Δείγμα πηγαίου κώδικα για πληροφορίες εικόνας χρησιμοποιώντας το Aspose.PDF για .NET 
```csharp
// Η διαδρομή προς τον κατάλογο εγγράφων.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Φορτώστε το αρχείο προέλευσης PDF
Document doc = new Document(dataDir+ "ImageInformation.pdf");
// Ορίστε την προεπιλεγμένη ανάλυση για την εικόνα
int defaultResolution = 72;
System.Collections.Stack graphicsState = new System.Collections.Stack();
// Καθορίστε το αντικείμενο λίστας πίνακα που θα περιέχει ονόματα εικόνων
System.Collections.ArrayList imageNames = new System.Collections.ArrayList(doc.Pages[1].Resources.Images.Names);
// Εισαγάγετε ένα αντικείμενο στη στοίβαξη
graphicsState.Push(new System.Drawing.Drawing2D.Matrix(1, 0, 0, 1, 0, 0));
// Πάρτε όλους τους τελεστές στην πρώτη σελίδα του εγγράφου
foreach (Operator op in doc.Pages[1].Contents)
{
	// Χρησιμοποιήστε τελεστές GSave/GRestore για να επαναφέρετε τους μετασχηματισμούς στην προηγούμενη ρύθμιση
	Aspose.Pdf.Operators.GSave opSaveState = op as Aspose.Pdf.Operators.GSave;
	Aspose.Pdf.Operators.GRestore opRestoreState = op as Aspose.Pdf.Operators.GRestore;
	// Δημιουργήστε το αντικείμενο ConcatenateMatrix όπως ορίζει τον τρέχοντα πίνακα μετασχηματισμού.
	Aspose.Pdf.Operators.ConcatenateMatrix opCtm = op as Aspose.Pdf.Operators.ConcatenateMatrix;
	// Δημιουργήστε τελεστή Do που αντλεί αντικείμενα από πόρους. Σχεδιάζει αντικείμενα φόρμας και αντικείμενα εικόνας
	Aspose.Pdf.Operators.Do opDo = op as Aspose.Pdf.Operators.Do;
	if (opSaveState != null)
	{
		//Αποθηκεύστε την προηγούμενη κατάσταση και σπρώξτε την τρέχουσα κατάσταση στην κορυφή της στοίβας
		graphicsState.Push(((System.Drawing.Drawing2D.Matrix)graphicsState.Peek()).Clone());
	}
	else if (opRestoreState != null)
	{
		// Πετάξτε την τρέχουσα κατάσταση και επαναφέρετε την προηγούμενη
		graphicsState.Pop();
	}
	else if (opCtm != null)
	{
		System.Drawing.Drawing2D.Matrix cm = new System.Drawing.Drawing2D.Matrix(
		   (float)opCtm.Matrix.A,
		   (float)opCtm.Matrix.B,
		   (float)opCtm.Matrix.C,
		   (float)opCtm.Matrix.D,
		   (float)opCtm.Matrix.E,
		   (float)opCtm.Matrix.F);
		// Πολλαπλασιάστε τον τρέχοντα πίνακα με τον πίνακα καταστάσεων
		((System.Drawing.Drawing2D.Matrix)graphicsState.Peek()).Multiply(cm);
		continue;
	}
	else if (opDo != null)
	{
		// Σε περίπτωση που πρόκειται για τελεστή σχεδίασης εικόνας
		if (imageNames.Contains(opDo.Name))
		{
			System.Drawing.Drawing2D.Matrix lastCTM = (System.Drawing.Drawing2D.Matrix)graphicsState.Peek();
			// Δημιουργήστε αντικείμενο XImage για να κρατήσετε εικόνες της πρώτης σελίδας pdf
			XImage image = doc.Pages[1].Resources.Images[opDo.Name];
			// Λάβετε διαστάσεις εικόνας
			double scaledWidth = Math.Sqrt(Math.Pow(lastCTM.Elements[0], 2) + Math.Pow(lastCTM.Elements[1], 2));
			double scaledHeight = Math.Sqrt(Math.Pow(lastCTM.Elements[2], 2) + Math.Pow(lastCTM.Elements[3], 2));
			// Λάβετε πληροφορίες ύψους και πλάτους της εικόνας
			double originalWidth = image.Width;
			double originalHeight = image.Height;
			// Υπολογίστε την ανάλυση με βάση τις παραπάνω πληροφορίες
			double resHorizontal = originalWidth * defaultResolution / scaledWidth;
			double resVertical = originalHeight * defaultResolution / scaledHeight;
			// Εμφάνιση πληροφοριών διάστασης και ανάλυσης κάθε εικόνας
			Console.Out.WriteLine(
					string.Format(dataDir + "image {0} ({1:.##}:{2:.##}): res {3:.##} x {4:.##}",
								 opDo.Name, scaledWidth, scaledHeight, resHorizontal,
								 resVertical));
		}
	}
}
```

## συμπέρασμα

Συγχαρητήρια ! Τώρα έχετε μάθει πώς να εξάγετε πληροφορίες εικόνας σε ένα αρχείο PDF χρησιμοποιώντας το Aspose.PDF για .NET. Μπορείτε να χρησιμοποιήσετε αυτές τις πληροφορίες για διάφορες εργασίες επεξεργασίας εικόνας στις εφαρμογές σας.

### Συχνές ερωτήσεις για πληροφορίες εικόνας σε αρχείο PDF

#### Ε: Ποιος είναι ο σκοπός της εξαγωγής πληροφοριών εικόνας από ένα έγγραφο PDF χρησιμοποιώντας το Aspose.PDF για .NET;

Α: Η εξαγωγή πληροφοριών εικόνας από ένα έγγραφο PDF παρέχει πληροφορίες για τις διαστάσεις, την ανάλυση και άλλα χαρακτηριστικά των εικόνων μέσα στο έγγραφο. Αυτές οι πληροφορίες μπορούν να χρησιμοποιηθούν για εργασίες επεξεργασίας εικόνας, ανάλυσης ή βελτιστοποίησης.

#### Ε: Πώς βοηθά το Aspose.PDF για .NET στην εξαγωγή πληροφοριών εικόνας από ένα έγγραφο PDF;

Α: Το Aspose.PDF για .NET παρέχει εργαλεία για πρόσβαση και ανάλυση του περιεχομένου ενός εγγράφου PDF, συμπεριλαμβανομένων των εικόνων του. Ο παρεχόμενος κώδικας δείχνει τον τρόπο εξαγωγής και εμφάνισης πληροφοριών εικόνας χρησιμοποιώντας διάφορους τελεστές.

#### Ε: Τι είδους πληροφορίες εικόνας μπορούν να εξαχθούν χρησιμοποιώντας αυτήν τη μέθοδο;

Α: Αυτή η μέθοδος σάς επιτρέπει να εξάγετε και να εμφανίζετε πληροφορίες όπως κλιμακωμένες διαστάσεις, ανάλυση και ονόματα εικόνων για εικόνες μέσα σε ένα έγγραφο PDF.

#### Ε: Πώς αναγνωρίζει και επεξεργάζεται ο κώδικας τελεστές που σχετίζονται με εικόνα μέσα σε ένα έγγραφο PDF;

Α: Ο κώδικας επαναλαμβάνεται μέσω των τελεστών σε μια καθορισμένη σελίδα του εγγράφου PDF. Προσδιορίζει και επεξεργάζεται τελεστές που σχετίζονται με λειτουργίες εικόνας, μετασχηματισμούς και απόδοση.

#### Ε: Ποια είναι η σημασία της προεπιλεγμένης ανάλυσης και πώς χρησιμοποιείται στον κώδικα;

Α: Η προεπιλεγμένη ανάλυση χρησιμοποιείται ως σημείο αναφοράς για τον υπολογισμό της πραγματικής ανάλυσης των εικόνων. Ο κώδικας υπολογίζει την ανάλυση κάθε εικόνας με βάση τις διαστάσεις της και την προεπιλεγμένη ρύθμιση ανάλυσης.

#### Ε: Πώς μπορούν να χρησιμοποιηθούν οι εξαγόμενες πληροφορίες εικόνας σε σενάρια πραγματικού κόσμου;

Α: Οι πληροφορίες εικόνας που εξάγονται μπορούν να χρησιμοποιηθούν για εργασίες όπως αξιολόγηση ποιότητας εικόνας, βελτιστοποίηση εικόνας, δημιουργία μικρογραφιών εικόνας και διευκόλυνση διαδικασιών λήψης αποφάσεων που σχετίζονται με την εικόνα.

#### Ε: Μπορώ να τροποποιήσω τον κώδικα για να εξαγάγω πρόσθετα χαρακτηριστικά που σχετίζονται με την εικόνα;

Α: Ναι, μπορείτε να προσαρμόσετε τον κώδικα για να εξαγάγετε πρόσθετα χαρακτηριστικά εικόνων, όπως χρωματικό διάστημα, βάθος pixel ή τύπο εικόνας.

#### Ε: Η διαδικασία εξαγωγής πληροφοριών εικόνας είναι εντατική ή χρονοβόρα;

Α: Η διαδικασία εξαγωγής πληροφοριών εικόνας είναι αποτελεσματική και βελτιστοποιημένη για απόδοση, εξασφαλίζοντας ελάχιστο αντίκτυπο στη χρήση των πόρων και στο χρόνο επεξεργασίας.

#### Ε: Πώς μπορούν οι προγραμματιστές να επωφεληθούν από τον εντοπισμό και την εξαγωγή πληροφοριών εικόνας από έγγραφα PDF;

Α: Οι προγραμματιστές μπορούν να αποκτήσουν πληροφορίες για τα χαρακτηριστικά των εικόνων σε έγγραφα PDF, επιτρέποντάς τους να λαμβάνουν τεκμηριωμένες αποφάσεις σχετικά με τη χειραγώγηση, την επεξεργασία και τη βελτιστοποίηση της εικόνας.

#### Ε: Μπορεί αυτή η μέθοδος να χρησιμοποιηθεί για ομαδική επεξεργασία εγγράφων PDF που περιέχουν εικόνες;

Α: Ναι, αυτή η μέθοδος μπορεί να επεκταθεί για ομαδική επεξεργασία με επανάληψη σε πολλές σελίδες ή έγγραφα, εξαγωγή πληροφοριών εικόνας και εκτέλεση εργασιών που σχετίζονται με την εικόνα.