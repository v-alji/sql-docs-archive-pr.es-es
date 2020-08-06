---
title: Cmdlet Invoke-PolicyEvaluation | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- Policy-Based Management, Invoke-PolicyEvaluation
- Policy-Based Management, PowerShell
- Invoke-PolicyEvaluation cmdlet
- Cmdlets [SQL Server], Invoke-PolicyEvaluation
- PowerShell [SQL Server], Invoke-PolicyEvaluation
ms.assetid: 3e6d4f5a-59b7-4203-b95a-f7e692c0f131
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 656fdffea191c9cf6fc42d860164bc5af1e04561
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87745398"
---
# <a name="invoke-policyevaluation-cmdlet"></a><span data-ttu-id="de770-102">cmdlet Invoke-PolicyEvaluation</span><span class="sxs-lookup"><span data-stu-id="de770-102">Invoke-PolicyEvaluation cmdlet</span></span>
  <span data-ttu-id="de770-103">**Invoke-PolicyEvaluation** es un cmdlet de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] que notifica si un conjunto de destino de objetos de SQL Server cumple las condiciones especificadas en una o más directivas de administración basada en directivas.</span><span class="sxs-lookup"><span data-stu-id="de770-103">**Invoke-PolicyEvaluation** is a [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] cmdlet that reports whether a target set of SQL Server objects complies with the conditions specified in one or more Policy-Based Management policies.</span></span>  
  
## <a name="using-invoke-policyevaluation"></a><span data-ttu-id="de770-104">Uso de Invoke-PolicyEvaluation</span><span class="sxs-lookup"><span data-stu-id="de770-104">Using Invoke-PolicyEvaluation</span></span>  
 <span data-ttu-id="de770-105">**Invoke-PolicyEvaluation** evalúa una o mas directivas comparándolas con un conjunto de objetos de SQL Server que se conoce como el conjunto de destino.</span><span class="sxs-lookup"><span data-stu-id="de770-105">**Invoke-PolicyEvaluation** evaluates one or more policies against a set of SQL Server objects called the target set.</span></span> <span data-ttu-id="de770-106">Los objetos del conjunto de destino provienen de un servidor de destino.</span><span class="sxs-lookup"><span data-stu-id="de770-106">The set of target objects comes from a target server.</span></span> <span data-ttu-id="de770-107">Cada directiva define condiciones, que son los estados permitidos de los objetos de destino.</span><span class="sxs-lookup"><span data-stu-id="de770-107">Each policy defines conditions, which are the allowed states for the target objects.</span></span> <span data-ttu-id="de770-108">Por ejemplo, la directiva **Trustworthy Database** indica que la propiedad de base de datos TRUSTWORTHY se debe establecer como OFF.</span><span class="sxs-lookup"><span data-stu-id="de770-108">For example, the **Trustworthy Database** policy states that the TRUSTWORTHY database property must be set to OFF.</span></span>  
  
 <span data-ttu-id="de770-109">El parámetro **-AdHocPolicyEvaluationMode** especifica las acciones realizadas:</span><span class="sxs-lookup"><span data-stu-id="de770-109">The **-AdHocPolicyEvaluationMode** parameter specifies the actions taken:</span></span>  
  
 <span data-ttu-id="de770-110">Comprobar</span><span class="sxs-lookup"><span data-stu-id="de770-110">Check</span></span>  
 <span data-ttu-id="de770-111">Informa del estado de cumplimiento de los objetos de destino mediante las credenciales del inicio de sesión actual.</span><span class="sxs-lookup"><span data-stu-id="de770-111">Report the compliance status of the target objects using the credentials of your current login.</span></span> <span data-ttu-id="de770-112">No configure ningún objeto.</span><span class="sxs-lookup"><span data-stu-id="de770-112">Do no reconfigure any objects.</span></span> <span data-ttu-id="de770-113">Esta es la configuración predeterminada.</span><span class="sxs-lookup"><span data-stu-id="de770-113">This is the default setting.</span></span>  
  
 <span data-ttu-id="de770-114">CheckSqlScriptAsProxy</span><span class="sxs-lookup"><span data-stu-id="de770-114">CheckSqlScriptAsProxy</span></span>  
 <span data-ttu-id="de770-115">Informa del estado de cumplimiento de los objetos de destino mediante las credenciales del inicio de sesión de proxy **##MS_PolicyTSQLExecutionLogin##** .</span><span class="sxs-lookup"><span data-stu-id="de770-115">Report the compliance status of the target objects using the credentials of the **##MS_PolicyTSQLExecutionLogin##** proxy login.</span></span> <span data-ttu-id="de770-116">No configure ningún objeto.</span><span class="sxs-lookup"><span data-stu-id="de770-116">Do no reconfigure any objects.</span></span>  
  
 <span data-ttu-id="de770-117">Configuración</span><span class="sxs-lookup"><span data-stu-id="de770-117">Configure</span></span>  
 <span data-ttu-id="de770-118">Informa del estado de cumplimiento de los objetos de destino mediante las credenciales del inicio de sesión actual.</span><span class="sxs-lookup"><span data-stu-id="de770-118">Report the compliance status of the target objects using the credentials of your current login.</span></span> <span data-ttu-id="de770-119">Vuelva a configurar cualquier opción que se pueda establecer y que sea determinista que no cumpla las directivas.</span><span class="sxs-lookup"><span data-stu-id="de770-119">Reconfigure any settable and deterministic options that are not in compliance with the policies.</span></span>  
  
## <a name="specifying-polices"></a><span data-ttu-id="de770-120">Especificar directivas</span><span class="sxs-lookup"><span data-stu-id="de770-120">Specifying Polices</span></span>  
 <span data-ttu-id="de770-121">La forma en la que se especifica una directiva depende de su ubicación de almacenamiento.</span><span class="sxs-lookup"><span data-stu-id="de770-121">How you specify a policy depends on where the policy is stored.</span></span> <span data-ttu-id="de770-122">Las directivas se pueden almacenar en dos formatos:</span><span class="sxs-lookup"><span data-stu-id="de770-122">Policies can be stored in two formats:</span></span>  
  
-   <span data-ttu-id="de770-123">Pueden ser objetos almacenados en un almacén de directivas, como una instancia del motor de base de datos.</span><span class="sxs-lookup"><span data-stu-id="de770-123">They can be objects stored in a policy store, such as an instance of the Database Engine.</span></span> <span data-ttu-id="de770-124">Puede usar la carpeta SQLSERVER:\SQLPolicy para especificar la ubicación de las directivas en un almacén de directivas.</span><span class="sxs-lookup"><span data-stu-id="de770-124">You can use the SQLSERVER:\SQLPolicy folder to specify the location of policies in a policy store.</span></span> <span data-ttu-id="de770-125">Puede usar los cmdlets de Windows PowerShell para filtrar las directivas de entrada basándose en sus propiedades, como el uso de Where-Object para filtrar por categoría de directiva o Get-Item para hacerlo por nombre de directiva.</span><span class="sxs-lookup"><span data-stu-id="de770-125">You can use Windows PowerShell cmdlets to filter the input polices based on their properties, such as using Where-Object to filter on the policy category or Get-Item to filter on policy name.</span></span>  
  
-   <span data-ttu-id="de770-126">Se pueden exportar como archivos XML.</span><span class="sxs-lookup"><span data-stu-id="de770-126">They can be exported as XML files.</span></span> <span data-ttu-id="de770-127">Puede utilizar una unidad de disco del sistema de archivos, como D:, para especificar la ubicación de los archivos XML.</span><span class="sxs-lookup"><span data-stu-id="de770-127">You can use a file system drive, such as D:, to specify the location of the XML files.</span></span> <span data-ttu-id="de770-128">Puede usar los cmdlets de Windows PowerShell como Where-Object para filtrar las directivas por sus propiedades de archivo, como nombre de archivo.</span><span class="sxs-lookup"><span data-stu-id="de770-128">You can use Windows PowerShell cmdlets such as Where-Object to filter the policies on their file properties, such as file name.</span></span>  
  
 <span data-ttu-id="de770-129">Si las directivas se almacenan en un almacén de directivas, debe pasar un conjunto de PSObjects que señalen a las directivas que se van a evaluar.</span><span class="sxs-lookup"><span data-stu-id="de770-129">If the policies are stored in a policy store, you must pass in a set of PSObjects pointing to the policies to be evaluated.</span></span> <span data-ttu-id="de770-130">Esto se suele realizar mediante la canalización de la salida de un cmdlet como Get-Item a **Invoke-PolicyEvaluation**y no requiere que se especifique el parámetro **-Policy** .</span><span class="sxs-lookup"><span data-stu-id="de770-130">This is typically done by piping the output of a cmdlet such as Get-Item to **Invoke-PolicyEvaluation**, and does not require that you specify the **-Policy** parameter.</span></span> <span data-ttu-id="de770-131">Por ejemplo, si ha importado las directivas de las prácticas recomendadas de Microsoft a la instancia del motor de base de datos, este comando evalúa la directiva **Database Status** :</span><span class="sxs-lookup"><span data-stu-id="de770-131">For example, if you have imported the Microsoft Best Practices policies into your instance of the database engine, this command evaluates the **Database Status** policy:</span></span>  
  
```powershell
sl "SQLSERVER:\SQLPolicy\MyComputer\DEFAULT\Policies"  
Get-Item "Database Status" | Invoke-PolicyEvaluation -TargetServerName "MYCOMPUTER"  
```  
  
 <span data-ttu-id="de770-132">En este ejemplo se muestra el uso de Where-Object para filtrar varias directivas de un almacén de directivas en función de su propiedad **PolicyCategory** .</span><span class="sxs-lookup"><span data-stu-id="de770-132">This example shows using Where-Object to filter multiple policies from a policy store based on their **PolicyCategory** property.</span></span> <span data-ttu-id="de770-133">**Invoke-PolicyEvaluation** usa los objetos de la salida canalizada de **Where-Object**.</span><span class="sxs-lookup"><span data-stu-id="de770-133">The objects from the piped output of **Where-Object** is consumed by **Invoke-PolicyEvaluation**.</span></span>  
  
```powershell
sl "SQLSERVER:\SQLPolicy\MyComputer\DEFAULT\Policies"  
gci | Where-Object {$_.PolicyCategory -eq "Microsoft Best Practices: Maintenance"} | Invoke-PolicyEvaluation -TargetServer "MYCOMPUTER"  
```  
  
 <span data-ttu-id="de770-134">Si las directivas se almacenan como archivos XML, debe usar el parámetro **-Policy** para proporcionar tanto la ruta de acceso como el nombre de cada directiva.</span><span class="sxs-lookup"><span data-stu-id="de770-134">If the policies are stored as XML files, you must use the **-Policy** parameter to supply both the path and name for each policy.</span></span> <span data-ttu-id="de770-135">Si no especifica una ruta de acceso en el parámetro **-Policy** , **Invoke-PolicyEvaulation** usa el valor actual de la ruta de acceso **sqlps** .</span><span class="sxs-lookup"><span data-stu-id="de770-135">If you do not specify a path in the **-Policy** parameter, **Invoke-PolicyEvaulation** uses the current setting of the **sqlps** path.</span></span> <span data-ttu-id="de770-136">Por ejemplo, este comando evalúa una de las directivas de las prácticas recomendadas de Microsoft instalada con SQL Server comparándola con la base de datos predeterminada para el inicio de sesión:</span><span class="sxs-lookup"><span data-stu-id="de770-136">For example, this command evaluates one of the Microsoft Best Practice policies installed with SQL Server against the default database for your login:</span></span>  
  
```powershell
Invoke-PolicyEvaluation -Policy "C:\Program Files\Microsoft SQL Server\120\Tools\Policies\DatabaseEngine\1033\Database Status.xml" -TargetServerName "MYCOMPUTER"  
```  
  
 <span data-ttu-id="de770-137">Este comando realiza la misma acción, pero usa la ruta de acceso de **sqlps** actual para establecer la ubicación del archivo XML de directivas:</span><span class="sxs-lookup"><span data-stu-id="de770-137">This command does the same thing, only it uses the current **sqlps** path to establish the location of the policy XML file:</span></span>  
  
```powershell
sl "C:\Program Files\Microsoft SQL Server\120\Tools\Policies\DatabaseEngine\1033"  
Invoke-PolicyEvaluation -Policy "Database Status.xml" -TargetServerName "MYCOMPUTER"  
```  
  
 <span data-ttu-id="de770-138">En este ejemplo se muestra el empleo del cmdlet **Get-ChildItem** para recuperar varios archivos XML de directivas y canalizar los objetos a **Invoke-PolicyEvaluation**:</span><span class="sxs-lookup"><span data-stu-id="de770-138">This example shows using the **Get-ChildItem** cmdlet to retrieve multiple policy XML files and pipe the objects into **Invoke-PolicyEvaluation**:</span></span>  
  
```powershell
sl "C:\Program Files\Microsoft SQL Server\120\Tools\Policies\DatabaseEngine\1033"  
gci "Database Status.xml", "Trustworthy Database.xml" | Invoke-PolicyEvaluation -TargetServer "MYCOMPUTER"  
```  
  
## <a name="specifying-the-target-set"></a><span data-ttu-id="de770-139">Especificar el conjunto de destino</span><span class="sxs-lookup"><span data-stu-id="de770-139">Specifying the Target Set</span></span>  
 <span data-ttu-id="de770-140">Use tres parámetros para especificar el conjunto de objetos de destino:</span><span class="sxs-lookup"><span data-stu-id="de770-140">Use three parameters to specify the set of target objects:</span></span>  
  
-   <span data-ttu-id="de770-141">**-TargetServerName** especifica la instancia de SQL Server que contiene los objetos de destino.</span><span class="sxs-lookup"><span data-stu-id="de770-141">**-TargetServerName** specifies the instance of SQL Server containing the target objects.</span></span> <span data-ttu-id="de770-142">Puede especificar la información en una cadena con el formato definido para la propiedad ConnectionString de la clase <xref:System.Data.SqlClient.SqlConnection> .</span><span class="sxs-lookup"><span data-stu-id="de770-142">You can specify the information in a string that uses the format defined for the ConnectionString property of the <xref:System.Data.SqlClient.SqlConnection> class.</span></span> <span data-ttu-id="de770-143">Puede usar la clase <xref:System.Data.SqlClient.SqlConnectionStringBuilder> para generar una cadena de conexión con el formato correcto.</span><span class="sxs-lookup"><span data-stu-id="de770-143">You can use the <xref:System.Data.SqlClient.SqlConnectionStringBuilder> class to build a correctly formatted connection string.</span></span> <span data-ttu-id="de770-144">También puede crear un objeto <xref:Microsoft.SqlServer.Management.Sdk.Sfc.SqlStoreConnection> y pasarlo a **-TargetServer**.</span><span class="sxs-lookup"><span data-stu-id="de770-144">You can also create a <xref:Microsoft.SqlServer.Management.Sdk.Sfc.SqlStoreConnection> object and pass it to **-TargetServer**.</span></span> <span data-ttu-id="de770-145">Si proporciona una cadena que solo contiene el nombre del servidor, **Invoke-PolicyEvaluation** usa autenticación de Windows para conectar con el servidor.</span><span class="sxs-lookup"><span data-stu-id="de770-145">If you supply a string that has only the name of the server, **Invoke-PolicyEvaluation** uses Windows Authentication to connect to the server.</span></span>  
  
-   <span data-ttu-id="de770-146">**-TargetObjects** toma un objeto o una matriz de objetos que representa a los objetos de SQL Server del conjunto de destino.</span><span class="sxs-lookup"><span data-stu-id="de770-146">**-TargetObjects** takes an object or array of objects that represent the SQL Server objects in the target set.</span></span> <span data-ttu-id="de770-147">Por ejemplo, podría crear una matriz de objetos de la clase <xref:Microsoft.SqlServer.Management.Smo.Database> para pasarlos a **-TargetObjects**.</span><span class="sxs-lookup"><span data-stu-id="de770-147">For example, you could create an array of <xref:Microsoft.SqlServer.Management.Smo.Database> class objects to pass in to **-TargetObjects**.</span></span>  
  
-   <span data-ttu-id="de770-148">**-TargetExpressions** toma una cadena que contiene una expresión de consulta que especifica los objetos del conjunto de destino.</span><span class="sxs-lookup"><span data-stu-id="de770-148">**-TargetExpressions** takes a string containing a query expression that specifies the objects in the target set.</span></span> <span data-ttu-id="de770-149">La expresión de consulta tiene el formato de los nodos separados por el carácter '/'.</span><span class="sxs-lookup"><span data-stu-id="de770-149">The query expression is in the form of nodes separated by the '/' character.</span></span> <span data-ttu-id="de770-150">Cada nodo tiene el formato ObjectType[Filter].</span><span class="sxs-lookup"><span data-stu-id="de770-150">Each node is in the form ObjectType[Filter].</span></span> <span data-ttu-id="de770-151">El tipo de objeto es uno de los objetos de una jerarquía de objetos de objetos de administración de SQL Server (SMO).</span><span class="sxs-lookup"><span data-stu-id="de770-151">Object type is one of the objects in a SQL Server Management Object (SMO) object hierarchy.</span></span> <span data-ttu-id="de770-152">Filter es una expresión que filtra los objetos de ese nodo.</span><span class="sxs-lookup"><span data-stu-id="de770-152">Filter is an expression that filters for objects at that node.</span></span> <span data-ttu-id="de770-153">Para más información, consulte [Query Expressions and Uniform Resource Names](../powershell/query-expressions-and-uniform-resource-names.md).</span><span class="sxs-lookup"><span data-stu-id="de770-153">For more information, see [Query Expressions and Uniform Resource Names](../powershell/query-expressions-and-uniform-resource-names.md).</span></span>  
  
 <span data-ttu-id="de770-154">Especifique **-TargetObjects** o **-TargetExpression**, no ambos.</span><span class="sxs-lookup"><span data-stu-id="de770-154">Specify either **-TargetObjects** or **-TargetExpression**, not both.</span></span>  
  
 <span data-ttu-id="de770-155">En este ejemplo se usa un objeto Sfc.SqlStoreConnection para especificar el servidor de destino:</span><span class="sxs-lookup"><span data-stu-id="de770-155">This example uses an Sfc.SqlStoreConnection object to specify the target server:</span></span>  
  
```powershell
sl "C:\Program Files\Microsoft SQL Server\120\Tools\Policies\DatabaseEngine\1033"  
$conn = New-Object Microsoft.SqlServer.Management.Sdk.Sfc.SqlStoreConnection("server='MYCOMPUTER';Trusted_Connection=True")  
Invoke-PolicyEvaluation -Policy "Database Status.xml" -TargetServerName $conn  
```  
  
 <span data-ttu-id="de770-156">En este ejemplo se usa **-TargetExpression** para identificar la base de datos concreta que se va a evaluar:</span><span class="sxs-lookup"><span data-stu-id="de770-156">This example uses **-TargetExpression** to identify the specific database to evaluate:</span></span>  
  
```powershell
sl "C:\Program Files\Microsoft SQL Server\120\Tools\Policies\DatabaseEngine\1033"  
Invoke-PolicyEvaluation -Policy "Database Status.xml" -TargetServerName "MyComputer" -TargetExpression "Server[@Name='MYCOMPUTER']/Database[@Name='AdventureWorks2012']"  
```  
  
## <a name="evaluating-analysis-services-policies"></a><span data-ttu-id="de770-157">Evaluar las directivas de Analysis Services</span><span class="sxs-lookup"><span data-stu-id="de770-157">Evaluating Analysis Services Policies</span></span>  
 <span data-ttu-id="de770-158">Para evaluar las directivas comparándolas con una instancia de [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)], debe cargar y registrar un ensamblado en PowerShell, crear una variable con un objeto de conexión de Analysis Services y pasársela al parámetro **-TargetObject** .</span><span class="sxs-lookup"><span data-stu-id="de770-158">To evaluate policies against an instance of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)], you must load and register an assembly into PowerShell, create a variable with an Analysis Services connection object, and pass the variable to the **-TargetObject** parameter.</span></span> <span data-ttu-id="de770-159">En este ejemplo se muestra cómo evaluar la directiva de configuración de área expuesta de las prácticas recomendadas de [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="de770-159">This example shows evaluating the Best Practices surface area configuration policy for [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)]:</span></span>  
  
```powershell
sl "C:\Program Files\Microsoft SQL Server\120\Tools\Policies\AnalysisServices\1033"  
[System.Reflection.Assembly]::LoadWithPartialName("Microsoft.AnalysisServices")  
$SSASsvr = New-Object Microsoft.AnalysisServices.Server  
$SSASsvr.Connect("Data Source=Localhost")  
Invoke-PolicyEvaluation -Policy "Surface Area Configuration for Analysis Services Features.xml" -TargetObject $SSASsvr  
```  
  
## <a name="evaluating-reporting-services-policies"></a><span data-ttu-id="de770-160">Evaluar las directivas de Reporting Services</span><span class="sxs-lookup"><span data-stu-id="de770-160">Evaluating Reporting Services Policies</span></span>  
 <span data-ttu-id="de770-161">Para evaluar las directivas de [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] , debe cargar y registrar un ensamblado en PowerShell, crear una variable con un objeto de conexión de [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] y pasársela al parámetro **-TargetObject** .</span><span class="sxs-lookup"><span data-stu-id="de770-161">To evaluate [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] policies, you must load and register an assembly into PowerShell, create a variable with a [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] connection object, and pass the variable to the **-TargetObject** parameter.</span></span> <span data-ttu-id="de770-162">En este ejemplo se muestra cómo evaluar la directiva de configuración de área expuesta de las prácticas recomendadas de [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="de770-162">This example shows evaluating the Best Practices surface area configuration policy for [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)]:</span></span>  
  
```powershell
sl "C:\Program Files\Microsoft SQL Server\120\Tools\Policies\ReportingServices\1033"  
[System.Reflection.Assembly]::LoadWithPartialName("Microsoft.SqlServer.Dmf.Adapters")  
$SSRSsvr = new-object Microsoft.SqlServer.Management.Adapters.RSContainer('MyComputer')  
Invoke-PolicyEvaluation -Policy "Surface Area Configuration for Reporting Services 2008 Features.xml" -TargetObject $SSRSsvr  
```  
  
## <a name="formatting-output"></a><span data-ttu-id="de770-163">Dar formato a los resultados</span><span class="sxs-lookup"><span data-stu-id="de770-163">Formatting Output</span></span>  
 <span data-ttu-id="de770-164">De forma predeterminada, la salida de **Invoke-PolicyEvaluation** se muestra en la ventana del símbolo del sistema como informe conciso en formato legible.</span><span class="sxs-lookup"><span data-stu-id="de770-164">By default, the output of **Invoke-PolicyEvaluation** is displayed in the command prompt window as a concise report in human-readable format.</span></span> <span data-ttu-id="de770-165">Puede usar el parámetro **-OutputXML** para especificar que el cmdlet genere un informe detallado como archivo XML.</span><span class="sxs-lookup"><span data-stu-id="de770-165">You can use the **-OutputXML** parameter to specify that the cmdlet instead produce a detailed report as an XML file.</span></span> <span data-ttu-id="de770-166">**Invoke-PolicyEvaluation** usa el esquema SML-IF (Systems Modeling Language Interchange Format) para que los lectores SML-IF puedan leer el archivo.</span><span class="sxs-lookup"><span data-stu-id="de770-166">**Invoke-PolicyEvaluation** uses the Systems Modeling Language Interchange Format (SML-IF) schema so the file can be read by SML-IF readers.</span></span>  
  
```powershell
sl "SQLSERVER:\SQLPolicy\MyComputer\DEFAULT\Policies"  
Invoke-PolicyEvaluation -Policy "Datbase Status" -TargetServer "MYCOMPUTER" -OutputXML > C:\MyReports\DatabaseStatusReport.xml  
```  
  
## <a name="see-also"></a><span data-ttu-id="de770-167">Consulte también</span><span class="sxs-lookup"><span data-stu-id="de770-167">See Also</span></span>  
 [<span data-ttu-id="de770-168">Utilizar los cmdlets del motor de base de datos</span><span class="sxs-lookup"><span data-stu-id="de770-168">Use the Database Engine cmdlets</span></span>](../../2014/database-engine/use-the-database-engine-cmdlets.md)  
