---
title: Especificar tipos de tablas (Asistente para minería de datos) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.dm.dmwizard.specifytabletypes.f1
ms.assetid: 8209a707-faef-4ffc-8991-6c13bb350753
author: minewiskan
ms.author: owend
ms.openlocfilehash: 88c09f26958c37ed0a99efb54a5eb5c08505d16b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87675540"
---
# <a name="specify-table-types-data-mining-wizard"></a><span data-ttu-id="d5722-102">Especificar tipos de tablas (Asistente para minería de datos)</span><span class="sxs-lookup"><span data-stu-id="d5722-102">Specify Table Types (Data Mining Wizard)</span></span>
  <span data-ttu-id="d5722-103">Utilice la página **Especificar tipos de tablas** para identificar las tablas que se van a utilizar para definir la estructura de minería de datos.</span><span class="sxs-lookup"><span data-stu-id="d5722-103">Use the **Specify Table Types** page to identify the tables to use to define the mining structure.</span></span> <span data-ttu-id="d5722-104">Si una tabla no está seleccionada, ésta no se utilizará para definir la estructura de minería de datos.</span><span class="sxs-lookup"><span data-stu-id="d5722-104">If a table is not selected, it will not be used to define the mining structure.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="d5722-105">Puede agregar tablas posteriormente desde la pestaña **Estructura de minería de datos** del **Diseñador de minería de datos**.</span><span class="sxs-lookup"><span data-stu-id="d5722-105">You can add tables later from the **Mining Structure** tab in **Data Mining Designer**.</span></span>  
  
 <span data-ttu-id="d5722-106">**Para más información:** [Tablas anidadas &#40;Analysis Services - Minería de datos&#41;](data-mining/nested-tables-analysis-services-data-mining.md), [Asistente para minería de datos &#40;Analysis Services - Minería de datos&#41;](data-mining/data-mining-wizard-analysis-services-data-mining.md), [Crear una estructura de minería de datos relacional](data-mining/create-a-relational-mining-structure.md)</span><span class="sxs-lookup"><span data-stu-id="d5722-106">**For More Information:** [Nested Tables &#40;Analysis Services - Data Mining&#41;](data-mining/nested-tables-analysis-services-data-mining.md), [Data Mining Wizard &#40;Analysis Services - Data Mining&#41;](data-mining/data-mining-wizard-analysis-services-data-mining.md), [Create a Relational Mining Structure](data-mining/create-a-relational-mining-structure.md)</span></span>  
  
## <a name="options"></a><span data-ttu-id="d5722-107">Opciones</span><span class="sxs-lookup"><span data-stu-id="d5722-107">Options</span></span>  
 <span data-ttu-id="d5722-108">**Tablas**</span><span class="sxs-lookup"><span data-stu-id="d5722-108">**Tables**</span></span>  
 <span data-ttu-id="d5722-109">Muestra las tablas de la vista del origen de datos que ha seleccionado en la página **Seleccionar vista del origen de datos** del asistente.</span><span class="sxs-lookup"><span data-stu-id="d5722-109">Displays the tables in the data source view that you selected on the **Select Data Source View** page of the wizard.</span></span>  
  
 <span data-ttu-id="d5722-110">**Y**</span><span class="sxs-lookup"><span data-stu-id="d5722-110">**Case**</span></span>  
 <span data-ttu-id="d5722-111">Seleccione una tabla para utilizar como la tabla de casos.</span><span class="sxs-lookup"><span data-stu-id="d5722-111">Select one table to use as the case table.</span></span>  
  
 <span data-ttu-id="d5722-112">**Anidado**</span><span class="sxs-lookup"><span data-stu-id="d5722-112">**Nested**</span></span>  
 <span data-ttu-id="d5722-113">Seleccione las tablas que se van a utilizar como tablas anidadas.</span><span class="sxs-lookup"><span data-stu-id="d5722-113">Select the tables to use as nested tables.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="d5722-114">Estas tablas deben tener una relación de varios a uno con la tabla de casos, no una relación de uno a varios.</span><span class="sxs-lookup"><span data-stu-id="d5722-114">These tables must have a many-to-one relationship with the case table, not a one-to-many relationship.</span></span> <span data-ttu-id="d5722-115">Debe especificar esta relación en la vista del origen de datos para poder seleccionar la tabla como anidada.</span><span class="sxs-lookup"><span data-stu-id="d5722-115">You must specify this relationship in the data source view before you can select the table as nested.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d5722-116">Consulte también</span><span class="sxs-lookup"><span data-stu-id="d5722-116">See Also</span></span>  
 <span data-ttu-id="d5722-117">[Asistente para minería de datos (ayuda F1) &#40;Analysis Services: minería de datos&#41;](data-mining-wizard-f1-help-analysis-services-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="d5722-117">[Data Mining Wizard F1 Help &#40;Analysis Services - Data Mining&#41;](data-mining-wizard-f1-help-analysis-services-data-mining.md) </span></span>  
 <span data-ttu-id="d5722-118">[Seleccionar vista del origen de datos &#40;Asistente para minería de datos&#41;](select-data-source-view-data-mining-wizard.md) </span><span class="sxs-lookup"><span data-stu-id="d5722-118">[Select Data Source View &#40;Data Mining Wizard&#41;](select-data-source-view-data-mining-wizard.md) </span></span>  
 [<span data-ttu-id="d5722-119">Especificar los datos de entrenamiento &#40;Asistente para minería de datos&#41;</span><span class="sxs-lookup"><span data-stu-id="d5722-119">Specify the Training Data &#40;Data Mining Wizard&#41;</span></span>](specify-the-training-data-data-mining-wizard.md)  
  
  
