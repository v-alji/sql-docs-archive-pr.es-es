---
title: Utilizar ADO para ejecutar consultas SQLXML 4.0
ms.custom: ''
ms.date: 12/18/2019
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- query testers [SQLXML]
- test scripts
- ADO [SQLXML]
- queries [SQLXML], ADO
- SQLXML, ADO
ms.assetid: 3d54e3bb-7c5f-427e-82f8-1403a54c4f53
author: rothja
ms.author: jroth
ms.openlocfilehash: 169d20b4192e4a5b8e7b32839f2da255fc58d89c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87744631"
---
# <a name="using-ado-to-execute-sqlxml-40-queries"></a><span data-ttu-id="c15f0-102">Utilizar ADO para ejecutar consultas SQLXML 4.0</span><span class="sxs-lookup"><span data-stu-id="c15f0-102">Using ADO to Execute SQLXML 4.0 Queries</span></span>
  <span data-ttu-id="c15f0-103">En versiones anteriores de SQLXML, la ejecución de consultas basadas en HTTP se admitía mediante la utilización de directorios virtuales de SQLXML IIS y el filtro SQLXML ISAPI.</span><span class="sxs-lookup"><span data-stu-id="c15f0-103">In previous versions of SQLXML, HTTP-based query execution was supported using SQLXML IIS virtual directories and the SQLXML ISAPI filter.</span></span> <span data-ttu-id="c15f0-104">En SQLXML 4.0, estos componentes se han quitado ya que se ofrece una funcionalidad similar superpuesta a través de servicios web XML nativos a partir de [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c15f0-104">In SQLXML 4.0, these components have been removed as similar and overlapping functionality is provided with native XML Web services beginning in [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)].</span></span>  
  
 <span data-ttu-id="c15f0-105">Como alternativa, puede ejecutar consultas y utilizar SQLXML 4.0 con las aplicaciones basadas en COM si aprovecha las extensiones SQLXML a Objetos de datos ActiveX (ADO) que se introdujeron por primera vez en Microsoft Data Access Components (MDAC) 2.6 y versiones posteriores.</span><span class="sxs-lookup"><span data-stu-id="c15f0-105">As an alternative, you can execute queries and use SQLXML 4.0 with your COM-based applications, by leveraging the SQLXML extensions to ActiveX Data Objects (ADO) that were first introduced in Microsoft Data Access Components (MDAC) 2.6 and later.</span></span>  
  
 <span data-ttu-id="c15f0-106">En este tema se muestra cómo utilizar SQLXML y ADO como parte de una aplicación Visual Basic Scripting Edition (VBScript) (un script con la extensión de archivo .vbs).</span><span class="sxs-lookup"><span data-stu-id="c15f0-106">This topic demonstrates using SQLXML and ADO as part of a Visual Basic Scripting Edition (VBScript) application (a script with the .vbs file extension).</span></span> <span data-ttu-id="c15f0-107">También se proporcionan los procedimientos de configuración iniciales que le ayudarán a volver a crear y probar ejemplos de consulta de la documentación de SQLXML 4.0.</span><span class="sxs-lookup"><span data-stu-id="c15f0-107">It provides initial setup procedures to help you recreate and test query samples in the SQLXML 4.0 documentation.</span></span>  
  
## <a name="creating-the-sqlxml-40-test-script"></a><span data-ttu-id="c15f0-108">Crear el script de prueba de SQLXML 4.0</span><span class="sxs-lookup"><span data-stu-id="c15f0-108">Creating the SQLXML 4.0 Test Script</span></span>  
 <span data-ttu-id="c15f0-109">En este procedimiento, crea un archivo VBScript (.vbs), Sqlxml4test.vbs, que se puede utilizar para ejecutar consultas SQLXML aprovechando las extensiones ADO de SQLXML en ADO 2.6 y versiones posteriores.</span><span class="sxs-lookup"><span data-stu-id="c15f0-109">In this procedure, you create a VBScript (.vbs) file, Sqlxml4test.vbs, which can be used to execute SQLXML queries by leveraging the SQLXML ADO extensions in ADO 2.6 and later.</span></span>  
  
#### <a name="to-create-the-sqlxml-40-query-tester-using-ado-vbscript"></a><span data-ttu-id="c15f0-110">Para crear el evaluador de consultas de SQLXML 4.0 mediante ADO (VBScript).</span><span class="sxs-lookup"><span data-stu-id="c15f0-110">To create the SQLXML 4.0 query tester using ADO (VBScript).</span></span>  
  
1.  <span data-ttu-id="c15f0-111">Copie el código de VBScript siguiente y péguelo en un archivo de texto.</span><span class="sxs-lookup"><span data-stu-id="c15f0-111">Copy the VBScript code below, and paste it into a text file.</span></span> <span data-ttu-id="c15f0-112">Guarde el archivo como Sqlxml4test.vbs.</span><span class="sxs-lookup"><span data-stu-id="c15f0-112">Save the file as Sqlxml4test.vbs.</span></span>  
  
    ```vb
    WScript.Echo "Query process may take a few seconds to complete. Please be patient."  
  
    ' Note that for SQL Server Native Client to be used as the data provider,  
    ' it needs to be installed on the client computer first. Also, SQLXML extensions   
    ' for ADO are used and available in MDAC 2.6 or later.  
  
    'Set script variables.  
    inputFile = "@@FILE_NAME@@"  
    strServer = "@@SERVER_NAME@@"  
    strDatabase = "@@DATABASE_NAME@@"  
    dbGuid = "{5d531cb2-e6ed-11d2-b252-00c04f681b71}"  
  
    ' Establish ADO connection to SQL Server and   
    ' create an instance of the ADO Command object.  
    Set conn = CreateObject("ADODB.Connection")  
    Set cmd = CreateObject("ADODB.Command")  
    conn.Open "Provider=SQLXMLOLEDB.4.0;Data Provider=SQLNCLI11;Server=" & strServer & _  
              ";Database=" & strDatabase & ";Integrated Security=SSPI"  
    Set cmd.ActiveConnection = conn  
  
    ' Create the input stream as an instance of the ADO Stream object.  
    Set inStream = CreateObject("ADODB.Stream")  
    inStream.Open  
    inStream.Charset = "utf-8"  
    inStream.LoadFromFile inputFile  
  
    ' Set ADO Command instance to use input stream.  
    Set cmd.CommandStream = inStream  
  
    ' Set the command dialect.  
    cmd.Dialect = dbGuid  
  
    ' Set a second ADO Stream instance for use as a results stream.   
    Set outStream = CreateObject("ADODB.Stream")  
    outStream.Open  
  
    ' Set dynamic properties used by the SQLXML ADO command instance.   
    cmd.Properties("XML Root").Value = "ROOT"  
    cmd.Properties("Output Encoding").Value = "UTF-8"  
  
    ' Connect the results stream to the command instance and execute the command.  
    cmd.Properties("Output Stream").Value = outStream  
    cmd.Execute , , 1024  
  
    ' Echo cropped/partial results to console.  
    WScript.Echo Left(outStream.ReadText, 1023)  
  
    inStream.Close  
    outStream.Close  
    ```  
  
2.  <span data-ttu-id="c15f0-113">Actualice los siguientes valores de script para obtener el ejemplo que está intentando probar y su entorno de pruebas.</span><span class="sxs-lookup"><span data-stu-id="c15f0-113">Update the following script values for the sample you are trying to test and your test environment.</span></span>  
  
    -   <span data-ttu-id="c15f0-114">Busque "`@@FILE_NAME@@`" y reemplácelo con el nombre del archivo de plantilla.</span><span class="sxs-lookup"><span data-stu-id="c15f0-114">Find "`@@FILE_NAME@@`" and replace it with the name of your template file.</span></span>  
  
    -   <span data-ttu-id="c15f0-115">Busque "`@@SERVER_NAME@@`" y reemplácelo con el nombre de la instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] (por ejemplo, "`(local)`" si [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] se ejecuta localmente).</span><span class="sxs-lookup"><span data-stu-id="c15f0-115">Find "`@@SERVER_NAME@@`" and replace it with the name of your [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance (for example, "`(local)`" if [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is running locally).</span></span>  
  
    -   <span data-ttu-id="c15f0-116">Busque "`@@DATABASE_NAME@@`" y reemplácelo con el nombre de la base de datos (por ejemplo, "`AdventureWorks2012`" o "`tempdb`").</span><span class="sxs-lookup"><span data-stu-id="c15f0-116">Find "`@@DATABASE_NAME@@`" and replace it with the name of the database (for example, either "`AdventureWorks2012`" or "`tempdb`").</span></span>  
  
     <span data-ttu-id="c15f0-117">Actualice cualquier otro valor si se menciona en las instrucciones concretas del ejemplo que intenta volver a crear localmente en el equipo.</span><span class="sxs-lookup"><span data-stu-id="c15f0-117">Update any other values if mentioned in the specific instructions for the example you are attempting to recreate locally on your computer.</span></span>  
  
3.  <span data-ttu-id="c15f0-118">Guarde el archivo y ciérrelo.</span><span class="sxs-lookup"><span data-stu-id="c15f0-118">Save the file and close it.</span></span>  
  
4.  <span data-ttu-id="c15f0-119">Compruebe que ha creado los archivos adicionales, como esquemas o plantillas XML que forman parte del ejemplo que intenta volver a crear localmente en el equipo.</span><span class="sxs-lookup"><span data-stu-id="c15f0-119">Verify that you have created any additional files, such as XML templates or schemas that are part of the sample you are attempting to recreate locally on your computer.</span></span> <span data-ttu-id="c15f0-120">Estos archivos deben estar incluidos en el mismo directorio donde se ha guardado el archivo de script de prueba (Sqlxml4test.vbs).</span><span class="sxs-lookup"><span data-stu-id="c15f0-120">These files should be located in the same directory where you have saved the test script file (Sqlxml4test.vbs).</span></span>  
  
5.  <span data-ttu-id="c15f0-121">Siga las instrucciones de la sección siguiente sobre cómo utilizar el script de prueba de SQLXML 4.0.</span><span class="sxs-lookup"><span data-stu-id="c15f0-121">Follow the instructions in the next section for how to use the SQLXML 4.0 test script.</span></span>  
  
## <a name="using-the-sqlxml-40-test-script"></a><span data-ttu-id="c15f0-122">Utilizar el script de prueba de SQLXML 4.0</span><span class="sxs-lookup"><span data-stu-id="c15f0-122">Using the SQLXML 4.0 Test Script</span></span>  
 <span data-ttu-id="c15f0-123">El procedimiento siguiente describe cómo utilizar los archivos Sqlxml4test.vbs probar las consultas de ejemplo incluidas en esta documentación.</span><span class="sxs-lookup"><span data-stu-id="c15f0-123">The following procedure describes how to use the Sqlxml4test.vbs files to test the example queries provided in this documentation.</span></span>  
  
#### <a name="to-use-the-sqlxml-40-query-tester"></a><span data-ttu-id="c15f0-124">Para utilizar el evaluador de consultas de SQLXML 4.0</span><span class="sxs-lookup"><span data-stu-id="c15f0-124">To use the SQLXML 4.0 query tester</span></span>  
  
1.  <span data-ttu-id="c15f0-125">Compruebe tal como se indica a continuación que [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client está instalado:</span><span class="sxs-lookup"><span data-stu-id="c15f0-125">Verify that [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client is installed, as follows:</span></span>  
  
    1.  <span data-ttu-id="c15f0-126">En el menú **Inicio** , seleccione **configuración**y, a continuación, haga clic en **Panel de control**.</span><span class="sxs-lookup"><span data-stu-id="c15f0-126">From the **Start** menu, point to **Settings**, and then click **Control Panel**.</span></span>  
  
    2.  <span data-ttu-id="c15f0-127">En el panel de control, Abra **Agregar o quitar programas** .</span><span class="sxs-lookup"><span data-stu-id="c15f0-127">In Control Panel, open **Add or Remove Programs**</span></span>  
  
    3.  <span data-ttu-id="c15f0-128">En la lista de programas instalados actualmente, compruebe que **Microsoft SQL Server Native Client** aparece en la lista.</span><span class="sxs-lookup"><span data-stu-id="c15f0-128">In the list of currently installed programs, verify that **Microsoft SQL Server Native Client** appears in the list.</span></span>  
  
        > [!NOTE]  
        >  <span data-ttu-id="c15f0-129">Si necesita instalar [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client, consulte Instalación de [SQL Server Native Client](../native-client/applications/installing-sql-server-native-client.md).</span><span class="sxs-lookup"><span data-stu-id="c15f0-129">If you need to install [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client, see [Installing SQL Server Native Client](../native-client/applications/installing-sql-server-native-client.md).</span></span>  
  
2.  <span data-ttu-id="c15f0-130">Compruebe que la versión de MDAC instalada en el equipo cliente es la versión 2.6 o posterior.</span><span class="sxs-lookup"><span data-stu-id="c15f0-130">Verify that the version of MDAC installed for the client computer is 2.6 or later.</span></span> <span data-ttu-id="c15f0-131">Si necesita comprobar la información de la versión de MDAC, puede usar la herramienta Comprobador de componentes de MDAC, que se proporciona como descarga gratuita en el sitio web de Microsoft [https://www.microsoft.com/](https://www.microsoft.com/) .</span><span class="sxs-lookup"><span data-stu-id="c15f0-131">If you need to verify MDAC version information, you can use the MDAC Component Checker tool, which is provided as free download from the Microsoft Web site [https://www.microsoft.com/](https://www.microsoft.com/).</span></span> <span data-ttu-id="c15f0-132">Para obtener más información, busque "MDAC Component Checker" en el sitio web de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="c15f0-132">For more information, search on "MDAC Component Checker" on the Microsoft Web site.</span></span>  
  
3.  <span data-ttu-id="c15f0-133">Ejecute el script.</span><span class="sxs-lookup"><span data-stu-id="c15f0-133">Execute the script.</span></span>  
  
     <span data-ttu-id="c15f0-134">Puede ejecutar el archivo VBScript en la línea de comandos utilizando Cscript.exe o haciendo doble clic en el archivo Sqlxml4test.vbs para invocar Windows Script Host (WScript.exe).</span><span class="sxs-lookup"><span data-stu-id="c15f0-134">You can execute the VBScript file either at the command line using Cscript.exe or by double-clicking Sqlxml4test.vbs file to invoke the Windows Script Host (WScript.exe).</span></span>  
  
     <span data-ttu-id="c15f0-135">Al ejecutarlo, el script debe mostrar un mensaje para advertir que puede tardar unos momentos en ejecutarse antes de devolver y mostrar los resultados de consulta como salida del script.</span><span class="sxs-lookup"><span data-stu-id="c15f0-135">When executed, the script should display a message to alert you that the script might take a few moments to execute before returning and displaying query results as script output.</span></span> <span data-ttu-id="c15f0-136">Cuando aparezca el resultado, compare su contenido con los resultados esperados del ejemplo.</span><span class="sxs-lookup"><span data-stu-id="c15f0-136">When the output appears, compare its contents to the expected results for the sample.</span></span>  
  
  
