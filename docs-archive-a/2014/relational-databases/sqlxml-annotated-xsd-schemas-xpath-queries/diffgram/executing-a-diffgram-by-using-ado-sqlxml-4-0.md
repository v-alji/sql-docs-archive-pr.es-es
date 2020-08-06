---
title: Ejecutar un DiffGram mediante ADO (SQLXML 4,0) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- providers [SQLXML], SQLOLEDB Provider
- ADO [SQLXML]
- SQLXMLOLEDB Provider, DiffGrams
- data providers [SQLXML], SQLOLEDB Provider
- DiffGrams [SQLXML], ADO
ms.assetid: 741fce82-de83-4923-86eb-30acb5b9a5e6
author: rothja
ms.author: jroth
ms.openlocfilehash: b96db25fd46b1ecbbc15c8acd912743e5560f178
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87673590"
---
# <a name="executing-a-diffgram-by-using-ado-sqlxml-40"></a><span data-ttu-id="cfc99-102">Ejecutar un DiffGram utilizando ADO (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="cfc99-102">Executing a DiffGram by Using ADO (SQLXML 4.0)</span></span>
  <span data-ttu-id="cfc99-103">Esta aplicación de [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Visual Basic utiliza ADO para establecer una conexión a una instancia de Microsoft [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] y después ejecuta un DiffGram.</span><span class="sxs-lookup"><span data-stu-id="cfc99-103">This [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Visual Basic application uses ADO to establish a connection to an instance of Microsoft [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] and then executes a DiffGram.</span></span> <span data-ttu-id="cfc99-104">En esta aplicación, el DiffGram y el esquema XSD están almacenados en un archivo.</span><span class="sxs-lookup"><span data-stu-id="cfc99-104">In this application, the DiffGram and the XSD schema are stored in a file.</span></span> <span data-ttu-id="cfc99-105">La aplicación carga el DiffGram del archivo especificado.</span><span class="sxs-lookup"><span data-stu-id="cfc99-105">The application loads the DiffGram from the specified file.</span></span> <span data-ttu-id="cfc99-106">Puede usar cualquiera de los DiffGrams (y el esquema XSD asociado) descrito en los [ejemplos de DiffGram](diffgram-examples-sqlxml-4-0.md).</span><span class="sxs-lookup"><span data-stu-id="cfc99-106">You can use any of the DiffGrams (and the associated XSD schema) described in [DiffGram Examples](diffgram-examples-sqlxml-4-0.md).</span></span>  
  
 <span data-ttu-id="cfc99-107">Éste es el proceso de la aplicación de ejemplo:</span><span class="sxs-lookup"><span data-stu-id="cfc99-107">This is the process for the sample application:</span></span>  
  
-   <span data-ttu-id="cfc99-108">Objeto **Conn** (**ADODB. Conexión**) establece una conexión a una instancia en ejecución de SQL Server en un servidor específico.</span><span class="sxs-lookup"><span data-stu-id="cfc99-108">The **conn** object (**ADODB.Connection**) establishes a connection to a running instance of SQL Server on a specific server.</span></span>  
  
-   <span data-ttu-id="cfc99-109">El objeto **cmd** (**ADODB. Command**) se ejecuta en la conexión establecida.</span><span class="sxs-lookup"><span data-stu-id="cfc99-109">The **cmd** object (**ADODB.Command**) executes on the established connection.</span></span>  
  
-   <span data-ttu-id="cfc99-110">El lenguaje de comandos está establecido en DBGUID_MSSQLXML.</span><span class="sxs-lookup"><span data-stu-id="cfc99-110">The command dialect is set to DBGUID_MSSQLXML.</span></span>  
  
-   <span data-ttu-id="cfc99-111">El DiffGram se copia en el flujo de comandos (**strmIn**) de un archivo.</span><span class="sxs-lookup"><span data-stu-id="cfc99-111">The DiffGram is copied to the command stream (**strmIn**) from a file.</span></span>  
  
-   <span data-ttu-id="cfc99-112">El flujo de salida del comando se establece en el objeto **StrmOut** (**ADODB. Stream**) para recibir los datos devueltos.</span><span class="sxs-lookup"><span data-stu-id="cfc99-112">The command's output stream is set to the **StrmOut** object (**ADODB.Stream**) to receive any returned data.</span></span>  
  
-   <span data-ttu-id="cfc99-113">Si está utilizando el proveedor SQLOLEDB, obtendrá de forma predeterminada la funcionalidad de Microsoft SQLXML que proporciona Sqlxmlx.dll.</span><span class="sxs-lookup"><span data-stu-id="cfc99-113">When you are using the SQLOLEDB Provider, by default you will get the Microsoft SQLXML functionality provided by Sqlxmlx.dll.</span></span> <span data-ttu-id="cfc99-114">Para utilizar Sqlxml4.dll con el proveedor SQLOLEDB, la propiedad **versión de SQLXML** debe establecerse en **SQLXML. 4.0** en el objeto de **conexión** del proveedor SQLOLEDB.</span><span class="sxs-lookup"><span data-stu-id="cfc99-114">To use Sqlxml4.dll with the SQLOLEDB Provider, the **SQLXML Version** property must be set to **SQLXML.4.0** on the SQLOLEDB Provider **Connection** object.</span></span>  
  
-   <span data-ttu-id="cfc99-115">Se ejecuta el comando (DiffGram).</span><span class="sxs-lookup"><span data-stu-id="cfc99-115">The command (DiffGram) is executed.</span></span>  
  
 <span data-ttu-id="cfc99-116">El siguiente código es la aplicación de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="cfc99-116">The following code is the sample application.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="cfc99-117">En el código, debe suministrarse el nombre de la instancia de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] en la cadena de conexión.</span><span class="sxs-lookup"><span data-stu-id="cfc99-117">In the code, you must provide the name of the instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] in the connection string.</span></span>  
  
```  
Private Sub Command1_Click()  
  Dim cmd As New ADODB.Command  
  Dim conn As New ADODB.Connection  
  Dim strmOut As New ADODB.Stream  
  Dim strmIn As New ADODB.Stream  
  
  'Open a connection to SQL Server.  
  conn.Provider = "SQLOLEDB"  
  conn.Open "server=SqlServerName; database=tempdb; Integrated Security=SSPI; "  
  conn.Properties("SQLXML Version") = "SQLXML.4.0"  
  Set cmd.ActiveConnection = conn  
  strmIn.Open  
  strmIn.Charset = "UTF-8"  
  strmIn.LoadFromFile "C:\SomeFilePath\SampleDiffGram.xml"  
  strmIn.Position = 0  
  Set cmd.CommandStream = strmIn  
  
  strmOut.Open  
  cmd.Properties("Output Stream").Value = strmOut  
  cmd.Properties("Output Encoding").Value = "UTF-8"  
  
  cmd.Dialect = "{5d531cb2-e6ed-11d2-b252-00c04f681b71}"  
  cmd.Properties("Mapping Schema") = "C:\SomeFilePath\SampleDiffGram.xml"  
  cmd.Execute , , adExecuteStream  
  strmOut.Position = 0  
  Set cmd = Nothing  
  strmOut.Charset = "UTF-8"  
  strmOut.SaveToFile "C:\DropIt.txt", adSaveCreateOverWrite  
  strmOut.Close  
  Set strmOut = Nothing  
  
End Sub  
```  
  
### <a name="to-test-the-diffgram"></a><span data-ttu-id="cfc99-118">Para probar el DiffGram:</span><span class="sxs-lookup"><span data-stu-id="cfc99-118">To test the DiffGram</span></span>  
  
1.  <span data-ttu-id="cfc99-119">En una carpeta del equipo, copie cualquiera de los DiffGrams y el esquema XSD correspondiente de uno de los ejemplos de los [ejemplos de DiffGram](diffgram-examples-sqlxml-4-0.md).</span><span class="sxs-lookup"><span data-stu-id="cfc99-119">To a folder on your computer, copy any one of the DiffGrams and the corresponding XSD schema from one of the examples in [DiffGram Examples](diffgram-examples-sqlxml-4-0.md).</span></span>  
  
2.  <span data-ttu-id="cfc99-120">Abra Visual Basic y cree un proyecto EXE estándar.</span><span class="sxs-lookup"><span data-stu-id="cfc99-120">Open Visual Basic and create a Standard EXE project.</span></span>  
  
3.  <span data-ttu-id="cfc99-121">Agregue estas referencias al proyecto:</span><span class="sxs-lookup"><span data-stu-id="cfc99-121">Add these references to the project:</span></span>  
  
    ```  
    Microsoft ActiveX Data Objects 2.8 Library  
    ```  
  
4.  <span data-ttu-id="cfc99-122">En el cuadro de herramientas, haga clic en **CommandButton**y, a continuación, dibuje un botón en el formulario.</span><span class="sxs-lookup"><span data-stu-id="cfc99-122">In the Toolbox, click **CommandButton**, and then draw a button on the form.</span></span>  
  
5.  <span data-ttu-id="cfc99-123">Haga doble clic en el botón para modificar el código y agregue el código de aplicación que se proporciona en el tema.</span><span class="sxs-lookup"><span data-stu-id="cfc99-123">Double-click the button to edit the code, and add the application code that is provided in the topic.</span></span>  
  
6.  <span data-ttu-id="cfc99-124">Modifique el código para especificar el DiffGram y los nombres de archivos XSD.</span><span class="sxs-lookup"><span data-stu-id="cfc99-124">Edit the code to specify the DiffGram and XSD file names.</span></span> <span data-ttu-id="cfc99-125">Modifique también la cadena de conexión según corresponda.</span><span class="sxs-lookup"><span data-stu-id="cfc99-125">Also edit the connection string as appropriate.</span></span>  
  
7.  <span data-ttu-id="cfc99-126">Ejecute la aplicación.</span><span class="sxs-lookup"><span data-stu-id="cfc99-126">Execute the application.</span></span> <span data-ttu-id="cfc99-127">El resultado de la ejecución depende del DiffGram que esté ejecutando.</span><span class="sxs-lookup"><span data-stu-id="cfc99-127">The result of the execution depends on what DiffGram you are executing.</span></span>  
  
  
