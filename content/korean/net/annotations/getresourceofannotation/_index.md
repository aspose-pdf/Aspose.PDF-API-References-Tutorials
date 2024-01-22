---
title: 주석 리소스 가져오기
linktitle: 주석 리소스 가져오기
second_title: .NET API 참조용 Aspose.PDF
description: 이 단계별 가이드를 통해 .NET용 Aspose.PDF를 사용하여 주석 리소스를 검색하는 방법을 알아보세요.
type: docs
weight: 90
url: /ko/net/annotations/getresourceofannotation/
---
이 예는 .NET용 Aspose.PDF를 사용하여 주석 리소스를 얻는 방법을 보여줍니다. .NET용 Aspose.PDF를 사용하여 주석 리소스를 얻으려면 다음 단계를 따르세요.

## 1단계: 문서가 위치한 디렉터리의 경로를 설정합니다.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 2단계: 얻으려는 리소스의 주석이 포함된 PDF 문서를 엽니다.

```csharp
Document doc = new Document(dataDir + "AddAnnotation.pdf");
```

## 3단계: 주석을 만듭니다.

```csharp
ScreenAnnotation sa = new ScreenAnnotation(doc.Pages[1], new Rectangle(100, 400, 300, 600), dataDir + "AddSwfFileAsAnnotation.swf");
```

## 4단계: 문서의 페이지에 주석을 추가합니다.

```csharp
doc.Pages[1].Annotations.Add(sa);
```

## 5단계: 문서를 저장합니다.

```csharp
doc.Save(dataDir + "GetResourceOfAnnotation_Out.pdf");
```

## 6단계: 수정된 문서를 엽니다.

```csharp
Document doc1 = new Document(dataDir + "GetResourceOfAnnotation_Out.pdf");
```

## 7단계: 주석 작업을 가져옵니다.

```csharp
RenditionAction action = (doc.Pages[1].Annotations[1] as ScreenAnnotation).Action as RenditionAction;
```

## 7단계: 동작의 표현을 가져옵니다.

```csharp
Rendition rendition = ((doc.Pages[1].Annotations[1] as ScreenAnnotation).Action as RenditionAction).Rendition;
```

## 8단계: 미디어 클립을 가져옵니다.

```csharp
MediaClip clip = (rendition as MediaRendition).MediaClip;
```

## 9단계: 파일 사양을 가져옵니다.

```csharp
FileSpecification data = (clip as MediaClipData).Data;
```

## 10단계: 미디어의 데이터를 읽습니다.

```csharp
MemoryStream ms = new MemoryStream();
byte[] buffer = new byte[1024];
int read = 0;
Stream source = data.Contents;
while ((read = source.Read(buffer, 0, buffer.Length)) > 0)
{
   ms.Write(buffer, 0, read);
}
```

## 11단계: 변환 이름과 변환 작업을 인쇄합니다.

```csharp
Console.WriteLine(rendition.Name);
Console.WriteLine(action.RenditionOperation);
```

다음 단계를 따르면 Aspose.PDF for .NET을 사용하여 PDF 문서의 주석 리소스를 쉽게 얻을 수 있습니다.

### .NET용 Aspose.PDF를 사용하여 주석 리소스 가져오기의 소스 코드 예:

```csharp
// 문서 디렉터리의 경로입니다.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// 문서 열기
Document doc = new Document(dataDir + "AddAnnotation.pdf");
//주석 만들기
ScreenAnnotation sa = new ScreenAnnotation(doc.Pages[1], new Rectangle(100, 400, 300, 600), dataDir + "AddSwfFileAsAnnotation.swf");
doc.Pages[1].Annotations.Add(sa);
// 문서 저장
doc.Save(dataDir + "GetResourceOfAnnotation_Out.pdf");
// 문서 열기
Document doc1 = new Document(dataDir + "GetResourceOfAnnotation_Out.pdf");
//주석 작업 가져오기
RenditionAction action = (doc.Pages[1].Annotations[1] as ScreenAnnotation).Action as RenditionAction;
//변환 작업의 변환 가져오기
Rendition rendition = ((doc.Pages[1].Annotations[1] as ScreenAnnotation).Action as RenditionAction).Rendition;
// 미디어 클립
MediaClip clip = (rendition as MediaRendition).MediaClip;
FileSpecification data = (clip as MediaClipData).Data;
MemoryStream ms = new MemoryStream();
byte[] buffer = new byte[1024];
int read = 0;
//FileSpecification.Contents에서 미디어 데이터에 액세스할 수 있습니다.
Stream source = data.Contents;
while ((read = source.Read(buffer, 0, buffer.Length)) > 0)
{
ms.Write(buffer, 0, read);
}
Console.WriteLine(rendition.Name);
Console.WriteLine(action.RenditionOperation);
```

## 결론

이 튜토리얼에서는 Aspose.PDF for .NET을 사용하여 PDF 문서에서 특정 주석의 리소스를 얻는 방법을 살펴보았습니다. 단계별 가이드를 따르고 제공된 C# 소스 코드를 사용하면 개발자는 PDF 문서에서 변환 주석을 포함한 주석에 쉽게 액세스하고 관리할 수 있습니다.

### FAQ

#### Q: PDF 주석과 관련하여 변환이란 무엇입니까?

A: PDF 주석과 관련하여 변환은 멀티미디어 콘텐츠 프레젠테이션입니다. PDF 문서 내에 오디오나 비디오와 같은 멀티미디어를 삽입할 수 있습니다. 변환 주석은 표시할 미디어와 재생 방법을 지정합니다.

#### Q: 변환 주석과 관련된 미디어 파일의 이름을 얻을 수 있습니까?

A: 예, .NET용 Aspose.PDF를 사용하여 변환 주석과 관련된 미디어 파일의 이름을 얻을 수 있습니다. 미디어 파일 이름은 다음을 통해 액세스할 수 있습니다.`FileSpecification` ~의`MediaClip` 물체.

#### Q: .NET용 Aspose.PDF는 변환 주석에서 미디어 파일을 추출할 수 있습니까?

A: 예, .NET용 Aspose.PDF는 오디오 또는 비디오 콘텐츠가 포함된 변환 주석에서 미디어 데이터를 추출하여 별도의 파일로 저장할 수 있습니다.

#### Q: 변환 주석의 미디어 데이터에 어떻게 액세스할 수 있습니까?

 A: 변환 주석의 미디어 데이터는 다음을 통해 액세스할 수 있습니다.`FileSpecification.Contents` 의 재산`MediaClipData` 물체.

#### Q: .NET용 Aspose.PDF를 사용하여 변환 주석과 연결된 미디어를 수정할 수 있습니까?

A: .NET용 Aspose.PDF는 변환 주석과 관련된 미디어 데이터에 액세스하고 수정하는 방법을 제공합니다. 변환 주석에 사용되는 미디어 파일을 업데이트하거나 교체할 수 있습니다.