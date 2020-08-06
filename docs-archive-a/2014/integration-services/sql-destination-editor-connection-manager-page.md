---
title: Editor de destino de SQL (página Administrador de conexiones) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.sqlserverdestadapter.connection.f1
helpviewer_keywords:
- SQL Server Destination Editor
ms.assetid: 423e1654-54af-47c6-ab6f-98670534557d
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 4f3a552968cb297de337e1f0c406b444d95dc5a6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87671589"
---
# <a name="sql-destination-editor-connection-manager-page"></a><span data-ttu-id="24940-102">Editor de destino de SQL (página Administrador de conexiones)</span><span class="sxs-lookup"><span data-stu-id="24940-102">SQL Destination Editor (Connection Manager Page)</span></span>
  <span data-ttu-id="24940-103">Utilice la página **Administrador de conexiones** del cuadro de diálogo **Editor de destino de SQL** para especificar la información de orígenes de datos y para obtener una vista previa de los resultados.</span><span class="sxs-lookup"><span data-stu-id="24940-103">Use the **Connection Manager** page of the **SQL Destination Editor** dialog box to specify data source information, and to preview the results.</span></span> <span data-ttu-id="24940-104">El [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] destino carga los datos en tablas o vistas en una base de datos [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="24940-104">The [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] destination loads data into tables or views in a [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] database.</span></span>  
  
 <span data-ttu-id="24940-105">Para obtener más información acerca del destino de SQL Server, vea [SQL Server Destination](data-flow/sql-server-destination.md).</span><span class="sxs-lookup"><span data-stu-id="24940-105">To learn more about the SQL Server destination, see [SQL Server Destination](data-flow/sql-server-destination.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="24940-106">Opciones</span><span class="sxs-lookup"><span data-stu-id="24940-106">Options</span></span>  
 <span data-ttu-id="24940-107">**Administrador de conexiones OLE DB**</span><span class="sxs-lookup"><span data-stu-id="24940-107">**OLE DB connection manager**</span></span>  
 <span data-ttu-id="24940-108">Seleccione una conexión existente de la lista o cree una nueva conexión haciendo clic en **Nueva**.</span><span class="sxs-lookup"><span data-stu-id="24940-108">Select an existing connection from the list, or create a new connection by clicking **New**.</span></span>  
  
 <span data-ttu-id="24940-109">**Nuevo**</span><span class="sxs-lookup"><span data-stu-id="24940-109">**New**</span></span>  
 <span data-ttu-id="24940-110">Cree una conexión mediante el cuadro de diálogo **Configurar el administrador de conexiones OLE DB** .</span><span class="sxs-lookup"><span data-stu-id="24940-110">Create a new connection by using the **Configure OLE DB Connection Manager** dialog box.</span></span>  
  
 <span data-ttu-id="24940-111">**Usar una tabla o una vista**</span><span class="sxs-lookup"><span data-stu-id="24940-111">**Use a table or view**</span></span>  
 <span data-ttu-id="24940-112">Seleccione una tabla o vista existente de la lista, o cree una nueva conexión haciendo clic en **Nueva**.</span><span class="sxs-lookup"><span data-stu-id="24940-112">Select an existing table or view from the list, or create a new connection by clicking **New**.</span></span>  
  
 <span data-ttu-id="24940-113">**Nuevo**</span><span class="sxs-lookup"><span data-stu-id="24940-113">**New**</span></span>  
 <span data-ttu-id="24940-114">Permite crear una tabla con el cuadro de diálogo **Crear tabla** .</span><span class="sxs-lookup"><span data-stu-id="24940-114">Create a new table by using the **Create Table** dialog box.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="24940-115">Al hacer clic en **Nueva**, [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] genera una instrucción predeterminada CREATE TABLE basada en el origen de datos conectado.</span><span class="sxs-lookup"><span data-stu-id="24940-115">When you click **New**, [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] generates a default CREATE TABLE statement based on the connected data source.</span></span> <span data-ttu-id="24940-116">La instrucción predeterminada CREATE TABLE no incluirá el atributo FILESTREAM, aunque la tabla de origen tenga una columna con el atributo FILESTREAM declarado.</span><span class="sxs-lookup"><span data-stu-id="24940-116">This default CREATE TABLE statement will not include the FILESTREAM attribute even if the source table includes a column with the FILESTREAM attribute declared.</span></span> <span data-ttu-id="24940-117">Para ejecutar un componente [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] con el atributo FILESTREAM, implemente en primer lugar el almacenamiento de FILESTREAM en la base de datos de destino.</span><span class="sxs-lookup"><span data-stu-id="24940-117">To run an [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] component with the FILESTREAM attribute, first implement FILESTREAM storage on the destination database.</span></span> <span data-ttu-id="24940-118">A continuación, agregue el atributo FILESTREAM a la instrucción CREATE TABLE en el cuadro de diálogo **Crear tabla** .</span><span class="sxs-lookup"><span data-stu-id="24940-118">Then, add the FILESTREAM attribute to the CREATE TABLE statement in the **Create Table** dialog box.</span></span> <span data-ttu-id="24940-119">Para más información, vea [Datos de objeto binario grande &#40;Blob&#41; &#40;SQL Server&#41;](../relational-databases/blob/binary-large-object-blob-data-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="24940-119">For more information, see [Binary Large Object &#40;Blob&#41; Data &#40;SQL Server&#41;](../relational-databases/blob/binary-large-object-blob-data-sql-server.md).</span></span>  
  
 <span data-ttu-id="24940-120">**Versión preliminar**</span><span class="sxs-lookup"><span data-stu-id="24940-120">**Preview**</span></span>  
 <span data-ttu-id="24940-121">Obtenga una vista previa de los resultados mediante el cuadro de diálogo **Vista previa de los resultados de la consulta** .</span><span class="sxs-lookup"><span data-stu-id="24940-121">Preview results by using the **Preview Query Results** dialog box.</span></span> <span data-ttu-id="24940-122">La vista previa puede mostrar hasta 200 filas.</span><span class="sxs-lookup"><span data-stu-id="24940-122">Preview can display up to 200 rows.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="24940-123">Consulte también</span><span class="sxs-lookup"><span data-stu-id="24940-123">See Also</span></span>  
 <span data-ttu-id="24940-124">[Referencia de errores y mensajes de Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="24940-124">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="24940-125">[&#40;página asignaciones del editor de destino de SQL&#41;](../../2014/integration-services/sql-destination-editor-mappings-page.md) </span><span class="sxs-lookup"><span data-stu-id="24940-125">[SQL Destination Editor &#40;Mappings Page&#41;](../../2014/integration-services/sql-destination-editor-mappings-page.md) </span></span>  
 <span data-ttu-id="24940-126">[Editor de destino de SQL &#40;página avanzadas&#41;](../../2014/integration-services/sql-destination-editor-advanced-page.md) </span><span class="sxs-lookup"><span data-stu-id="24940-126">[SQL Destination Editor &#40;Advanced Page&#41;](../../2014/integration-services/sql-destination-editor-advanced-page.md) </span></span>  
 [<span data-ttu-id="24940-127">Realizar una carga masiva de datos mediante el destino de SQL Server</span><span class="sxs-lookup"><span data-stu-id="24940-127">Bulk Load Data by Using the SQL Server Destination</span></span>](data-flow/bulk-load-data-by-using-the-sql-server-destination.md)  
  
  
