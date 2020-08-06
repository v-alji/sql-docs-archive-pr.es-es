---
title: Cambiar una base de datos de Analysis Services entre los modos ReadOnly y ReadWrite | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- ReadOnly property
- ReadWriteMode command
- operations [Analysis Services - multidimensional data]
ms.assetid: 4eff8181-08dd-4fad-b091-d400fc21a020
author: minewiskan
ms.author: owend
ms.openlocfilehash: 757aedd985d969f932deacf5599716078021a1af
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87743653"
---
# <a name="switch-an-analysis-services-database-between-readonly-and-readwrite-modes"></a><span data-ttu-id="6661f-102">Cambiar entre los modos ReadOnly y ReadWrite en una base de datos de Analysis Services</span><span class="sxs-lookup"><span data-stu-id="6661f-102">Switch an Analysis Services database between ReadOnly and ReadWrite modes</span></span>
  <span data-ttu-id="6661f-103">Con frecuencia se producen situaciones en las que un administrador de bases de datos (dba) de [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] quiere cambiar el modo de lectura/escritura de una base de datos tabular o multidimensional.</span><span class="sxs-lookup"><span data-stu-id="6661f-103">There are often situations when a [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database administrator (dba) wants to change the read/write mode of a tabular or multidimensional database.</span></span> <span data-ttu-id="6661f-104">Estas situaciones suelen responder a necesidades empresariales, como compartir la base de datos entre un grupo de servidores de [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] para proporcionar una mejor experiencia para el usuario.</span><span class="sxs-lookup"><span data-stu-id="6661f-104">These situations are often driven by business needs, such as sharing the database among a pool of [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] servers for a better user experience.</span></span>  
  
 <span data-ttu-id="6661f-105">El modo de una base de datos se puede cambiar de muchas formas.</span><span class="sxs-lookup"><span data-stu-id="6661f-105">A database mode can be switched in many ways.</span></span> <span data-ttu-id="6661f-106">En este documento se describen los siguientes escenarios comunes:</span><span class="sxs-lookup"><span data-stu-id="6661f-106">This document explains the following common scenarios:</span></span>  
  
-   <span data-ttu-id="6661f-107">Usar [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6661f-107">Interactively using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]</span></span>  
  
-   <span data-ttu-id="6661f-108">Usar programación a través de AMO</span><span class="sxs-lookup"><span data-stu-id="6661f-108">Programmatically using AMO</span></span>  
  
-   <span data-ttu-id="6661f-109">Usar script XMLA</span><span class="sxs-lookup"><span data-stu-id="6661f-109">By script using XMLA</span></span>  
  
## <a name="procedures"></a><span data-ttu-id="6661f-110">Procedimientos</span><span class="sxs-lookup"><span data-stu-id="6661f-110">Procedures</span></span>  
  
#### <a name="to-switch-the-readwrite-mode-of-a-database-interactively-using-management-studio"></a><span data-ttu-id="6661f-111">Para cambiar el modo de lectura/escritura de una base de datos de forma interactiva mediante Management Studio</span><span class="sxs-lookup"><span data-stu-id="6661f-111">To switch the read/write mode of a database interactively using Management Studio</span></span>  
  
1.  <span data-ttu-id="6661f-112">Localice la base de datos en el panel izquierdo o derecho de [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6661f-112">Locate the database to be switched in the left or right pane of [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)].</span></span>  
  
2.  <span data-ttu-id="6661f-113">Haga clic con el botón secundario en la base de datos y seleccione **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="6661f-113">Right-click the database and select **Properties**.</span></span> <span data-ttu-id="6661f-114">Busque la carpeta de la base de datos y anote su ubicación.</span><span class="sxs-lookup"><span data-stu-id="6661f-114">Find the database folder and note the location.</span></span> <span data-ttu-id="6661f-115">Una ubicación de almacenamiento de la base de datos vacía indica que la carpeta de la base de datos está ubicada en la carpeta de datos del servidor.</span><span class="sxs-lookup"><span data-stu-id="6661f-115">An empty database storage location indicates that the database folder is located in the server data folder.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="6661f-116">En cuanto se separa la base de datos, [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] ya no puede ayudarle a obtener su ubicación.</span><span class="sxs-lookup"><span data-stu-id="6661f-116">As soon as the database is detached, [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] can no longer help you obtain the database location.</span></span>  
  
3.  <span data-ttu-id="6661f-117">Haga clic con el botón derecho en la base de datos y seleccione **desasociar..** .</span><span class="sxs-lookup"><span data-stu-id="6661f-117">Right-click the database and select **Detach...**</span></span>  
  
4.  <span data-ttu-id="6661f-118">Asigne una contraseña a la base de datos que se va separar y, a continuación, haga clic en **Aceptar** para ejecutar el comando Detach.</span><span class="sxs-lookup"><span data-stu-id="6661f-118">Assign a password to the database to be detached, and then click **OK** to execute the detach command.</span></span>  
  
5.  <span data-ttu-id="6661f-119">Busque la carpeta **bases de datos** en el panel izquierdo o derecho de [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="6661f-119">Locate the **Databases** folder in the left or right pane of [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)].</span></span>  
  
6.  <span data-ttu-id="6661f-120">Haga clic con el botón secundario en la carpeta **bases** de datos y seleccione **adjuntar..** .</span><span class="sxs-lookup"><span data-stu-id="6661f-120">Right-click the **Databases** folder and select **Attach...**</span></span>  
  
7.  <span data-ttu-id="6661f-121">En el cuadro de texto **Carpeta** , escriba la ubicación original de la carpeta de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="6661f-121">In the **folder** text box, type the original location of the database folder.</span></span> <span data-ttu-id="6661f-122">Como alternativa, puede usar el botón Examinar (**...**) para buscar la carpeta de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="6661f-122">Alternatively, you can use the browse button (**...**) to locate the database folder.</span></span>  
  
8.  <span data-ttu-id="6661f-123">Seleccione el modo de lectura/escritura para la base de datos.</span><span class="sxs-lookup"><span data-stu-id="6661f-123">Select the read/write mode for the database.</span></span>  
  
9. <span data-ttu-id="6661f-124">Escriba la contraseña que se usó en el paso 3 y haga clic en **Aceptar** para ejecutar el comando adjuntar.</span><span class="sxs-lookup"><span data-stu-id="6661f-124">Type the password that was used in step 3 and click **OK** to execute the attach command.</span></span>  
  
#### <a name="to-switch-the-readwrite-mode-to-a-database-programmatically-using-amo"></a><span data-ttu-id="6661f-125">Para cambiar el modo de lectura/escritura de una base de datos mediante programación a través de AMO</span><span class="sxs-lookup"><span data-stu-id="6661f-125">To switch the read/write mode to a database programmatically using AMO</span></span>  
  
1.  <span data-ttu-id="6661f-126">En la aplicación C#, adapte el código de ejemplo siguiente y complete las tareas indicadas.</span><span class="sxs-lookup"><span data-stu-id="6661f-126">In your C# application, adapt the following sample code and complete the indicated tasks.</span></span>  
  
 `private void SwitchReadWrite(Server server, string dbName,`  
  
 `ReadWriteMode dbReadWriteMode)`  
  
 `{`  
  
 `if (server.Databases.ContainsName(dbName))`  
  
 `{`  
  
 `Database db;`  
  
 `string databaseLocation;`  
  
 `db = server.Databases[dbName];`  
  
 `databaseLocation = db.DbStorageLocation;`  
  
 `if (databaseLocation == null)`  
  
 `{`  
  
 `string dataDir = server.ServerProperties["DataDir"].Value;`  
  
 `String[] possibleFolders = Directory.GetDirectories(dataDir, string.Concat(dbName,"*"), SearchOption.TopDirectoryOnly);`  
  
 `if (possibleFolders.Length > 1)`  
  
 `{`  
  
 `List<String> sortedFolders = new List<string>(possibleFolders.Length);`  
  
 `sortedFolders.AddRange(possibleFolders);`  
  
 `sortedFolders.Sort();`  
  
 `databaseLocation = sortedFolders[sortedFolders.Count - 1];`  
  
 `}`  
  
 `else`  
  
 `{`  
  
 `databaseLocation = possibleFolders[0];`  
  
 `}`  
  
 `}`  
  
 `db.Detach();`  
  
 `server.Attach(databaseLocation, dbReadWriteMode);`  
  
 `}`  
  
 `}`  
  
1.  <span data-ttu-id="6661f-127">En la aplicación C#, invoque `SwitchReadWrite()` con los parámetros necesarios.</span><span class="sxs-lookup"><span data-stu-id="6661f-127">In your C# application, invoke `SwitchReadWrite()` with the necessary parameters.</span></span>  
  
2.  <span data-ttu-id="6661f-128">Compile y ejecute el código para mover la base de datos.</span><span class="sxs-lookup"><span data-stu-id="6661f-128">Compile and execute your code to move the database.</span></span>  
  
#### <a name="to-switch-the-readwrite-mode-to-a-database-by-script-using-xmla"></a><span data-ttu-id="6661f-129">Para cambiar el modo de lectura/escritura de una base de datos mediante script XMLA</span><span class="sxs-lookup"><span data-stu-id="6661f-129">To switch the read/write mode to a database by script using XMLA</span></span>  
  
1.  <span data-ttu-id="6661f-130">Localice la base de datos en el panel izquierdo o derecho de [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6661f-130">Locate the database to be switched in the left or right pane of [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)].</span></span>  
  
2.  <span data-ttu-id="6661f-131">Haga clic con el botón secundario en la base de datos y seleccione **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="6661f-131">Right-click the database and select **Properties**.</span></span> <span data-ttu-id="6661f-132">Busque la carpeta de la base de datos y anote su ubicación.</span><span class="sxs-lookup"><span data-stu-id="6661f-132">Find the database folder and note the location.</span></span> <span data-ttu-id="6661f-133">Una ubicación de almacenamiento de la base de datos vacía indica que la carpeta de la base de datos está ubicada en la carpeta de datos del servidor.</span><span class="sxs-lookup"><span data-stu-id="6661f-133">An empty database storage location indicates that the database folder is located in the server data folder.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="6661f-134">En cuanto se separa la base de datos, [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] ya no puede ayudarle a obtener su ubicación.</span><span class="sxs-lookup"><span data-stu-id="6661f-134">As soon as the database is detached, [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] can no longer help you obtain the database location.</span></span>  
  
3.  <span data-ttu-id="6661f-135">Abra una nueva pestaña XMLA en [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6661f-135">Open a new XMLA tab in [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)].</span></span>  
  
4.  <span data-ttu-id="6661f-136">Copie la plantilla de script siguiente para XMLA:</span><span class="sxs-lookup"><span data-stu-id="6661f-136">Copy the following script template for XMLA:</span></span>  
  
 `<Detach xmlns="https://schemas.microsoft.com/analysisservices/2003/engine">`  
  
 `<Object>`  
  
 `<DatabaseID>%dbName%</DatabaseID>`  
  
 `<Password>%password%</Password>`  
  
 `</Object>`  
  
 `</Detach>`  
  
1.  <span data-ttu-id="6661f-137">Reemplace `%dbName%` por el nombre de la base de datos y `%password%` por la contraseña.</span><span class="sxs-lookup"><span data-stu-id="6661f-137">Replace `%dbName%` with the name of the database and `%password%` with the password.</span></span> <span data-ttu-id="6661f-138">Los caracteres % forman parte de la plantilla y se deben quitar.</span><span class="sxs-lookup"><span data-stu-id="6661f-138">The % characters are part of the template and must be removed.</span></span>  
  
2.  <span data-ttu-id="6661f-139">Ejecute el comando XMLA.</span><span class="sxs-lookup"><span data-stu-id="6661f-139">Execute the XMLA command.</span></span>  
  
3.  <span data-ttu-id="6661f-140">Copie la plantilla de script siguiente para XMLA en una nueva pestaña XMLA</span><span class="sxs-lookup"><span data-stu-id="6661f-140">Copy the following script template for XMLA in a new XMLA tab</span></span>  
  
 <span data-ttu-id="6661f-141">`<Attach xmlns="https://schemas.microsoft.com/analysisservices/2003` `/engine` `">`</span><span class="sxs-lookup"><span data-stu-id="6661f-141">`<Attach xmlns="https://schemas.microsoft.com/analysisservices/2003` `/engine` `">`</span></span>  
  
 `<Folder>%dbFolder%</Folder>`  
  
 `<ReadWriteMode xmlns="https://schemas.microsoft.com/analysisservices/2008/engine/100">%ReadOnlyMode%</ReadWriteMode>`  
  
 `</Attach>`  
  
1.  <span data-ttu-id="6661f-142">Reemplace `%dbFolder%` por la ruta UNC completa de la carpeta de la base de datos, `%ReadOnlyMode%` por el valor `ReadOnly` o `ReadWrite` correspondiente, y `%password%` por la contraseña.</span><span class="sxs-lookup"><span data-stu-id="6661f-142">Replace `%dbFolder%` with the complete UNC path of the database folder, `%ReadOnlyMode%` with the corresponding value `ReadOnly` or `ReadWrite`, and `%password%` with the password.</span></span> <span data-ttu-id="6661f-143">Los caracteres % forman parte de la plantilla y se deben quitar.</span><span class="sxs-lookup"><span data-stu-id="6661f-143">The % characters are part of the template and must be removed.</span></span>  
  
2.  <span data-ttu-id="6661f-144">Ejecute el comando XMLA.</span><span class="sxs-lookup"><span data-stu-id="6661f-144">Execute the XMLA command.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6661f-145">Consulte también</span><span class="sxs-lookup"><span data-stu-id="6661f-145">See Also</span></span>  
 <xref:Microsoft.AnalysisServices.Server.Attach%2A>   
 <span data-ttu-id="6661f-146">[Microsoft. AnalysisServices. Database. Detach \*](/dotnet/api/microsoft.analysisservices.core.database.detach) </span><span class="sxs-lookup"><span data-stu-id="6661f-146">[Microsoft.AnalysisServices.Database.Detach\*](/dotnet/api/microsoft.analysisservices.core.database.detach) </span></span>  
 <span data-ttu-id="6661f-147">[Adjuntar y separar bases de datos de Analysis Services](attach-and-detach-analysis-services-databases.md) </span><span class="sxs-lookup"><span data-stu-id="6661f-147">[Attach and Detach Analysis Services Databases](attach-and-detach-analysis-services-databases.md) </span></span>  
 <span data-ttu-id="6661f-148">[Ubicación de almacenamiento de base de datos](database-storage-location.md) </span><span class="sxs-lookup"><span data-stu-id="6661f-148">[Database Storage Location](database-storage-location.md) </span></span>  
 <span data-ttu-id="6661f-149">[Base de datos Readwritemode](database-readwritemodes.md) </span><span class="sxs-lookup"><span data-stu-id="6661f-149">[Database ReadWriteModes](database-readwritemodes.md) </span></span>  
 <span data-ttu-id="6661f-150">[Elemento Attach](https://docs.microsoft.com/bi-reference/xmla/xml-elements-commands/attach-element) </span><span class="sxs-lookup"><span data-stu-id="6661f-150">[Attach Element](https://docs.microsoft.com/bi-reference/xmla/xml-elements-commands/attach-element) </span></span>  
 <span data-ttu-id="6661f-151">[Elemento detach](https://docs.microsoft.com/bi-reference/xmla/xml-elements-commands/detach-element) </span><span class="sxs-lookup"><span data-stu-id="6661f-151">[Detach Element](https://docs.microsoft.com/bi-reference/xmla/xml-elements-commands/detach-element) </span></span>  
 <span data-ttu-id="6661f-152">[Elemento ReadWriteMode](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/readwritemode-element) </span><span class="sxs-lookup"><span data-stu-id="6661f-152">[ReadWriteMode Element](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/readwritemode-element) </span></span>  
 [<span data-ttu-id="6661f-153">Elemento DbStorageLocation</span><span class="sxs-lookup"><span data-stu-id="6661f-153">DbStorageLocation Element</span></span>](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/dbstoragelocation-element)  
  
  
