---
title: Columnas de coincidencia de calidad de datos (Complemento MDS para Excel) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
ms.assetid: f683fdc6-0d4c-4793-8143-567616cb2094
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 939ec9727cc81ce3b206b8bc7ca3ed8dd62c3877
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87662128"
---
# <a name="data-quality-matching-columns-mds-add-in-for-excel"></a><span data-ttu-id="10bf1-102">Columnas de coincidencia de calidad de datos (Complemento MDS para Excel)</span><span class="sxs-lookup"><span data-stu-id="10bf1-102">Data Quality Matching Columns (MDS Add-in for Excel)</span></span>
  <span data-ttu-id="10bf1-103">En [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)][!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)], después de buscar los datos coincidentes, en el grupo **Calidad de datos** en la cinta de opciones, puede hacer clic en **Mostrar detalles** para ver las columnas que proporcionan detalles de la coincidencia.</span><span class="sxs-lookup"><span data-stu-id="10bf1-103">In the [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)][!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)], after you match data, in the **Data Quality** group on the ribbon, you can click **Show Details** to display columns that provide matching details.</span></span>  
  
 <span data-ttu-id="10bf1-104">La tabla siguiente se muestra las columnas que se presentan al coincidir los datos.</span><span class="sxs-lookup"><span data-stu-id="10bf1-104">The following table shows the columns that are displayed when matching data.</span></span>  
  
|<span data-ttu-id="10bf1-105">Nombre</span><span class="sxs-lookup"><span data-stu-id="10bf1-105">Name</span></span>|<span data-ttu-id="10bf1-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="10bf1-106">Description</span></span>|  
|----------|-----------------|  
|<span data-ttu-id="10bf1-107">**CLUSTER_ID**</span><span class="sxs-lookup"><span data-stu-id="10bf1-107">**CLUSTER_ID**</span></span>|<span data-ttu-id="10bf1-108">Identificador único que se usa para agrupar registros similares.</span><span class="sxs-lookup"><span data-stu-id="10bf1-108">A unique identifier used to group similar records.</span></span> <span data-ttu-id="10bf1-109">Todas las filas similares tienen el mismo **CLUSTER_ID**.</span><span class="sxs-lookup"><span data-stu-id="10bf1-109">All rows that are similar have the same **CLUSTER_ID**.</span></span> <span data-ttu-id="10bf1-110">Si no se muestra ningún **CLUSTER_ID** para una fila, es porque no se han encontrado registros similares.</span><span class="sxs-lookup"><span data-stu-id="10bf1-110">If no **CLUSTER_ID** is displayed for a row, then no similar records were found.</span></span>|  
|<span data-ttu-id="10bf1-111">**RECORD_ID**</span><span class="sxs-lookup"><span data-stu-id="10bf1-111">**RECORD_ID**</span></span>|<span data-ttu-id="10bf1-112">Identificador único que se usa para identificar los registros.</span><span class="sxs-lookup"><span data-stu-id="10bf1-112">A unique identifier used to identify records.</span></span> <span data-ttu-id="10bf1-113">Similar al valor del código almacenado en el repositorio MDS, es un valor que se usa para identificar un registro.</span><span class="sxs-lookup"><span data-stu-id="10bf1-113">Similar to the Code value stored in the MDS repository, it is a value used to identify a record.</span></span> <span data-ttu-id="10bf1-114">Se genera automáticamente cada vez que se realiza la coincidencia.</span><span class="sxs-lookup"><span data-stu-id="10bf1-114">It is generated automatically each time matching takes place.</span></span>|  
|<span data-ttu-id="10bf1-115">**PIVOT_MARK**</span><span class="sxs-lookup"><span data-stu-id="10bf1-115">**PIVOT_MARK**</span></span>|<span data-ttu-id="10bf1-116">Registro arbitrario con el que otros registros se comparan; no tiene un valor de puntuación.</span><span class="sxs-lookup"><span data-stu-id="10bf1-116">An arbitrary record that other records are compared to; it does not have a score value.</span></span>|  
|<span data-ttu-id="10bf1-117">**CARÁCTER**</span><span class="sxs-lookup"><span data-stu-id="10bf1-117">**SCORE**</span></span>|<span data-ttu-id="10bf1-118">Representa el grado de similitud de los registros del grupo con el registro dinámico.</span><span class="sxs-lookup"><span data-stu-id="10bf1-118">Represents how similar the records in the group are to the pivot record.</span></span> <span data-ttu-id="10bf1-119">Esta puntuación está determinada por DQS.</span><span class="sxs-lookup"><span data-stu-id="10bf1-119">This score is determined by DQS.</span></span> <span data-ttu-id="10bf1-120">Si no se muestra ninguna puntuación, el registro es la dinamización para otros registros o no se encontraron coincidencias.</span><span class="sxs-lookup"><span data-stu-id="10bf1-120">If no score is displayed, either the record is the pivot for other records, or no matches were found.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="10bf1-121">Consulte también</span><span class="sxs-lookup"><span data-stu-id="10bf1-121">See Also</span></span>  
 <span data-ttu-id="10bf1-122">[Coincidencia de calidad de datos en el Complemento MDS para Excel](data-quality-matching-in-the-mds-add-in-for-excel.md) </span><span class="sxs-lookup"><span data-stu-id="10bf1-122">[Data Quality Matching in the MDS Add-in for Excel](data-quality-matching-in-the-mds-add-in-for-excel.md) </span></span>  
 <span data-ttu-id="10bf1-123">[Coincide con &#40;de datos similares Complemento MDS para Excel&#41;](match-similar-data-mds-add-in-for-excel.md) </span><span class="sxs-lookup"><span data-stu-id="10bf1-123">[Match Similar Data &#40;MDS Add-in for Excel&#41;](match-similar-data-mds-add-in-for-excel.md) </span></span>  
 [<span data-ttu-id="10bf1-124">Coincidencia de datos</span><span class="sxs-lookup"><span data-stu-id="10bf1-124">Data Matching</span></span>](../../data-quality-services/data-matching.md)  
  
  
