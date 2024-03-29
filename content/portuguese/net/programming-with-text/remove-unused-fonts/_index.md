---
title: Remover fontes não utilizadas em arquivo PDF
linktitle: Remover fontes não utilizadas em arquivo PDF
second_title: Referência da API Aspose.PDF para .NET
description: Aprenda como remover fontes não utilizadas em arquivos PDF usando Aspose.PDF for .NET.
type: docs
weight: 300
url: /pt/net/programming-with-text/remove-unused-fonts/
---
Neste tutorial, explicaremos como remover fontes não utilizadas em arquivo PDF usando a biblioteca Aspose.PDF para .NET. Seguiremos o processo passo a passo de carregamento de um PDF, identificação e remoção de fontes não utilizadas e salvamento do PDF atualizado usando o código-fonte C# fornecido.

## Requisitos

Antes de começar, certifique-se de ter o seguinte:

- A biblioteca Aspose.PDF para .NET instalada.
- Uma compreensão básica da programação C#.

## Etapa 1: configurar o diretório de documentos

 Primeiro, você precisa definir o caminho para o diretório onde seus arquivos PDF estão localizados. Substituir`"YOUR DOCUMENT DIRECTORY"` no`dataDir` variável com o caminho para seus arquivos PDF.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Passo 2: Carregue o PDF Fonte

 A seguir, carregamos o documento PDF de origem usando o`Document` classe da biblioteca Aspose.PDF.

```csharp
Document doc = new Document(dataDir + "ReplaceTextPage.pdf");
```

## Etapa 3: identificar e remover fontes não utilizadas

 Nós criamos um`TextFragmentAbsorber` objeto com o`TextEditOptions` parâmetro definido como`TextEditOptions.FontReplace.RemoveUnusedFonts` . Esta opção nos permite identificar e remover fontes não utilizadas no documento PDF. Em seguida, iteramos por todos os`TextFragments` e defina a fonte para a fonte desejada.

```csharp
TextFragmentAbsorber absorber = new TextFragmentAbsorber(new TextEditOptions(TextEditOptions.FontReplace.RemoveUnusedFonts));
doc.Pages.Accept(absorb);

foreach(TextFragment textFragment in absorber.TextFragments)
{
     textFragment.TextState.Font = FontRepository.FindFont("Arial, Bold");
}
```

## Etapa 4: salve o PDF atualizado

Finalmente, salvamos o documento PDF atualizado no arquivo de saída especificado.

```csharp
dataDir = dataDir + "RemoveUnusedFonts_out.pdf";
doc.Save(dataDir);
Console.WriteLine("\nUnused fonts removed successfully from the PDF document.\nFile saved at " + dataDir);
```

### Exemplo de código-fonte para remover fontes não utilizadas usando Aspose.PDF para .NET 
```csharp
try
{
	// O caminho para o diretório de documentos.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// Carregar arquivo PDF de origem
	Document doc = new Document(dataDir + "ReplaceTextPage.pdf");
	TextFragmentAbsorber absorber = new TextFragmentAbsorber(new TextEditOptions(TextEditOptions.FontReplace.RemoveUnusedFonts));
	doc.Pages.Accept(absorber);
	// Iterar por todos os TextFragments
	foreach (TextFragment textFragment in absorber.TextFragments)
	{
		textFragment.TextState.Font = FontRepository.FindFont("Arial, Bold");
	}
	dataDir = dataDir + "RemoveUnusedFonts_out.pdf";
	// Salvar documento atualizado
	doc.Save(dataDir);
	Console.WriteLine("\nUnused fonts removed successfully from pdf document.\nFile saved at " + dataDir);
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message + "\nThis example will only work if you apply a valid Aspose License. You can purchase full license or get 30 day temporary license from http:// www.aspose.com/purchase/default.aspx.");
}
```

## Conclusão

Neste tutorial, você aprendeu como remover fontes não utilizadas de um documento PDF usando a biblioteca Aspose.PDF para .NET. Seguindo o guia passo a passo e executando o código C# fornecido, você pode carregar um PDF, identificar e remover fontes não utilizadas e salvar o PDF atualizado.

### Perguntas frequentes

#### P: Qual é o objetivo do tutorial "Remover fontes não utilizadas em arquivo PDF"?

R: O tutorial "Remover fontes não utilizadas em arquivo PDF" explica como usar a biblioteca Aspose.PDF para .NET para remover fontes não utilizadas de um documento PDF. O tutorial orienta você no processo de carregamento de um PDF, identificação e remoção de fontes não utilizadas e salvamento do PDF atualizado.

#### P: Por que eu desejaria remover fontes não utilizadas de um documento PDF?

R: A remoção de fontes não utilizadas de um documento PDF pode ajudar a reduzir o tamanho do arquivo e otimizar o documento para obter melhor desempenho. Isto é particularmente útil ao lidar com PDFs que contêm fontes incorporadas que não são realmente usadas no conteúdo do documento.

#### P: Como configuro o diretório de documentos?

R: Para configurar o diretório de documentos:

1.  Substituir`"YOUR DOCUMENT DIRECTORY"` no`dataDir` variável com o caminho para o diretório onde seus arquivos PDF estão localizados.

#### P: Como removo fontes não utilizadas de um documento PDF usando a biblioteca Aspose.PDF?

R: O tutorial orienta você passo a passo pelo processo:

1.  Abra o documento PDF usando o`Document` aula.
2.  Criar uma`TextFragmentAbsorber` objeto com`TextEditOptions` definido como`FontReplace.RemoveUnusedFonts`.
3. Use o absorvedor para identificar e remover fontes não utilizadas do PDF.
4.  Iterar por tudo`TextFragments` e defina a fonte para a fonte desejada.
5. Salve o documento PDF atualizado.

####  P: Qual é o propósito do`TextEditOptions.FontReplace.RemoveUnusedFonts` parameter?

 R: O`TextEditOptions.FontReplace.RemoveUnusedFonts` parâmetro instrui o`TextFragmentAbsorber` para identificar e remover fontes não utilizadas do documento PDF.

#### P: Posso substituir fontes não utilizadas por uma fonte de minha escolha?

R: Sim, você pode modificar o código para substituir fontes não utilizadas por uma fonte de sua escolha. No código de exemplo fornecido, a fonte "Arial, Bold" é usada como substituta.

####  P: Como é que`TextFragmentAbsorber` work to remove unused fonts?

 R: O`TextFragmentAbsorber` está configurado com o`TextEditOptions.FontReplace.RemoveUnusedFonts` parâmetro, que identifica fontes não utilizadas nos fragmentos de texto do PDF. Após a absorção, você pode iterar através do`TextFragments` e defina suas fontes para as fontes de substituição desejadas.

#### P: Qual é o resultado esperado da execução do código fornecido?

R: Seguindo o tutorial e executando o código C# fornecido, você removerá fontes não utilizadas do documento PDF de entrada e salvará a versão atualizada como o arquivo PDF de saída.

#### P: Posso modificar o código para remover fontes apenas de páginas ou áreas específicas?

R: O código fornecido concentra-se na remoção de fontes não utilizadas de todo o documento PDF. Se quiser direcionar páginas ou regiões específicas para remoção de fontes, você precisará modificar a abordagem e usar uma lógica mais complexa para identificar fontes não utilizadas nessas áreas.