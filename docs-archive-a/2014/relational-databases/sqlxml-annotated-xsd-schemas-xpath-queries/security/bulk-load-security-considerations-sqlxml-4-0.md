---
title: Consideraciones de seguridad de carga masiva (SQLXML 4,0) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- SQLXML, XML Bulk Load
- bulk load [SQLXML], security
- security [SQLXML], XML Bulk Load
- XML Bulk Load [SQLXML], security
ms.assetid: 192fc6d4-ecbc-4a4d-a5cb-55e1f64af318
author: rothja
ms.author: jroth
ms.openlocfilehash: 21c1cbe7f94ef42327aa7b81f75fa521d9f7c0e9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87678164"
---
# <a name="bulk-load-security-considerations-sqlxml-40"></a><span data-ttu-id="03ea6-102">Consideraciones de seguridad sobre la carga masiva (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="03ea6-102">Bulk Load Security Considerations (SQLXML 4.0)</span></span>
  <span data-ttu-id="03ea6-103">A continuación se muestran una serie de instrucciones de seguridad para utilizar la carga masiva XML:</span><span class="sxs-lookup"><span data-stu-id="03ea6-103">The following are security guidelines for using XML Bulk Load:</span></span>  
  
-   <span data-ttu-id="03ea6-104">Cuando especifique que la operación de carga masiva debe realizarse como una transacción, debe utilizar la propiedad `TempFilePath` para especificar una carpeta en la que crear los archivos temporales.</span><span class="sxs-lookup"><span data-stu-id="03ea6-104">When you specify that the Bulk Load operation is to be performed as a transaction, you use the `TempFilePath` property to specify a folder in which to create the temporary files.</span></span>  
  
     <span data-ttu-id="03ea6-105">El proceso de carga masiva crea estos archivos temporales con los siguientes permisos:</span><span class="sxs-lookup"><span data-stu-id="03ea6-105">The Bulk Load process creates these temporary files with the following permissions:</span></span>  
  
    -   <span data-ttu-id="03ea6-106">Se concede acceso de lectura/escritura/eliminación al proceso de carga masiva.</span><span class="sxs-lookup"><span data-stu-id="03ea6-106">Read/Write/Delete access is granted to the Bulk Load process.</span></span>  
  
    -   <span data-ttu-id="03ea6-107">Se concede permiso de lectura a todos los usuarios porque se desconoce la cuenta con la que Microsoft [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] obtendrá acceso a estos archivos.</span><span class="sxs-lookup"><span data-stu-id="03ea6-107">Read permission is granted to all users, because the account under which Microsoft [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] will access these files is unknown.</span></span> <span data-ttu-id="03ea6-108">Puede restringir el acceso a estos archivos temporales estableciendo los permisos adecuados en la carpeta que los contiene.</span><span class="sxs-lookup"><span data-stu-id="03ea6-108">You can restrict the access to these temporary files by setting the appropriate permissions on the folder that contains them.</span></span>  
  
-   <span data-ttu-id="03ea6-109">La carga masiva XML propiamente dicha no tiene ninguna configuración de permisos.</span><span class="sxs-lookup"><span data-stu-id="03ea6-109">XML Bulk Load does not itself have any permissions settings.</span></span> <span data-ttu-id="03ea6-110">Se asume que la base de datos está configurada correctamente y que el contexto del usuario (es decir, el inicio de sesión de la carga masiva) tiene establecidos los permisos adecuados.</span><span class="sxs-lookup"><span data-stu-id="03ea6-110">It is assumed that the database is set up correctly and that the user context (that is, the login that Bulk Load is set use) has appropriate permissions set.</span></span>  
  
-   <span data-ttu-id="03ea6-111">En el modo no transaccional, si se produce un error durante el proceso de carga masiva, los datos pueden quedar en un estado parcialmente cargado.</span><span class="sxs-lookup"><span data-stu-id="03ea6-111">In non-transactional mode, if an error occurs during the Bulk Load process, data may be left in a partially loaded state.</span></span> <span data-ttu-id="03ea6-112">La carga masiva simplemente se detendrá en el punto donde esto ocurra.</span><span class="sxs-lookup"><span data-stu-id="03ea6-112">Bulk Load will simply stop at the point where it is when this happens.</span></span> <span data-ttu-id="03ea6-113">El modo transaccional puede utilizarse para mitigar este problema.</span><span class="sxs-lookup"><span data-stu-id="03ea6-113">Transactional mode can be used to alleviate this issue.</span></span>  
  
-   <span data-ttu-id="03ea6-114">Cuando se producen errores de carga masiva, éstos pueden incluir información sobre la base de datos.</span><span class="sxs-lookup"><span data-stu-id="03ea6-114">When Bulk Load errors occur, they may include information about the database.</span></span> <span data-ttu-id="03ea6-115">Por ejemplo, pueden incluir el nombre de una tabla o columna o información del tipo de columna.</span><span class="sxs-lookup"><span data-stu-id="03ea6-115">For example, they may include the name of a table or column, or column type information.</span></span> <span data-ttu-id="03ea6-116">Cuando utilice la carga masiva, debe tener cuidado de detectar los errores que se produzcan durante el proceso de carga masiva y devolver un mensaje de error genérico, en lugar de exponer los errores directamente a los usuarios.</span><span class="sxs-lookup"><span data-stu-id="03ea6-116">When you use Bulk Load, you should take care to catch errors from the Bulk Load process and return a generic error message, rather than exposing errors directly to users.</span></span>  
  
-   <span data-ttu-id="03ea6-117">La carga masiva no establece ningún límite en la cantidad de datos con los que puede trabajar.</span><span class="sxs-lookup"><span data-stu-id="03ea6-117">Bulk Load sets no limit on the amount of data it works over.</span></span> <span data-ttu-id="03ea6-118">La carga masiva no realiza ninguna comprobación de tamaño de los datos que va a cargarse.</span><span class="sxs-lookup"><span data-stu-id="03ea6-118">Bulk Load does not do any checking on the size of the data to be loaded.</span></span> <span data-ttu-id="03ea6-119">Es responsabilidad del usuario que ejecuta la carga masiva asegurarse de que hay suficiente memoria como para procesar el archivo especificado y suficiente espacio en la base de datos como para almacenar los datos que están cargándose.</span><span class="sxs-lookup"><span data-stu-id="03ea6-119">It is the responsibility of the user executing Bulk Load to ensure that there is enough memory to process the specified file, and that there is enough room in the database to store the data being loaded.</span></span>  
  
-   <span data-ttu-id="03ea6-120">La carga masiva no intenta usar los datos suministrados como código.</span><span class="sxs-lookup"><span data-stu-id="03ea6-120">Bulk Load does not make an attempt to use the data it is given as code.</span></span> <span data-ttu-id="03ea6-121">Los datos de entrada no se ejecutan nunca de ninguna forma.</span><span class="sxs-lookup"><span data-stu-id="03ea6-121">The data input is never executed in any fashion.</span></span> <span data-ttu-id="03ea6-122">Todo el código o los comando de los datos de entrada se consideran datos normales y no se ejecutan.</span><span class="sxs-lookup"><span data-stu-id="03ea6-122">Any code or commands in the input data are treated as normal data and will not be executed.</span></span>  
  
-   <span data-ttu-id="03ea6-123">La carga masiva puede realizar cambios de formato en los datos proporcionados basándose en las diferencias entre los modelos de datos XML y [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="03ea6-123">Bulk Load may make formatting changes to the given data based on differences between the XML and [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] data models.</span></span> <span data-ttu-id="03ea6-124">Por ejemplo, el formato para especificar una hora es distinto.</span><span class="sxs-lookup"><span data-stu-id="03ea6-124">For example, the format for specifying a time is different.</span></span> <span data-ttu-id="03ea6-125">La carga masiva intentará resolver estas diferencias.</span><span class="sxs-lookup"><span data-stu-id="03ea6-125">Bulk Load will attempt to resolve these differences.</span></span> <span data-ttu-id="03ea6-126">Como resultado, es posible que se pierdan algunos datos de precisión.</span><span class="sxs-lookup"><span data-stu-id="03ea6-126">As a result, some precision information may be lost.</span></span>  
  
-   <span data-ttu-id="03ea6-127">La carga masiva no establece ningún límite en la cantidad de tiempo que tarda en procesar los datos.</span><span class="sxs-lookup"><span data-stu-id="03ea6-127">Bulk Load sets no limit on the amount of time it takes to process the data.</span></span> <span data-ttu-id="03ea6-128">El procesamiento continúa hasta que se completa o hasta que se produce un error.</span><span class="sxs-lookup"><span data-stu-id="03ea6-128">Processing will continue until processing is complete or an error occurs.</span></span>  
  
-   <span data-ttu-id="03ea6-129">La carga masiva es capaz de crear y eliminar tablas temporales en la base de datos y necesita permisos para hacerlo.</span><span class="sxs-lookup"><span data-stu-id="03ea6-129">Bulk Load can create and delete temporary tables within the database, and needs permissions to do so.</span></span> <span data-ttu-id="03ea6-130">Se concederán permisos sobre estas tablas al mismo usuario que esté conectándose a la base de datos para el proceso de carga masiva.</span><span class="sxs-lookup"><span data-stu-id="03ea6-130">Permissions to these tables will be given to the same user who is connecting to the database for the Bulk Load process.</span></span>  
  
-   <span data-ttu-id="03ea6-131">La carga masiva puede crear y eliminar los archivos temporales utilizados durante el procesamiento en modo transaccional y necesita permisos para hacerlo.</span><span class="sxs-lookup"><span data-stu-id="03ea6-131">Bulk Load can create and delete temporary files used during transactional mode processing, and needs permissions to do so.</span></span> <span data-ttu-id="03ea6-132">Estos archivos se crean con los mismos permisos que el usuario actual del subproceso dentro del que se ejecuta la carga masiva.</span><span class="sxs-lookup"><span data-stu-id="03ea6-132">These files are created with the same permissions as the current user of the thread within which Bulk Load is running.</span></span>  
  
-   <span data-ttu-id="03ea6-133">Si el usuario establece un archivo de registro de errores para que SQLXML escriba errores en él, cada vez se ejecute la carga masiva, el archivo se sobrescribirá con los datos del último proceso de carga masiva.</span><span class="sxs-lookup"><span data-stu-id="03ea6-133">If the user sets an error Log file for SQLXML to write errors into, then each time Bulk Load is executed the file will be overwritten with data from the last Bulk Load process.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="03ea6-134">Consulte también</span><span class="sxs-lookup"><span data-stu-id="03ea6-134">See Also</span></span>  
 [<span data-ttu-id="03ea6-135">Carga masiva de datos XML &#40;SQLXML 4.0&#41;</span><span class="sxs-lookup"><span data-stu-id="03ea6-135">Performing Bulk Load of XML Data &#40;SQLXML 4.0&#41;</span></span>](../bulk-load-xml/performing-bulk-load-of-xml-data-sqlxml-4-0.md)  
  
  