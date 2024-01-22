---
title: Preservar Direitos
linktitle: Preservar Direitos
second_title: Referência da API Aspose.PDF para .NET
description: Preserve os direitos de formulário em seus documentos PDF com Aspose.PDF para .NET.
type: docs
weight: 210
url: /pt/net/programming-with-forms/preserve-rights/
---
Neste tutorial, mostraremos como preservar os direitos do formulário em um documento PDF usando Aspose.PDF for .NET. Explicaremos o código-fonte C# passo a passo para guiá-lo nesse processo.

## Etapa 1: Preparação

Certifique-se de importar as bibliotecas necessárias e definir o caminho para o diretório de documentos:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Passo 2: Abra o documento

 Abra o documento PDF de origem usando um`FileStream` com permissão de leitura e gravação:

```csharp
FileStream fs = new FileStream(dataDir + "input.pdf", FileMode.Open, FileAccess.ReadWrite);
Aspose.Pdf.Document pdfDocument = new Aspose.Pdf.Document(fs);
```

## Etapa 3: editar os campos do formulário

Percorra todos os campos do formulário do documento e faça as alterações necessárias. Neste exemplo, estamos alterando o valor de um campo de formulário que possui “A1” no nome:

```csharp
foreach(Field formField in pdfDocument.Form)
{
if (formField.FullName.Contains("A1"))
{
TextBoxField textBoxField = formField as TextBoxField;
textBoxField.Value = "Testing";
}
}
```

## Etapa 4: salve o documento atualizado

Salve o documento PDF modificado:

```csharp
pdfDocument.Save();
```

##  Etapa 5: feche o`FileStream`

 Não se esqueça de fechar o`FileStream` objeto quando terminar:

```csharp
fs. Close();
```

### Exemplo de código-fonte para Preserve Rights usando Aspose.PDF para .NET 
```csharp
// O caminho para o diretório de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Leia o formulário PDF de origem com FileAccess de leitura e gravação.
// Precisamos da permissão ReadWrite porque após a modificação,
// Precisamos salvar o conteúdo atualizado no mesmo documento/arquivo.
FileStream fs = new FileStream(dataDir + "input.pdf", FileMode.Open, FileAccess.ReadWrite);
// Instanciar instância de documento
Aspose.Pdf.Document pdfDocument = new Aspose.Pdf.Document(fs);
// Obtenha valores de todos os campos
foreach (Field formField in pdfDocument.Form)
{
	// Se o nome completo do campo contiver A1, execute a operação
	if (formField.FullName.Contains("A1"))
	{
		// Converter campo de formulário como TextBox
		TextBoxField textBoxField = formField as TextBoxField;
		// Modificar valor do campo
		textBoxField.Value = "Testing";
	}
}
// Salve o documento atualizado em save FileStream
pdfDocument.Save();
// Feche o objeto Fluxo de Arquivos
fs.Close();
```

## Conclusão

Neste tutorial, aprendemos como preservar os direitos de um formulário em um documento PDF usando Aspose.PDF for .NET. Seguindo essas etapas, você pode acessar facilmente os campos do formulário e fazer alterações específicas, preservando o acesso e as permissões de gravação.


### Perguntas frequentes

#### P: Posso preservar os direitos de campos específicos do formulário sem afetar outros no documento PDF?

 R: Sim, usando o`FullName` propriedade dos campos do formulário, você pode direcionar campos de formulário específicos para preservação, deixando outros inalterados.

#### P: Posso preservar os direitos de um formulário em um documento PDF protegido por senha?

R: Sim, o Aspose.PDF for .NET permite preservar os direitos de um formulário mesmo em documentos PDF protegidos por senha, desde que você forneça a senha correta para acessar e modificar o arquivo.

#### P: O que acontece se eu tentar modificar os campos do formulário sem os direitos de acesso apropriados?

R: Se você tentar modificar os campos do formulário sem os direitos de acesso apropriados, as alterações não serão salvas no documento PDF e você poderá receber uma exceção ou uma mensagem de erro.

#### P: O Aspose.PDF for .NET é compatível com todas as versões do .NET Framework?

R: Sim, Aspose.PDF for .NET é compatível com todas as versões do .NET Framework, incluindo .NET Core e .NET Standard.

#### P: Posso preservar os direitos de formulário em um documento PDF programaticamente em outras linguagens de programação além de C#?

R: Sim, Aspose.PDF for .NET oferece suporte a várias linguagens de programação, como VB.NET e ASP.NET, além de C#.