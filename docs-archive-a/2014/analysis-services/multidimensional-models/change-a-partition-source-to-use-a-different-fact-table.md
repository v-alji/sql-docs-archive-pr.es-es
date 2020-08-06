---
title: Cambiar el origen de una partición para usar una tabla de hechos diferente | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- fact tables [Analysis Services]
- partitions [Analysis Services], fact tables
ms.assetid: 5508312f-8e46-4802-9362-6688ca03d098
author: minewiskan
ms.author: owend
ms.openlocfilehash: 0063a6023d769dc6dccd616655d10e0bd3c65a98
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87748381"
---
# <a name="change-a-partition-source-to-use-a-different-fact-table"></a><span data-ttu-id="07ae6-102">Cambiar el origen de una partición para usar una tabla de hechos diferente</span><span class="sxs-lookup"><span data-stu-id="07ae6-102">Change a partition source to use a different fact table</span></span>
  <span data-ttu-id="07ae6-103">Cuando se crea una partición para un cubo, se puede usar una tabla de hechos diferente.</span><span class="sxs-lookup"><span data-stu-id="07ae6-103">When you create a partition for a cube, you can choose to use a different fact table.</span></span> <span data-ttu-id="07ae6-104">Las tablas diferentes pueden proceder de una única vista del origen de datos, de diferentes vistas del origen de datos o de diferentes orígenes de datos.</span><span class="sxs-lookup"><span data-stu-id="07ae6-104">Different tables may be from a single data source view, from different data source views, or from different data sources.</span></span> <span data-ttu-id="07ae6-105">Una vista del origen de datos también puede contener tablas diferentes de más de un origen de datos.</span><span class="sxs-lookup"><span data-stu-id="07ae6-105">A data source view may also contain different tables from more than one data source.</span></span>  
  
 <span data-ttu-id="07ae6-106">Todas las tablas de hechos y dimensiones correspondientes a las particiones de un cubo deben tener la misma estructura que la tabla de hechos y las dimensiones del cubo.</span><span class="sxs-lookup"><span data-stu-id="07ae6-106">All fact tables and dimensions for a cube's partitions must have the same structure as the fact table and dimensions of the cube.</span></span> <span data-ttu-id="07ae6-107">Por ejemplo, varias tablas de hechos pueden tener la misma estructura pero contener datos de años distintos o de líneas de productos diferentes.</span><span class="sxs-lookup"><span data-stu-id="07ae6-107">For example, different fact tables can have the same structure but contain data for different years or different product lines.</span></span>  
  
 <span data-ttu-id="07ae6-108">La tabla de hechos se especifica en la página **Especificar información de origen** del Asistente para particiones.</span><span class="sxs-lookup"><span data-stu-id="07ae6-108">You specify a fact table on the **Specify Source Information** page of the Partition Wizard.</span></span> <span data-ttu-id="07ae6-109">En esta página, en el grupo Origen de la partición que hay al lado de **Buscar en**, especifique un origen de datos o una vista del origen de datos en la que se debe buscar.</span><span class="sxs-lookup"><span data-stu-id="07ae6-109">On this page, in the Partition Source group next to **Look in**, specify a data source or data source view in which to look.</span></span> <span data-ttu-id="07ae6-110">A continuación, haga clic en **Buscar tablas**y, a continuación, en **Tablas disponibles**, seleccione la tabla que desea usar.</span><span class="sxs-lookup"><span data-stu-id="07ae6-110">Next, click **Find Tables**, and then, under **Available Tables**, select the table you want to use.</span></span>  
  
 <span data-ttu-id="07ae6-111">Cuando utilice tablas de hechos diferentes, asegúrese de que no hay datos duplicados en las distintas particiones.</span><span class="sxs-lookup"><span data-stu-id="07ae6-111">When you use different fact tables, ensure that no data is duplicated among the partitions.</span></span> <span data-ttu-id="07ae6-112">Por ejemplo, si una tabla de hechos contiene únicamente transacciones del año 2012 y otra solo contiene transacciones correspondientes a 2013, ambas contienen datos independientes.</span><span class="sxs-lookup"><span data-stu-id="07ae6-112">For example, if one fact table contains transactions for 2012 only, and another fact table contains transactions for 2013 only, these tables contain independent data.</span></span> <span data-ttu-id="07ae6-113">Igualmente son independientes las tablas de hechos correspondientes a líneas de productos o a áreas geográficas distintas.</span><span class="sxs-lookup"><span data-stu-id="07ae6-113">Similarly, fact tables for distinct product lines or distinct geographical areas are independent.</span></span>  
  
 <span data-ttu-id="07ae6-114">Es posible, pero no se recomienda, utilizar diferentes tablas de hechos que contengan datos duplicados.</span><span class="sxs-lookup"><span data-stu-id="07ae6-114">It is possible, but not recommended, to use different fact tables that contain duplicated data.</span></span> <span data-ttu-id="07ae6-115">En este caso, debe utilizar filtros en las particiones para asegurarse de que los datos empleados por una partición no serán utilizados por ninguna otra.</span><span class="sxs-lookup"><span data-stu-id="07ae6-115">In this case, you must use filters in the partitions to ensure that data used by one partition is not used by any other partition.</span></span> <span data-ttu-id="07ae6-116">Para obtener más información, vea [Crear y administrar una partición local &#40;Analysis Services&#41;](create-and-manage-a-local-partition-analysis-services.md).</span><span class="sxs-lookup"><span data-stu-id="07ae6-116">For more information, see [Create and Manage a Local Partition &#40;Analysis Services&#41;](create-and-manage-a-local-partition-analysis-services.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="07ae6-117">Consulte también</span><span class="sxs-lookup"><span data-stu-id="07ae6-117">See Also</span></span>  
 [<span data-ttu-id="07ae6-118">Crear y administrar una partición local &#40;Analysis Services&#41;</span><span class="sxs-lookup"><span data-stu-id="07ae6-118">Create and Manage a Local Partition &#40;Analysis Services&#41;</span></span>](create-and-manage-a-local-partition-analysis-services.md)  
  
  
