---
title: Realizar una carga masiva de datos mediante el destino de SQL Server | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- SQL Server destination
- loading data
- destinations [Integration Services], SQL Server
- inserting data
- bulk load [Integration Services]
ms.assetid: 8f982f85-a82e-4e2d-9cd8-cd2f85402d8e
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 92ed530ae849f7a4ce123cded421ac0cd0c411ee
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87672212"
---
# <a name="bulk-load-data-by-using-the-sql-server-destination"></a><span data-ttu-id="8fbe2-102">Realizar una carga masiva de datos mediante el destino de SQL Server</span><span class="sxs-lookup"><span data-stu-id="8fbe2-102">Bulk Load Data by Using the SQL Server Destination</span></span>
  <span data-ttu-id="8fbe2-103">Para agregar y configurar un destino de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , el paquete ya debe incluir por lo menos una tarea Flujo de datos y un origen de datos.</span><span class="sxs-lookup"><span data-stu-id="8fbe2-103">To add and configure a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] destination, the package must already include at least one Data Flow task and a data source.</span></span>  
  
### <a name="to-load-data-using-a-sql-server-destination"></a><span data-ttu-id="8fbe2-104">Para cargar datos mediante un destino de SQL Server</span><span class="sxs-lookup"><span data-stu-id="8fbe2-104">To load data using a SQL Server destination</span></span>  
  
1.  <span data-ttu-id="8fbe2-105">En [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], abra el proyecto de [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] que contiene el paquete que desea.</span><span class="sxs-lookup"><span data-stu-id="8fbe2-105">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] project that contains the package you want.</span></span>  
  
2.  <span data-ttu-id="8fbe2-106">En el Explorador de soluciones, haga doble clic en el paquete para abrirlo.</span><span class="sxs-lookup"><span data-stu-id="8fbe2-106">In Solution Explorer, double-click the package to open it.</span></span>  
  
3.  <span data-ttu-id="8fbe2-107">Haga clic en la pestaña **Flujo de datos** y, a continuación, desde el **cuadro de herramientas**, arrastre el destino de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] a la superficie de diseño.</span><span class="sxs-lookup"><span data-stu-id="8fbe2-107">Click the **Data Flow** tab, and then, from the **Toolbox**, drag the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] destination to the design surface.</span></span>  
  
4.  <span data-ttu-id="8fbe2-108">Conecte el destino a un origen o a una transformación previa en el flujo de datos arrastrando un conector al destino.</span><span class="sxs-lookup"><span data-stu-id="8fbe2-108">Connect the destination to a source or a previous transformation in the data flow by dragging a connector to the destination.</span></span>  
  
5.  <span data-ttu-id="8fbe2-109">Haga doble clic en el destino.</span><span class="sxs-lookup"><span data-stu-id="8fbe2-109">Double-click the destination.</span></span>  
  
6.  <span data-ttu-id="8fbe2-110">En el **Editor de destino de SQL Server**, en la página del **Administrador de conexiones** , seleccione un administrador de conexiones OLE DB o haga clic en **Nuevo** para crear un nuevo administrador de conexiones.</span><span class="sxs-lookup"><span data-stu-id="8fbe2-110">In the **SQL Server Destination Editor**, on the **Connection Manager** page, select an existing OLE DB connection manager or click **New** to create a new connection manager.</span></span> <span data-ttu-id="8fbe2-111">Para más información, consulte [OLE DB Connection Manager](../connection-manager/ole-db-connection-manager.md).</span><span class="sxs-lookup"><span data-stu-id="8fbe2-111">For more information, see [OLE DB Connection Manager](../connection-manager/ole-db-connection-manager.md).</span></span>  
  
7.  <span data-ttu-id="8fbe2-112">Para especificar la tabla o vista en la que desea cargar los datos, realice una de las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="8fbe2-112">To specify the table or view into which to load the data, do one of the following:</span></span>  
  
    -   <span data-ttu-id="8fbe2-113">Seleccione una tabla o vista existente.</span><span class="sxs-lookup"><span data-stu-id="8fbe2-113">Select an existing table or view.</span></span>  
  
    -   <span data-ttu-id="8fbe2-114">Haga clic en **Nuevo**y, en el cuadro de diálogo **Crear tabla** , escriba una instrucción SQL que cree una tabla o vista.</span><span class="sxs-lookup"><span data-stu-id="8fbe2-114">Click **New**, and in the **Create Table** dialog boxwrite an SQL statement that creates a table or view.</span></span>  
  
        > [!NOTE]  
        >  [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] <span data-ttu-id="8fbe2-115">genera una instrucción CREATE TABLE predeterminada basada en el origen de datos conectado.</span><span class="sxs-lookup"><span data-stu-id="8fbe2-115">generates a default CREATE TABLE statement based on the connected data source.</span></span> <span data-ttu-id="8fbe2-116">La instrucción predeterminada CREATE TABLE no incluirá el atributo FILESTREAM, aunque la tabla de origen tenga una columna con el atributo FILESTREAM declarado.</span><span class="sxs-lookup"><span data-stu-id="8fbe2-116">This default CREATE TABLE statement will not include the FILESTREAM attribute even if the source table includes a column with the FILESTREAM attribute declared.</span></span> <span data-ttu-id="8fbe2-117">Para ejecutar un componente [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] con el atributo FILESTREAM, implemente en primer lugar el almacenamiento de FILESTREAM en la base de datos de destino.</span><span class="sxs-lookup"><span data-stu-id="8fbe2-117">To run an [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] component with the FILESTREAM attribute, first implement FILESTREAM storage on the destination database.</span></span> <span data-ttu-id="8fbe2-118">A continuación, agregue el atributo FILESTREAM a la instrucción CREATE TABLE en el cuadro de diálogo **Crear tabla** .</span><span class="sxs-lookup"><span data-stu-id="8fbe2-118">Then, add the FILESTREAM attribute to the CREATE TABLE statement in the **Create Table** dialog box.</span></span> <span data-ttu-id="8fbe2-119">Para más información, vea [Datos de objeto binario grande &#40;Blob&#41; &#40;SQL Server&#41;](../../relational-databases/blob/binary-large-object-blob-data-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="8fbe2-119">For more information, see [Binary Large Object &#40;Blob&#41; Data &#40;SQL Server&#41;](../../relational-databases/blob/binary-large-object-blob-data-sql-server.md).</span></span>  
  
8.  <span data-ttu-id="8fbe2-120">Haga clic en **Asignaciones** y asigne columnas de la lista **Columnas de entrada disponibles** a columnas en la lista **Columnas de destino disponibles** arrastrando columnas de una lista a otra.</span><span class="sxs-lookup"><span data-stu-id="8fbe2-120">Click **Mappings** and map columns from the **Available Input Columns** list to columns in the **Available Destination Columns** list by dragging columns from one list to another.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="8fbe2-121">El destino asigna automáticamente las columnas con el mismo nombre.</span><span class="sxs-lookup"><span data-stu-id="8fbe2-121">The destination automatically maps same-named columns.</span></span>  
  
9. <span data-ttu-id="8fbe2-122">Haga clic en **Avanzadas** y establezca las opciones de carga masiva: **Mantener valores de identidad**, **Mantener valores NULL**, **Bloqueo de tabla**, **Comprobar restricciones**y **Activar desencadenadores**.</span><span class="sxs-lookup"><span data-stu-id="8fbe2-122">Click **Advanced** and set the bulk load options: **Keep identity**, **Keep nulls**, **Table lock**, **Check constraints**, and **Fire triggers**.</span></span>  
  
     <span data-ttu-id="8fbe2-123">Opcionalmente, especifique la primera y última fila de entrada que desea insertar, la cantidad máxima de errores que pueden producirse antes de que se detenga la operación de inserción y las columnas en las que se ordena la inserción.</span><span class="sxs-lookup"><span data-stu-id="8fbe2-123">Optionally, specify the first and last input rows to insert, the maximum number of errors that can occur before the insert operation stops, and the columns on which the insert is sorted.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="8fbe2-124">El orden es determinado por el orden en que se enumeran las columnas.</span><span class="sxs-lookup"><span data-stu-id="8fbe2-124">The sort order is determined by the order in which the columns are listed.</span></span>  
  
10. <span data-ttu-id="8fbe2-125">Haga clic en **OK**.</span><span class="sxs-lookup"><span data-stu-id="8fbe2-125">Click **OK**.</span></span>  
  
11. <span data-ttu-id="8fbe2-126">Para guardar el paquete actualizado, haga clic en **Guardar los elementos seleccionados**, en el menú **Archivo**.</span><span class="sxs-lookup"><span data-stu-id="8fbe2-126">To save the updated package, click **Save Selected Items** on the **File** menu.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8fbe2-127">Consulte también</span><span class="sxs-lookup"><span data-stu-id="8fbe2-127">See Also</span></span>  
 <span data-ttu-id="8fbe2-128">[SQL Server Destination](sql-server-destination.md) </span><span class="sxs-lookup"><span data-stu-id="8fbe2-128">[SQL Server Destination](sql-server-destination.md) </span></span>  
 <span data-ttu-id="8fbe2-129">[Transformaciones de Integration Services](transformations/integration-services-transformations.md) </span><span class="sxs-lookup"><span data-stu-id="8fbe2-129">[Integration Services Transformations](transformations/integration-services-transformations.md) </span></span>  
 <span data-ttu-id="8fbe2-130">[Rutas de Integration Services](integration-services-paths.md) </span><span class="sxs-lookup"><span data-stu-id="8fbe2-130">[Integration Services Paths](integration-services-paths.md) </span></span>  
 [<span data-ttu-id="8fbe2-131">Tarea Flujo de datos</span><span class="sxs-lookup"><span data-stu-id="8fbe2-131">Data Flow Task</span></span>](../control-flow/data-flow-task.md)  
  
  
