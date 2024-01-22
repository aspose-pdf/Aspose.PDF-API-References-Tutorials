---
title: 누락된 글꼴 바꾸기
linktitle: 누락된 글꼴 바꾸기
second_title: .NET API 참조용 Aspose.PDF
description: .NET용 Aspose.PDF를 사용하여 PDF 파일에서 누락된 글꼴을 대체하는 단계별 가이드입니다.
type: docs
weight: 260
url: /ko/net/document-conversion/replace-missing-fonts/
---
이 튜토리얼에서는 .NET용 Aspose.PDF를 사용하여 PDF 파일에서 누락된 글꼴을 바꾸는 과정을 안내합니다. 특정 글꼴이 누락된 컴퓨터에서 PDF 파일을 열면 글꼴 표시 문제가 발생할 수 있습니다. 이러한 경우 누락된 글꼴을 기기에서 사용할 수 있는 다른 글꼴로 대체할 수 있습니다. 아래 단계에 따라 PDF 파일에서 누락된 글꼴을 교체할 수 있습니다.

## 전제조건
시작하기 전에 다음 전제 조건을 충족하는지 확인하세요.

- C# 프로그래밍 언어에 대한 기본 지식.
- 시스템에 설치된 .NET용 Aspose.PDF 라이브러리.
- Visual Studio와 같은 개발 환경.

## 1단계: 누락된 글꼴 찾기
첫 번째 단계는 PDF 파일에서 누락된 글꼴을 찾는 것입니다. 다음 코드를 사용하세요.

```csharp
// 문서 디렉터리의 경로입니다.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

Aspose.Pdf.Text.Font originalFont = null;
try
{
     // 원본 글꼴을 찾아보세요
     originalFont = FontRepository.FindFont("AgencyFB");
}
catch(Exception)
{
     // 대상 컴퓨터에 글꼴이 없습니다.
     // 간단한 글꼴 대체 추가
     FontRepository.Substitutions.Add(new SimpleFontSubstitution("AgencyFB", "Arial"));
}
```

 꼭 교체하세요`"YOUR DOCUMENTS DIRECTORY"` PDF 파일이 있는 실제 디렉토리를 사용하세요.

## 2단계: 누락된 글꼴 교체
다음으로 누락된 글꼴을 사용 가능한 다른 글꼴로 교체하겠습니다. 다음 코드를 사용하세요.

```csharp
var fileNew = new FileInfo(dataDir + "newfile_out.pdf");
var pdf = new Document(dataDir + "input.pdf");

// 오류 제거를 통해 PDF 파일을 PDF/A 형식으로 변환
pdf.Convert(dataDir + "log.xml", PdfFormat.PDF_A_1B, ConvertErrorAction.Delete);

// 결과 PDF 파일을 저장
pdf.Save(fileNew.FullName);
```

 꼭 교체하세요`"input.pdf"` 원본 PDF 파일의 실제 경로와`"newfile_out.pdf"` 결과 PDF 파일에 원하는 이름을 붙입니다.

## 3단계: 결과 PDF 파일 저장
마지막으로 대체된 글꼴을 사용하여 결과 PDF 파일을 저장합니다. 다음 코드를 사용하세요.

```csharp
// 결과 PDF 파일을 저장
pdf.Save(fileNew.FullName);
```

결과 PDF 파일에 대한 올바른 대상 경로를 설정했는지 확인하십시오.

### .NET용 Aspose.PDF를 사용하여 누락된 글꼴 대체에 대한 예제 소스 코드

```csharp
// 문서 디렉터리의 경로입니다.
string dataDir = "YOUR DOCUMENT DIRECTORY";

Aspose.Pdf.Text.Font originalFont = null;
try
{
	originalFont = FontRepository.FindFont("AgencyFB");
}
catch (Exception)
{
	// 대상 컴퓨터에 글꼴이 없습니다.
	FontRepository.Substitutions.Add(new SimpleFontSubstitution("AgencyFB", "Arial"));
}
var fileNew = new FileInfo(dataDir + "newfile_out.pdf");
var pdf = new Document(dataDir + "input.pdf");
pdf.Convert( dataDir +  "log.xml", PdfFormat.PDF_A_1B, ConvertErrorAction.Delete);
pdf.Save(fileNew.FullName);
```

## 결론
이 튜토리얼에서는 .NET용 Aspose.PDF를 사용하여 PDF 파일에서 누락된 글꼴을 바꾸는 단계별 프로세스를 다루었습니다. 위에 설명된 지침을 따르면 PDF 파일에서 누락된 글꼴을 성공적으로 교체할 수 있습니다.

### FAQ

#### Q: .NET용 Aspose.PDF이 무엇인가요?

A: .NET용 Aspose.PDF는 개발자가 C# 애플리케이션에서 PDF 문서 작업을 할 수 있게 해주는 강력한 라이브러리입니다. PDF 파일에서 누락된 글꼴을 대체하는 기능을 포함하여 다양한 기능을 제공합니다.

#### Q: PDF 파일에서 글꼴이 누락되는 이유는 무엇입니까?

A: 필요한 글꼴이 설치되지 않은 컴퓨터에서 파일을 열면 PDF 파일에서 글꼴이 누락될 수 있습니다. 이로 인해 글꼴이 대체되어 문서의 시각적 모양에 영향을 미칠 수 있습니다.

#### Q: .NET용 Aspose.PDF를 사용하여 PDF 파일에서 누락된 글꼴을 어떻게 찾고 바꿀 수 있습니까?

 A: 누락된 글꼴을 찾아 바꾸려면 다음을 사용할 수 있습니다.`FontRepository.FindFont` 필요한 글꼴이 있는지 확인하는 방법입니다. 글꼴이 누락된 경우 다음을 사용하여 대체 글꼴을 추가할 수 있습니다.`FontRepository.Substitutions` 재산.

#### Q: 글꼴 대체 프로세스를 사용자 정의할 수 있습니까?

A: 예, 대체 글꼴을 다르게 지정하여 글꼴 대체 프로세스를 사용자 정의할 수 있습니다. 제공된 코드에서는 누락된 "AgencyFB" 글꼴 대신 Arial을 사용했지만 기본 설정에 따라 다른 글꼴을 선택할 수 있습니다.

#### Q: 대체 후 글꼴 렌더링의 정확성을 어떻게 보장할 수 있습니까?

A: .NET용 Aspose.PDF는 강력한 글꼴 처리 기능을 제공하여 대체 후 정확한 글꼴 렌더링을 보장합니다. 결과 PDF 파일을 미리 보고 글꼴 교체를 확인할 수 있습니다.