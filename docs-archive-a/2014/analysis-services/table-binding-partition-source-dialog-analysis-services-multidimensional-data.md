---
title: Detalle del enlace de tablas (cuadro de diálogo origen de la partición) (Analysis Services-datos multidimensionales) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.cubeeditor.partitions.partitiontableselection.f1
ms.assetid: 67d05389-81ae-4a6b-947b-986d37ec72b1
author: minewiskan
ms.author: owend
ms.openlocfilehash: 10845e18a2b7c74a8ed3aeec42f710b9706dc94a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87671713"
---
# <a name="table-binding-detail-partition-source-dialog-box-analysis-services---multidimensional-data"></a><span data-ttu-id="03216-102">Detalle del enlace de tablas (cuadro de diálogo Origen de la partición) (Analysis Services - Datos multidimensionales)</span><span class="sxs-lookup"><span data-stu-id="03216-102">Table Binding Detail (Partition Source Dialog Box) (Analysis Services - Multidimensional Data)</span></span>
  <span data-ttu-id="03216-103">Use la opción **Enlace de tablas** del cuadro de diálogo **Origen de la partición** para especificar la tabla de hechos que proporciona los datos para la partición.</span><span class="sxs-lookup"><span data-stu-id="03216-103">Use the **Table Binding** option in the **Partition Source** dialog box to specify the fact table that provides the data for the partition.</span></span> <span data-ttu-id="03216-104">Puede mostrar este panel seleccionando **Enlace de tablas** en la opción **Tipo de enlace** del cuadro de diálogo **Origen de la partición** .</span><span class="sxs-lookup"><span data-stu-id="03216-104">You can display this pane by selecting **Table Binding** from the **Binding type** option in the **Partition Source** dialog box.</span></span>  
  
## <a name="options"></a><span data-ttu-id="03216-105">Opciones</span><span class="sxs-lookup"><span data-stu-id="03216-105">Options</span></span>  
 <span data-ttu-id="03216-106">**Grupo de medida**</span><span class="sxs-lookup"><span data-stu-id="03216-106">**Measure group**</span></span>  
 <span data-ttu-id="03216-107">Muestra el grupo de medida para esta partición.</span><span class="sxs-lookup"><span data-stu-id="03216-107">Displays the measure group for this partition.</span></span>  
  
 <span data-ttu-id="03216-108">**Buscar en**</span><span class="sxs-lookup"><span data-stu-id="03216-108">**Look in**</span></span>  
 <span data-ttu-id="03216-109">Seleccione el origen de datos o la vista del origen de datos que contiene las tablas de origen para la partición.</span><span class="sxs-lookup"><span data-stu-id="03216-109">Select the data source or data source view that contains the source tables for this partition.</span></span> <span data-ttu-id="03216-110">La vista del origen de datos utilizada por el grupo de medida seleccionado es el valor seleccionado de manera predeterminada.</span><span class="sxs-lookup"><span data-stu-id="03216-110">The data source view used by the selected measure group is selected by default.</span></span>  
  
 <span data-ttu-id="03216-111">**Tablas de filtros**</span><span class="sxs-lookup"><span data-stu-id="03216-111">**Filter tables**</span></span>  
 <span data-ttu-id="03216-112">Escriba la cadena que quiere usar para restringir las tablas mostradas en **Tablas disponibles**con el nombre de la tabla.</span><span class="sxs-lookup"><span data-stu-id="03216-112">Type the string used to restrict, by table name, the tables displayed in **Available tables**.</span></span>  
  
 <span data-ttu-id="03216-113">**Buscar tablas**</span><span class="sxs-lookup"><span data-stu-id="03216-113">**Find tables**</span></span>  
 <span data-ttu-id="03216-114">Seleccione esta opción para actualizar la lista de tablas de **Tablas disponibles**y restringir la lista si se ha especificado una cadena en **Tablas de filtros**.</span><span class="sxs-lookup"><span data-stu-id="03216-114">Select to refresh the list of tables in **Available tables**, further restricting the list if a string was specified in **Filter tables**.</span></span>  
  
 <span data-ttu-id="03216-115">**Tablas disponibles**</span><span class="sxs-lookup"><span data-stu-id="03216-115">**Available tables**</span></span>  
 <span data-ttu-id="03216-116">Haga clic en esta opción para seleccionar la tabla que se debe usar como tabla de origen para la partición.</span><span class="sxs-lookup"><span data-stu-id="03216-116">Click to select the table to use as a source table for the partition.</span></span>  
  
 <span data-ttu-id="03216-117">Si no se especifica ningún filtro en **Tablas de filtros**, se enumeran todas las tablas del origen de datos o de la vista del origen de datos que se especificaron en **Buscar en** y cuya estructura es similar a la tabla de hechos utilizada por el grupo de medida especificado en **Grupo de medida** .</span><span class="sxs-lookup"><span data-stu-id="03216-117">If no filter is specified in **Filter tables**, all tables in the data source or data source view specified in **Look in** that are similar in structure to the fact table used by the measure group specified in **Measure group** are listed.</span></span>  
  
 <span data-ttu-id="03216-118">Si se especifica un filtro en **Tablas de filtros**, la lista se restringe aún más mediante la comparación del filtro con los nombres de tabla que cumplen los criterios mencionados anteriormente.</span><span class="sxs-lookup"><span data-stu-id="03216-118">If a filter is specified in **Filter tables**, the list is further restricted by comparing the filter against the table names that meet the above criteria.</span></span> <span data-ttu-id="03216-119">Solo se mostrarán las tablas que contengan la cadena especificada en **Tablas de filtros** .</span><span class="sxs-lookup"><span data-stu-id="03216-119">Only those tables that contain the string specified in **Filter tables** are displayed.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="03216-120">Consulte también</span><span class="sxs-lookup"><span data-stu-id="03216-120">See Also</span></span>  
 [<span data-ttu-id="03216-121">Cuadro de diálogo origen de la partición &#40;Analysis Services de datos multidimensionales&#41;</span><span class="sxs-lookup"><span data-stu-id="03216-121">Partition Source Dialog Box &#40;Analysis Services - Multidimensional Data&#41;</span></span>](partition-source-dialog-box-analysis-services-multidimensional-data.md)  
  
  
