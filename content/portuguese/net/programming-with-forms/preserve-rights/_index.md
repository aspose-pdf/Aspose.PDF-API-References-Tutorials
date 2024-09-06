---
title: Preservar direitos
linktitle: Preservar direitos
second_title: Referência da API do Aspose.PDF para .NET
description: Preserve os direitos de formulário em seus documentos PDF com Aspose.PDF para .NET.
type: docs
weight: 210
url: /pt/net/programming-with-forms/preserve-rights/
---
Neste tutorial, mostraremos como preservar direitos de formulário em um documento PDF usando Aspose.PDF para .NET. Explicaremos o código-fonte C# passo a passo para guiá-lo por esse processo.

## Etapa 1: Preparação

Certifique-se de ter importado as bibliotecas necessárias e definido o caminho para o diretório de documentos:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Etapa 2: Abra o documento

 Abra o documento PDF de origem usando um`FileStream` com permissão de leitura e escrita:

```csharp
FileStream fs = new FileStream(dataDir + "input.pdf", FileMode.Open, FileAccess.ReadWrite);
Aspose.Pdf.Document pdfDocument = new Aspose.Pdf.Document(fs);
```

## Etapa 3: Editar campos do formulário

Passe por todos os campos de formulário no documento e faça as alterações necessárias. Neste exemplo, estamos alterando o valor de um campo de formulário que tem "A1" em seu nome:

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

## Etapa 4: Salve o documento atualizado

Salve o documento PDF modificado:

```csharp
pdfDocument.Save();
```

##  Etapa 5: Feche o`FileStream`

 Não se esqueça de fechar o`FileStream` objeto quando terminar:

```csharp
fs. Close();
```

### Código-fonte de exemplo para Preserve Rights usando Aspose.PDF para .NET 
```csharp
// O caminho para o diretório de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Leia o formulário PDF de origem com o FileAccess de Leitura e Gravação.
// Precisamos da permissão ReadWrite porque após a modificação,
// Precisamos salvar o conteúdo atualizado no mesmo documento/arquivo.
FileStream fs = new FileStream(dataDir + "input.pdf", FileMode.Open, FileAccess.ReadWrite);
// Instanciar instância de documento
Aspose.Pdf.Document pdfDocument = new Aspose.Pdf.Document(fs);
// Obter valores de todos os campos
foreach (Field formField in pdfDocument.Form)
{
	// Se o nome completo do campo contiver A1, execute a operação
	if (formField.FullName.Contains("A1"))
	{
		// Campo de formulário de conversão como caixa de texto
		TextBoxField textBoxField = formField as TextBoxField;
		// Modificar valor do campo
		textBoxField.Value = "Testing";
	}
}
// Salve o documento atualizado em salvar FileStream
pdfDocument.Save();
// Feche o objeto File Stream
fs.Close();
```

## Conclusão

Neste tutorial, aprendemos como preservar os direitos de um formulário em um documento PDF usando Aspose.PDF para .NET. Seguindo essas etapas, você pode acessar facilmente os campos do formulário e fazer alterações específicas, preservando o acesso e as permissões de gravação.


### Perguntas frequentes

#### P: Posso preservar os direitos de campos específicos do formulário sem afetar outros no documento PDF?

 R: Sim, usando o`FullName` propriedade dos campos de formulário, você pode direcionar campos de formulário específicos para preservação, deixando outros inalterados.

#### P: Posso preservar os direitos de um formulário em um documento PDF protegido por senha?

R: Sim, o Aspose.PDF para .NET permite que você preserve os direitos de um formulário mesmo em documentos PDF protegidos por senha, desde que você forneça a senha correta para acessar e modificar o arquivo.

#### P: O que acontece se eu tentar modificar campos de formulário sem os direitos de acesso apropriados?

R: Se você tentar modificar campos de formulário sem os direitos de acesso apropriados, as alterações não serão salvas no documento PDF e você poderá receber uma exceção ou uma mensagem de erro.

#### P: O Aspose.PDF para .NET é compatível com todas as versões do .NET Framework?

R: Sim, o Aspose.PDF para .NET é compatível com todas as versões do .NET Framework, incluindo .NET Core e .NET Standard.

#### P: Posso preservar direitos de formulário em um documento PDF programaticamente em outras linguagens de programação além de C#?

R: Sim, o Aspose.PDF para .NET oferece suporte a várias linguagens de programação, como VB.NET e ASP.NET, além de C#.