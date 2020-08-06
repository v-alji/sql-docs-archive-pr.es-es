---
title: Agregar una tabla (SSAS tabular) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: d713c432-db99-4983-acc1-52b0fdd58bd6
author: minewiskan
ms.author: owend
ms.openlocfilehash: a80c22c992a89ed2cb3db84809b47a7cd08cb514
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87675524"
---
# <a name="add-a-table-ssas-tabular"></a><span data-ttu-id="e0437-102">Agregar una tabla (SSAS tabular)</span><span class="sxs-lookup"><span data-stu-id="e0437-102">Add a Table (SSAS Tabular)</span></span>
  <span data-ttu-id="e0437-103">En este tema se describe cómo agregar una tabla de un origen de datos del que ha importado datos previamente en el modelo.</span><span class="sxs-lookup"><span data-stu-id="e0437-103">This topic describes how to add a table from a data source from which you have previously imported data into your model.</span></span> <span data-ttu-id="e0437-104">Para agregar una tabla del mismo origen de datos, puede usar la conexión de origen de datos existente.</span><span class="sxs-lookup"><span data-stu-id="e0437-104">To add a table from the same data source, you can use the existing data source connection.</span></span> <span data-ttu-id="e0437-105">Se recomienda usar siempre una conexión única al importar cualquier número de tablas de un origen de datos único.</span><span class="sxs-lookup"><span data-stu-id="e0437-105">It is recommended you always use a single connection when importing any number of tables from a single data source.</span></span>  
  
### <a name="to-add-a-table-from-an-existing-data-source"></a><span data-ttu-id="e0437-106">Para agregar una tabla de un origen de datos existente</span><span class="sxs-lookup"><span data-stu-id="e0437-106">To add a table from an existing data source</span></span>  
  
1.  <span data-ttu-id="e0437-107">En [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], haga clic en el menú **Modelo** y, a continuación, en **Conexiones existentes**.</span><span class="sxs-lookup"><span data-stu-id="e0437-107">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], click the **Model** menu, and then click **Existing Connections**.</span></span>  
  
2.  <span data-ttu-id="e0437-108">En la página **Conexiones existentes** , seleccione la conexión al origen de datos que tiene la tabla que desea agregar y haga clic en **Abrir**.</span><span class="sxs-lookup"><span data-stu-id="e0437-108">On the **Existing Connections** page, select the connection to the data source that has the table you want to add, and then click **Open**.</span></span>  
  
3.  <span data-ttu-id="e0437-109">En la página **Seleccionar tablas y vistas** , seleccione la tabla del origen de datos que desea agregar al modelo.</span><span class="sxs-lookup"><span data-stu-id="e0437-109">On the **Select Tables and Views** page, select the table from the data source you want to add to your model.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="e0437-110">En la página **Seleccionar tablas y vistas** no se mostrarán las tablas que se importaron previamente como activadas.</span><span class="sxs-lookup"><span data-stu-id="e0437-110">The **Select Tables and Views** page will not show tables that were previously imported as checked.</span></span>  <span data-ttu-id="e0437-111">Si selecciona una tabla que se importó previamente con esta conexión y no proporcionó a la tabla un nombre descriptivo diferente, se agrega un 1 al nombre descriptivo.</span><span class="sxs-lookup"><span data-stu-id="e0437-111">If you select a table that was previously imported using this connection, and you did not give the table a different friendly name, a 1 will be appended to the friendly name.</span></span> <span data-ttu-id="e0437-112">No tiene que volver a seleccionar las tablas que se importaron previamente con esta conexión.</span><span class="sxs-lookup"><span data-stu-id="e0437-112">You do not need to re-select any tables that were previously imported by using this connection.</span></span>  
  
4.  <span data-ttu-id="e0437-113">En caso necesario, use **Vista previa y filtro** para seleccionar solo algunas columnas o para aplicar filtros a los datos que se van a importar.</span><span class="sxs-lookup"><span data-stu-id="e0437-113">If necessary, use **Preview & Filter** to select only certain columns or apply filters to the data to be imported.</span></span>  
  
5.  <span data-ttu-id="e0437-114">Haga clic en **Finalizar** para importar la nueva tabla.</span><span class="sxs-lookup"><span data-stu-id="e0437-114">Click **Finish** to import the new table.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="e0437-115">Cuando se importan varias tablas al mismo tiempo desde un único origen de datos, las relaciones entre dichas tablas en el origen se crean automáticamente en el modelo.</span><span class="sxs-lookup"><span data-stu-id="e0437-115">When importing multiple tables at the same time from a single data source, any relationships between those tables at the source will automatically be created in the model.</span></span> <span data-ttu-id="e0437-116">Sin embargo, cuando posteriormente agregue una tabla, es posible que tenga que crear las relaciones manualmente en el modelo entre las tablas recién agregadas y las tablas que se importaron previamente.</span><span class="sxs-lookup"><span data-stu-id="e0437-116">When adding a table later; however, you may need to manually create relationships in the model between newly added tables and the tables that were previously imported.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e0437-117">Consulte también</span><span class="sxs-lookup"><span data-stu-id="e0437-117">See Also</span></span>  
 <span data-ttu-id="e0437-118">[Importar datos &#40;&#41;tabular de SSAS](../import-data-ssas-tabular.md) </span><span class="sxs-lookup"><span data-stu-id="e0437-118">[Import Data &#40;SSAS Tabular&#41;](../import-data-ssas-tabular.md) </span></span>  
 [<span data-ttu-id="e0437-119">Eliminar una tabla &#40;SSAS tabular&#41;</span><span class="sxs-lookup"><span data-stu-id="e0437-119">Delete a Table &#40;SSAS Tabular&#41;</span></span>](delete-a-table-ssas-tabular.md)  
  
  
