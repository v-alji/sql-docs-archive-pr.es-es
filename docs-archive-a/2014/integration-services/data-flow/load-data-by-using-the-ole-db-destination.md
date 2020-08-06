---
title: Cargar datos mediante el destino de OLE DB | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- loading data
- OLE DB destination [Integration Services]
- destinations [Integration Services], OLE DB
ms.assetid: 78899498-725e-4300-a7af-f983f4ea384b
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 43e8d1123ae91d9e68c00fbe3e05c490383afe0c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87745925"
---
# <a name="load-data-by-using-the-ole-db-destination"></a><span data-ttu-id="4da5a-102">Cargar datos mediante el destino de OLE DB</span><span class="sxs-lookup"><span data-stu-id="4da5a-102">Load Data by Using the OLE DB Destination</span></span>
  <span data-ttu-id="4da5a-103">Para agregar y configurar un destino de OLE DB, el paquete ya debe incluir al menos una tarea Flujo de datos y un origen.</span><span class="sxs-lookup"><span data-stu-id="4da5a-103">To add and configure an OLE DB destination, the package must already include at least one Data Flow task and a source.</span></span>  
  
### <a name="to-load-data-using-an-ole-db-destination"></a><span data-ttu-id="4da5a-104">Para cargar datos mediante un destino de OLE DB</span><span class="sxs-lookup"><span data-stu-id="4da5a-104">To load data using an OLE DB destination</span></span>  
  
1.  <span data-ttu-id="4da5a-105">En [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], abra el proyecto de [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] que contiene el paquete que desea.</span><span class="sxs-lookup"><span data-stu-id="4da5a-105">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] project that contains the package you want.</span></span>  
  
2.  <span data-ttu-id="4da5a-106">En el Explorador de soluciones, haga doble clic en el paquete para abrirlo.</span><span class="sxs-lookup"><span data-stu-id="4da5a-106">In Solution Explorer, double-click the package to open it.</span></span>  
  
3.  <span data-ttu-id="4da5a-107">Haga clic en la pestaña **Flujo de datos** y, a continuación, desde el **cuadro de herramientas**, arrastre el destino de OLE DB a la superficie de diseño.</span><span class="sxs-lookup"><span data-stu-id="4da5a-107">Click the **Data Flow** tab, and then, from the **Toolbox**, drag the OLE DB destination to the design surface.</span></span>  
  
4.  <span data-ttu-id="4da5a-108">Conecte el destino de OLE DB al flujo de datos arrastrando el conector desde un origen de datos o una transformación anterior al destino.</span><span class="sxs-lookup"><span data-stu-id="4da5a-108">Connect the OLE DB destination to the data flow by dragging a connector from a data source or a previous transformation to the destination.</span></span>  
  
5.  <span data-ttu-id="4da5a-109">Haga doble clic en el destino de OLE DB.</span><span class="sxs-lookup"><span data-stu-id="4da5a-109">Double-click the OLE DB destination.</span></span>  
  
6.  <span data-ttu-id="4da5a-110">En el **Editor de destino de OLE DB** , en la página **Administrador de conexiones** , seleccione un administrador de conexiones OLE DB o haga clic en **Nuevo** para crear un nuevo administrador de conexiones.</span><span class="sxs-lookup"><span data-stu-id="4da5a-110">In the **OLE DB Destination Editor** dialog box, on the **Connection Manager** page, select an existing OLE DB connection manager or click **New** to create a new connection manager.</span></span> <span data-ttu-id="4da5a-111">Para más información, consulte [OLE DB Connection Manager](../connection-manager/ole-db-connection-manager.md).</span><span class="sxs-lookup"><span data-stu-id="4da5a-111">For more information, see [OLE DB Connection Manager](../connection-manager/ole-db-connection-manager.md).</span></span>  
  
7.  <span data-ttu-id="4da5a-112">Seleccione el método de acceso de datos:</span><span class="sxs-lookup"><span data-stu-id="4da5a-112">Select the data access method:</span></span>  
  
    -   <span data-ttu-id="4da5a-113">**Tabla o vista** Seleccione una tabla o vista en la base de datos que contiene los datos.</span><span class="sxs-lookup"><span data-stu-id="4da5a-113">**Table or view** Select a table or view in the database that contains the data.</span></span>  
  
    -   <span data-ttu-id="4da5a-114">**Carga rápida de tabla o vista** Seleccione una tabla o una vista en la base de datos que contiene los datos y, después, establezca las opciones de carga rápida: **Mantener valores de identidad**, **Mantener valores NULL**, **Bloqueo de tabla**, **Restricción CHECK**, **Filas por lote**o **Tamaño máximo de confirmación de inserción**.</span><span class="sxs-lookup"><span data-stu-id="4da5a-114">**Table or view - fast load** Select a table or view in the database that contains the data, and then set the fast-load options: **Keep identity**, **Keep null**, **Table lock**, **Check constraint**, **Rows per batch**, or **Maximum insert commit size**.</span></span>  
  
    -   <span data-ttu-id="4da5a-115">**Variable de nombre de tabla o nombre de vista** Seleccione la variable definida por el usuario que contiene el nombre de una tabla o vista en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="4da5a-115">**Table name or view name variable** Select the user-defined variable that contains the name of a table or view in the database.</span></span>  
  
    -   <span data-ttu-id="4da5a-116">**Carga rápida de variable de nombre de tabla o nombre de vista** Seleccione la variable definida por el usuario que contiene el nombre de una tabla o vista en la base de datos que contiene los datos y, después, establezca las opciones de carga rápida.</span><span class="sxs-lookup"><span data-stu-id="4da5a-116">**Table name or view name variable fast load** Select the user-defined variable that contains the name of a table or view in the database that contains the data, and then set the fast-load options.</span></span>  
  
    -   <span data-ttu-id="4da5a-117">**Comando SQL** Escriba un comando SQL o haga clic en **Generar consulta** para escribir un comando SQL mediante el **Generador de consultas**.</span><span class="sxs-lookup"><span data-stu-id="4da5a-117">**SQL command** Type an SQL command or click **Build Query** to write an SQL command by using the **Query Builder**.</span></span>  
  
8.  <span data-ttu-id="4da5a-118">Haga clic en **Asignaciones** y asigne columnas de la lista **Columnas de entrada disponibles** a columnas en la lista **Columnas de destino disponibles** arrastrando columnas de una lista a otra.</span><span class="sxs-lookup"><span data-stu-id="4da5a-118">Click **Mappings** and then map columns from the **Available Input Columns** list to columns in the **Available Destination Columns** list by dragging columns from one list to another.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="4da5a-119">El destino de OLE DB asigna automáticamente las columnas con el mismo nombre.</span><span class="sxs-lookup"><span data-stu-id="4da5a-119">The OLE DB destination automatically maps same-named columns.</span></span>  
  
9. <span data-ttu-id="4da5a-120">Para configurar la salida de error, haga clic en **Salida de error**.</span><span class="sxs-lookup"><span data-stu-id="4da5a-120">To configure the error output, click **Error Output**.</span></span> <span data-ttu-id="4da5a-121">Para más información, vea [Configurar una salida de error en un componente de flujo de datos](../configure-an-error-output-in-a-data-flow-component.md).</span><span class="sxs-lookup"><span data-stu-id="4da5a-121">For more information, see [Configure an Error Output in a Data Flow Component](../configure-an-error-output-in-a-data-flow-component.md).</span></span>  
  
10. <span data-ttu-id="4da5a-122">Haga clic en **OK**.</span><span class="sxs-lookup"><span data-stu-id="4da5a-122">Click **OK**.</span></span>  
  
11. <span data-ttu-id="4da5a-123">Para guardar el paquete actualizado, haga clic en **Guardar los elementos seleccionados**, en el menú **Archivo**.</span><span class="sxs-lookup"><span data-stu-id="4da5a-123">To save the updated package, click **Save Selected Items** on the **File** menu.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4da5a-124">Consulte también</span><span class="sxs-lookup"><span data-stu-id="4da5a-124">See Also</span></span>  
 <span data-ttu-id="4da5a-125">[Destino de OLE DB](ole-db-destination.md) </span><span class="sxs-lookup"><span data-stu-id="4da5a-125">[OLE DB Destination](ole-db-destination.md) </span></span>  
 <span data-ttu-id="4da5a-126">[Transformaciones de Integration Services](transformations/integration-services-transformations.md) </span><span class="sxs-lookup"><span data-stu-id="4da5a-126">[Integration Services Transformations](transformations/integration-services-transformations.md) </span></span>  
 <span data-ttu-id="4da5a-127">[Rutas de Integration Services](integration-services-paths.md) </span><span class="sxs-lookup"><span data-stu-id="4da5a-127">[Integration Services Paths](integration-services-paths.md) </span></span>  
 [<span data-ttu-id="4da5a-128">Tarea Flujo de datos</span><span class="sxs-lookup"><span data-stu-id="4da5a-128">Data Flow Task</span></span>](../control-flow/data-flow-task.md)  
  
  
