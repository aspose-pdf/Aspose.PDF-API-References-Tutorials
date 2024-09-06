---
title: हेडर फ़ुटर में प्रतिस्थापन योग्य प्रतीक
linktitle: हेडर फ़ुटर में प्रतिस्थापन योग्य प्रतीक
second_title: .NET API संदर्भ के लिए Aspose.PDF
description: .NET के लिए Aspose.PDF का उपयोग करके PDF दस्तावेज़ के शीर्षलेख और पादलेख में प्रतिस्थापन योग्य प्रतीकों का उपयोग करना सीखें।
type: docs
weight: 320
url: /hi/net/programming-with-text/replaceable-symbols-in-header-footer/
---
इस ट्यूटोरियल में, हम बताएंगे कि .NET के लिए Aspose.PDF लाइब्रेरी का उपयोग करके PDF दस्तावेज़ के हेडर और फ़ुटर में रिप्लेसेबल सिंबल का उपयोग कैसे करें। हम PDF बनाने, मार्जिन सेट करने, रिप्लेसेबल सिंबल के साथ हेडर और फ़ुटर जोड़ने और दिए गए C# सोर्स कोड का उपयोग करके PDF को सेव करने की चरण-दर-चरण प्रक्रिया से गुजरेंगे।

## आवश्यक शर्तें

आरंभ करने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित हैं:

- .NET के लिए Aspose.PDF लाइब्रेरी स्थापित की गई।
- C# प्रोग्रामिंग की बुनियादी समझ.

## चरण 1: दस्तावेज़ निर्देशिका सेट करें

 सबसे पहले, आपको उस डायरेक्टरी का पथ सेट करना होगा जहाँ आप जेनरेट की गई पीडीएफ फाइल को सेव करना चाहते हैं।`"YOUR DOCUMENT DIRECTORY"` में`dataDir` अपने इच्छित निर्देशिका के पथ के साथ चर।

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## चरण 2: एक पीडीएफ दस्तावेज़ और पेज बनाएँ

 इसके बाद, हम एक नया पीडीएफ दस्तावेज़ बनाते हैं और इसमें एक पृष्ठ जोड़ते हैं`Document` वर्ग और`Page` Aspose.PDF लाइब्रेरी से क्लास.

```csharp
Document doc = new Document();
Page page = doc.Pages.Add();
```

## चरण 3: मार्जिन सेट करें

हम पृष्ठ के लिए मार्जिन सेट करते हैं`MarginInfo` वर्ग। अपनी आवश्यकताओं के अनुसार मार्जिन मान समायोजित करें।

```csharp
MarginInfo marginInfo = new MarginInfo();
marginInfo.Top = 90;
marginInfo.Bottom = 50;
marginInfo.Left = 50;
marginInfo.Right = 50;
page.PageInfo.Margin = marginInfo;
```

## चरण 4: प्रतिस्थापन योग्य प्रतीकों के साथ हेडर जोड़ें

 हम एक बनाते हैं`HeaderFooter` पृष्ठ के लिए ऑब्जेक्ट और जोड़ें`TextFragment` इसमें प्रतिस्थापन योग्य प्रतीक भी हैं।

```csharp
HeaderFooter hfFirst = new HeaderFooter();
page.Header = hfFirst;
hfFirst.Margin.Left = 50;
hfFirst.Margin.Right = 50;

TextFragment t1 = new TextFragment("report title");
// यदि चाहें तो पाठ गुण सेट करें
t1.TextState.Font = FontRepository.FindFont("Arial");
t1.TextState.FontSize = 16;
t1.TextState.ForegroundColor = Aspose.Pdf.Color.Black;
t1.TextState.FontStyle = FontStyles.Bold;
t1.TextState.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Center;
t1.TextState.LineSpacing = 5f;

hfFirst.Paragraphs.Add(t1);

// अधिक टेक्स्टफ़्रेग्मेंट जोड़ें या आवश्यकतानुसार अनुकूलित करें
```

## चरण 5: प्रतिस्थापन योग्य प्रतीकों के साथ फ़ुटर जोड़ें

 इसी प्रकार, हम एक बनाते हैं`HeaderFooter` पृष्ठ पाद लेख के लिए ऑब्जेक्ट और जोड़ें`TextFragment` इसमें प्रतिस्थापन योग्य प्रतीकों वाली वस्तुएं शामिल हैं।

```csharp
HeaderFooter hfFoot = new HeaderFooter();
page.Footer = hfFoot;
hfFoot.Margin.Left = 50;
hfFoot.Margin.Right = 50;

TextFragment t3 = new TextFragment("Generated on test date");
TextFragment t4 = new TextFragment("report name ");
TextFragment t5 = new TextFragment("Page $p of $P");

// अधिक टेक्स्टफ़्रेग्मेंट जोड़ें या आवश्यकतानुसार अनुकूलित करें

hfFoot.Paragraphs.Add(tab2);
```

## चरण 6: पीडीएफ दस्तावेज़ सहेजें

अंत में, हम पीडीएफ दस्तावेज़ को निर्दिष्ट आउटपुट फ़ाइल में सहेजते हैं।

```csharp
dataDir = dataDir + "ReplaceableSymbolsInHeaderFooter_out.pdf";
doc.Save(dataDir);
Console.WriteLine("\nReplaceable symbols replaced successfully in the header and footer.\nFile saved at " + dataDir);
```

### .NET के लिए Aspose.PDF का उपयोग करके हेडर फ़ुटर में प्रतिस्थापन योग्य प्रतीकों के लिए नमूना स्रोत कोड 
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
// sec1.PageInfo की मार्जिन प्रॉपर्टी को marginInfo इंस्टेंस असाइन करें
page.PageInfo.Margin = marginInfo;
HeaderFooter hfFirst = new HeaderFooter();
page.Header = hfFirst;
hfFirst.Margin.Left = 50;
hfFirst.Margin.Right = 50;
// एक टेक्स्ट पैराग्राफ़ को इंस्टैंसिएट करें जो हेडर के रूप में दिखाने के लिए सामग्री को संग्रहीत करेगा
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
// अनुभाग के लिए HeaderFooter ऑब्जेक्ट बनाएँ
HeaderFooter hfFoot = new HeaderFooter();
// HeaderFooter ऑब्जेक्ट को विषम और सम फ़ुटर पर सेट करें
page.Footer = hfFoot;
hfFoot.Margin.Left = 50;
hfFoot.Margin.Right = 50;
// कुल पृष्ठों की वर्तमान पृष्ठ संख्या वाला एक पाठ पैराग्राफ जोड़ें
TextFragment t3 = new TextFragment("Generated on test date");
TextFragment t4 = new TextFragment("report name ");
TextFragment t5 = new TextFragment("Page $p of $P");
// तालिका ऑब्जेक्ट को इंस्टैंसिएट करें
Table tab2 = new Table();
// इच्छित अनुभाग के पैराग्राफ संग्रह में तालिका जोड़ें
hfFoot.Paragraphs.Add(tab2);
// तालिका की स्तंभ चौड़ाई के साथ सेट करें
tab2.ColumnWidths = "165 172 165";
// तालिका में पंक्तियाँ बनाएँ और फिर पंक्तियों में कक्ष बनाएँ
Row row3 = tab2.Rows.Add();
row3.Cells.Add();
row3.Cells.Add();
row3.Cells.Add();
// पाठ के ऊर्ध्वाधर संरेखण को केंद्र संरेखित के रूप में सेट करें
row3.Cells[0].Alignment = Aspose.Pdf.HorizontalAlignment.Left;
row3.Cells[1].Alignment = Aspose.Pdf.HorizontalAlignment.Center;
row3.Cells[2].Alignment = Aspose.Pdf.HorizontalAlignment.Right;
row3.Cells[0].Paragraphs.Add(t3);
row3.Cells[1].Paragraphs.Add(t4);
row3.Cells[2].Paragraphs.Add(t5);
//Sec1.Paragraphs.Add(New Text("Aspose.Total for Java, Aspose द्वारा प्रस्तुत प्रत्येक Java घटक का संकलन है। यह सुनिश्चित करने के लिए कि इसमें हमारे प्रत्येक Java घटक का सबसे अद्यतित संस्करण शामिल है, इसे दैनिक आधार पर संकलित किया जाता है।" #$NL " + "Aspose.Total for Java का उपयोग करके डेवलपर्स कई तरह के अनुप्रयोग बना सकते हैं। #$NL #$NL #$NP" + "Aspose.Total for Java, Aspose द्वारा प्रस्तुत प्रत्येक Java घटक का संकलन है। यह सुनिश्चित करने के लिए कि इसमें हमारे प्रत्येक Java घटक का सबसे अद्यतित संस्करण शामिल है, इसे दैनिक आधार पर संकलित किया जाता है।" #$NL " + "Aspose.Total for Java का उपयोग करके डेवलपर्स कई तरह के अनुप्रयोग बना सकते हैं। #$NL #$NL #$NP" + "Aspose.Total for Java, Aspose द्वारा प्रस्तुत प्रत्येक Java घटक का संकलन है। यह सुनिश्चित करने के लिए कि इसमें हमारे प्रत्येक Java घटक का सबसे अद्यतित संस्करण शामिल है, इसे दैनिक आधार पर संकलित किया जाता है।" + "जावा डेवलपर्स के लिए Aspose.Total का उपयोग करके अनुप्रयोगों की एक विस्तृत श्रृंखला बनाई जा सकती है। #$NL #$NL"))
Table table = new Table();
table.ColumnWidths = "33% 33% 34%";
table.DefaultCellPadding = new MarginInfo();
table.DefaultCellPadding.Top = 10;
table.DefaultCellPadding.Bottom = 10;
// इच्छित अनुभाग के पैराग्राफ संग्रह में तालिका जोड़ें
page.Paragraphs.Add(table);
// BorderInfo ऑब्जेक्ट का उपयोग करके डिफ़ॉल्ट सेल बॉर्डर सेट करें
table.DefaultCellBorder = new BorderInfo(BorderSide.All, 0.1f);
// किसी अन्य अनुकूलित BorderInfo ऑब्जेक्ट का उपयोग करके तालिका बॉर्डर सेट करें
table.Border = new BorderInfo(BorderSide.All, 1f);
table.RepeatingRowsCount = 1;
// तालिका में पंक्तियाँ बनाएँ और फिर पंक्तियों में कक्ष बनाएँ
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

इस ट्यूटोरियल में, आपने सीखा है कि .NET के लिए Aspose.PDF लाइब्रेरी का उपयोग करके PDF दस्तावेज़ के हेडर और फ़ुटर में प्रतिस्थापन योग्य प्रतीकों का उपयोग कैसे करें। चरण-दर-चरण मार्गदर्शिका का पालन करके और दिए गए C# कोड को निष्पादित करके, आप एक PDF बना सकते हैं, मार्जिन सेट कर सकते हैं, प्रतिस्थापन योग्य प्रतीकों के साथ हेडर और फ़ुटर जोड़ सकते हैं, और PDF को सहेज सकते हैं।

### अक्सर पूछे जाने वाले प्रश्न

#### प्रश्न: "हैडर-फ़ुटर में प्रतिस्थापन योग्य प्रतीक" ट्यूटोरियल का उद्देश्य क्या है?

उत्तर: "हेडर फ़ुटर में प्रतिस्थापन योग्य प्रतीक" ट्यूटोरियल का उद्देश्य आपको .NET के लिए Aspose.PDF लाइब्रेरी का उपयोग करने की प्रक्रिया के माध्यम से मार्गदर्शन करना है ताकि PDF दस्तावेज़ के हेडर और फ़ुटर में प्रतिस्थापन योग्य प्रतीक जोड़े जा सकें। प्रतिस्थापन योग्य प्रतीक आपको PDF बनाते समय विशिष्ट प्लेसहोल्डर्स को वास्तविक मानों से गतिशील रूप से बदलने की अनुमति देते हैं।

#### प्रश्न: पीडीएफ हेडर और फुटर के संदर्भ में प्रतिस्थापन योग्य प्रतीक क्या हैं?

उत्तर: प्रतिस्थापन योग्य प्रतीक प्लेसहोल्डर हैं जिन्हें आप PDF दस्तावेज़ के शीर्षलेख और पादलेख में डाल सकते हैं। ये प्रतीक उन मानों के लिए गतिशील प्लेसहोल्डर के रूप में कार्य करते हैं जिन्हें रनटाइम पर भरा जा सकता है, जैसे पृष्ठ संख्याएँ, तिथियाँ और कस्टम जानकारी।

#### प्रश्न: मैं पीडीएफ हेडर और फुटर में प्रतिस्थापन योग्य प्रतीकों का उपयोग क्यों करना चाहूंगा?

उत्तर: शीर्षलेख और पादलेख में प्रतिस्थापन योग्य प्रतीक तब उपयोगी होते हैं जब आप अपने PDF दस्तावेज़ों में गतिशील जानकारी शामिल करना चाहते हैं, जैसे पृष्ठ संख्या, दिनांक या अन्य परिवर्तनीय डेटा जो दस्तावेज़ तैयार होने पर बदल सकते हैं।

#### प्रश्न: मैं पीडीएफ पृष्ठ के लिए मार्जिन कैसे सेट कर सकता हूं?

 उत्तर: आप पीडीएफ पेज के लिए मार्जिन सेट कर सकते हैं`MarginInfo` कक्षा और इसे असाइन करना`Margin` की संपत्ति`PageInfo` पृष्ठ का मार्जिन मान आवश्यकतानुसार समायोजित करें।

#### प्रश्न: मैं हेडर और फ़ूटर में प्रतिस्थापन योग्य प्रतीक कैसे जोड़ूं?

 उत्तर: आप एक प्रतिस्थापन योग्य प्रतीक बनाकर जोड़ सकते हैं`HeaderFooter` पेज के हेडर और फ़ुटर के लिए ऑब्जेक्ट। फिर, आप जोड़ सकते हैं`TextFragment`वांछित पाठ वाली वस्तुओं को, जिसमें प्रतिस्थापन योग्य प्रतीक भी शामिल हैं,`Paragraphs` का संग्रह`HeaderFooter` वस्तु।

#### प्रश्न: क्या मैं प्रतिस्थापन योग्य प्रतीकों के स्वरूप को अनुकूलित कर सकता हूँ?

 उत्तर: हां, आप प्रतिस्थापन योग्य प्रतीकों के गुणों को संशोधित करके उनकी उपस्थिति को अनुकूलित कर सकते हैं।`TextFragment` ऑब्जेक्ट जिसमें प्रतीक होते हैं। आप फ़ॉन्ट, फ़ॉन्ट आकार, रंग, संरेखण और पंक्ति रिक्ति जैसे गुण सेट कर सकते हैं।

#### प्रश्न: मैं किस प्रकार के प्रतिस्थापन योग्य प्रतीकों का उपयोग कर सकता हूँ?

उत्तर: आप विभिन्न प्रकार के प्रतिस्थापन योग्य प्रतीकों का उपयोग कर सकते हैं, जैसे:

- `$p`: वर्तमान पृष्ठ संख्या.
- `$P`: कुल पृष्ठों की संख्या.
- `$d`: वर्तमान दिनांक.
- `$t`: वर्तमान समय.
- आपके द्वारा परिभाषित कस्टम प्लेसहोल्डर्स.

#### प्रश्न: क्या मैं प्रतिस्थापन योग्य प्रतीकों के आसपास अन्य पाठ और स्वरूपण शामिल कर सकता हूँ?

 उत्तर: हां, आप प्रतिस्थापन योग्य प्रतीकों के आसपास अन्य पाठ और स्वरूपण शामिल कर सकते हैं`TextFragment` ऑब्जेक्ट्स। यह आपको अधिक जटिल हेडर और फ़ुटर बनाने की अनुमति देता है जो गतिशील और स्थिर सामग्री को शामिल करते हैं।

#### प्रश्न: मैं उत्पन्न पीडीएफ दस्तावेज़ को कैसे सहेज सकता हूं?

 उत्तर: उत्पन्न पीडीएफ दस्तावेज़ को सहेजने के लिए, आप इसका उपयोग कर सकते हैं`Save` की विधि`Document`class. वांछित आउटपुट फ़ाइल पथ और नाम को तर्क के रूप में प्रदान करें।

#### प्रश्न: क्या इस ट्यूटोरियल के लिए वैध एस्पोज लाइसेंस आवश्यक है?

उत्तर: हाँ, इस ट्यूटोरियल में कोड को सफलतापूर्वक निष्पादित करने के लिए एक वैध Aspose लाइसेंस की आवश्यकता है। आप Aspose वेबसाइट से पूर्ण लाइसेंस या 30-दिन का अस्थायी लाइसेंस प्राप्त कर सकते हैं।