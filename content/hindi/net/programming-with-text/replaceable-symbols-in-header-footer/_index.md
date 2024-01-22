---
title: शीर्ष लेख पाद लेख में बदले जाने योग्य प्रतीक
linktitle: शीर्ष लेख पाद लेख में बदले जाने योग्य प्रतीक
second_title: .NET API संदर्भ के लिए Aspose.PDF
description: .NET के लिए Aspose.PDF का उपयोग करके PDF दस्तावेज़ के शीर्षलेख और पादलेख में प्रतिस्थापन योग्य प्रतीकों का उपयोग करना सीखें।
type: docs
weight: 320
url: /hi/net/programming-with-text/replaceable-symbols-in-header-footer/
---
इस ट्यूटोरियल में, हम बताएंगे कि .NET के लिए Aspose.PDF लाइब्रेरी का उपयोग करके पीडीएफ दस्तावेज़ के शीर्षलेख और पादलेख में प्रतिस्थापन योग्य प्रतीकों का उपयोग कैसे करें। हम पीडीएफ बनाने, मार्जिन सेट करने, बदले जाने योग्य प्रतीकों के साथ हेडर और फुटर जोड़ने और दिए गए सी # स्रोत कोड का उपयोग करके पीडीएफ को सहेजने की चरण-दर-चरण प्रक्रिया से गुजरेंगे।

## आवश्यक शर्तें

शुरू करने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित हैं:

- .NET लाइब्रेरी के लिए Aspose.PDF स्थापित किया गया।
- C# प्रोग्रामिंग की बुनियादी समझ।

## चरण 1: दस्तावेज़ निर्देशिका सेट करें

 सबसे पहले, आपको उस निर्देशिका के लिए पथ सेट करना होगा जहां आप जेनरेट की गई पीडीएफ फाइल को सहेजना चाहते हैं। प्रतिस्थापित करें`"YOUR DOCUMENT DIRECTORY"` में`dataDir`आपकी वांछित निर्देशिका के पथ के साथ परिवर्तनीय।

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## चरण 2: एक पीडीएफ दस्तावेज़ और पेज बनाएं

 इसके बाद, हम एक नया पीडीएफ दस्तावेज़ बनाते हैं और इसका उपयोग करके इसमें एक पेज जोड़ते हैं`Document` कक्षा और`Page` Aspose.PDF लाइब्रेरी से कक्षा।

```csharp
Document doc = new Document();
Page page = doc.Pages.Add();
```

## चरण 3: मार्जिन सेट करें

 हम इसका उपयोग करके पेज के लिए मार्जिन सेट करते हैं`MarginInfo`कक्षा। अपनी आवश्यकताओं के अनुसार मार्जिन मानों को समायोजित करें।

```csharp
MarginInfo marginInfo = new MarginInfo();
marginInfo.Top = 90;
marginInfo.Bottom = 50;
marginInfo.Left = 50;
marginInfo.Right = 50;
page.PageInfo.Margin = marginInfo;
```

## चरण 4: बदले जाने योग्य प्रतीकों के साथ हेडर जोड़ें

 हम एक बनाते हैं`HeaderFooter` पेज के लिए ऑब्जेक्ट करें और एक जोड़ें`TextFragment` इसके बदले जाने योग्य प्रतीकों के साथ।

```csharp
HeaderFooter hfFirst = new HeaderFooter();
page.Header = hfFirst;
hfFirst.Margin.Left = 50;
hfFirst.Margin.Right = 50;

TextFragment t1 = new TextFragment("report title");
// यदि वांछित हो तो टेक्स्ट गुण सेट करें
t1.TextState.Font = FontRepository.FindFont("Arial");
t1.TextState.FontSize = 16;
t1.TextState.ForegroundColor = Aspose.Pdf.Color.Black;
t1.TextState.FontStyle = FontStyles.Bold;
t1.TextState.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Center;
t1.TextState.LineSpacing = 5f;

hfFirst.Paragraphs.Add(t1);

// अधिक TextFragments जोड़ें या आवश्यकतानुसार अनुकूलित करें
```

## चरण 5: बदले जाने योग्य प्रतीकों के साथ पाद लेख जोड़ें

 इसी प्रकार, हम एक बनाते हैं`HeaderFooter` पृष्ठ पाद लेख के लिए ऑब्जेक्ट करें और जोड़ें`TextFragment` प्रतिस्थापन योग्य प्रतीकों वाली वस्तुएं।

```csharp
HeaderFooter hfFoot = new HeaderFooter();
page.Footer = hfFoot;
hfFoot.Margin.Left = 50;
hfFoot.Margin.Right = 50;

TextFragment t3 = new TextFragment("Generated on test date");
TextFragment t4 = new TextFragment("report name ");
TextFragment t5 = new TextFragment("Page $p of $P");

// अधिक TextFragments जोड़ें या आवश्यकतानुसार अनुकूलित करें

hfFoot.Paragraphs.Add(tab2);
```

## चरण 6: पीडीएफ दस्तावेज़ सहेजें

अंत में, हम पीडीएफ दस्तावेज़ को निर्दिष्ट आउटपुट फ़ाइल में सहेजते हैं।

```csharp
dataDir = dataDir + "ReplaceableSymbolsInHeaderFooter_out.pdf";
doc.Save(dataDir);
Console.WriteLine("\nReplaceable symbols replaced successfully in the header and footer.\nFile saved at " + dataDir);
```

### .NET के लिए Aspose.PDF का उपयोग करके हेडर फ़ुटर में बदले जाने योग्य प्रतीकों के लिए नमूना स्रोत कोड 
```csharp
// दस्तावेज़ निर्देशिका का पथ.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
Page page = doc.Pages.Add();
MarginInfo marginInfo = new MarginInfo();
marginInfo.Top = 90;
marginInfo.Bottom = 50;
marginInfo.Left = 50;
marginInfo.Right = 50;
// मार्जिनइन्फो इंस्टेंस को sec1.PageInfo की मार्जिन प्रॉपर्टी पर असाइन करें
page.PageInfo.Margin = marginInfo;
HeaderFooter hfFirst = new HeaderFooter();
page.Header = hfFirst;
hfFirst.Margin.Left = 50;
hfFirst.Margin.Right = 50;
// एक टेक्स्ट पैराग्राफ को इंस्टेंट करें जो सामग्री को हेडर के रूप में दिखाने के लिए संग्रहीत करेगा
TextFragment t1 = new TextFragment("report title");
t1.TextState.Font = FontRepository.FindFont("Arial");
t1.TextState.FontSize = 16;
t1.TextState.ForegroundColor = Aspose.Pdf.Color.Black;
t1.TextState.FontStyle = FontStyles.Bold;
t1.TextState.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Center;
t1.TextState.LineSpacing = 5f;
hfFirst.Paragraphs.Add(t1);
TextFragment t2 = new TextFragment("Report_Name");
t2.TextState.Font = FontRepository.FindFont("Arial");
t2.TextState.ForegroundColor = Aspose.Pdf.Color.Black;
t2.TextState.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Center;
t2.TextState.LineSpacing = 5f;
t2.TextState.FontSize = 12;
hfFirst.Paragraphs.Add(t2);
// अनुभाग के लिए एक हेडरफुटर ऑब्जेक्ट बनाएं
HeaderFooter hfFoot = new HeaderFooter();
// हेडरफ़ुटर ऑब्जेक्ट को विषम और सम फ़ुटर पर सेट करें
page.Footer = hfFoot;
hfFoot.Margin.Left = 50;
hfFoot.Margin.Right = 50;
// कुल पृष्ठों की संख्या की वर्तमान पृष्ठ संख्या वाला एक टेक्स्ट पैराग्राफ जोड़ें
TextFragment t3 = new TextFragment("Generated on test date");
TextFragment t4 = new TextFragment("report name ");
TextFragment t5 = new TextFragment("Page $p of $P");
// किसी तालिका ऑब्जेक्ट को त्वरित करें
Table tab2 = new Table();
// वांछित अनुभाग के पैराग्राफ संग्रह में तालिका जोड़ें
hfFoot.Paragraphs.Add(tab2);
// तालिका की कॉलम चौड़ाई के साथ सेट करें
tab2.ColumnWidths = "165 172 165";
// तालिका में पंक्तियाँ और फिर पंक्तियों में कक्ष बनाएँ
Row row3 = tab2.Rows.Add();
row3.Cells.Add();
row3.Cells.Add();
row3.Cells.Add();
// टेक्स्ट के ऊर्ध्वाधर संरेखण को केंद्र संरेखण के रूप में सेट करें
row3.Cells[0].Alignment = Aspose.Pdf.HorizontalAlignment.Left;
row3.Cells[1].Alignment = Aspose.Pdf.HorizontalAlignment.Center;
row3.Cells[2].Alignment = Aspose.Pdf.HorizontalAlignment.Right;
row3.Cells[0].Paragraphs.Add(t3);
row3.Cells[1].Paragraphs.Add(t4);
row3.Cells[2].Paragraphs.Add(t5);
//Sec1.Paragraphs.Add(नया टेक्स्ट ("Aspose.Total for Java, Aspose द्वारा पेश किए गए प्रत्येक जावा घटक का एक संकलन है। इसे #$NL" + "दैनिक आधार पर संकलित किया जाता है ताकि यह सुनिश्चित किया जा सके कि इसमें प्रत्येक के सबसे अद्यतित संस्करण शामिल हैं) हमारे जावा घटकों का। #$NL " + "जावा डेवलपर्स के लिए Aspose.Total का उपयोग करके अनुप्रयोगों की एक विस्तृत श्रृंखला बनाई जा सकती है। #$NL #$NL #$NP" + "Aspose.Total for Java प्रत्येक जावा घटक का संकलन है Aspose द्वारा प्रस्तावित। इसे #$NL" + "दैनिक आधार पर संकलित किया जाता है ताकि यह सुनिश्चित किया जा सके कि इसमें हमारे प्रत्येक जावा घटक के सबसे अद्यतित संस्करण शामिल हैं। #$NL " + "जावा डेवलपर्स के लिए Aspose.Total का उपयोग करके एक विस्तृत बनाया जा सकता है अनुप्रयोगों की श्रेणी। #$NL #$NL #$NP" + "Aspose.Total for Java, Aspose द्वारा पेश किए गए प्रत्येक जावा घटक का एक संकलन है। इसे #$NL" + "दैनिक आधार पर संकलित किया जाता है ताकि यह सुनिश्चित किया जा सके कि इसमें सबसे अधिक शामिल है हमारे प्रत्येक जावा घटक के अद्यतन संस्करण। #$NL " + "जावा डेवलपर्स के लिए Aspose.Total का उपयोग करके अनुप्रयोगों की एक विस्तृत श्रृंखला बनाई जा सकती है। #$NL #$NL"))
Table table = new Table();
table.ColumnWidths = "33% 33% 34%";
table.DefaultCellPadding = new MarginInfo();
table.DefaultCellPadding.Top = 10;
table.DefaultCellPadding.Bottom = 10;
// वांछित अनुभाग के पैराग्राफ संग्रह में तालिका जोड़ें
page.Paragraphs.Add(table);
// बॉर्डरइन्फो ऑब्जेक्ट का उपयोग करके डिफ़ॉल्ट सेल बॉर्डर सेट करें
table.DefaultCellBorder = new BorderInfo(BorderSide.All, 0.1f);
// किसी अन्य अनुकूलित बॉर्डरइन्फो ऑब्जेक्ट का उपयोग करके टेबल बॉर्डर सेट करें
table.Border = new BorderInfo(BorderSide.All, 1f);
table.RepeatingRowsCount = 1;
// तालिका में पंक्तियाँ और फिर पंक्तियों में कक्ष बनाएँ
Row row1 = table.Rows.Add();
row1.Cells.Add("col1");
row1.Cells.Add("col2");
row1.Cells.Add("col3");
const string CRLF = "\r\n";
for (int i = 0; i <= 10; i++)
{
	Row row = table.Rows.Add();
	row.IsRowBroken = true;
	for (int c = 0; c <= 2; c++)
	{
		Cell c1;
		if (c == 2)
			c1 = row.Cells.Add("Aspose.Total for Java is a compilation of every Java component offered by Aspose. It is compiled on a" + CRLF + "daily basis to ensure it contains the most up to date versions of each of our Java components. " + CRLF + "daily basis to ensure it contains the most up to date versions of each of our Java components. " + CRLF + "Using Aspose.Total for Java developers can create a wide range of applications.");
		else
			c1 = row.Cells.Add("item1" + c);
		c1.Margin = new MarginInfo();
		c1.Margin.Left = 30;
		c1.Margin.Top = 10;
		c1.Margin.Bottom = 10;
	}
}
dataDir = dataDir + "ReplaceableSymbolsInHeaderFooter_out.pdf";
doc.Save(dataDir);
Console.WriteLine("\nSymbols replaced successfully in header and footer.\nFile saved at " + dataDir);
```

## निष्कर्ष

इस ट्यूटोरियल में, आपने सीखा है कि .NET के लिए Aspose.PDF लाइब्रेरी का उपयोग करके पीडीएफ दस्तावेज़ के शीर्षलेख और पादलेख में प्रतिस्थापन योग्य प्रतीकों का उपयोग कैसे करें। चरण-दर-चरण मार्गदर्शिका का पालन करके और दिए गए C# कोड को निष्पादित करके, आप एक पीडीएफ बना सकते हैं, मार्जिन सेट कर सकते हैं, बदले जाने योग्य प्रतीकों के साथ हेडर और पाद लेख जोड़ सकते हैं और पीडीएफ को सहेज सकते हैं।

### अक्सर पूछे जाने वाले प्रश्न

#### प्रश्न: "हेडर फूटर में रिप्लेसेबल सिंबल" ट्यूटोरियल का उद्देश्य क्या है?

उ: "हेडर फूटर में रिप्लेसेबल सिंबल" ट्यूटोरियल का उद्देश्य पीडीएफ दस्तावेज़ के हेडर और फुटर में रिप्लेसेबल सिंबल जोड़ने के लिए .NET के लिए Aspose.PDF लाइब्रेरी का उपयोग करने की प्रक्रिया के माध्यम से आपका मार्गदर्शन करना है। बदले जाने योग्य प्रतीक आपको पीडीएफ बनाते समय विशिष्ट प्लेसहोल्डर्स को वास्तविक मानों के साथ गतिशील रूप से बदलने की अनुमति देते हैं।

#### प्रश्न: पीडीएफ शीर्षलेख और पादलेख के संदर्भ में प्रतिस्थापन योग्य प्रतीक क्या हैं?

उ: बदली जाने योग्य प्रतीक प्लेसहोल्डर हैं जिन्हें आप पीडीएफ दस्तावेज़ के शीर्ष लेख और पाद लेख में सम्मिलित कर सकते हैं। ये प्रतीक उन मानों के लिए गतिशील प्लेसहोल्डर के रूप में कार्य करते हैं जिन्हें रनटाइम पर भरा जा सकता है, जैसे पृष्ठ संख्या, दिनांक और कस्टम जानकारी।

#### प्रश्न: मैं पीडीएफ शीर्षलेख और पादलेख में प्रतिस्थापन योग्य प्रतीकों का उपयोग क्यों करना चाहूंगा?

उ: जब आप अपने पीडीएफ दस्तावेज़ों में गतिशील जानकारी शामिल करना चाहते हैं, जैसे पृष्ठ संख्या, दिनांक, या अन्य परिवर्तनीय डेटा जो दस्तावेज़ उत्पन्न होने पर बदल सकते हैं, तो शीर्ष लेख और पाद लेख में प्रतिस्थापन योग्य प्रतीक उपयोगी होते हैं।

#### प्रश्न: मैं पीडीएफ पेज के लिए मार्जिन कैसे सेट कर सकता हूं?

 उ: आप इसका उपयोग करके पीडीएफ पेज के लिए मार्जिन सेट कर सकते हैं`MarginInfo` क्लास और इसे असाइन करना`Margin` की संपत्ति`PageInfo` पेज का. आवश्यकतानुसार मार्जिन मान समायोजित करें।

#### प्रश्न: मैं शीर्षलेख और पादलेख में बदले जाने योग्य प्रतीकों को कैसे जोड़ूँ?

 उ: आप एक बनाकर प्रतिस्थापन योग्य प्रतीक जोड़ सकते हैं`HeaderFooter` पृष्ठ के शीर्ष लेख और पाद लेख के लिए ऑब्जेक्ट। फिर, आप जोड़ सकते हैं`TextFragment`बदली जाने योग्य प्रतीकों सहित, वांछित पाठ वाली वस्तुओं को`Paragraphs` का संग्रह`HeaderFooter` वस्तु।

#### प्रश्न: क्या मैं बदले जाने योग्य प्रतीकों के स्वरूप को अनुकूलित कर सकता हूँ?

 उ: हां, आप गुणों को संशोधित करके बदले जाने योग्य प्रतीकों की उपस्थिति को अनुकूलित कर सकते हैं`TextFragment` वे वस्तुएँ जिनमें प्रतीक हैं। आप फ़ॉन्ट, फ़ॉन्ट आकार, रंग, संरेखण और पंक्ति रिक्ति जैसे गुण सेट कर सकते हैं।

#### प्रश्न: मैं किस प्रकार के प्रतिस्थापन योग्य प्रतीकों का उपयोग कर सकता हूँ?

उ: आप विभिन्न प्रकार के प्रतिस्थापन योग्य प्रतीकों का उपयोग कर सकते हैं, जैसे:

- `$p`: वर्तमान पृष्ठ संख्या.
- `$P`: पृष्ठों की कुल संख्या.
- `$d`: आज की तारीख।
- `$t`: वर्तमान समय।
- आपके द्वारा परिभाषित कस्टम प्लेसहोल्डर.

#### प्रश्न: क्या मैं बदले जाने योग्य प्रतीकों के आसपास अन्य टेक्स्ट और फ़ॉर्मेटिंग शामिल कर सकता हूँ?

 उत्तर: हाँ, आप इसके भीतर बदले जा सकने वाले प्रतीकों के आसपास अन्य टेक्स्ट और फ़ॉर्मेटिंग शामिल कर सकते हैं`TextFragment` वस्तुएं. यह आपको अधिक जटिल शीर्षलेख और पादलेख बनाने की अनुमति देता है जिसमें गतिशील और स्थिर सामग्री शामिल होती है।

#### प्रश्न: मैं जेनरेट किए गए पीडीएफ दस्तावेज़ को कैसे सहेज सकता हूं?

 उ: जनरेट किए गए पीडीएफ दस्तावेज़ को सहेजने के लिए, आप इसका उपयोग कर सकते हैं`Save` की विधि`Document`कक्षा। तर्क के रूप में वांछित आउटपुट फ़ाइल पथ और नाम प्रदान करें।

#### प्रश्न: क्या इस ट्यूटोरियल के लिए वैध Aspose लाइसेंस आवश्यक है?

उत्तर: हां, इस ट्यूटोरियल में कोड को सफलतापूर्वक निष्पादित करने के लिए एक वैध Aspose लाइसेंस की आवश्यकता है। आप Aspose वेबसाइट से पूर्ण लाइसेंस या 30-दिवसीय अस्थायी लाइसेंस प्राप्त कर सकते हैं।