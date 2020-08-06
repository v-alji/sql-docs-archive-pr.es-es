---
title: Asignar parámetros de consulta a variables en un componente de flujo de datos | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- queries [Integration Services], parameter mapping
- parameters [Integration Services]
- mapping query parameters to variables [Integration Services]
- variables [Integration Services], mapping parameters to
ms.assetid: 5e26977c-758c-46d6-acf1-4fd9238f0950
author: chugugrace
ms.author: chugu
ms.openlocfilehash: b38940313397c7be7a8bcdbd2bf7f5233583096e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87750046"
---
# <a name="map-query-parameters-to-variables-in-a-data-flow-component"></a><span data-ttu-id="ef991-102">Asignar parámetros de consulta a variables en un componente de flujo de datos</span><span class="sxs-lookup"><span data-stu-id="ef991-102">Map Query Parameters to Variables in a Data Flow Component</span></span>
  <span data-ttu-id="ef991-103">Al configurar el origen de OLE DB para utilizar las consultas parametrizadas, puede asignar los parámetros a las variables.</span><span class="sxs-lookup"><span data-stu-id="ef991-103">When you configure the OLE DB source to use parameterized queries, you can map the parameters to variables.</span></span>  
  
 <span data-ttu-id="ef991-104">El origen de OLE DB utiliza las consultas parametrizadas para filtrar los datos cuando el origen conecta con un origen de datos.</span><span class="sxs-lookup"><span data-stu-id="ef991-104">The OLE DB source uses parameterized queries to filter data when the source connects to a data source.</span></span>  
  
### <a name="to-map-a-query-parameter-to-a-variable"></a><span data-ttu-id="ef991-105">Para asignar un parámetro de consulta a una variable</span><span class="sxs-lookup"><span data-stu-id="ef991-105">To map a query parameter to a variable</span></span>  
  
1.  <span data-ttu-id="ef991-106">En [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], abra el proyecto de [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] que contiene el paquete que desea.</span><span class="sxs-lookup"><span data-stu-id="ef991-106">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] project that contains the package you want.</span></span>  
  
2.  <span data-ttu-id="ef991-107">En el Explorador de soluciones, haga doble clic en el paquete para abrirlo.</span><span class="sxs-lookup"><span data-stu-id="ef991-107">In Solution Explorer, double-click the package to open it.</span></span>  
  
3.  <span data-ttu-id="ef991-108">Haga clic en la pestaña **Flujo de datos** y, a continuación, desde el **cuadro de herramientas**, arrastre el origen de OLE DB hasta la superficie de diseño.</span><span class="sxs-lookup"><span data-stu-id="ef991-108">Click the **Data Flow** tab, and then, from the **Toolbox**, drag the OLE DB source to the design surface.</span></span>  
  
4.  <span data-ttu-id="ef991-109">Haga clic con el botón derecho en el origen de OLE DB y, después, haga clic en **Editar**.</span><span class="sxs-lookup"><span data-stu-id="ef991-109">Right-click the OLE DB source, and then click **Edit**.</span></span>  
  
5.  <span data-ttu-id="ef991-110">En el **Editor de origen de OLE DB**, seleccione un administrador de conexiones OLE DB para conectarse al origen de datos o haga clic en **Nuevo** para crear un nuevo administrador de conexiones OLE DB.</span><span class="sxs-lookup"><span data-stu-id="ef991-110">In the **OLE DB Source Editor**, select an OLE DB connection manager to use to connect to the data source, or click **New** to create a new OLE DB connection manager.</span></span>  
  
6.  <span data-ttu-id="ef991-111">Seleccione la opción **Comando SQL** para el modo de acceso a datos y, a continuación, escriba una consulta parametrizada en el panel **Texto de comando SQL** .</span><span class="sxs-lookup"><span data-stu-id="ef991-111">Select the **SQL command** option for data access mode, and then type a parameterized query in the **SQL command text** pane.</span></span>  
  
7.  <span data-ttu-id="ef991-112">Haga clic en **Parámetros**.</span><span class="sxs-lookup"><span data-stu-id="ef991-112">Click **Parameters**.</span></span>  
  
8.  <span data-ttu-id="ef991-113">En el cuadro de diálogo **Establecer parámetros de consulta**, asigne cada parámetro de la lista **Parámetros** a una variable de la lista **Variables** o cree una variable haciendo clic en **\<New variable>** .</span><span class="sxs-lookup"><span data-stu-id="ef991-113">In the **Set Query Parameters** dialog box, map each parameter in the **Parameters** list to a variable in the **Variables** list, or create a new variable by clicking **\<New variable>**.</span></span> <span data-ttu-id="ef991-114">Haga clic en **OK**.</span><span class="sxs-lookup"><span data-stu-id="ef991-114">Click **OK**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="ef991-115">Solo están disponibles para su asignación las variables del sistema y las variables definidas por el usuario que están en el ámbito del paquete, un contenedor principal como un bucle Foreach, o la tarea Flujo de datos que contiene el componente de flujo de datos.</span><span class="sxs-lookup"><span data-stu-id="ef991-115">Only system variables and user-defined variables that are in the scope of the package, a parent container such as a Foreach Loop, or the Data Flow task that contains the data flow component are available for mapping.</span></span> <span data-ttu-id="ef991-116">La variable debe tener un tipo de datos compatible con la columna en la cláusula WHERE a la que se asigna el parámetro.</span><span class="sxs-lookup"><span data-stu-id="ef991-116">The variable must have a data type that is compatible with the column in the WHERE clause to which the parameter is assigned.</span></span>  
  
9. <span data-ttu-id="ef991-117">Puede hacer clic en **Vista previa** para ver hasta 200 filas de los datos que devuelve la consulta.</span><span class="sxs-lookup"><span data-stu-id="ef991-117">You can click **Preview** to view up to 200 rows of the data that the query returns.</span></span>  
  
10. <span data-ttu-id="ef991-118">Para guardar el paquete actualizado, haga clic en **Guardar los elementos seleccionados**, en el menú **Archivo**.</span><span class="sxs-lookup"><span data-stu-id="ef991-118">To save the updated package, click **Save Selected Items** on the **File** menu.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ef991-119">Consulte también</span><span class="sxs-lookup"><span data-stu-id="ef991-119">See Also</span></span>  
 <span data-ttu-id="ef991-120">[Origen de OLE DB](ole-db-source.md) </span><span class="sxs-lookup"><span data-stu-id="ef991-120">[OLE DB Source](ole-db-source.md) </span></span>  
 [<span data-ttu-id="ef991-121">Transformación Búsqueda</span><span class="sxs-lookup"><span data-stu-id="ef991-121">Lookup Transformation</span></span>](transformations/lookup-transformation.md)  
  
  
