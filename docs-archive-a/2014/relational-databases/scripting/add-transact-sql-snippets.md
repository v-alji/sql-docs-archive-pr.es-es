---
title: Agregar fragmentos de código de Transact-SQL
ms.custom: seo-lt-2019
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: 901c7995-8eb5-4d12-8bb0-de0a922b48f8
author: rothja
ms.author: jroth
ms.openlocfilehash: 5b5886f8f36ae3753fcb7c89dd3aeff9c69eeba5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87671462"
---
# <a name="add-transact-sql-snippets"></a><span data-ttu-id="142be-102">Agregar fragmentos de código de Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="142be-102">Add Transact-SQL Snippets</span></span>
  <span data-ttu-id="142be-103">Puede agregar sus propios fragmentos de código de Transact-SQL al conjunto de fragmentos de código predefinidos que se incluyen en [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="142be-103">You can add your own Transact-SQL code snippets to the set of pre-defined snippets included in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
## <a name="creating-a-transact-sql-snippet-file"></a><span data-ttu-id="142be-104">Crear un archivo de fragmento de código de Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="142be-104">Creating a Transact-SQL Snippet File</span></span>  
 <span data-ttu-id="142be-105">La primera parte de la creación de un fragmento de código de [!INCLUDE[tsql](../../includes/tsql-md.md)] consiste en crear un archivo XML con el texto del fragmento de código.</span><span class="sxs-lookup"><span data-stu-id="142be-105">The first part of creating a [!INCLUDE[tsql](../../includes/tsql-md.md)] code snippet is to create an XML file with the text of your code snippet.</span></span> <span data-ttu-id="142be-106">El archivo debe tener una extensión de archivo .snippet y cumplir los requisitos del tema sobre [referencia de esquemas de fragmento de código](https://go.microsoft.com/fwlink/?LinkId=207504).</span><span class="sxs-lookup"><span data-stu-id="142be-106">The file must have a .snippet file extension, and meet the requirements of the [Code Snippets Schema](https://go.microsoft.com/fwlink/?LinkId=207504).</span></span> <span data-ttu-id="142be-107">El lenguaje del fragmento de código se establece en SQL.</span><span class="sxs-lookup"><span data-stu-id="142be-107">Set the snippet language to SQL.</span></span>  
  
 <span data-ttu-id="142be-108">Puede utilizar los fragmentos de código predefinidos que se proporcionan con [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] como ejemplos.</span><span class="sxs-lookup"><span data-stu-id="142be-108">You can use the pre-defined snippets that ship with [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] as examples.</span></span> <span data-ttu-id="142be-109">Para buscar los fragmentos de código predefinidos, abra [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], seleccione el menú **Herramientas** y haga clic en **Administrador de fragmentos de código**.</span><span class="sxs-lookup"><span data-stu-id="142be-109">To find the pre-defined snippets, open [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], select the **Tools** menu, and click **Code Snippet Manager**.</span></span> <span data-ttu-id="142be-110">Seleccione **SQL** en el cuadro de lista **Lenguaje** ; la ruta de acceso a los fragmentos de código de [!INCLUDE[tsql](../../includes/tsql-md.md)] se muestra en el cuadro **Ubicación** .</span><span class="sxs-lookup"><span data-stu-id="142be-110">Select **SQL** in the **Language** list box, the path to the [!INCLUDE[tsql](../../includes/tsql-md.md)] snippets is displayed in the **Location** box.</span></span>  
  
## <a name="registering-the-code-snippet"></a><span data-ttu-id="142be-111">Registrar el fragmento de código</span><span class="sxs-lookup"><span data-stu-id="142be-111">Registering the Code Snippet</span></span>  
 <span data-ttu-id="142be-112">Después de crear el archivo de fragmento de código, utilice el Administrador de fragmentos de código para registrar el fragmento de código con [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="142be-112">After creating the snippet file, use the Code Snippets Manager to register the snippet with [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="142be-113">Puede agregar una carpeta que contiene varios fragmentos de código o importar fragmentos de código individuales a la carpeta **Mis fragmentos de código** .</span><span class="sxs-lookup"><span data-stu-id="142be-113">You can either add a folder containing multiple snippets, or import individual snippets to the **My Code Snippets** folder.</span></span>  
  
## <a name="procedures"></a><span data-ttu-id="142be-114">Procedimientos</span><span class="sxs-lookup"><span data-stu-id="142be-114">Procedures</span></span>  
  
#### <a name="adding-a-snippet-folder"></a><span data-ttu-id="142be-115">Agregar una carpeta de fragmentos de código</span><span class="sxs-lookup"><span data-stu-id="142be-115">Adding a Snippet Folder</span></span>  
  
1.  <span data-ttu-id="142be-116">Abra [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="142be-116">Open [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
2.  <span data-ttu-id="142be-117">Seleccione el menú **Herramientas** y haga clic en **Administrador de fragmentos de código**.</span><span class="sxs-lookup"><span data-stu-id="142be-117">Select the **Tools** menu, and click **Code Snippets Manager**.</span></span>  
  
3.  <span data-ttu-id="142be-118">Haga clic en el botón **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="142be-118">Click the **Add** button.</span></span>  
  
4.  <span data-ttu-id="142be-119">Navegue a la carpeta que contiene los fragmentos de código y haga clic en el botón **Seleccionar carpeta** .</span><span class="sxs-lookup"><span data-stu-id="142be-119">Navigate to the folder containing your code snippets, and click the **Select Folder** button.</span></span>  
  
#### <a name="importing-a-snippet"></a><span data-ttu-id="142be-120">Importar un fragmento de código</span><span class="sxs-lookup"><span data-stu-id="142be-120">Importing a Snippet</span></span>  
  
1.  <span data-ttu-id="142be-121">Abra [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="142be-121">Open [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
2.  <span data-ttu-id="142be-122">Seleccione el menú **Herramientas** y haga clic en **Administrador de fragmentos de código**.</span><span class="sxs-lookup"><span data-stu-id="142be-122">Select the **Tools** menu, and click **Code Snippets Manager**.</span></span>  
  
3.  <span data-ttu-id="142be-123">Haga clic en el botón **Import** (Importar).</span><span class="sxs-lookup"><span data-stu-id="142be-123">Click the **Import** button.</span></span>  
  
4.  <span data-ttu-id="142be-124">Navegue a la carpeta que contiene el fragmento de código, haga clic en el archivo .snippet y haga clic en el botón **Abrir** .</span><span class="sxs-lookup"><span data-stu-id="142be-124">Navigate to the folder containing your snippet, click on the .snippet file, and click the **Open** button.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="142be-125">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="142be-125">Examples</span></span>  
 <span data-ttu-id="142be-126">En el ejemplo siguiente se crea un fragmento de código rodear con `TRY-CATCH` y se importa a [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="142be-126">The following example creates a `TRY-CATCH` surround-with snippet and imports it to [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
1.  <span data-ttu-id="142be-127">Pegue el código siguiente en el Bloc de notas y, a continuación, guárdelo como un archivo denominado TryCatch.snippet.</span><span class="sxs-lookup"><span data-stu-id="142be-127">Paste the following code into notepad, then save as a file named TryCatch.snippet.</span></span>  
  
    ```  
    <?xml version="1.0" encoding="utf-8" ?>  
    <CodeSnippets  xmlns="https://schemas.microsoft.com/VisualStudio/2005/CodeSnippet">  
    <_locDefinition xmlns="urn:locstudio">  
        <_locDefault _loc="locNone" />  
        <_locTag _loc="locData">Title</_locTag>  
        <_locTag _loc="locData">Description</_locTag>  
        <_locTag _loc="locData">Author</_locTag>  
        <_locTag _loc="locData">ToolTip</_locTag>  
       <_locTag _loc="locData">Default</_locTag>  
    </_locDefinition>  
    <CodeSnippet Format="1.0.0">  
    <Header>  
    <Title>TryCatch</Title>  
                            <Shortcut></Shortcut>  
    <Description>Example Snippet for Try-Catch.</Description>  
    <Author>SQL Server Books Online Example</Author>  
    <SnippetTypes>  
                                    <SnippetType>SurroundsWith</SnippetType>  
    </SnippetTypes>  
    </Header>  
    <Snippet>  
    <Declarations>  
                                    <Literal>  
                                    <ID>CatchCode</ID>  
                                    <ToolTip>Code to handle the caught error</ToolTip>  
                                    <Default>CatchCode</Default>  
                                    </Literal>  
    </Declarations>  
    <Code Language="SQL"><![CDATA[  
    BEGIN TRY  
  
    $selected$ $end$  
  
    END TRY  
    BEGIN CATCH  
  
    $CatchCode$  
  
    END CATCH;  
    ]]>  
    </Code>  
    </Snippet>  
    </CodeSnippet>  
    </CodeSnippets>  
    ```  
  
2.  <span data-ttu-id="142be-128">Abra [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="142be-128">Open [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
3.  <span data-ttu-id="142be-129">Seleccione el menú **Herramientas** y haga clic en **Administrador de fragmentos de código**.</span><span class="sxs-lookup"><span data-stu-id="142be-129">Select the **Tools** menu, and click **Code Snippets Manager**.</span></span>  
  
4.  <span data-ttu-id="142be-130">Haga clic en el botón **Import** (Importar).</span><span class="sxs-lookup"><span data-stu-id="142be-130">Click the **Import** button.</span></span>  
  
5.  <span data-ttu-id="142be-131">Navegue a la carpeta que contiene el archivo TryCatch.snippet, haga clic en el citado archivo y haga clic en el botón **Abrir** .</span><span class="sxs-lookup"><span data-stu-id="142be-131">Navigate to the folder containing TryCatch.snippet, click on the TryCatch.snippet file, and click the **Open** button.</span></span> <span data-ttu-id="142be-132">No debe haber un fragmento de código TryCatch en la carpeta **Mis fragmentos de código** .</span><span class="sxs-lookup"><span data-stu-id="142be-132">You should not have a TryCatch snippet in your **My Code Snippets** folder.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="142be-133">Consulte también</span><span class="sxs-lookup"><span data-stu-id="142be-133">See Also</span></span>  
 [<span data-ttu-id="142be-134">Insertar fragmentos de código de Transact-SQL para rodear</span><span class="sxs-lookup"><span data-stu-id="142be-134">Insert Surround-with Transact-SQL snippets</span></span>](insert-surround-with-transact-sql-snippets.md)  
  
  
