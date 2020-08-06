---
title: Especificar información de origen (Asistente para particiones) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.partitionwizard.specifydsvandfacttables.f1
ms.assetid: b6c13587-c690-45d9-af90-b3d652afc55b
author: minewiskan
ms.author: owend
ms.openlocfilehash: 088a8abf7b143b68766f22af37f8ff4fa2065d65
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87675542"
---
# <a name="specify-source-information-partition-wizard"></a><span data-ttu-id="561e9-102">Especificar información de origen (Asistente para particiones)</span><span class="sxs-lookup"><span data-stu-id="561e9-102">Specify Source Information (Partition Wizard)</span></span>
  <span data-ttu-id="561e9-103">Use la página **Especificar información de origen** para seleccionar el grupo de medida en el que desea crear la partición, así como la vista del origen de datos y las tablas de filtros de la partición.</span><span class="sxs-lookup"><span data-stu-id="561e9-103">Use the **Specify Source Information** page to select the measure group in which to create the partition, and also the data source view and filter tables for your partition.</span></span>  
  
> [!CAUTION]  
>  <span data-ttu-id="561e9-104">Si especifica una tabla en **Tablas disponibles** usada por otra partición, deberá proporcionar una consulta en la página **Restringir filas** para evitar duplicar datos en el cubo.</span><span class="sxs-lookup"><span data-stu-id="561e9-104">If you specify a table in **Available Tables** that is used by another partition, you must provide a query in the **Restrict Rows** page or risk duplicating data in the cube.</span></span>  
  
## <a name="options"></a><span data-ttu-id="561e9-105">Opciones</span><span class="sxs-lookup"><span data-stu-id="561e9-105">Options</span></span>  
 <span data-ttu-id="561e9-106">**Grupo de medida**</span><span class="sxs-lookup"><span data-stu-id="561e9-106">**Measure group**</span></span>  
 <span data-ttu-id="561e9-107">Seleccione un grupo de medida para la partición.</span><span class="sxs-lookup"><span data-stu-id="561e9-107">Select a measure group for this partition.</span></span>  
  
 <span data-ttu-id="561e9-108">**Buscar en**</span><span class="sxs-lookup"><span data-stu-id="561e9-108">**Look in**</span></span>  
 <span data-ttu-id="561e9-109">Seleccione el origen de datos o la vista del origen de datos que contiene las tablas de origen para la partición.</span><span class="sxs-lookup"><span data-stu-id="561e9-109">Select the data source or data source view that contains the source tables for this partition.</span></span> <span data-ttu-id="561e9-110">La vista del origen de datos utilizada por el grupo de medida aparece seleccionada de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="561e9-110">The data source view used by the measure group is selected by default.</span></span>  
  
 <span data-ttu-id="561e9-111">**Tablas de filtros**</span><span class="sxs-lookup"><span data-stu-id="561e9-111">**Filter tables**</span></span>  
 <span data-ttu-id="561e9-112">Escriba la cadena que quiere usar para restringir las tablas mostradas en **Tablas disponibles**con el nombre de la tabla.</span><span class="sxs-lookup"><span data-stu-id="561e9-112">Type the string used to restrict, by table name, the tables displayed in **Available tables**.</span></span>  
  
 <span data-ttu-id="561e9-113">**Buscar tablas**</span><span class="sxs-lookup"><span data-stu-id="561e9-113">**Find tables**</span></span>  
 <span data-ttu-id="561e9-114">Seleccione esta opción para actualizar la lista de tablas de **Tablas disponibles**y restringir la lista si se ha especificado una cadena en **Tablas de filtros**.</span><span class="sxs-lookup"><span data-stu-id="561e9-114">Select to refresh the list of tables in **Available tables**, further restricting the list if a string was specified in **Filter tables**.</span></span>  
  
 <span data-ttu-id="561e9-115">**Tablas disponibles**</span><span class="sxs-lookup"><span data-stu-id="561e9-115">**Available tables**</span></span>  
 <span data-ttu-id="561e9-116">Seleccione las tablas que desea utilizar como tablas de origen para las particiones.</span><span class="sxs-lookup"><span data-stu-id="561e9-116">Select the tables to use as source tables for partitions.</span></span> <span data-ttu-id="561e9-117">El **Asistente para particiones** crea una partición para cada una de las tablas seleccionadas en **Tablas disponibles**.</span><span class="sxs-lookup"><span data-stu-id="561e9-117">The **Partition Wizard** creates one partition for each table selected in **Available tables**.</span></span>  
  
 <span data-ttu-id="561e9-118">Si no ha especificado ningún filtro en **Tablas de filtros**, esta opción mostrará la lista de todas las tablas en el origen de datos o en la vista del origen de datos especificados en **Buscar en** que presenten una estructura similar a la tabla de hechos utilizada por el grupo de medida especificado en **Grupo de medida**.</span><span class="sxs-lookup"><span data-stu-id="561e9-118">If no filter is specified in **Filter tables**, this option lists all tables in the data source or data source view that are specified in **Look in** and that are similar in structure to the fact table used by the measure group specified in **Measure group**.</span></span>  
  
 <span data-ttu-id="561e9-119">Si ha especificado un filtro en **Tablas de filtros**, podrá restringir aún más la lista mediante la comparación del filtro con los nombres de tabla que cumplen los criterios anteriores.</span><span class="sxs-lookup"><span data-stu-id="561e9-119">If a filter is specified in **Filter tables**, the list is further restricted by comparing the filter against the table names that meet the previous criteria.</span></span> <span data-ttu-id="561e9-120">Solo se mostrarán las tablas que contengan la cadena especificada en **Tablas de filtros** .</span><span class="sxs-lookup"><span data-stu-id="561e9-120">Only those tables that contain the string specified in **Filter tables** are displayed.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="561e9-121">Si selecciona más de una tabla, no podrá mostrarse la página **Restringir filas** y no podrán restringirse las filas para las particiones creadas a partir de las tablas seleccionadas.</span><span class="sxs-lookup"><span data-stu-id="561e9-121">If more than one table is selected, the **Restrict Rows** page cannot be displayed and rows cannot be restricted for the partitions created from the selected tables.</span></span> <span data-ttu-id="561e9-122">Para restringir filas en las particiones, ejecute el Asistente para particiones para cada tabla en la que desea crear una partición.</span><span class="sxs-lookup"><span data-stu-id="561e9-122">To restrict rows for each partition, run the Partition Wizard once for each table from which a partition is to be created.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="561e9-123">Consulte también</span><span class="sxs-lookup"><span data-stu-id="561e9-123">See Also</span></span>  
 [<span data-ttu-id="561e9-124">Particiones &#40;Analysis Services - Datos multidimensionales&#41;</span><span class="sxs-lookup"><span data-stu-id="561e9-124">Partitions &#40;Analysis Services - Multidimensional Data&#41;</span></span>](multidimensional-models-olap-logical-cube-objects/partitions-analysis-services-multidimensional-data.md)  
  
  
