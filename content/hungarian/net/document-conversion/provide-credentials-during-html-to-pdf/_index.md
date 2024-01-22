---
title: Hitelesítő adatok megadása a HTML-hez PDF-be
linktitle: Hitelesítő adatok megadása a HTML-hez PDF-be
second_title: Aspose.PDF for .NET API Reference
description: Útmutató lépésről lépésre a HTML konvertálásához PDF formátumba az Aspose.PDF for .NET hitelesítő adatainak megadásával.
type: docs
weight: 240
url: /hu/net/document-conversion/provide-credentials-during-html-to-pdf/
---
Ebben az oktatóanyagban végigvezetjük a HTML-fájlok PDF-formátumba konvertálásának folyamatán, miközben hitelesítési adatokat biztosítunk, amikor egy biztonságos URL-hez fér hozzá az Aspose.PDF for .NET használatával. Az alábbi lépések követésével a megfelelő hitelesítő adatok használatával konvertálhatja a HTML-tartalmat PDF-be.

## Előfeltételek
Mielőtt elkezdené, győződjön meg arról, hogy megfelel a következő előfeltételeknek:

- C# programozási nyelv alapismerete.
- Aspose.PDF könyvtár a .NET-hez telepítve a rendszerére.
- Fejlesztői környezet, például a Visual Studio.

## 1. lépés: Töltse le a biztonságos HTML-tartalmat
Ebben a lépésben biztonságos HTML-tartalmat kérünk le egy URL-ről a megfelelő hitelesítő adatok használatával. Használja a következő kódot:

```csharp
// A dokumentumok könyvtár elérési útja.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Hozzon létre egy kérést az URL-hez.
WebRequest request = WebRequest.Create("http://My.signchart.com/Report/PrintBook.asp?ProjectGuid=6FB9DBB0-");
// Ha szükséges a szerverhez, állítsa be a hitelesítési adatokat.
request.Credentials = CredentialCache.DefaultCredentials;
// Kapja meg a választ.
HttpWebResponse response = (HttpWebResponse)request.GetResponse();

// Szerezze be a szerver által visszaadott tartalmat tartalmazó adatfolyamot.
Stream dataStream = response. GetResponseStream();
// Nyissa meg az adatfolyamot a StreamReader segítségével az egyszerű hozzáférés érdekében.
StreamReader reader = new StreamReader(dataStream);
// Olvassa el a tartalmat.
string responseFromServer = reader.ReadToEnd();
reader. Close();
dataStream.Close();
response. Close();
```

 Feltétlenül cserélje ki`"YOUR DOCUMENTS DIRECTORY"` azzal a tényleges könyvtárral, ahová menteni szeretné az eredményül kapott PDF-fájlt.

## 2. lépés: Konvertálja a HTML-t PDF-be hitelesítő adatok megadásával
Most betöltjük a letöltött HTML tartalmat, és PDF formátumba konvertáljuk, miközben megadjuk a megfelelő hitelesítő adatokat. Használja a következő kódot:

```csharp
MemoryStream stream = new MemoryStream(System.Text.Encoding.UTF8.GetBytes(responseFromServer));

HtmlLoadOptions options = new HtmlLoadOptions("http://My.signchart.com/");
options.ExternalResourcesCredentials = CredentialCache.DefaultCredentials;

// Töltse be a HTML fájlt
Document pdfDocument = new Document(stream, options);
```

## 3. lépés: Mentse el a kapott PDF-fájlt
Végül elmentjük a kapott PDF fájlt. Használja a következő kódot:

```csharp
// Mentse el a kapott PDF-fájlt
pdfDocument.Save(dataDir + "ProvideCredentialsDuringHTMLToPDF_out.pdf");
```

 A fenti kód elmenti az eredményül kapott PDF-fájlt a fájlnévvel`"ProvideCredentialsDuringHTMLToPDF_out.pdf"`.

### Példa forráskódra a Hitelesítő adatok megadása során a HTML-ben PDF-be az Aspose.PDF for .NET használatával

```csharp
try
{
	
	// A dokumentumok könyvtárának elérési útja.
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	// Hozzon létre egy kérést az URL-hez.
	WebRequest request = WebRequest.Create("http:// My.signchart.com/Report/PrintBook.asp?ProjectGuid=6FB9DBB0-");
	// Ha a szerver megköveteli, állítsa be a hitelesítő adatokat.
	request.Credentials = CredentialCache.DefaultCredentials;
	// Kapja meg a választ.
	HttpWebResponse response = (HttpWebResponse)request.GetResponse();

	// Szerezze be a szerver által visszaadott tartalmat tartalmazó adatfolyamot.
	Stream dataStream = response.GetResponseStream();
	// Nyissa meg az adatfolyamot a StreamReader segítségével az egyszerű hozzáférés érdekében.
	StreamReader reader = new StreamReader(dataStream);
	// Olvassa el a tartalmat.
	string responseFromServer = reader.ReadToEnd();
	reader.Close();
	dataStream.Close();
	response.Close();

	MemoryStream stream = new MemoryStream(System.Text.Encoding.UTF8.GetBytes(responseFromServer));

	HtmlLoadOptions options = new HtmlLoadOptions("http:// My.signchart.com/");
	options.ExternalResourcesCredentials = CredentialCache.DefaultCredentials;

	// HTML fájl betöltése
	Document pdfDocument = new Document(stream, options);
	// Az eredményül kapott fájl mentése
	pdfDocument.Save("ProvideCredentialsDuringHTMLToPDF_out.pdf");
	
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## Következtetés
Ebben az oktatóanyagban a HTML-fájlok PDF-formátumba konvertálásának lépésről lépésre bemutatott folyamatát ismertetjük, miközben hitelesítő adatokat biztosítunk egy biztonságos URL elérésekor az Aspose.PDF for .NET használatával. A fent vázolt utasítások követésével sikeresen konvertálhatja a HTML-tartalmat PDF-be, miközben megadja a megfelelő hitelesítő adatokat.

### GYIK

#### K: Mi az Aspose.PDF for .NET?

V: Az Aspose.PDF for .NET egy robusztus könyvtár, amely lehetővé teszi a fejlesztők számára, hogy PDF dokumentumokkal dolgozzanak C# alkalmazásokban. A funkciók széles skáláját kínálja, beleértve a HTML-ből PDF-be konvertálást.

#### K: Hogyan tölthetek le biztonságos HTML tartalmat egy URL-ről?

 V: Ha biztonságos HTML-tartalmat szeretne lekérni egy URL-ről, használja a`WebRequest` osztály C# nyelven. Ügyeljen arra, hogy a megfelelő hitelesítő adatokat a`Credentials` ingatlan.

#### K: Milyen előfeltételei vannak ennek az oktatóanyagnak?

V: Mielőtt folytatná az oktatóanyagot, győződjön meg arról, hogy rendelkezik a következő előfeltételekkel:

- C# programozási nyelv alapismerete.
- Aspose.PDF könyvtár a .NET-hez telepítve a rendszerére.
- Fejlesztői környezet, például a Visual Studio.

#### K: Hogyan kezeli az Aspose.PDF for .NET a külső erőforrásokat, miközben HTML-t PDF-be konvertál?

 V: Az Aspose.PDF for .NET biztosítja a`HtmlLoadOptions`osztály a külső erőforrások kezelésére a HTML-ből PDF-be átalakítás során. A külső erőforrás hitelesítő adatait a következővel állíthatja be`ExternalResourcesCredentials` ingatlan.

#### K: Testreszabhatom a kapott PDF-fájl fájlnevét?

 V: Igen, testreszabhatja a létrejövő PDF-fájl fájlnevét a PDF-dokumentumot mentő kód módosításával. Egyszerűen módosítsa a kívánt fájlnevet a`pdfDocument.Save()` módszer.