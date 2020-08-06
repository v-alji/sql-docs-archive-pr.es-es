---
title: Recuperar y describir datos modificados | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- incremental load [Integration Services],retrieving data
ms.assetid: af366697-6942-42bb-aea5-18fdef018965
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 62f60bf4a79c39b4f0cb7d1ba8fb3f52680a1f11
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87747716"
---
# <a name="retrieve-and-understand-the-change-data"></a><span data-ttu-id="f5249-102">Recuperar y describir datos modificados</span><span class="sxs-lookup"><span data-stu-id="f5249-102">Retrieve and Understand the Change Data</span></span>
  <span data-ttu-id="f5249-103">En el flujo de datos de un paquete de [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] que realiza una carga incremental de datos modificados, la primera tarea consiste en ejecutar la consulta que recupera los datos modificados.</span><span class="sxs-lookup"><span data-stu-id="f5249-103">In the data flow of an [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] package that performs an incremental load of change data, the first task is to run the query that retrieves the change data.</span></span> <span data-ttu-id="f5249-104">Esta consulta se ejecuta dentro de un componente de origen en una tarea Flujo de Datos.</span><span class="sxs-lookup"><span data-stu-id="f5249-104">You execute this query inside a source component in a Data Flow task.</span></span> <span data-ttu-id="f5249-105">A continuación, pueden utilizarse transformaciones y destinos de nivel inferior para aplicar los datos modificados a un destino.</span><span class="sxs-lookup"><span data-stu-id="f5249-105">You can then use downstream transformations and destinations to apply the change data to your destination.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="f5249-106">La creación de una consulta que contiene una función con valores de tabla es el tercer paso en el proceso de crear un paquete que realiza una carga incremental de datos modificados.</span><span class="sxs-lookup"><span data-stu-id="f5249-106">The creation of a query that contains a table-valued function is the third step in the process of creating a package that performs an incremental load of change data.</span></span> <span data-ttu-id="f5249-107">Para obtener más información sobre esta consulta, vea [Crear la función para recuperar los datos modificados](create-the-function-to-retrieve-the-change-data.md).</span><span class="sxs-lookup"><span data-stu-id="f5249-107">For more information about this query, see, [Create the Function to Retrieve the Change Data](create-the-function-to-retrieve-the-change-data.md).</span></span> <span data-ttu-id="f5249-108">Para obtener una descripción del proceso general de creación de un paquete que realiza una carga incremental de los datos modificados, vea [Captura de datos modificados &#40;SSIS&#41;](change-data-capture-ssis.md).</span><span class="sxs-lookup"><span data-stu-id="f5249-108">For a description of the overall process for creating a package that performs an incremental load of change data, see [Change Data Capture &#40;SSIS&#41;](change-data-capture-ssis.md).</span></span>  
  
## <a name="adding-the-data-flow-task"></a><span data-ttu-id="f5249-109">Agregar la tarea Flujo de datos</span><span class="sxs-lookup"><span data-stu-id="f5249-109">Adding the Data Flow Task</span></span>  
 <span data-ttu-id="f5249-110">En el flujo de datos del paquete, se recuperan los datos modificados, se separan las filas basándose en el tipo de cambio que se produjo y, a continuación, se aplican los cambios al destino.</span><span class="sxs-lookup"><span data-stu-id="f5249-110">In the data flow of the package, you retrieve the change data, separate the rows based on the type of change that occurred, and then apply the changes to the destination.</span></span>  
  
#### <a name="to-add-a-data-flow-task-to-the-package"></a><span data-ttu-id="f5249-111">Para agregar una tarea Flujo de datos al paquete</span><span class="sxs-lookup"><span data-stu-id="f5249-111">To add a Data Flow task to the package</span></span>  
  
1.  <span data-ttu-id="f5249-112">En la pestaña [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]Flujo de control **de** , agregue una tarea Flujo de datos.</span><span class="sxs-lookup"><span data-stu-id="f5249-112">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], on the **Control Flow** tab, add a Data Flow task.</span></span>  
  
2.  <span data-ttu-id="f5249-113">Conecte la tarea anterior que preparó la cadena de consulta con la tarea Flujo de datos.</span><span class="sxs-lookup"><span data-stu-id="f5249-113">Connect the preceding task that prepared the query string to the Data Flow task.</span></span>  
  
## <a name="configuring-the-source-component-to-query-for-changes"></a><span data-ttu-id="f5249-114">Configurar el componente de origen para consultar los cambios</span><span class="sxs-lookup"><span data-stu-id="f5249-114">Configuring the Source Component to Query for Changes</span></span>  
 <span data-ttu-id="f5249-115">El componente de origen utiliza la cadena de consulta que se preparó y se almacenó en una variable para llamar a la función con valores de tabla que recupera los datos que han cambiado.</span><span class="sxs-lookup"><span data-stu-id="f5249-115">The source component uses the query string that was prepared and stored in a variable to calls the table-valued function that retrieves the changed data.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="f5249-116">Para obtener más información sobre la cadena de consulta que se preparó y se almacenó en una variable, vea [Preparar para consultar datos modificados](prepare-to-query-for-the-change-data.md).</span><span class="sxs-lookup"><span data-stu-id="f5249-116">For more information about the query string that was prepared and stored in a variable, see [Prepare to Query for the Change Data](prepare-to-query-for-the-change-data.md).</span></span> <span data-ttu-id="f5249-117">Para obtener más información sobre la función con valores de tabla que recupera los datos modificados, vea [Crear la función para recuperar los datos modificados](create-the-function-to-retrieve-the-change-data.md).</span><span class="sxs-lookup"><span data-stu-id="f5249-117">For more information about the table-valued function that retrieves the change data, see [Create the Function to Retrieve the Change Data](create-the-function-to-retrieve-the-change-data.md).</span></span>  
  
#### <a name="to-configure-an-ole-db-source-to-retrieve-the-change-data"></a><span data-ttu-id="f5249-118">Para configurar un origen de OLE DB para recuperar los datos modificados</span><span class="sxs-lookup"><span data-stu-id="f5249-118">To configure an OLE DB source to retrieve the change data</span></span>  
  
1.  <span data-ttu-id="f5249-119">En [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], en la pestaña **Flujo de datos** , agregue un origen de OLE DB.</span><span class="sxs-lookup"><span data-stu-id="f5249-119">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], on the **Data Flow** tab, add an OLE DB source.</span></span>  
  
2.  <span data-ttu-id="f5249-120">En el **Editor de origen de OLE DB**, en la página **Administrador de conexiones** , seleccione las opciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="f5249-120">In the **OLE DB Source Editor**, on the **Connection Manager** page, select the following options:</span></span>  
  
    1.  <span data-ttu-id="f5249-121">Configure una conexión válida con una base de datos de origen.</span><span class="sxs-lookup"><span data-stu-id="f5249-121">Configure a valid connection to the source database.</span></span>  
  
    2.  <span data-ttu-id="f5249-122">Para **Modo de acceso a datos**, seleccione **Comando SQL de variable**.</span><span class="sxs-lookup"><span data-stu-id="f5249-122">For **Data access mode**, select **SQL command from variable**.</span></span>  
  
    3.  <span data-ttu-id="f5249-123">Para **Nombre de variable**, seleccione **User::SqlDataQuery**.</span><span class="sxs-lookup"><span data-stu-id="f5249-123">For **Variable name**, select **User::SqlDataQuery**.</span></span>  
  
3.  <span data-ttu-id="f5249-124">En el **Editor de origen de OLE DB**, en la página **Columnas** , asegúrese de que todas las columnas que desea están asignadas a columnas de resultados.</span><span class="sxs-lookup"><span data-stu-id="f5249-124">In the **OLE DB Source Editor**, on the **Columns** page, make sure that all the columns that you want are mapped to output columns.</span></span>  
  
## <a name="next-step"></a><span data-ttu-id="f5249-125">siguiente paso</span><span class="sxs-lookup"><span data-stu-id="f5249-125">Next Step</span></span>  
 <span data-ttu-id="f5249-126">Después de haber configurado un origen de OLE DB para recuperar los datos modificados, el paso siguiente consiste en iniciar el diseño del flujo de datos del paquete.</span><span class="sxs-lookup"><span data-stu-id="f5249-126">After you have configured an OLE DB source to retrieve the change data, the next step is to start designing the data flow in the package.</span></span>  
  
 <span data-ttu-id="f5249-127">**Tema siguiente:** [Procesar inserciones, actualizaciones y eliminaciones](process-inserts-updates-and-deletes.md)</span><span class="sxs-lookup"><span data-stu-id="f5249-127">**Next topic:** [Process Inserts, Updates, and Deletes](process-inserts-updates-and-deletes.md)</span></span>  
  
  
