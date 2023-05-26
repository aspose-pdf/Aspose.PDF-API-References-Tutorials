---
title: Ajouter Supprimer Javascript au document
linktitle: Ajouter Supprimer Javascript au document
second_title: Référence de l'API Aspose.PDF pour .NET
description: Découvrez comment ajouter et supprimer JavaScript des documents PDF à l'aide d'Aspose.PDF pour .NET. Guide étape par étape avec des didacticiels de code pour la création de scripts au niveau du document.
type: docs
weight: 30
url: /fr/net/programming-with-document/addremovejavascripttodoc/
---

Pour ajouter et supprimer JavaScript des documents PDF, nous utiliserons la bibliothèque Aspose.PDF pour .NET. Cette puissante bibliothèque nous permet de manipuler des fichiers PDF dans des applications .NET. Suivez les instructions étape par étape ci-dessous pour ajouter et supprimer JavaScript à l'aide d'Aspose.PDF pour .NET.

## Étape 1 : créer un nouveau document PDF

 Commencez par créer une nouvelle instance de`Document` classe fournie par Aspose.PDF pour .NET. Cela servira de document PDF où nous ajouterons le JavaScript.

```csharp
// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
doc.Pages.Add();
```

## Étape 2 : Ajouter JavaScript au niveau du document

 Pour ajouter JavaScript au niveau du document, utilisez le`JavaScript` propriété de la`Document` classe. Attribuez des fonctions JavaScript aux clés dans le dictionnaire JavaScript.

```csharp
doc.JavaScript["func1"] = "function func1() { hello(); }";
doc.JavaScript["func2"] = "function func2() { hello(); }";
doc.Save(dataDir + "AddJavascript.pdf");
```

 Dans ce tutoriel, nous avons ajouté deux fonctions JavaScript,`func1` et`func2`, au document PDF.

## Étape 3 : Supprimer le JavaScript au niveau du document

 Pour supprimer JavaScript au niveau du document, chargez le document PDF et accédez au`JavaScript` dictionnaire. Parcourez les clés et supprimez la fonction JavaScript souhaitée.

```csharp
Document doc1 = new Document(dataDir + "AddJavascript.pdf");
IList keys = (System.Collections.IList)doc1.JavaScript.Keys;

foreach (string key in keys)
{
    Console.WriteLine(key + " ==> " + doc1.JavaScript[key]);
}

doc1.JavaScript.Remove("func1");
Console.WriteLine("Key 'func1' removed");
```

 Dans ce tutoriel, nous supprimons le`func1` Fonction JavaScript du document PDF.

## Étape 4 : Enregistrer et vérifier les modifications

Enregistrez le document PDF modifié et vérifiez les modifications.

```csharp
Console.WriteLine("\nJavascript added/removed successfully to a document.");
```

Ce code enregistrera le document PDF modifié et affichera le message de réussite.

### Exemple de code source pour Ajouter Supprimer Javascript des documents PDF à l'aide d'Aspose.PDF pour .NET

```csharp

            
            // Chemin d'accès au répertoire des documents.
            string dataDir = "YOUR DOCUMENT DIRECTORY";

            Document doc = new Document();
            doc.Pages.Add();
            doc.JavaScript["func1"] = "function func1() { hello(); }";
            doc.JavaScript["func2"] = "function func2() { hello(); }";
            doc.Save(dataDir + "AddJavascript.pdf");

            // Supprimer le JavaScript au niveau du document
            Document doc1 = new Document(dataDir + "AddJavascript.pdf");
            IList keys = (System.Collections.IList)doc1.JavaScript.Keys;
            Console.WriteLine("=============================== ");
            foreach (string key in keys)
            {
                Console.WriteLine(key + " ==> " + doc1.JavaScript[key]);
            }

            doc1.JavaScript.Remove("func1");
            Console.WriteLine("Key 'func1' removed ");
            Console.WriteLine("=============================== ");
            
            Console.WriteLine("\nJavascript added/removed successfully to a document.");
        
```

## Conclusion

Dans cet article, nous avons fourni un guide étape par étape pour ajouter et supprimer JavaScript des documents PDF à l'aide d'Aspose.PDF pour .NET. En suivant les instructions et en utilisant les didacticiels de code fournis, vous pouvez facilement incorporer JavaScript dans vos documents PDF et le supprimer si nécessaire. JavaScript permet une fonctionnalité dynamique et une interactivité dans vos fichiers PDF, améliorant ainsi l'expérience utilisateur.