---
title: Kivonat aláírási információ
linktitle: Kivonat aláírási információ
second_title: Aspose.PDF for .NET API Reference
description: Aláírási információk kinyerése az Aspose.PDF for .NET használatával.
type: docs
weight: 80
url: /hu/net/programming-with-security-and-signatures/extract-signature-info/
---
Az aláírási információk PDF-dokumentumból való kinyerésének folyamata számos forgatókönyv esetén igen hasznos lehet. Akár egy aláírt dokumentum hitelességét kell ellenőriznie, akár az aláíráshoz használt tanúsítványt kell elemeznie, az Aspose.PDF for .NET könyvtár kényelmes megoldást kínál. Ebben az oktatóanyagban lépésről lépésre végigvezetjük az aláírási információk kinyerésének folyamatán a biztosított C# forráskód használatával.

## Követelmények

Mielőtt elkezdené, győződjön meg arról, hogy a következő előfeltételek teljesülnek:

1. C# programozási nyelv alapismerete.
2. Aspose.PDF for .NET könyvtár telepítve a rendszerére.
3. Érvényes PDF-dokumentum egy vagy több aláírási mezővel.

Most merüljünk el a megvalósítás részleteiben.

## 1. lépés: A szükséges könyvtárak importálása

 A kezdéshez importálnia kell a szükséges könyvtárakat a C# projektbe. Ebben az esetben importálnunk kell a`Aspose.Pdf` és`System.IO` névterek. Ezt úgy teheti meg, hogy hozzáadja a következő kódot a C# fájl elejéhez:

```csharp
using Aspose.Pdf;
using System.IO;
```

## 2. lépés: A dokumentum elérési útjának beállítása

Ezután be kell állítania annak a PDF-dokumentumnak az elérési útját, amelyből ki szeretné bontani az aláírási információkat. Cserélje ki`"YOUR DOCUMENTS DIRECTORY"` a következő kódrészletben a dokumentum tényleges elérési útjával:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
string input = dataDir + "ExtractSignatureInfo.pdf";
```

## 3. lépés: Az aláírás információinak kinyerése

Most térjünk át a kód fő részére, ahol kivonjuk az aláírási információkat a PDF-dokumentumból. A dokumentum űrlapjának minden egyes mezőjét ismételjük, és ellenőrizzük, hogy aláírási mező-e. Ha aláírási mezőt találunk, folytatjuk a tanúsítvány kibontását. Adja hozzá a következő kódrészletet:

```csharp
using (Document pdfDocument = new Document(input))
{
     foreach(Field field in pdfDocument.Form)
     {
         SignatureField sf = field as SignatureField;
         if (sf != null)
         {
             // Vegye ki a tanúsítványt
             Stream cerStream = sf.ExtractCertificate();
             if (cerStream != null)
             {
                 using (cerStream)
                 {
                     byte[] bytes = new byte[cerStream.Length];
                     using (FileStream fs = new FileStream(dataDir + @"input.cer", FileMode.CreateNew))
                     {
                         cerStream.Read(bytes, 0, bytes.Length);
                         fs.Write(bytes, 0, bytes.Length);
                     }
                 }
             }
         }
     }
}
```

## 4. lépés: A tanúsítvány kibontása

Ebben a lépésben kibontjuk a tanúsítványt az aláírási mezőből, és elmentjük fájlként. A kivont tanúsítvány tovább elemezhető, illetve érvényesítési célokra felhasználható. Az alábbi kódrészlet a kinyerési és mentési folyamatot mutatja be:

```csharp
Stream cerStream = sf.ExtractCertificate();
if (cerStream != null)
{
     using (cerStream)
     {
         byte[] bytes = new byte[cerStream.Length];
         using (FileStream fs = new FileStream(dataDir + @"input.cer", FileMode.CreateNew))
         {
             cerStream.Read(bytes, 0, bytes.Length);
             fs.Write(bytes, 0, bytes.Length);
         }
     }
}
```

## 5. lépés

: A tanúsítvány mentése

Végül a kibontott tanúsítványt fájlként mentjük el. Ebben a példában a tanúsítvány „input.cer” néven kerül mentésre a megadott könyvtárba. A kódot igényeinek megfelelően módosíthatja. Íme a kódrészlet a tanúsítvány mentéséhez:

```csharp
using (FileStream fs = new FileStream(dataDir + @"input.cer", FileMode.CreateNew))
{
     fs.Write(bytes, 0, bytes.Length);
}
```

Ennyi! Sikeresen kinyerte az aláírási információkat az Aspose.PDF for .NET használatával. Nyugodtan integrálhatja ezt a kódot saját alkalmazásaiba, vagy módosíthatja igényei szerint.

### Minta forráskód az aláírási információk kibontásához az Aspose.PDF for .NET használatával 
```csharp
try
{
	// A dokumentumok könyvtárának elérési útja.
	string dataDir = "YOUR DOCUMENTS DIRECTORY";
	string input = dataDir + "ExtractSignatureInfo.pdf";
	using (Document pdfDocument = new Document(input))
	{
		foreach (Field field in pdfDocument.Form)
		{
			SignatureField sf = field as SignatureField;
			if (sf != null)
			{
				Stream cerStream = sf.ExtractCertificate();
				if (cerStream != null)
				{
					using (cerStream)
					{
						byte[] bytes = new byte[cerStream.Length];
						using (FileStream fs = new FileStream(dataDir + @"input.cer", FileMode.CreateNew))
						{
							cerStream.Read(bytes, 0, bytes.Length);
							fs.Write(bytes, 0, bytes.Length);
						}
					}
				}
			}
		}
	}
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## Következtetés

Ebben az oktatóanyagban lépésről lépésre bemutattuk, hogyan lehet aláírási információkat kinyerni egy PDF-dokumentumból az Aspose.PDF for .NET könyvtár használatával. Kitértünk a szükséges könyvtárak importálására, a dokumentum elérési útjának beállítására, az aláírási információk kinyerésére, a tanúsítvány kibontására és fájlba mentésére. Ha követi ezeket a lépéseket, könnyedén lekérheti az aláírás adatait, és szükség szerint dolgozhat velük.

### GYIK

#### K: Miért kell az aláírási információkat kivonnom egy PDF-dokumentumból?

V: Az aláírási információk PDF-dokumentumból való kinyerése hasznos az aláírt dokumentum hitelességének ellenőrzéséhez és az aláíráshoz használt tanúsítvány elemzéséhez. Ez a folyamat segít biztosítani az aláírt tartalom integritását, és jogi és biztonsági okokból elengedhetetlen lehet.

#### K: Mi az Aspose.PDF for .NET?

V: Az Aspose.PDF for .NET egy olyan könyvtár, amely lehetővé teszi a fejlesztők számára, hogy PDF-dokumentumokkal dolgozzanak .NET-alkalmazásokban. Funkciók széles skáláját kínálja a PDF-fájlok programozott létrehozásához, módosításához és interakciójához.

#### K: Milyen előfeltételei vannak az aláírási információk kinyerésének az Aspose.PDF for .NET használatával?

V: Az aláírási információk kinyeréséhez alapvető ismeretekre van szüksége a C# programozási nyelvről, a rendszerére telepített Aspose.PDF for .NET könyvtárról, valamint egy érvényes PDF dokumentumról, amely egy vagy több aláírási mezőt tartalmaz.

#### K: Hogyan importálhatom a kibontási folyamathoz szükséges könyvtárakat?

V: Importálhatja a szükséges könyvtárakat a`using` számára vonatkozó irányelvek`Aspose.Pdf` és`System.IO` a C# fájl elején. Ezek az irányelvek lehetővé teszik az aláírási információk kinyeréséhez szükséges osztályok és metódusok használatát.

#### K: Hogyan adhatom meg a PDF-dokumentumot az aláírási információk kinyeréséhez?

 V: Cserélésével beállíthatja a PDF-dokumentum elérési útját`"YOUR DOCUMENTS DIRECTORY"` a dokumentum tényleges elérési útjával a megadott kódrészletben. Ezt az elérési utat használják annak a PDF-dokumentumnak a betöltésére, amelyből aláírási információkat kíván kivonni.

#### K: Mi a folyamata az aláírási információk kinyerésének egy PDF-dokumentumból?

V: A kinyerési folyamat magában foglalja a PDF-dokumentum űrlapmezőinek iterációját, annak ellenőrzését, hogy minden mező aláírásmező-e, és ha igen, akkor a kapcsolódó tanúsítvány kibontását. A kibontott tanúsítvány fájlként menthető el további elemzés vagy érvényesítés céljából.

#### K: Hogyan nyerhető ki a tanúsítvány az aláírási mezőből?

V: A tanúsítvány egy aláírási mezőből nyerhető ki a`ExtractCertificate()` által biztosított módszer`SignatureField` osztály az Aspose.PDF-ben .NET-hez. Ez a metódus a tanúsítvány adatait tartalmazó adatfolyamot ad vissza.

#### K: Hogyan menthetem el a kibontott tanúsítványt fájlként?

 V: A kibontott tanúsítványt fájlként mentheti, ha elolvassa a tanúsítványfolyamot, és a tartalmát fájlba írja a`FileStream` osztály. Az oktatóanyagban található kód bemutatja ezt a folyamatot.

#### K: Használhatom ezt a kibontott tanúsítványt aláírás-ellenőrzéshez?

V: Igen, a kivont tanúsítvány használható aláírás-ellenőrzésre. Elemezheti a tanúsítvány részleteit, és ellenőrizheti annak hitelességét az aláírt dokumentum sértetlenségének biztosítása érdekében.

#### K: Hogyan integrálhatom ezt a kódot a saját alkalmazásaimba?

V: A megadott kódot a lépésenkénti útmutató követésével integrálhatja saját C# alkalmazásaiba. Szükség szerint módosítsa az elérési utakat és a fájlneveket, és építse be a kódot meglévő projektjeibe.

#### K: Vannak az Aspose.PDF for .NET-ben egyéb, az aláíráskezeléshez kapcsolódó funkciók?

V: Igen, az Aspose.PDF for .NET számos szolgáltatást kínál a digitális aláírásokkal való munkavégzéshez, beleértve a dokumentumok aláírását, az aláírások ellenőrzését és az időbélyegző információk hozzáadását. A funkciókkal kapcsolatos további részletekért tekintse meg a hivatalos dokumentációt.

#### K: Hol találhatok további forrásokat az Aspose.PDF for .NET használatához?

 V: Az Aspose.PDF .NET-hez használatával kapcsolatos további információkért, oktatóanyagokért és forrásokért,[Aspose.PDF for .NET](https://reference.aspose.com/pdf/net/).

#### K: Lehetséges aláírásokat kinyerni titkosított PDF dokumentumokból?

V: A titkosított PDF-dokumentumokból aláírások kinyerésének képessége a dokumentum titkosítási beállításaitól és engedélyeitől függhet. Előfordulhat, hogy meg kell győződnie arról, hogy rendelkezik a szükséges engedélyekkel az aláírási információk eléréséhez és kivonásához.

#### K: Kivonhatok több aláírást egyetlen PDF dokumentumból?

V: Igen, módosíthatja a megadott kódot, hogy a PDF-dokumentum összes aláírási mezőjében végigfusson, és mindegyikből kivonja az aláírási információkat. Ez lehetővé teszi, hogy információkat nyerjen ki a dokumentumban található több aláírásról.

#### K: Milyen gyakorlati esetek alkalmazhatók az aláírási információk kinyerésére?

V: Az aláírási információk kinyerésére szolgáló gyakorlati felhasználási esetek közé tartozik a digitálisan aláírt dokumentumok hitelességének ellenőrzése, a tanúsítvány részleteinek megfelelőségi célú elemzése, valamint az aláírások és aláírók nyilvántartása ellenőrzési célból.

#### K: Vannak-e jogi megfontolások az aláírási információk kinyerésekor?

V: Az aláírási információk kinyerésének jogi következményei lehetnek, különösen a jogilag kötelező erejű dokumentumok kezelésekor. Győződjön meg arról, hogy betartja az elektronikus aláírással és a dokumentumok hitelességével kapcsolatos vonatkozó előírásokat és törvényeket az Ön joghatóságában.