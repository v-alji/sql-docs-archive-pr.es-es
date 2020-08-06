---
title: Transformación Limpieza de DQS | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- data correction
- correct data
ms.assetid: d2ec1b1a-c745-4741-b57c-6fdb524a154c
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 5e980497905b8fa96a73516916af17f934221992
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87663031"
---
# <a name="dqs-cleansing-transformation"></a><span data-ttu-id="60b54-102">Transformación Limpieza de DQS</span><span class="sxs-lookup"><span data-stu-id="60b54-102">DQS Cleansing Transformation</span></span>
  <span data-ttu-id="60b54-103">La transformación Limpieza de DQS usa Data Quality Services (DQS) para corregir datos de un origen de datos conectado aplicando reglas aprobadas que se crearon para el origen de datos conectado o un origen de datos similar.</span><span class="sxs-lookup"><span data-stu-id="60b54-103">The DQS Cleansing transformation uses Data Quality Services (DQS) to correct data from a connected data source, by applying approved rules that were created for the connected data source or a similar data source.</span></span> <span data-ttu-id="60b54-104">Para obtener más información acerca de las reglas de corrección de datos, vea [DQS Knowledge Bases and Domains](../../../data-quality-services/dqs-knowledge-bases-and-domains.md).</span><span class="sxs-lookup"><span data-stu-id="60b54-104">For more information about data correction rules, see [DQS Knowledge Bases and Domains](../../../data-quality-services/dqs-knowledge-bases-and-domains.md).</span></span> <span data-ttu-id="60b54-105">Para obtener más información acerca de DQS, vea [Data Quality Services Concepts](../../../data-quality-services/data-quality-services-concepts.md).</span><span class="sxs-lookup"><span data-stu-id="60b54-105">For more information DQS, see [Data Quality Services Concepts](../../../data-quality-services/data-quality-services-concepts.md).</span></span>  
  
 <span data-ttu-id="60b54-106">Para determinar si es necesario corregir los datos, la transformación Limpieza de DQS procesa los datos de una columna de entrada cuando se cumplen las condiciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="60b54-106">To determine whether the data has to be corrected, the DQS Cleansing transformation processes data from an input column when the following conditions are true:</span></span>  
  
-   <span data-ttu-id="60b54-107">La columna está seleccionada para la corrección de datos.</span><span class="sxs-lookup"><span data-stu-id="60b54-107">The column is selected for data correction.</span></span>  
  
-   <span data-ttu-id="60b54-108">El tipo de datos de la columna se admite para la corrección de datos.</span><span class="sxs-lookup"><span data-stu-id="60b54-108">The column data type is supported for data correction.</span></span>  
  
-   <span data-ttu-id="60b54-109">La columna está asignada a un dominio que tiene un tipo de datos compatible.</span><span class="sxs-lookup"><span data-stu-id="60b54-109">The column is mapped a domain that has a compatible data type.</span></span>  
  
 <span data-ttu-id="60b54-110">La transformación también incluye una salida de error que puede configurar para controlar los errores de fila.</span><span class="sxs-lookup"><span data-stu-id="60b54-110">The transformation also includes an error output that you configure to handle row-level errors.</span></span> <span data-ttu-id="60b54-111">Para configurar la salida de error, use el **Editor de transformación Limpieza de DQS**.</span><span class="sxs-lookup"><span data-stu-id="60b54-111">To configure the error output, use the **DQS Cleansing Transformation Editor**.</span></span>  
  
 <span data-ttu-id="60b54-112">Puede incluir la [Fuzzy Grouping Transformation](fuzzy-grouping-transformation.md) en el flujo de datos para identificar filas de datos que probablemente estén duplicadas.</span><span class="sxs-lookup"><span data-stu-id="60b54-112">You can include the [Fuzzy Grouping Transformation](fuzzy-grouping-transformation.md) in the data flow to identify rows of data that are likely to be duplicates.</span></span>  
  
## <a name="data-quality-projects-and-values"></a><span data-ttu-id="60b54-113">Proyectos y valores de calidad de los datos</span><span class="sxs-lookup"><span data-stu-id="60b54-113">Data Quality Projects and Values</span></span>  
 <span data-ttu-id="60b54-114">Al procesar datos con la transformación Limpieza de DQS, un proyecto de limpieza se crea en el servidor Data Quality Server.</span><span class="sxs-lookup"><span data-stu-id="60b54-114">When you process data with the DQS Cleansing transformation, a cleansing project is created on the Data Quality Server.</span></span> <span data-ttu-id="60b54-115">Utilice Data Quality Client para administrar el proyecto.</span><span class="sxs-lookup"><span data-stu-id="60b54-115">You use the Data Quality Client to manage the project.</span></span> <span data-ttu-id="60b54-116">Además, puede utilizar Data Quality Client para importar los valores del proyecto en un dominio de base de conocimiento de DQS.</span><span class="sxs-lookup"><span data-stu-id="60b54-116">In addition, you can use the Data Quality Client to import the project values into a DQS knowledge base domain.</span></span> <span data-ttu-id="60b54-117">Puede importar los valores solo a un dominio (o dominio vinculado) que la transformación Limpieza de DQS se configurara para usar.</span><span class="sxs-lookup"><span data-stu-id="60b54-117">You can import the values only to a domain (or linked domain) that the DQS Cleansing transformation was configured to use.</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="60b54-118">Related Tasks</span><span class="sxs-lookup"><span data-stu-id="60b54-118">Related Tasks</span></span>  
  
-   [<span data-ttu-id="60b54-119">Abrir proyectos de Integration Services en Data Quality Client</span><span class="sxs-lookup"><span data-stu-id="60b54-119">Open Integration Services Projects in Data Quality Client</span></span>](../../../data-quality-services/open-integration-services-projects-in-data-quality-client.md)  
  
-   [<span data-ttu-id="60b54-120">Importar valores de un proyecto de limpieza en un dominio</span><span class="sxs-lookup"><span data-stu-id="60b54-120">Import Cleansing Project Values into a Domain</span></span>](../../../data-quality-services/import-cleansing-project-values-into-a-domain.md)  
  
-   [<span data-ttu-id="60b54-121">Aplicación de reglas de calidad de los datos al origen de datos</span><span class="sxs-lookup"><span data-stu-id="60b54-121">Apply Data Quality Rules to Data Source</span></span>](apply-data-quality-rules-to-data-source.md)  
  
## <a name="related-content"></a><span data-ttu-id="60b54-122">Contenido relacionado</span><span class="sxs-lookup"><span data-stu-id="60b54-122">Related Content</span></span>  
  
-   [<span data-ttu-id="60b54-123">Administrar &#40;abrir, desbloquear, cambiar el nombre y eliminar&#41; un proyecto de calidad de datos</span><span class="sxs-lookup"><span data-stu-id="60b54-123">Manage &#40;Open, Unlock, Rename, and Delete&#41; a Data Quality Project</span></span>](../../../data-quality-services/manage-open-unlock-rename-and-delete-a-data-quality-project.md)  
  
-   <span data-ttu-id="60b54-124">Artículo sobre la [limpieza de datos complejos con dominios compuestos](https://social.technet.microsoft.com/wiki/contents/articles/13324.using-dqs-cleansing-complex-data-using-composite-domains.aspx), en social.technet.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="60b54-124">Article, [Cleansing complex data using composite domains](https://social.technet.microsoft.com/wiki/contents/articles/13324.using-dqs-cleansing-complex-data-using-composite-domains.aspx), on social.technet.microsoft.com.</span></span>  
  
  
