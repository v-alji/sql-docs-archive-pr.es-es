---
title: Especificar información de origen (Asistente para dimensiones) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.dimensionwizard.dimensionmaintable.f1
ms.assetid: 0538b490-5185-49e1-a783-4ce3539a0de5
author: minewiskan
ms.author: owend
ms.openlocfilehash: 99bbaac0bdf24a18dcde455e779f056b98106dc4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87675543"
---
# <a name="specify-source-information-dimension-wizard"></a><span data-ttu-id="85d72-102">Especificar información de origen (Asistente para dimensiones)</span><span class="sxs-lookup"><span data-stu-id="85d72-102">Specify Source Information (Dimension Wizard)</span></span>
  <span data-ttu-id="85d72-103">Use la página **Seleccionar la tabla de dimensiones principal** para seleccionar la vista del origen de datos, la tabla de dimensiones principal, las columnas de clave y la columna de nombre de miembro para la dimensión que se va a crear.</span><span class="sxs-lookup"><span data-stu-id="85d72-103">Use the **Select the Main Dimension Table** page to select the data source view, main dimension table, key columns, and member name column for the dimension to be created.</span></span>  
  
 <span data-ttu-id="85d72-104">**Para abrir el Asistente para dimensiones**</span><span class="sxs-lookup"><span data-stu-id="85d72-104">**To open the Dimension Wizard**</span></span>  
  
-   <span data-ttu-id="85d72-105">En [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], en el **Explorador de soluciones**, haga clic con el botón derecho en la carpeta **Dimensiones** para un proyecto de [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] y, luego, haga clic en **Nueva dimensión**.</span><span class="sxs-lookup"><span data-stu-id="85d72-105">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], in **Solution Explorer**, right-click the **Dimensions** folder for an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] project, and then click **New Dimension**.</span></span>  
  
## <a name="options"></a><span data-ttu-id="85d72-106">Opciones</span><span class="sxs-lookup"><span data-stu-id="85d72-106">Options</span></span>  
 <span data-ttu-id="85d72-107">**Vista del origen de datos**</span><span class="sxs-lookup"><span data-stu-id="85d72-107">**Data source view**</span></span>  
 <span data-ttu-id="85d72-108">Seleccione una vista del origen de datos.</span><span class="sxs-lookup"><span data-stu-id="85d72-108">Select a data source view.</span></span>  
  
 <span data-ttu-id="85d72-109">**Tabla principal**</span><span class="sxs-lookup"><span data-stu-id="85d72-109">**Main table**</span></span>  
 <span data-ttu-id="85d72-110">Seleccione una tabla en la vista de origen de datos seleccionada para utilizarla como tabla principal para la dimensión.</span><span class="sxs-lookup"><span data-stu-id="85d72-110">Select a table from the selected data source view to use as the main table for the dimension.</span></span>  
  
 <span data-ttu-id="85d72-111">**Columnas de clave**</span><span class="sxs-lookup"><span data-stu-id="85d72-111">**Key columns**</span></span>  
 <span data-ttu-id="85d72-112">Seleccione las columnas de clave de la tabla especificada en **Tabla principal** para obtener el atributo clave de la dimensión.</span><span class="sxs-lookup"><span data-stu-id="85d72-112">Select the key columns from the table specified in **Main table** for the key attribute of the dimension.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="85d72-113">Se puede seleccionar más de una columna.</span><span class="sxs-lookup"><span data-stu-id="85d72-113">More than one column can be selected.</span></span> <span data-ttu-id="85d72-114">Si la tabla contiene una clave principal compuesta, seleccione todas las columnas incluidas en la clave principal compuesta.</span><span class="sxs-lookup"><span data-stu-id="85d72-114">If the table contains a composite primary key, select all the columns included in the composite primary key.</span></span> <span data-ttu-id="85d72-115">El orden de las columnas de clave es importante.</span><span class="sxs-lookup"><span data-stu-id="85d72-115">The order of the key columns is important.</span></span>  
  
 <span data-ttu-id="85d72-116">**Columna de nombre**</span><span class="sxs-lookup"><span data-stu-id="85d72-116">**Name column**</span></span>  
 <span data-ttu-id="85d72-117">Seleccione la columna de la tabla especificada en **Tabla principal** que proporciona los nombres de los miembros para la dimensión.</span><span class="sxs-lookup"><span data-stu-id="85d72-117">Select the column from the table specified in **Main table** that provides the member names for the dimension.</span></span> <span data-ttu-id="85d72-118">Cuando se usa una clave compuesta, se debe especificar una columna de nombre.</span><span class="sxs-lookup"><span data-stu-id="85d72-118">A name column must be specified when a composite key is used.</span></span> <span data-ttu-id="85d72-119">Para crear una columna de nombre para una clave compuesta, recomendamos que cree un cálculo con nombre en la vista del origen de datos que concatena las columnas de clave especificadas.</span><span class="sxs-lookup"><span data-stu-id="85d72-119">To create a name column for a composite key, we recommend that you create a named calculation in the data source view that concatenates the specified key columns.</span></span> <span data-ttu-id="85d72-120">Cuando se usa una clave única, la columna de nombre es opcional.</span><span class="sxs-lookup"><span data-stu-id="85d72-120">When a single key is used, the name column is optional.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="85d72-121">Consulte también</span><span class="sxs-lookup"><span data-stu-id="85d72-121">See Also</span></span>  
 <span data-ttu-id="85d72-122">[Asistente para dimensiones (ayuda F1)](dimension-wizard-f1-help.md) </span><span class="sxs-lookup"><span data-stu-id="85d72-122">[Dimension Wizard F1 Help](dimension-wizard-f1-help.md) </span></span>  
 <span data-ttu-id="85d72-123">[Dimensiones &#40;Analysis Services de datos multidimensionales&#41;](multidimensional-models-olap-logical-dimension-objects/dimensions-analysis-services-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="85d72-123">[Dimensions &#40;Analysis Services - Multidimensional Data&#41;](multidimensional-models-olap-logical-dimension-objects/dimensions-analysis-services-multidimensional-data.md) </span></span>  
 [<span data-ttu-id="85d72-124">Dimensiones en modelos multidimensionales</span><span class="sxs-lookup"><span data-stu-id="85d72-124">Dimensions in Multidimensional Models</span></span>](multidimensional-models/dimensions-in-multidimensional-models.md)  
  
  
