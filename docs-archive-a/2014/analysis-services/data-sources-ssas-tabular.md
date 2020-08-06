---
title: Orígenes de datos (SSAS tabular) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 6908998b-9302-4a90-976e-770106b48d18
author: minewiskan
ms.author: owend
ms.openlocfilehash: d686d8100e30d7608e8d90f135022bdf46785723
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87746598"
---
# <a name="data-sources-ssas-tabular"></a><span data-ttu-id="64efd-102">Orígenes de datos (SSAS tabular)</span><span class="sxs-lookup"><span data-stu-id="64efd-102">Data Sources (SSAS Tabular)</span></span>
  <span data-ttu-id="64efd-103">Los orígenes de datos proporcionan los datos que se van a incluir en una solución de modelo tabular.</span><span class="sxs-lookup"><span data-stu-id="64efd-103">Data sources provide the data to be included in a tabular model solution.</span></span> <span data-ttu-id="64efd-104">Puede importar en el modelo datos procedentes de una gran variedad de orígenes: bases de datos relacionales; fuentes de distribución de datos; orígenes de datos multidimensionales, como los cubos de Analysis Services; y archivos de texto, como los libros de Microsoft Excel.</span><span class="sxs-lookup"><span data-stu-id="64efd-104">You can import data into your model from a wide variety of sources such as relational databases, data feeds, multidimensional data sources such as an Analysis Services cube, and from text files such as a Microsoft Excel workbook.</span></span> <span data-ttu-id="64efd-105">En los temas de esta sección hallará información sobre los tipos de orígenes de datos desde los que puede importar y los tipos de datos que puede importar; además, encontrará tareas que describen cómo importar datos desde esos orígenes.</span><span class="sxs-lookup"><span data-stu-id="64efd-105">Topics in this section provide information about the types of data sources you can import from, the various data types you can import, and tasks describing how to import data from those sources.</span></span>  
  
## <a name="related-topics-and-tasks"></a><span data-ttu-id="64efd-106">Temas y tareas relacionados</span><span class="sxs-lookup"><span data-stu-id="64efd-106">Related Topics and Tasks</span></span>  
  
|<span data-ttu-id="64efd-107">Tema</span><span class="sxs-lookup"><span data-stu-id="64efd-107">Topic</span></span>|<span data-ttu-id="64efd-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="64efd-108">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="64efd-109">Orígenes de datos compatibles &#40;SSAS tabular&#41;</span><span class="sxs-lookup"><span data-stu-id="64efd-109">Data Sources Supported &#40;SSAS Tabular&#41;</span></span>](tabular-models/data-sources-supported-ssas-tabular.md)|<span data-ttu-id="64efd-110">Este tema contiene información sobre los distintos orígenes de datos desde los que puede importar datos.</span><span class="sxs-lookup"><span data-stu-id="64efd-110">This topic provides information about the different data sources that you can import data from.</span></span>|  
|[<span data-ttu-id="64efd-111">Tipos de datos compatibles &#40;SSAS tabular&#41;</span><span class="sxs-lookup"><span data-stu-id="64efd-111">Data Types Supported &#40;SSAS Tabular&#41;</span></span>](tabular-models/data-types-supported-ssas-tabular.md)|<span data-ttu-id="64efd-112">Este tema contiene información sobre los distintos tipos de datos admitidos en un modelo tabular.</span><span class="sxs-lookup"><span data-stu-id="64efd-112">This topic provides information about the various data types that are supported in a Tabular Model.</span></span>|  
|[<span data-ttu-id="64efd-113">Suplantación &#40;SSAS tabular&#41;</span><span class="sxs-lookup"><span data-stu-id="64efd-113">Impersonation &#40;SSAS Tabular&#41;</span></span>](tabular-models/impersonation-ssas-tabular.md)|<span data-ttu-id="64efd-114">Este tema contiene información sobre la suplantación, que proporciona las credenciales de inicio de sesión que usa Analysis Services cuando se conecta a un origen de datos para importar y actualizar datos.</span><span class="sxs-lookup"><span data-stu-id="64efd-114">This topic provides information about impersonation, which provides logon credentials that are used by Analysis Services when connecting to a data source to import and refresh data.</span></span>|  
|[<span data-ttu-id="64efd-115">Importar datos &#40;SSAS tabular&#41;</span><span class="sxs-lookup"><span data-stu-id="64efd-115">Import Data &#40;SSAS Tabular&#41;</span></span>](import-data-ssas-tabular.md)|<span data-ttu-id="64efd-116">En las tareas de esta sección se describe cómo importar datos de varios orígenes de datos.</span><span class="sxs-lookup"><span data-stu-id="64efd-116">Tasks in this section describe how to import data from different data sources.</span></span>|  
|[<span data-ttu-id="64efd-117">Procesar datos &#40;SSAS tabular&#41;</span><span class="sxs-lookup"><span data-stu-id="64efd-117">Process Data &#40;SSAS Tabular&#41;</span></span>](process-data-ssas-tabular.md)|<span data-ttu-id="64efd-118">En las tareas de esta sección se describe cómo procesar (actualizar) o cambiar los datos que se han importado en un modelo.</span><span class="sxs-lookup"><span data-stu-id="64efd-118">Tasks in this section describe how to process (refresh) or change data that has already been imported into a model.</span></span>|  
|[<span data-ttu-id="64efd-119">Editar una conexión de origen de datos existente &#40;SSAS tabular&#41;</span><span class="sxs-lookup"><span data-stu-id="64efd-119">Edit an Existing Data Source Connection &#40;SSAS Tabular&#41;</span></span>](edit-an-existing-data-source-connection-ssas-tabular.md)|<span data-ttu-id="64efd-120">Describe cómo modificar una conexión a un origen de datos que se ha creado y se ha utilizado previamente para importar datos de un origen.</span><span class="sxs-lookup"><span data-stu-id="64efd-120">Describes how to edit a data source connection that has already been created and used to import data from a source.</span></span>|  
  
  
