---
title: 페이지에 XForm 그리기
linktitle: 페이지에 XForm 그리기
second_title: .NET API 참조용 Aspose.PDF
description: .NET용 Aspose.PDF를 사용하여 PDF 페이지에 XForm 양식을 그리는 방법에 대한 단계별 가이드입니다. 페이지에 양식을 추가하고 배치합니다.
type: docs
weight: 10
url: /ko/net/programming-with-operators/draw-xform-on-page/
---
이 튜토리얼에서는 Aspose.PDF for .NET을 사용하여 페이지에 XForm을 그리는 방법에 대한 단계별 가이드를 제공합니다. Aspose.PDF는 PDF 문서를 프로그래밍 방식으로 생성, 조작 및 변환할 수 있는 강력한 라이브러리입니다. Aspose.PDF에서 제공하는 연산자를 사용하면 기존 PDF 페이지에 XForm 양식을 추가하고 배치할 수 있습니다.

## 전제조건

시작하기 전에 다음 전제 조건이 충족되었는지 확인하세요.

1. .NET 프레임워크와 함께 설치된 Visual Studio.
2. .NET용 Aspose.PDF 라이브러리.

## 1단계: 프로젝트 설정

시작하려면 Visual Studio에서 새 프로젝트를 만들고 .NET용 Aspose.PDF 라이브러리에 대한 참조를 추가하세요. Aspose 공식 웹사이트에서 라이브러리를 다운로드하여 컴퓨터에 설치할 수 있습니다.

## 2단계: 필요한 네임스페이스 가져오기

C# 코드 파일에서 Aspose.PDF에서 제공하는 클래스 및 메서드에 액세스하는 데 필요한 네임스페이스를 가져옵니다.

```csharp
using System;
using System.IO;
using Aspose.Pdf;
using Aspose.Pdf.Operators;
```

## 3단계: 파일 경로 설정

배경 이미지, 입력 PDF 파일 및 출력 PDF 파일의 파일 경로를 정의합니다.

```csharp
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";
string imageFile = dataDir + "aspose-logo.jpg";
string inFile = dataDir + "DrawXFormOnPage.pdf";
string outFile = dataDir + "blank-sample2_out.pdf";
```

컴퓨터의 실제 파일 경로를 지정해야 합니다.

## 4단계: 입력 PDF 파일 로드

다음 코드를 사용하여 입력 PDF 파일을 로드합니다.

```csharp
using (Document doc = new Document(inFile))
{
OperatorCollection pageContents = doc.Pages[1].Contents;
// 다음 코드는 GSave/GRestore 연산자를 사용합니다.
// 코드는 ContatenateMatrix 연산자를 사용하여 XForm의 위치를 지정합니다.
// 코드는 Do 연산자를 사용하여 페이지에 XForm을 그립니다.
// GSave/GRestore 연산자는 기존 콘텐츠를 래핑합니다.
// 이는 기존 콘텐츠의 끝에서 초기 그래픽 상태를 가져오기 위해 수행됩니다.
// 그렇지 않으면 기존 연산자 체인의 끝에 원치 않는 변환이 남을 수 있습니다.
pageContents. Insert(1, new GSave());
pageContents. Add(new GRestore());
// 새로운 명령 후에 그래픽 상태를 적절하게 재설정하기 위해 GSave 연산자를 추가했습니다.
pageContents. Add(new GSave());

// 변환 생성
XForm form = XForm.CreateNewForm(doc.Pages[1], doc);
doc.Pages[1].Resources.Forms.Add(form);
form.Contents.Add(new GSave());
// 이미지의 너비와 높이를 설정합니다.
form.Contents.Add(new ConcatenateMatrix(200, 0, 0, 200, 0, 0));
// 이미지를 스트림에 로드
Stream imageStream = new FileStream(imageFile, FileMode.Open);
// XForm 리소스 이미지 컬렉션에 이미지 추가
form.Resources.Images.Add(imageStream);
XImage ximage = form.Resources.Images[form.Resources.Images.Count];
// Do 연산자 사용: 이 연산자는 이미지를 그립니다.
form.Contents.Add(new Do(ximage.Name));
form.Contents.Add(new GRestore());

pageContents. Add(new GSave());
//x=100 및 y=500 좌표에 XForm을 배치합니다.
pageContents. Add(new ConcatenateMatrix(1, 0, 0, 1, 100, 500));
// Do 연산자를 사용하여 XForm 그리기
pageContents.Add(new Do(form.Name));
pageContents. Add(new GRestore());

pageContents. Add(new GSave());
// x=100 및 y=300 좌표에 XForm을 배치합니다.
pageContents. Add(new ConcatenateMatrix(1, 0, 0, 1, 100, 300));
// Do 연산자를 사용하여 XForm 그리기
pageContents.Add(new Do(form.Name));
pageContents. Add(new GRestore());

// GSave 후 GRestore를 사용하여 그래픽 상태 복원
pageContents. Add(new GRestore());
doc.Save(outFile);
}
```

실제 파일 경로를 지정하고 필요에 따라 페이지 번호와 XForm 위치를 조정하십시오.

### .NET용 Aspose.PDF를 사용하여 페이지에 Draw XForm을 위한 샘플 소스 코드
 
```csharp

// 문서 디렉터리의 경로입니다.
string dataDir = "YOUR DOCUMENT DIRECTORY";
string imageFile = dataDir+ "aspose-logo.jpg";
string inFile = dataDir + "DrawXFormOnPage.pdf";
string outFile = dataDir + "blank-sample2_out.pdf";
using (Document doc = new Document(inFile))
{
	OperatorCollection pageContents = doc.Pages[1].Contents;
	// 샘플에서 보여줍니다.
	// GSave/GRestore 연산자 사용법
	// xForm 위치를 지정하기 위한 ContatenateMatrix 연산자 사용
	// 페이지에 xForm을 그리려면 연산자를 사용하십시오.
	// GSave/GRestore 연산자 쌍으로 기존 콘텐츠 래핑
	// 이는 기존 콘텐츠의 초기 그래픽 상태를 가져오는 것입니다.
	// 그렇지 않으면 기존 연산자 체인 끝에 바람직하지 않은 변형이 남아 있을 수 있습니다.
	pageContents.Insert(1, new Aspose.Pdf.Operators.GSave());
	pageContents.Add(new Aspose.Pdf.Operators.GRestore());
	// 새 명령 후 그래픽 상태를 올바르게 지우려면 그래픽 상태 저장 연산자를 추가하세요.
	pageContents.Add(new Aspose.Pdf.Operators.GSave());
	#region create xForm
	// xForm 생성
	XForm form = XForm.CreateNewForm(doc.Pages[1], doc);
	doc.Pages[1].Resources.Forms.Add(form);
	form.Contents.Add(new Aspose.Pdf.Operators.GSave());
	// 이미지 너비와 높이 정의
	form.Contents.Add(new Aspose.Pdf.Operators.ConcatenateMatrix(200, 0, 0, 200, 0, 0));
	// 스트림에 이미지 로드
	Stream imageStream = new FileStream(imageFile, FileMode.Open);
	//XForm 리소스의 이미지 컬렉션에 이미지 추가
	form.Resources.Images.Add(imageStream);
	XImage ximage = form.Resources.Images[form.Resources.Images.Count];
	// Do 연산자 사용: 이 연산자는 이미지를 그립니다.
	form.Contents.Add(new Aspose.Pdf.Operators.Do(ximage.Name));
	form.Contents.Add(new Aspose.Pdf.Operators.GRestore());
	#endregion
	pageContents.Add(new Aspose.Pdf.Operators.GSave());
	// x=100 y=500 좌표에 양식 배치
	pageContents.Add(new Aspose.Pdf.Operators.ConcatenateMatrix(1, 0, 0, 1, 100, 500));
	// Do 연산자를 사용하여 양식 그리기
	pageContents.Add(new Aspose.Pdf.Operators.Do(form.Name));
	pageContents.Add(new Aspose.Pdf.Operators.GRestore());
	pageContents.Add(new Aspose.Pdf.Operators.GSave());
	// x=100 y=300 좌표에 양식 배치
	pageContents.Add(new Aspose.Pdf.Operators.ConcatenateMatrix(1, 0, 0, 1, 100, 300));
	// Do 연산자를 사용하여 양식 그리기
	pageContents.Add(new Aspose.Pdf.Operators.Do(form.Name));
	pageContents.Add(new Aspose.Pdf.Operators.GRestore());
	// GSave 후 GRestore를 사용하여 그래픽 상태 복원
	pageContents.Add(new Aspose.Pdf.Operators.GRestore());
	doc.Save(outFile);                
}

```

## 결론

이 튜토리얼에서는 .NET용 Aspose.PDF를 사용하여 PDF 페이지에 XForm 양식을 그리는 방법을 배웠습니다. 설명된 단계를 수행하면 기존 페이지에 XForm 양식을 추가하고 배치할 수 있으므로 PDF 문서에 더 많은 유연성이 제공됩니다.

### 페이지의 Draw XForm에 대한 FAQ

#### Q: Aspose.PDF의 XForm이 무엇입니까?

A: XForm은 PDF 문서에서 재사용 가능한 그래픽 개체입니다. 이를 통해 여러 페이지에서 여러 번 재사용할 수 있는 복잡한 그래픽, 이미지 또는 텍스트를 정의하고 그릴 수 있습니다.

#### Q: Aspose.PDF에 필요한 네임스페이스를 어떻게 가져오나요?

 A: C# 코드 파일에서`using` Aspose.PDF에서 제공하는 클래스 및 메서드에 액세스하는 데 필요한 네임스페이스를 가져오는 지시어:
```csharp
using System;
using System.IO;
using Aspose.Pdf;
using Aspose.Pdf.Operators;
```

#### Q: GSave 및 GRestore 연산자의 목적은 무엇입니까?

 답:`GSave` 그리고`GRestore`Aspose.PDF의 연산자는 그래픽 상태를 저장하고 복원하는 데 사용됩니다. 이는 콘텐츠의 한 섹션에 적용된 변형 및 설정이 후속 섹션에 영향을 미치지 않도록 하는 데 도움이 됩니다.

#### Q: Aspose.PDF를 사용하여 XForm을 어떻게 정의합니까?

 A: XForm을 생성하려면`XForm.CreateNewForm` 메소드를 추가하고`Resources.Forms` 특정 페이지의 모음입니다. 그런 다음 XForm에 콘텐츠를 추가할 수 있습니다.`Contents` 재산.

#### Q: XForm 내에서 이미지를 어떻게 그릴 수 있습니까?

 A: 이미지를 스트림에 로드하고`Resources.Images` XForm의 컬렉션입니다. 사용`Do` XForm 내의 연산자`Contents` 이미지를 그리려고.

#### Q: PDF 페이지에 XForm을 배치하려면 어떻게 해야 합니까?

 A: 페이지에 XForm을 배치하려면`ConcatenateMatrix` 페이지 내의 연산자`Contents`. 행렬 매개변수를 조정하여 XForm의 변환(위치) 및 배율 조정을 지정합니다.

#### Q: 동일한 페이지에 여러 XForm을 그릴 수 있습니까?

 A: 예.`ConcatenateMatrix`매개변수를 사용하여 각 XForm을 서로 다른 좌표에 배치합니다.

#### Q: XForm을 만든 후에 XForm의 콘텐츠를 수정할 수 있습니까?

 A: 예. 생성 후 XForm에 추가 연산자를 추가하여 XForm의 내용을 수정할 수 있습니다.`Contents` 재산.

#### Q: GSave 및 GRestore 연산자를 생략하면 어떻게 되나요?

A: GSave 및 GRestore 연산자를 생략하면 원치 않는 변환이나 설정이 후속 콘텐츠에 적용될 수 있습니다. 이를 사용하면 깨끗한 그래픽 상태를 유지하는 데 도움이 됩니다.

#### Q: PDF 문서의 여러 페이지에서 XForms를 재사용할 수 있습니까?

 A: 예. 동일한 XForm을`Resources.Forms` 다양한 페이지 모음.

#### Q: 만들 수 있는 XForms 수에 제한이 있습니까?

A: 만들 수 있는 XForm 수에는 엄격한 제한이 없지만 XForm이 너무 많으면 성능과 메모리 사용량에 영향을 미칠 수 있다는 점을 명심하세요. 신중하게 사용하십시오.

#### Q: XForm을 회전하거나 다른 변환을 적용할 수 있습니까?

 A: 예, 다음을 사용할 수 있습니다.`ConcatenateMatrix`XForm에 회전, 크기 조정, 변환 등의 변환을 적용하는 연산자입니다.
