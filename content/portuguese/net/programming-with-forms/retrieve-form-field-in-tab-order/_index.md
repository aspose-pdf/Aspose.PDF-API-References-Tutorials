---
title: Recuperar campo de formulário em ordem de tabulação
linktitle: Recuperar campo de formulário em ordem de tabulação
second_title: Referência da API do Aspose.PDF para .NET
description: Aprenda como recuperar campos de formulário em ordem de tabulação usando Aspose.PDF para .NET.
type: docs
weight: 240
url: /pt/net/programming-with-forms/retrieve-form-field-in-tab-order/
---
Ao trabalhar com documentos PDF em C# usando Aspose.PDF para .NET, você pode se deparar com um cenário em que precisa recuperar campos de formulário em uma ordem de tabulação específica. Isso pode ser útil quando você deseja executar operações em campos de formulário com base em sua sequência de tabulação. Neste tutorial, nós o guiaremos passo a passo sobre como recuperar campos de formulário em ordem de tabulação usando Aspose.PDF para .NET.

## Requisitos

Antes de começar, certifique-se de ter os seguintes pré-requisitos:

- Visual Studio instalado no seu sistema
- Biblioteca Aspose.PDF para .NET instalada

Agora, vamos nos aprofundar nas etapas para recuperar campos de formulário em ordem de tabulação.

## Etapa 1: Configurando o diretório de documentos

 Para começar, você precisa definir o diretório do documento onde seu documento PDF está localizado. Você pode fazer isso especificando o caminho para o diretório no`dataDir` variável.

```csharp
// O caminho para o diretório de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Substituir`"YOUR DOCUMENT DIRECTORY"` com o caminho real para o diretório do seu documento.

## Etapa 2: Carregando o documento PDF

 Nesta etapa, carregaremos o documento PDF usando Aspose.PDF para .NET. O`Document` A classe fornece a capacidade de carregar e manipular documentos PDF.

```csharp
Document doc = new Document(dataDir + "Test2.pdf");
```

 Aqui,`"Test2.pdf"`é o nome do documento PDF que você quer carregar. Certifique-se de que o documento esteja presente no diretório de documentos especificado.

## Etapa 3: Recuperando campos de formulário em ordem de tabulação

 Para recuperar campos de formulário em ordem de tabulação, precisamos acessar o`FieldsInTabOrder` propriedade do`Page` classe. Esta propriedade retorna uma lista de campos de formulário classificados por sua sequência de tabulações.

```csharp
Page page = doc.Pages[1];
IList<Field> fields = page.FieldsInTabOrder;
string s = "";
foreach (Field field in fields)
{
     s += field. PartialName;
}
```

No trecho de código acima, recuperamos os campos do formulário da segunda página (`doc.Pages[1]` ) e iterar por cada campo para concatenar seus nomes parciais no`s` variável. Você pode modificar este trecho de código com base em seus requisitos específicos.

## Etapa 4: Modificando a ordem das guias

 Se você quiser modificar a ordem das guias dos campos do formulário, poderá fazê-lo acessando o`TabOrder` propriedade de cada campo e atribuindo um novo valor de ordem de tabulação. Aqui está um exemplo:

```csharp
(doc.Form[3] as Field).TabOrder = 1;
(doc.Form[1] as Field).TabOrder = 2;
(doc.Form[2] as Field).TabOrder = 3;
```

No trecho de código acima, atribuímos novos valores de ordem de tabulação a três campos de formulário (`doc.Form[3]`, `doc.Form[1]` , e`doc.Form[2]`). Ajuste os índices de campo e os valores da ordem de tabulação de acordo com suas necessidades específicas.

## Etapa 5: Salvando o documento modificado

 Após modificar a ordem de tabulação dos campos do formulário, você precisa salvar o documento modificado. Você pode fazer isso usando o`Save` método do`Document` aula.

```csharp
doc.Save(dataDir + "39522_out.pdf");
```

 Aqui,`"39522_out.pdf"` é o nome do arquivo de saída onde o documento modificado será salvo. Especifique o nome e o local desejados para o arquivo de saída.

### Código-fonte de exemplo para recuperar campo de formulário em ordem de tabulação usando Aspose.PDF para .NET 
```csharp
// O caminho para o diretório de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Test2.pdf");
Page page = doc.Pages[1];
IList<Field> fields = page.FieldsInTabOrder;
string s = "";
foreach (Field field in fields)
{
	s += field.PartialName;
}
(doc.Form[3] as Field).TabOrder = 1;
(doc.Form[1] as Field).TabOrder = 2;
(doc.Form[2] as Field).TabOrder = 3;
doc.Save(dataDir + "39522_out.pdf");
Document doc1 = new Document(dataDir + "39522_out.pdf");
s = "";
foreach (Field field in doc1.Pages[1].FieldsInTabOrder)
{
	s += field.PartialName;
}
string index = "";
foreach (Field field in doc1.Form)
{
	index += field.TabOrder;
}
```

## Conclusão

Neste tutorial, aprendemos como recuperar campos de formulário em ordem de tabulação usando o Aspose.PDF para .NET. Cobrimos as etapas envolvidas no carregamento de um documento PDF, recuperando campos de formulário em ordem de tabulação, modificando a ordem de tabulação e salvando o documento modificado. Ao seguir essas etapas, você pode trabalhar eficientemente com campos de formulário e personalizar sua sequência de tabulação conforme suas necessidades.


### Perguntas frequentes

#### P: Como posso usar os campos de formulário recuperados no meu código C# para processamento posterior?

 R: Você pode usar os campos de formulário recuperados em seu código C# acessando suas propriedades, como`Value`, `Name`, `Rect`etc. Essas propriedades permitem que você leia e modifique os dados do campo do formulário conforme necessário.

#### P: Posso recuperar campos de formulário de todas as páginas do documento PDF em ordem de tabulação?

 R: Sim, você pode recuperar campos de formulário de todas as páginas do documento PDF iterando por cada página e acessando o`FieldsInTabOrder` propriedade como mostrado no tutorial. Isso lhe dará campos de formulário classificados por sua sequência de tabulação em todas as páginas.

#### P: É possível recuperar apenas tipos específicos de campos de formulário, como campos de texto ou caixas de seleção, em ordem de tabulação?

R: Sim, você pode filtrar campos de formulário com base em seus tipos, como campos de texto ou caixas de seleção, após recuperá-los em ordem de tabulação. Você pode usar instruções condicionais para verificar o tipo de cada campo de formulário e processá-los adequadamente.

#### P: Posso recuperar campos de formulário com base em seus nomes em vez da ordem de tabulação?

 R: Sim, você pode recuperar campos de formulário com base em seus nomes usando o`doc.Form` coleção e especificando o nome do campo como um índice. Por exemplo,`doc.Form["fieldName"]`recuperará o campo do formulário com o nome especificado.

#### P: O Aspose.PDF para .NET oferece suporte para trabalhar com documentos PDF criptografados?

R: Sim, o Aspose.PDF for .NET fornece suporte para trabalhar com documentos PDF criptografados. Você pode carregar e manipular arquivos PDF criptografados usando parâmetros de senha apropriados.