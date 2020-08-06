---
title: 'Lección 2: generar una estructura de distribución de correo directo (tutorial básico de minería de datos) | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 9d0d6ceb-49b5-47c7-9ee6-464da43cc1f6
author: minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: 005baa09e802a9ffe98f87239070401f170ddfa9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87662430"
---
# <a name="lesson-2-building-a-targeted-mailing-structure-basic-data-mining-tutorial"></a><span data-ttu-id="e49c4-102">Lección 2: Generar una estructura de distribución de correo directo (Tutorial básico de minería de datos)</span><span class="sxs-lookup"><span data-stu-id="e49c4-102">Lesson 2: Building a Targeted Mailing Structure (Basic Data Mining Tutorial)</span></span>
  <span data-ttu-id="e49c4-103">El departamento de marketing de [!INCLUDE[ssSampleDBCoFull](../includes/sssampledbcofull-md.md)] desea aumentar las ventas dirigiendo una campaña de correo directo a clientes específicos.</span><span class="sxs-lookup"><span data-stu-id="e49c4-103">The Marketing department of [!INCLUDE[ssSampleDBCoFull](../includes/sssampledbcofull-md.md)] wants to increase sales by targeting specific customers for a mailing campaign.</span></span> <span data-ttu-id="e49c4-104">La base de datos de la empresa contiene una lista de clientes antiguos y otra de nuevos clientes potenciales.</span><span class="sxs-lookup"><span data-stu-id="e49c4-104">The company's database contains a list of past customers and a list of potential new customers.</span></span> <span data-ttu-id="e49c4-105">Mediante el análisis de los atributos de clientes anteriores, la empresa espera detectar los patrones que posteriormente se aplicarán a los clientes potenciales.</span><span class="sxs-lookup"><span data-stu-id="e49c4-105">By investigating the attributes of previous customers, the company hopes to discover patterns that they can then apply to potential customers.</span></span> <span data-ttu-id="e49c4-106">Por ejemplo, podrían usar tendencias anteriores para predecir qué clientes potenciales tienen más probabilidades de comprar una bicicleta [!INCLUDE[ssSampleDBCoFull](../includes/sssampledbcofull-md.md)] , o crear segmentos de clientes para campañas de marketing futuras.</span><span class="sxs-lookup"><span data-stu-id="e49c4-106">For example, they might use past trends to predict which potential customers are most likely to purchase a bike from [!INCLUDE[ssSampleDBCoFull](../includes/sssampledbcofull-md.md)], or create customer segments for future marketing campaigns.</span></span>  
  
 <span data-ttu-id="e49c4-107">En esta lección utilizará el **Asistente para minería de datos** para crear la estructura de distribución de correo directo.</span><span class="sxs-lookup"><span data-stu-id="e49c4-107">In this lesson you will use the **Data Mining Wizard** to create the targeted mailing structure.</span></span> <span data-ttu-id="e49c4-108">Después de completar las tareas de esta lección, tendrá una estructura de minería de datos con un modelo sencillo.</span><span class="sxs-lookup"><span data-stu-id="e49c4-108">After you complete the tasks in this lesson, you will have a mining structure with a single model.</span></span> <span data-ttu-id="e49c4-109">Dado que la creación de una estructura conlleva muchos pasos y conceptos importantes, hemos separado este proceso en las tres tareas siguientes:</span><span class="sxs-lookup"><span data-stu-id="e49c4-109">Because there are many steps and important concepts involved in creating a structure, we have separated this process into the following three tasks:</span></span>  
  
 [<span data-ttu-id="e49c4-110">Crear una estructura de modelo de minería de datos de destino &#40;tutorial básico de minería de datos&#41;</span><span class="sxs-lookup"><span data-stu-id="e49c4-110">Creating a Targeted Mailing Mining Model Structure &#40;Basic Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/creating-a-targeted-mailing-mining-model-structure-basic-data-mining-tutorial.md)  
  
 [<span data-ttu-id="e49c4-111">Especificar el tipo de datos y el tipo de contenido &#40;tutorial básico de minería de datos&#41;</span><span class="sxs-lookup"><span data-stu-id="e49c4-111">Specifying the Data Type and Content Type &#40;Basic Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/specifying-the-data-type-and-content-type-basic-data-mining-tutorial.md)  
  
 [<span data-ttu-id="e49c4-112">Especificar un conjunto de datos de prueba para la estructura &#40;tutorial básico de minería de datos&#41;</span><span class="sxs-lookup"><span data-stu-id="e49c4-112">Specifying a Testing Data Set for the Structure &#40;Basic Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/specifying-a-testing-data-set-for-the-structure-basic-data-mining-tutorial.md)  
  
## <a name="first-task-in-lesson"></a><span data-ttu-id="e49c4-113">Primera tarea de la lección</span><span class="sxs-lookup"><span data-stu-id="e49c4-113">First Task in Lesson</span></span>  
 [<span data-ttu-id="e49c4-114">Crear una estructura de modelo de minería de datos de destino &#40;tutorial básico de minería de datos&#41;</span><span class="sxs-lookup"><span data-stu-id="e49c4-114">Creating a Targeted Mailing Mining Model Structure &#40;Basic Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/creating-a-targeted-mailing-mining-model-structure-basic-data-mining-tutorial.md)  
  
## <a name="previous-lesson"></a><span data-ttu-id="e49c4-115">Lección anterior</span><span class="sxs-lookup"><span data-stu-id="e49c4-115">Previous Lesson</span></span>  
 [<span data-ttu-id="e49c4-116">Lección 1: preparar la base de datos de Analysis Services &#40;tutorial básico de minería de datos&#41;</span><span class="sxs-lookup"><span data-stu-id="e49c4-116">Lesson 1: Preparing the Analysis Services Database &#40;Basic Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/lesson-1-preparing-the-analysis-services-database-basic-data-mining-tutorial.md)  
  
## <a name="next--lesson"></a><span data-ttu-id="e49c4-117">Lección siguiente</span><span class="sxs-lookup"><span data-stu-id="e49c4-117">Next  Lesson</span></span>  
 [<span data-ttu-id="e49c4-118">Lección 3: Adición y procesamiento de modelos</span><span class="sxs-lookup"><span data-stu-id="e49c4-118">Lesson 3: Adding and Processing Models</span></span>](../../2014/tutorials/lesson-3-adding-and-processing-models.md)  
  
## <a name="see-also"></a><span data-ttu-id="e49c4-119">Consulte también</span><span class="sxs-lookup"><span data-stu-id="e49c4-119">See Also</span></span>  
 <span data-ttu-id="e49c4-120">[Crear la estructura de minería de datos &#40;Asistente para minería de datos&#41;](../../2014/analysis-services/create-the-data-mining-structure-data-mining-wizard.md) </span><span class="sxs-lookup"><span data-stu-id="e49c4-120">[Create the Data Mining Structure &#40;Data Mining Wizard&#41;](../../2014/analysis-services/create-the-data-mining-structure-data-mining-wizard.md) </span></span>  
 [<span data-ttu-id="e49c4-121">Crear una estructura de minería de datos relacional</span><span class="sxs-lookup"><span data-stu-id="e49c4-121">Create a Relational Mining Structure</span></span>](../../2014/analysis-services/data-mining/create-a-relational-mining-structure.md)  
  
  
