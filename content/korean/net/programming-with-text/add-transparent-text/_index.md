---
title: PDF 파일에 투명 텍스트 추가
linktitle: PDF 파일에 투명 텍스트 추가
second_title: .NET API 참조용 Aspose.PDF
description: .NET용 Aspose.PDF를 사용하여 PDF 파일에 투명한 텍스트를 추가하는 방법을 알아보세요.
type: docs
weight: 100
url: /ko/net/programming-with-text/add-transparent-text/
---
이 튜토리얼은 .NET용 Aspose.PDF를 사용하여 PDF 문서에 투명한 텍스트를 추가하는 과정을 안내합니다. 제공된 C# 소스 코드는 필요한 단계를 보여줍니다.

## 요구사항
시작하기 전에 다음 사항이 있는지 확인하세요.

- 컴퓨터에 Visual Studio 또는 기타 C# 컴파일러가 설치되어 있습니다.
- .NET 라이브러리용 Aspose.PDF. 공식 Aspose 웹사이트에서 다운로드하거나 NuGet과 같은 패키지 관리자를 사용하여 설치할 수 있습니다.

## 1단계: 프로젝트 설정
1. 원하는 개발 환경에서 새 C# 프로젝트를 만듭니다.
2. .NET 라이브러리용 Aspose.PDF에 대한 참조를 추가합니다.

## 2단계: 필수 네임스페이스 가져오기
투명한 텍스트를 추가하려는 코드 파일에서 파일 상단에 다음 using 지시문을 추가합니다.

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Drawing;
```

## 3단계: 문서 디렉터리 설정
 코드에서 다음과 같은 줄을 찾으세요.`string dataDir = "YOUR DOCUMENT DIRECTORY";` 교체하고`"YOUR DOCUMENT DIRECTORY"` 문서가 저장된 디렉토리의 경로를 사용하세요.

## 4단계: 새 문서 인스턴스 만들기
 새 인스턴스화`Document` 다음 코드 줄을 추가하여 객체를 생성합니다.

```csharp
Document doc = new Document();
```

## 5단계: 문서에 페이지 추가
 다음을 사용하여 문서에 새 페이지를 추가합니다.`Add` 의 방법`Pages`수집. 제공된 코드에서 새 페이지는 변수에 할당됩니다.`page`.

```csharp
Aspose.Pdf.Page page = doc.Pages.Add();
```

## 6단계: 그래프 개체 만들기
 새로 만들기`Graph` 특정 너비와 높이를 가진 개체.

```csharp
Aspose.Pdf.Drawing.Graph canvas = new Aspose.Pdf.Drawing.Graph(100, 400);
```

## 7단계: 투명도가 있는 직사각형 만들기
 특정 치수로 직사각형을 만들고 다음을 사용하여 채우기 색상을 투명 색상으로 설정합니다.`Color.FromRgb` 방법.

```csharp
Aspose.Pdf.Drawing.Rectangle rect = new Aspose.Pdf.Drawing.Rectangle(100, 100, 400, 400);
rect.GraphInfo.FillColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.FromArgb(128, System.Drawing.Color.FromArgb(12957183)));
canvas.Shapes.Add(rect);
```

## 8단계: 페이지에 그래프 개체 추가
 추가`Graph` 페이지의 단락 모음에 반대합니다.

```csharp
page.Paragraphs.Add(canvas);
```

## 9단계: 그래프 개체의 위치 설정
 설정`IsChangePosition` 의 재산`Graph` 반대하다`false` 위치가 바뀌는 것을 방지합니다.

```csharp
canvas. IsChangePosition = false;
```

## 10단계: 투명도가 있는 TextFragment 만들기
 만들기`TextFragment` 개체를 선택하고 그 내용을 원하는 텍스트로 설정합니다. 설정`ForegroundColor` 의 재산`TextState` 다음을 사용하여 투명도가 있는 색상으로`Color.FromArgb` 방법.

```csharp
TextFragment text = new TextFragment("transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text ");
Aspose.Pdf.Color color = Aspose.Pdf.Color.FromArgb(30, 0, 255, 0);
text.TextState.ForegroundColor = color;
page.Paragraphs.Add(text);
```

## 11단계: PDF 문서 저장
 다음을 사용하여 PDF 문서를 저장합니다.`Save` 의 방법`Document` 물체.

```csharp
doc.Save(dataDir + "AddTransparentText_out.pdf");
doc.Save(dataDir);
Console.WriteLine("\nTransparent text added successfully.\nFile saved at " + dataDir);
```

### .NET용 Aspose.PDF를 사용하여 투명 텍스트 추가에 대한 샘플 소스 코드 
```csharp
// 문서 디렉터리의 경로입니다.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// 문서 인스턴스 생성
Document doc = new Document();
// PDF 파일의 페이지 간 컬렉션 생성
Aspose.Pdf.Page page = doc.Pages.Add();
// 그래프 객체 생성
Aspose.Pdf.Drawing.Graph canvas = new Aspose.Pdf.Drawing.Graph(100, 400);
// 특정 치수로 직사각형 인스턴스 생성
Aspose.Pdf.Drawing.Rectangle rect = new Aspose.Pdf.Drawing.Rectangle(100, 100, 400, 400);
// 알파 색상 채널에서 색상 객체 만들기
rect.GraphInfo.FillColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.FromArgb(128, System.Drawing.Color.FromArgb(12957183)));
// Graph 개체의 모양 컬렉션에 직사각형 추가
canvas.Shapes.Add(rect);
//페이지 개체의 단락 컬렉션에 그래프 개체 추가
page.Paragraphs.Add(canvas);
// 그래프 개체의 위치가 변경되지 않도록 값을 설정합니다.
canvas.IsChangePosition = false;
// 샘플 값으로 TextFragment 인스턴스 생성
TextFragment text = new TextFragment("transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text ");
// 알파 채널에서 색상 객체 만들기
Aspose.Pdf.Color color = Aspose.Pdf.Color.FromArgb(30, 0, 255, 0);
// 텍스트 인스턴스의 색상 정보 설정
text.TextState.ForegroundColor = color;
// 페이지 인스턴스의 단락 컬렉션에 텍스트 추가
page.Paragraphs.Add(text);
dataDir = dataDir + "AddTransparentText_out.pdf";
doc.Save(dataDir);
Console.WriteLine("\nTransparent text added successfully.\nFile saved at " + dataDir);
```


## 결론
.NET용 Aspose.PDF를 사용하여 PDF 문서에 투명한 텍스트를 성공적으로 추가했습니다. 이제 결과 PDF 파일을 지정된 출력 파일 경로에서 찾을 수 있습니다.

### FAQ

#### Q: 이 튜토리얼의 초점은 무엇입니까?

A: 이 튜토리얼은 .NET용 Aspose.PDF 라이브러리를 사용하여 PDF 문서에 투명한 텍스트를 추가하는 데 중점을 둡니다. 제공된 C# 소스 코드는 이 효과를 달성하는 데 필요한 단계를 보여줍니다.

#### Q: 이 튜토리얼에서는 어떤 네임스페이스를 가져와야 합니까?

A: 투명한 텍스트를 추가하려는 코드 파일에서 파일 시작 부분에 다음 네임스페이스를 가져옵니다.

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Drawing;
```

#### Q: 문서 디렉터리를 어떻게 지정합니까?

 A: 코드에서 다음 줄을 찾으세요.`string dataDir = "YOUR DOCUMENT DIRECTORY";` 교체하고`"YOUR DOCUMENT DIRECTORY"` 문서 디렉토리의 실제 경로를 사용하십시오.

#### Q: 새 문서 인스턴스를 어떻게 생성합니까?

 A: 4단계에서는 새 인스턴스를 생성합니다.`Document` 제공된 코드를 사용하여 객체를 생성합니다.

#### Q: 문서에 페이지를 어떻게 추가하나요?

 A: 5단계에서는 다음을 사용하여 문서에 새 페이지를 추가합니다.`Add` 의 방법`Pages` 수집.

#### Q: 그래프 개체를 어떻게 생성합니까?

 A: 6단계에서는 새`Graph` 특정 너비와 높이를 가진 개체.

#### Q: 투명도가 있는 직사각형을 어떻게 만듭니까?

A: 7단계에서는 특정 크기의 직사각형을 만들고 다음을 사용하여 채우기 색상을 투명 색상으로 설정합니다.`Color.FromRgb` 방법.

#### Q: 그래프 개체를 페이지에 어떻게 추가합니까?

 A: 8단계에서는`Graph` 페이지의 단락 모음에 반대합니다.

#### Q: 그래프 개체의 위치를 어떻게 설정합니까?

 A: 9단계에서는`IsChangePosition` 의 재산`Graph` 반대하다`false` 위치가 바뀌는 것을 방지합니다.

#### Q: 투명도가 있는 TextFragment를 어떻게 생성합니까?

 A: 10단계에서는`TextFragment` 객체를 선택하고 그 내용을 설정합니다.`ForegroundColor` 투명한 텍스트를 얻기 위한 속성입니다.

#### Q: PDF 문서를 어떻게 저장하나요?

 A: 11단계에서는 다음을 사용하여 PDF 문서를 저장합니다.`Save` 의 방법`Document` 물체.

#### Q: 이 튜토리얼의 주요 내용은 무엇입니까?

A: 이 튜토리얼을 따라 .NET용 Aspose.PDF를 사용하여 PDF 문서에 투명한 텍스트를 추가하는 방법을 배웠습니다. 이는 시각적으로 매력적이고 창의적인 PDF 문서를 만드는 데 유용할 수 있습니다.