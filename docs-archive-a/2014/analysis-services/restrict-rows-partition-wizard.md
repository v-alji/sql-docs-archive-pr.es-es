---
title: Restringir filas (Asistente para particiones) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.partitionwizard.typefilterexpression.f1
ms.assetid: eec8da8f-eab4-4ac4-a81d-995c814f88ca
author: minewiskan
ms.author: owend
ms.openlocfilehash: 9b0acc9ab24cfe92877d9abcd86353c85b4f8905
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87669935"
---
# <a name="restrict-rows-partition-wizard"></a><span data-ttu-id="793bd-102">Restringir filas (Asistente para particiones)</span><span class="sxs-lookup"><span data-stu-id="793bd-102">Restrict Rows (Partition Wizard)</span></span>
  <span data-ttu-id="793bd-103">Utilice la página **Restringir filas** para restringir las filas que se recuperarán de la tabla especificada y que se agregarán e incluirán en la partición.</span><span class="sxs-lookup"><span data-stu-id="793bd-103">Use the **Restrict Rows** page to restrict the rows that will be retrieved from the specified table and will be aggregated and included in the partition.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="793bd-104"> Esta página solo aparece si se ha seleccionado una única tabla en la página **Especificar información de origen** .</span><span class="sxs-lookup"><span data-stu-id="793bd-104">This page is appears only if you selected a single table in the **Specify Source Information** page.</span></span>  
  
> [!CAUTION]  
>  <span data-ttu-id="793bd-105"> Si, en **Tablas disponibles** en la página **Especificar información de origen** , ha especificado una tabla que se utiliza en otra partición, debe proporcionar una consulta en la página **Restringir filas** ; de lo contrario, corre el riesgo de duplicar datos en el cubo.</span><span class="sxs-lookup"><span data-stu-id="793bd-105">If you specified a table in **Available Tables** on the **Specify Source Information** page that is used by another partition, you must provide a query in the **Restrict Rows** page or risk duplicating data in the cube.</span></span>  
  
## <a name="options"></a><span data-ttu-id="793bd-106">Opciones</span><span class="sxs-lookup"><span data-stu-id="793bd-106">Options</span></span>  
 <span data-ttu-id="793bd-107">**Especificar una consulta para restringir las filas**</span><span class="sxs-lookup"><span data-stu-id="793bd-107">**Specify a query to restrict rows**</span></span>  
 <span data-ttu-id="793bd-108">Seleccione esta opción para escribir una consulta que restrinja las filas del cuadro **Consulta** .</span><span class="sxs-lookup"><span data-stu-id="793bd-108">Select to enter a query that restricts rows into the **Query** box.</span></span>  
  
 <span data-ttu-id="793bd-109">Si la opción **Consulta** está vacía cuando se selecciona esta opción, dicha opción se rellena con una instrucción SQL que recupera todas las columnas y todas las filas de la tabla seleccionada con anterioridad.</span><span class="sxs-lookup"><span data-stu-id="793bd-109">If **Supply a WHERE clause** is empty when this option is selected, that option is populated with an SQL statement that retrieves all columns and all rows from the previously selected table.</span></span>  
  
 <span data-ttu-id="793bd-110">**Consultar**</span><span class="sxs-lookup"><span data-stu-id="793bd-110">**Query**</span></span>  
 <span data-ttu-id="793bd-111">Escriba o modifique la instrucción SQL que se utiliza al recuperar filas de la tabla cuando se procesa la partición.</span><span class="sxs-lookup"><span data-stu-id="793bd-111">Type or modify the SQL statement used when retrieving rows from the table when the partition is processed.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="793bd-112">Si se especifica una cláusula WHERE, puede utilizarse un subconjunto de registros para esta partición.</span><span class="sxs-lookup"><span data-stu-id="793bd-112">By specifying a WHERE clause, a subset of records can be used for this partition.</span></span> <span data-ttu-id="793bd-113">Esto es muy importante para evitar la duplicación de datos cuando varias particiones se basan en una única tabla de hechos.</span><span class="sxs-lookup"><span data-stu-id="793bd-113">This is essential to prevent duplication of data when multiple partitions are based on a single fact table.</span></span>  
  
 <span data-ttu-id="793bd-114">**Comprobación**</span><span class="sxs-lookup"><span data-stu-id="793bd-114">**Check**</span></span>  
 <span data-ttu-id="793bd-115">Comprueba si la instrucción de **Consulta** es una instrucción SQL válida.</span><span class="sxs-lookup"><span data-stu-id="793bd-115">Verifies that the statement in **Query** is a valid SQL statement.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="793bd-116">Consulte también</span><span class="sxs-lookup"><span data-stu-id="793bd-116">See Also</span></span>  
 [<span data-ttu-id="793bd-117">Particiones &#40;Analysis Services - Datos multidimensionales&#41;</span><span class="sxs-lookup"><span data-stu-id="793bd-117">Partitions &#40;Analysis Services - Multidimensional Data&#41;</span></span>](multidimensional-models-olap-logical-cube-objects/partitions-analysis-services-multidimensional-data.md)  
  
  
