---
title: Obter campos da região em arquivo PDF
linktitle: Obter campos da região em arquivo PDF
second_title: Referência da API do Aspose.PDF para .NET
description: Obtenha facilmente campos de uma região específica em arquivo PDF com Aspose.PDF para .NET.
type: docs
weight: 130
url: /pt/net/programming-with-forms/get-fields-from-region/
---
Neste tutorial, mostraremos como obter os campos de uma região específica em um arquivo PDF usando Aspose.PDF para .NET. Explicaremos o código-fonte C# passo a passo para guiá-lo por esse processo.

## Etapa 1: Preparação

Certifique-se de ter importado as bibliotecas necessárias e definido o caminho para o diretório de documentos:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Etapa 2: Abra o arquivo PDF

Abra o arquivo PDF:

```csharp
Aspose.Pdf.Document doc = new Aspose.Pdf.Document(dataDir + "GetFieldsFromRegion.pdf");
```

## Etapa 3: Crie um objeto retângulo para delimitar a região

Crie um objeto retângulo para delimitar a região onde você deseja obter os campos:

```csharp
Aspose.Pdf.Rectangle rectangle = new Aspose.Pdf.Rectangle(35, 30, 500, 500);
```

## Etapa 4: Obtenha o formulário PDF

Obtenha o formato PDF do documento:

```csharp
Aspose.Pdf.Forms.Form form = doc.Form;
```

## Etapa 5: Obtenha os campos na região retangular

Obtenha os campos localizados na região retangular especificada:

```csharp
Aspose.Pdf.Forms.Field[] fields = form.GetFieldsInRect(rectangle);
```

## Etapa 6: Exibir nomes e valores de campos

Itere pelos campos resultantes e exiba seus nomes e valores:

```csharp
foreach (Field field in fields)
{
Console.Out.WriteLine("Field name: " + field.FullName + "-" + "Field value: " + field.Value);
}
```

### Código-fonte de exemplo para Obter campos da região usando Aspose.PDF para .NET 
```csharp
// O caminho para o diretório de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Abrir arquivo pdf
Aspose.Pdf.Document doc = new Aspose.Pdf.Document(dataDir + "GetFieldsFromRegion.pdf");
// Crie um objeto retângulo para obter campos nessa área
Aspose.Pdf.Rectangle rectangle = new Aspose.Pdf.Rectangle(35, 30, 500, 500);
// Obtenha o formulário PDF
Aspose.Pdf.Forms.Form form = doc.Form;
// Obter campos na área retangular
Aspose.Pdf.Forms.Field[] fields = form.GetFieldsInRect(rectangle);
// Exibir nomes e valores de campos
foreach (Field field in fields)
{
	// Exibir propriedades de posicionamento de imagem para todos os posicionamentos
	Console.Out.WriteLine("Field Name: " + field.FullName + "-" + "Field Value: " + field.Value);
}
```

## Conclusão

Neste tutorial, aprendemos como obter os campos de uma região específica em um documento PDF usando Aspose.PDF para .NET. Seguindo essas etapas, você pode facilmente extrair os campos localizados em uma determinada área retangular do seu documento PDF usando Aspose.PDF.

### Perguntas frequentes

#### P: Posso usar esse método para obter campos de uma região não retangular em um documento PDF?

 R: Não, o método fornecido`GetFieldsInRect` é projetado especificamente para recuperar campos localizados dentro de uma região retangular em um documento PDF. Se você precisar extrair campos de uma região não retangular, precisará implementar lógica personalizada para identificar e extrair os campos com base em outros critérios, como coordenadas ou nomes de campo.

#### P: Como posso modificar o tamanho ou a posição do retângulo para obter campos de uma região diferente?

 R: Para obter campos de uma região diferente, você pode modificar o`Aspose.Pdf.Rectangle` parâmetros do objeto usados para definir o retângulo delimitador. O`Rectangle` O construtor recebe quatro parâmetros:`x`, `y`, `width` , e`height`que representam as coordenadas do canto superior esquerdo e as dimensões do retângulo. Ajustar esses parâmetros mudará a região da qual os campos são extraídos.

#### P: E se não houver campos dentro da região retangular especificada?

 A: Se não houver campos dentro da região retangular especificada, o`GetFieldsInRect` método retornará um array vazio. Você pode verificar o comprimento do array para determinar se há algum campo dentro da região.

#### P: Posso obter campos de regiões sobrepostas em um documento PDF?

 R: Sim, você pode obter campos de regiões sobrepostas em um documento PDF criando vários`Aspose.Pdf.Rectangle` objetos e chamando o`GetFieldsInRect` método para cada um deles. Regiões sobrepostas serão manipuladas independentemente, e você receberá matrizes separadas de campos para cada região.

#### P: É possível obter campos de uma página específica ou de várias páginas no documento PDF?

R: Sim, você pode obter campos de uma página específica ou de várias páginas em um documento PDF. Para fazer isso, você pode carregar o documento PDF, acessar as páginas desejadas usando o`doc.Pages` coleta e, em seguida, aplicar o`GetFieldsInRect` método para cada região específica da página.