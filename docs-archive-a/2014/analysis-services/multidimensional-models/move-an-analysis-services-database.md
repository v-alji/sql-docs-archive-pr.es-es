---
title: Traslado de una base de datos Analysis Services | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- moving databases [Anlysis Services]
- moving databases
- operations [Analysis Services - multidimensional data]
ms.assetid: fa644e5d-e276-445e-98d9-673afcfb83fe
author: minewiskan
ms.author: owend
ms.openlocfilehash: bd9b099ad6765d9caccb9b0af6622eb4aa77d38c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87749513"
---
# <a name="move-an-analysis-services-database"></a><span data-ttu-id="d88e4-102">Mover una base de datos de Analysis Services</span><span class="sxs-lookup"><span data-stu-id="d88e4-102">Move an Analysis Services Database</span></span>
  <span data-ttu-id="d88e4-103">Con frecuencia, se producen situaciones en las que un administrador de base de datos de [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] quiere mover una base de datos modelo multidimensional o tabular a otra ubicación.</span><span class="sxs-lookup"><span data-stu-id="d88e4-103">There are often situations when an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database administrator (dba) wants to move a multidimensional or tabular model database to a different location.</span></span> <span data-ttu-id="d88e4-104">Estas situaciones suelen responder a necesidades empresariales, como mover la base de datos a otro disco para mejorar el rendimiento, disponer de más espacio para que la base de datos pueda crecer o actualizar un producto.</span><span class="sxs-lookup"><span data-stu-id="d88e4-104">These situations are often driven by business needs, such as moving the database to a different disk for better performance, gaining room for database growth, or to upgrade a product.</span></span>  
  
 <span data-ttu-id="d88e4-105">Una base de datos se puede mover de muchas maneras.</span><span class="sxs-lookup"><span data-stu-id="d88e4-105">A database can be moved in many ways.</span></span> <span data-ttu-id="d88e4-106">En este documento se describen los siguientes escenarios comunes:</span><span class="sxs-lookup"><span data-stu-id="d88e4-106">This document explains the following common scenarios:</span></span>  
  
-   <span data-ttu-id="d88e4-107">Usar SSMS de forma interactiva</span><span class="sxs-lookup"><span data-stu-id="d88e4-107">Interactively using SSMS</span></span>  
  
-   <span data-ttu-id="d88e4-108">Usar programación a través de AMO</span><span class="sxs-lookup"><span data-stu-id="d88e4-108">Programmatically using AMO</span></span>  
  
-   <span data-ttu-id="d88e4-109">Usar script XMLA</span><span class="sxs-lookup"><span data-stu-id="d88e4-109">By script using XMLA</span></span>  
  
 <span data-ttu-id="d88e4-110">En todos los escenarios se requiere que el usuario tenga acceso a la carpeta de la base de datos y que use un método para mover los archivos al destino final deseado.</span><span class="sxs-lookup"><span data-stu-id="d88e4-110">All scenarios require the user to access the database folder and to use a method for moving the files to the desired final destination.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="d88e4-111">Si se separa una base de datos sin asignarla antes una contraseña, quedará desprotegida.</span><span class="sxs-lookup"><span data-stu-id="d88e4-111">Detaching a database without assigning a password to it leaves the database in an unsecured state.</span></span> <span data-ttu-id="d88e4-112">Se recomienda asignar una contraseña a la base de datos para proteger la información confidencial.</span><span class="sxs-lookup"><span data-stu-id="d88e4-112">We recommend assigning a password to the database to protect confidential information.</span></span> <span data-ttu-id="d88e4-113">Además, se deberá aplicar la seguridad de acceso correspondiente a la carpeta, las subcarpetas y los archivos de la base de datos para impedir el acceso no autorizado.</span><span class="sxs-lookup"><span data-stu-id="d88e4-113">Also, the corresponding access security should be applied to the database folder, sub-folders, and files to prevent unauthorized access to them.</span></span>  
  
## <a name="procedures"></a><span data-ttu-id="d88e4-114">Procedimientos</span><span class="sxs-lookup"><span data-stu-id="d88e4-114">Procedures</span></span>  
  
#### <a name="moving-a-database-interactively-using-ssms"></a><span data-ttu-id="d88e4-115">Mover una base de datos interactivamente mediante SSMS</span><span class="sxs-lookup"><span data-stu-id="d88e4-115">Moving a database interactively using SSMS</span></span>  
  
1.  <span data-ttu-id="d88e4-116">Localice la base de datos que desea mover en el panel izquierdo o derecho de SSMS.</span><span class="sxs-lookup"><span data-stu-id="d88e4-116">Locate the database to be moved in the left or right pane of SSMS.</span></span>  
  
2.  <span data-ttu-id="d88e4-117">Haga clic con el botón derecho en la base de datos y seleccione **desasociar..** .</span><span class="sxs-lookup"><span data-stu-id="d88e4-117">Right-click on the database and select **Detach...**</span></span>  
  
3.  <span data-ttu-id="d88e4-118">Asigne una contraseña a la base de datos que se va separar y, a continuación, haga clic en **Aceptar** para ejecutar el comando Detach.</span><span class="sxs-lookup"><span data-stu-id="d88e4-118">Assign a password to the database to be detached, then click **OK** to execute the detach command.</span></span>  
  
4.  <span data-ttu-id="d88e4-119">Use cualquier mecanismo del sistema operativo o el método que emplee normalmente para mover archivos con objeto de mover la carpeta de la base de datos a la nueva ubicación.</span><span class="sxs-lookup"><span data-stu-id="d88e4-119">Use any operating system mechanism or your standard method for moving files to move the database folder to the new location.</span></span>  
  
5.  <span data-ttu-id="d88e4-120">Localice la carpeta **Bases de datos** en el panel izquierdo o derecho de SSMS.</span><span class="sxs-lookup"><span data-stu-id="d88e4-120">Locate the **Databases** folder in the left or right pane of SSMS.</span></span>  
  
6.  <span data-ttu-id="d88e4-121">Haga clic con el botón derecho en la carpeta **bases** de **datos y seleccione adjuntar..** .</span><span class="sxs-lookup"><span data-stu-id="d88e4-121">Right-click on the **Databases** folder and select **Attach...**</span></span>  
  
7.  <span data-ttu-id="d88e4-122">En el cuadro de texto **Carpeta** , escriba la nueva ubicación de la carpeta de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="d88e4-122">In the **folder** text box, type the new location of the database folder.</span></span> <span data-ttu-id="d88e4-123">Como alternativa, puede usar el botón Examinar (**...**) para buscar la carpeta de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="d88e4-123">Alternatively, you can use the browse button (**...**) to locate the database folder.</span></span>  
  
8.  <span data-ttu-id="d88e4-124">Seleccione el `ReadWrite` modo de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="d88e4-124">Select the `ReadWrite` mode for the database.</span></span>  
  
9. <span data-ttu-id="d88e4-125">Escriba la contraseña que se usó en el paso 3 y haga clic en **Aceptar** para ejecutar el comando Attach.</span><span class="sxs-lookup"><span data-stu-id="d88e4-125">Type the password used in step 3 and click **OK** to execute the attach command.</span></span>  
  
#### <a name="moving-a-database-programmatically-using-amo"></a><span data-ttu-id="d88e4-126">Mover una base de datos mediante programación a través de AMO</span><span class="sxs-lookup"><span data-stu-id="d88e4-126">Moving a database programmatically using AMO</span></span>  
  
1.  <span data-ttu-id="d88e4-127">En la aplicación C#, adapte el código de ejemplo siguiente y complete las tareas indicadas.</span><span class="sxs-lookup"><span data-stu-id="d88e4-127">In your C# application, adapt the following sample code and complete the indicated tasks.</span></span>  
  
 `private void MoveDb(Server server, string dbName,`  
  
 `string dbInitialLocation, string dbFinalLocation,`  
  
 `string dbPassword, ReadWriteMode dbReadWriteMode)`  
  
 `{`  
  
 `//Verify dbInitialLocation exists before continuing`  
  
 `if (server.Databases.ContainsName(dbName))`  
  
 `{`  
  
 `Database db;`  
  
 `//Save current cursor and change cursor to Cursors.WaitCursor`  
  
 `db = server.Databases[dbName];`  
  
 `db.Detach(dbPassword);`  
  
 `//Add your own code to copy the database files to the destination where you intend to attach the database`  
  
 `//Verify dbFinalLocation exists before continuing`  
  
 `server.Attach(dbFinalLocation, dbReadWriteMode, dbPassword);`  
  
 `//Restore cursor to its original`  
  
 `}`  
  
 `}`  
  
1.  <span data-ttu-id="d88e4-128">En la aplicación C#, invoque `MoveDb()` con los parámetros necesarios.</span><span class="sxs-lookup"><span data-stu-id="d88e4-128">In your C# application, invoke `MoveDb()` with the necessary parameters.</span></span>  
  
2.  <span data-ttu-id="d88e4-129">Compile y ejecute el código para mover la base de datos.</span><span class="sxs-lookup"><span data-stu-id="d88e4-129">Compile and execute your code to move the database.</span></span>  
  
#### <a name="moving-a-database-by-script-using-xmla"></a><span data-ttu-id="d88e4-130">Mover una base de datos mediante script XMLA</span><span class="sxs-lookup"><span data-stu-id="d88e4-130">Moving a database by script using XMLA</span></span>  
  
1.  <span data-ttu-id="d88e4-131">Abra una nueva pestaña XMLA en SSMS.</span><span class="sxs-lookup"><span data-stu-id="d88e4-131">Open a new XMLA tab in SSMS.</span></span>  
  
2.  <span data-ttu-id="d88e4-132">Copie la plantilla de script siguiente para XMLA</span><span class="sxs-lookup"><span data-stu-id="d88e4-132">Copy the following script template for XMLA</span></span>  
  
 `<Detach xmlns="https://schemas.microsoft.com/analysisservices/2003/engine">`  
  
 `<Object>`  
  
 `<DatabaseID>%dbName%</DatabaseID>`  
  
 `<Password>%password%</Password>`  
  
 `</Object>`  
  
 `</Detach>`  
  
1.  <span data-ttu-id="d88e4-133">Reemplace `%dbName%` por el nombre de la base de datos y `%password%` por la contraseña.</span><span class="sxs-lookup"><span data-stu-id="d88e4-133">Replace `%dbName%` with the name of the database and `%password%` with the password.</span></span> <span data-ttu-id="d88e4-134">Los caracteres % forman parte de la plantilla y se deben quitar.</span><span class="sxs-lookup"><span data-stu-id="d88e4-134">The % characters are part of the template and must be removed.</span></span>  
  
2.  <span data-ttu-id="d88e4-135">Ejecute el comando XMLA.</span><span class="sxs-lookup"><span data-stu-id="d88e4-135">Execute the XMLA command.</span></span>  
  
3.  <span data-ttu-id="d88e4-136">Use cualquier mecanismo del sistema operativo o el método que emplee normalmente para mover archivos con objeto de mover la carpeta de la base de datos a la nueva ubicación.</span><span class="sxs-lookup"><span data-stu-id="d88e4-136">Use any operating system mechanism or your standard method for moving files to move the database folder to the new location.</span></span>  
  
4.  <span data-ttu-id="d88e4-137">Copie la plantilla de script siguiente para XMLA en una nueva pestaña XMLA</span><span class="sxs-lookup"><span data-stu-id="d88e4-137">Copy the following script template for XMLA in a new XMLA tab</span></span>  
  
 `<Attach xmlns="https://schemas.microsoft.com/analysisservices/2003/engine">`  
  
 `<Folder>%dbFolder%</Folder>`  
  
 `<ReadWriteMode xmlns="https://schemas.microsoft.com/analysisservices/2008/engine/100">%ReadOnlyMode%</ReadWriteMode>`  
  
 `</Attach>`  
  
1.  <span data-ttu-id="d88e4-138">Reemplace `%dbFolder%` por la ruta UNC completa de la carpeta de la base de datos, `%ReadOnlyMode%` por el valor `ReadOnly` o `ReadWrite` correspondiente, y `%password%` por la contraseña.</span><span class="sxs-lookup"><span data-stu-id="d88e4-138">Replace `%dbFolder%` with the complete UNC path of the database folder, `%ReadOnlyMode%` with the corresponding value `ReadOnly` or `ReadWrite`, and `%password%` with the password.</span></span> <span data-ttu-id="d88e4-139">Los caracteres % forman parte de la plantilla y se deben quitar.</span><span class="sxs-lookup"><span data-stu-id="d88e4-139">The % characters are part of the template and must be removed.</span></span>  
  
2.  <span data-ttu-id="d88e4-140">Ejecute el comando XMLA.</span><span class="sxs-lookup"><span data-stu-id="d88e4-140">Execute the XMLA command.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d88e4-141">Consulte también</span><span class="sxs-lookup"><span data-stu-id="d88e4-141">See Also</span></span>  
 <xref:Microsoft.AnalysisServices.Server.Attach%2A>   
 <span data-ttu-id="d88e4-142">[Microsoft. AnalysisServices. Database. Detach \*](/dotnet/api/microsoft.analysisservices.core.database.detach) </span><span class="sxs-lookup"><span data-stu-id="d88e4-142">[Microsoft.AnalysisServices.Database.Detach\*](/dotnet/api/microsoft.analysisservices.core.database.detach) </span></span>  
 <span data-ttu-id="d88e4-143">[Adjuntar y separar bases de datos de Analysis Services](attach-and-detach-analysis-services-databases.md) </span><span class="sxs-lookup"><span data-stu-id="d88e4-143">[Attach and Detach Analysis Services Databases](attach-and-detach-analysis-services-databases.md) </span></span>  
 <span data-ttu-id="d88e4-144">[Ubicación de almacenamiento de base de datos](database-storage-location.md) </span><span class="sxs-lookup"><span data-stu-id="d88e4-144">[Database Storage Location](database-storage-location.md) </span></span>  
 <span data-ttu-id="d88e4-145">[Base de datos Readwritemode](database-readwritemodes.md) </span><span class="sxs-lookup"><span data-stu-id="d88e4-145">[Database ReadWriteModes](database-readwritemodes.md) </span></span>  
 <span data-ttu-id="d88e4-146">[Elemento Attach](https://docs.microsoft.com/bi-reference/xmla/xml-elements-commands/attach-element) </span><span class="sxs-lookup"><span data-stu-id="d88e4-146">[Attach Element](https://docs.microsoft.com/bi-reference/xmla/xml-elements-commands/attach-element) </span></span>  
 <span data-ttu-id="d88e4-147">[Elemento detach](https://docs.microsoft.com/bi-reference/xmla/xml-elements-commands/detach-element) </span><span class="sxs-lookup"><span data-stu-id="d88e4-147">[Detach Element](https://docs.microsoft.com/bi-reference/xmla/xml-elements-commands/detach-element) </span></span>  
 <span data-ttu-id="d88e4-148">[Elemento ReadWriteMode](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/readwritemode-element) </span><span class="sxs-lookup"><span data-stu-id="d88e4-148">[ReadWriteMode Element](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/readwritemode-element) </span></span>  
 [<span data-ttu-id="d88e4-149">Elemento DbStorageLocation</span><span class="sxs-lookup"><span data-stu-id="d88e4-149">DbStorageLocation Element</span></span>](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/dbstoragelocation-element)  
  
  
