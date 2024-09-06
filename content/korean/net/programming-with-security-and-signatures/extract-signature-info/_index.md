---
title: 서명 정보 추출
linktitle: 서명 정보 추출
second_title: .NET API 참조를 위한 Aspose.PDF
description: Aspose.PDF for .NET을 사용하여 서명 정보를 추출합니다.
type: docs
weight: 80
url: /ko/net/programming-with-security-and-signatures/extract-signature-info/
---
PDF 문서에서 서명 정보를 추출하는 프로세스는 다양한 시나리오에서 매우 유용할 수 있습니다. 서명된 문서의 진위성을 검증하거나 서명에 사용된 인증서를 분석해야 하는 경우 Aspose.PDF for .NET 라이브러리는 편리한 솔루션을 제공합니다. 이 튜토리얼에서는 제공된 C# 소스 코드를 사용하여 서명 정보를 추출하는 단계별 프로세스를 안내합니다.

## 요구 사항

시작하기 전에 다음 전제 조건이 충족되었는지 확인하세요.

1. C# 프로그래밍 언어에 대한 기본 지식.
2. 시스템에 .NET 라이브러리용 Aspose.PDF가 설치되어 있습니다.
3. 하나 이상의 서명 필드가 있는 유효한 PDF 문서입니다.

이제 구현 세부 사항을 살펴보겠습니다.

## 1단계: 필요한 라이브러리 가져오기

 시작하려면 필요한 라이브러리를 C# 프로젝트로 가져와야 합니다. 이 경우 다음을 가져와야 합니다.`Aspose.Pdf` 그리고`System.IO` 네임스페이스. C# 파일의 시작 부분에 다음 코드를 추가하면 됩니다.

```csharp
using Aspose.Pdf;
using System.IO;
```

## 2단계: 문서 경로 설정

다음으로, 서명 정보를 추출하려는 PDF 문서의 경로를 설정해야 합니다. 바꾸기`"YOUR DOCUMENTS DIRECTORY"` 다음 코드 조각에 문서의 실제 경로를 추가합니다.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
string input = dataDir + "ExtractSignatureInfo.pdf";
```

## 3단계: 서명 정보 추출

이제 PDF 문서에서 서명 정보를 추출하는 코드의 주요 부분으로 넘어가겠습니다. 문서 양식의 각 필드를 반복하면서 서명 필드인지 확인합니다. 서명 필드가 발견되면 인증서 추출을 진행합니다. 다음 코드 조각을 추가합니다.

```csharp
using (Document pdfDocument = new Document(input))
{
     foreach(Field field in pdfDocument.Form)
     {
         SignatureField sf = field as SignatureField;
         if (sf != null)
         {
             // 인증서 추출
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

## 4단계: 인증서 추출

이 단계에서는 서명 필드에서 인증서를 추출하여 파일로 저장합니다. 추출된 인증서는 추가로 분석하거나 검증 목적으로 사용할 수 있습니다. 아래 코드 조각은 추출 및 저장 프로세스를 보여줍니다.

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

## 5단계

: 인증서 저장

마지막으로, 추출된 인증서를 파일로 저장합니다. 이 예에서 인증서는 지정된 디렉토리에 "input.cer"이라는 이름으로 저장됩니다. 요구 사항에 맞게 코드를 수정할 수 있습니다. 인증서를 저장하는 코드 조각은 다음과 같습니다.

```csharp
using (FileStream fs = new FileStream(dataDir + @"input.cer", FileMode.CreateNew))
{
     fs.Write(bytes, 0, bytes.Length);
}
```

다 됐어요! Aspose.PDF for .NET을 사용하여 서명 정보를 성공적으로 추출했습니다. 이 코드를 자신의 애플리케이션에 통합하거나 필요에 따라 수정해도 됩니다.

### .NET용 Aspose.PDF를 사용하여 서명 정보 추출을 위한 샘플 소스 코드 
```csharp
try
{
	// 문서 디렉토리의 경로입니다.
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

## 결론

이 튜토리얼에서는 Aspose.PDF for .NET 라이브러리를 사용하여 PDF 문서에서 서명 정보를 추출하는 방법에 대한 단계별 가이드를 살펴보았습니다. 필요한 라이브러리 가져오기, 문서 경로 설정, 서명 정보 추출, 인증서 추출 및 파일에 저장하는 프로세스를 다루었습니다. 이러한 단계를 따르면 서명 세부 정보를 쉽게 검색하고 필요에 따라 작업할 수 있습니다.

### 자주 묻는 질문

#### 질문: PDF 문서에서 서명 정보를 추출해야 하는 이유는 무엇인가요?

A: PDF 문서에서 서명 정보를 추출하는 것은 서명된 문서의 진위성을 검증하고 서명에 사용된 인증서를 분석하는 데 유용합니다. 이 프로세스는 서명된 콘텐츠의 무결성을 보장하는 데 도움이 되며 법률 및 보안 목적에 필수적일 수 있습니다.

#### 질문: .NET용 Aspose.PDF란 무엇인가요?

A: Aspose.PDF for .NET은 개발자가 .NET 애플리케이션에서 PDF 문서로 작업할 수 있도록 하는 라이브러리입니다. PDF 파일을 프로그래밍 방식으로 만들고, 수정하고, 상호 작용하기 위한 광범위한 기능을 제공합니다.

#### 질문: Aspose.PDF for .NET을 사용하여 서명 정보를 추출하기 위한 전제 조건은 무엇입니까?

답변: 서명 정보를 추출하려면 C# 프로그래밍 언어에 대한 기본 지식, 시스템에 설치된 .NET용 Aspose.PDF 라이브러리, 그리고 하나 이상의 서명 필드가 포함된 유효한 PDF 문서가 필요합니다.

#### 질문: 추출 과정에 필요한 라이브러리를 어떻게 가져오나요?

A: 필요한 라이브러리를 추가하면 가져올 수 있습니다.`using` 지시사항`Aspose.Pdf` 그리고`System.IO` C# 파일의 시작 부분에 있습니다. 이러한 지시문을 사용하면 서명 정보를 추출하는 데 필요한 클래스와 메서드를 사용할 수 있습니다.

#### 질문: 서명 정보를 추출할 PDF 문서를 어떻게 지정합니까?

 A: PDF 문서의 경로를 다음과 같이 바꿀 수 있습니다.`"YOUR DOCUMENTS DIRECTORY"` 제공된 코드 조각에 문서의 실제 경로가 있습니다. 이 경로는 서명 정보를 추출하려는 PDF 문서를 로드하는 데 사용됩니다.

#### 질문: PDF 문서에서 서명 정보를 추출하는 과정은 무엇인가요?

A: 추출 프로세스에는 PDF 문서의 양식 필드를 반복하고, 각 필드가 서명 필드인지 확인하고, 그렇다면 연관된 인증서를 추출하는 것이 포함됩니다. 추출된 인증서는 추가 분석 또는 검증을 위해 파일로 저장할 수 있습니다.

#### 질문: 서명 필드에서 인증서는 어떻게 추출되나요?

A: 인증서는 다음을 사용하여 서명 필드에서 추출됩니다.`ExtractCertificate()` 에 의해 제공되는 방법`SignatureField` .NET용 Aspose.PDF의 클래스. 이 메서드는 인증서 데이터를 포함하는 스트림을 반환합니다.

#### 질문: 추출한 인증서를 파일로 저장하려면 어떻게 해야 하나요?

 A: 인증서 스트림을 읽고 해당 내용을 파일에 쓰면 추출된 인증서를 파일로 저장할 수 있습니다.`FileStream` 클래스. 튜토리얼에 제공된 코드는 이 프로세스를 보여줍니다.

#### 질문: 추출한 인증서를 서명 검증에 사용할 수 있나요?

A: 네, 추출된 인증서는 서명 검증에 사용할 수 있습니다. 인증서의 세부 정보를 분석하고 진위성을 검증하여 서명된 문서의 무결성을 보장할 수 있습니다.

#### 질문: 이 코드를 내 애플리케이션에 어떻게 통합할 수 있나요?

A: 단계별 가이드를 따라 제공된 코드를 자신의 C# 애플리케이션에 통합할 수 있습니다. 필요에 따라 경로와 파일 이름을 수정하고 코드를 기존 프로젝트에 통합합니다.

#### 질문: .NET용 Aspose.PDF에는 서명 관리와 관련된 다른 기능이 있습니까?

A: 네, Aspose.PDF for .NET은 문서 서명, 서명 확인, 타임스탬프 정보 추가 등 디지털 서명 작업을 위한 다양한 기능을 제공합니다. 이러한 기능에 대한 자세한 내용은 공식 문서를 참조하세요.

#### 질문: .NET에서 Aspose.PDF를 사용하기 위한 추가 리소스는 어디에서 찾을 수 있나요?

 A: .NET용 Aspose.PDF 사용에 대한 자세한 정보, 튜토리얼 및 리소스는 다음과 같습니다.[Aspose.PDF for .NET](https://reference.aspose.com/pdf/net/).

#### 질문: 암호화된 PDF 문서에서 서명을 추출하는 것이 가능합니까?

A: 암호화된 PDF 문서에서 서명을 추출하는 기능은 문서의 암호화 설정 및 권한에 따라 달라질 수 있습니다. 서명 정보에 액세스하고 추출하는 데 필요한 권한이 있는지 확인해야 할 수도 있습니다.

#### 질문: 하나의 PDF 문서에서 여러 개의 서명을 추출할 수 있나요?

A: 네, 제공된 코드를 수정하여 PDF 문서의 모든 서명 필드를 반복하고 각 필드에서 서명 정보를 추출할 수 있습니다. 이를 통해 문서에 있는 여러 서명에 대한 정보를 추출할 수 있습니다.

#### 질문: 서명 정보를 추출하는 실제 사용 사례는 어떤 것이 있나요?

답변: 서명 정보 추출의 몇 가지 실용적인 사용 사례로는 디지털 서명된 문서의 진위성 검증, 규정 준수 목적으로 인증서 세부 정보 분석, 감사 목적으로 서명 및 서명자 기록 유지 관리 등이 있습니다.

#### 질문: 서명 정보를 추출할 때 고려해야 할 법적 사항이 있나요?

A: 서명 정보를 추출하는 것은 특히 법적 구속력이 있는 문서를 처리할 때 법적 의미를 가질 수 있습니다. 관할권에서 전자 서명 및 문서 진위성과 관련된 관련 규정 및 법률을 준수해야 합니다.