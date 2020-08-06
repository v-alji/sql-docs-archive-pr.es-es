---
title: Propiedades de la tabla (SSAS tabular) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.bidtoolset.tableprop.f1
ms.assetid: 16d3347b-7e43-4a6b-9956-fdd6ede092e6
author: minewiskan
ms.author: owend
ms.openlocfilehash: 9613609c42de8fd3a4aab7aec3208dfe3d31be4a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87748935"
---
# <a name="table-properties-ssas-tabular"></a><span data-ttu-id="3193f-102">Propiedades de la tabla (SSAS tabular)</span><span class="sxs-lookup"><span data-stu-id="3193f-102">Table Properties (SSAS Tabular)</span></span>
  <span data-ttu-id="3193f-103">En este tema se describen las propiedades de la tabla del modelo.</span><span class="sxs-lookup"><span data-stu-id="3193f-103">This topic describes tabular model table properties.</span></span> <span data-ttu-id="3193f-104">Las propiedades que se describen aquí son diferentes de las del cuadro de diálogo Editar propiedades de tabla, que definen qué columnas del origen se importan.</span><span class="sxs-lookup"><span data-stu-id="3193f-104">The properties described here are different from those in the Edit Table Properties dialog box, which define which columns from the source are imported.</span></span>  
  
 <span data-ttu-id="3193f-105">Secciones de este tema:</span><span class="sxs-lookup"><span data-stu-id="3193f-105">Sections in this topic:</span></span>  
  
-   [<span data-ttu-id="3193f-106">Propiedades de la tabla</span><span class="sxs-lookup"><span data-stu-id="3193f-106">Table Properties</span></span>](#bkmk_properties)  
  
-   [<span data-ttu-id="3193f-107">Para configurar los valores de las propiedades de la tabla</span><span class="sxs-lookup"><span data-stu-id="3193f-107">To configure table property settings</span></span>](#bkmk_config_prop)  
  
##  <a name="table-properties"></a><a name="bkmk_properties"></a><span data-ttu-id="3193f-108">Propiedades de la tabla</span><span class="sxs-lookup"><span data-stu-id="3193f-108">Table Properties</span></span>  
 <span data-ttu-id="3193f-109">**Basic**</span><span class="sxs-lookup"><span data-stu-id="3193f-109">**Basic**</span></span>  
  
|<span data-ttu-id="3193f-110">Propiedad</span><span class="sxs-lookup"><span data-stu-id="3193f-110">Property</span></span>|<span data-ttu-id="3193f-111">Valor predeterminado</span><span class="sxs-lookup"><span data-stu-id="3193f-111">Default Setting</span></span>|<span data-ttu-id="3193f-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="3193f-112">Description</span></span>|  
|--------------|---------------------|-----------------|  
|<span data-ttu-id="3193f-113">**Nombre de la conexión**</span><span class="sxs-lookup"><span data-stu-id="3193f-113">**Connection Name**</span></span>|\<connection name>|<span data-ttu-id="3193f-114">Nombre de la conexión con el origen de datos de la tabla.</span><span class="sxs-lookup"><span data-stu-id="3193f-114">The name of the connection to the table's data source.</span></span><br /><br /> <span data-ttu-id="3193f-115">Para modificar la conexión, haga clic en el botón.</span><span class="sxs-lookup"><span data-stu-id="3193f-115">To edit the connection, click the button.</span></span>|  
|<span data-ttu-id="3193f-116">**Oculto**</span><span class="sxs-lookup"><span data-stu-id="3193f-116">**Hidden**</span></span>|<span data-ttu-id="3193f-117">False</span><span class="sxs-lookup"><span data-stu-id="3193f-117">False</span></span>|<span data-ttu-id="3193f-118">Especifica si la tabla se oculta en las listas de campos del cliente de informes.</span><span class="sxs-lookup"><span data-stu-id="3193f-118">Specifies whether the table is hidden from reporting client field lists.</span></span>|  
|<span data-ttu-id="3193f-119">**Particiones**</span><span class="sxs-lookup"><span data-stu-id="3193f-119">**Partitions**</span></span>||<span data-ttu-id="3193f-120">Las particiones de la tabla no se muestran en la ventana **Propiedades** .</span><span class="sxs-lookup"><span data-stu-id="3193f-120">Partitions for the table cannot be displayed in the **Properties** window.</span></span> <span data-ttu-id="3193f-121">Para ver, crear o modificar las particiones, haga clic en el botón para abrir el Administrador de particiones.</span><span class="sxs-lookup"><span data-stu-id="3193f-121">To view, create, or edit partitions, click the button to open the Partition Manager.</span></span>|  
|<span data-ttu-id="3193f-122">**Datos de origen**</span><span class="sxs-lookup"><span data-stu-id="3193f-122">**Source Data**</span></span>||<span data-ttu-id="3193f-123">El origen de datos de la tabla no se pueden mostrar en la ventana **Propiedades** .</span><span class="sxs-lookup"><span data-stu-id="3193f-123">Source data for the table cannot be displayed in the **Properties** window.</span></span> <span data-ttu-id="3193f-124">Para ver o modificar los datos de origen, haga clic en el botón para abrir el cuadro de diálogo Editar propiedades de tabla.</span><span class="sxs-lookup"><span data-stu-id="3193f-124">To view or edit the source data, click the button to open the Edit Table Properties dialog box.</span></span>|  
|<span data-ttu-id="3193f-125">**Descripción de tabla**</span><span class="sxs-lookup"><span data-stu-id="3193f-125">**Table Description**</span></span>||<span data-ttu-id="3193f-126">Descripción de la tabla.</span><span class="sxs-lookup"><span data-stu-id="3193f-126">A text description for the table.</span></span><br /><br /> <span data-ttu-id="3193f-127">En [!INCLUDE[ssGeminiClient](../../includes/ssgeminiclient-md.md)], si un usuario final coloca el cursor sobre esta tabla en la lista de campos, aparece la descripción como una información sobre herramientas.</span><span class="sxs-lookup"><span data-stu-id="3193f-127">In [!INCLUDE[ssGeminiClient](../../includes/ssgeminiclient-md.md)], if an end-user places the cursor over this table in the field list, the description appears as a tooltip.</span></span>|  
|<span data-ttu-id="3193f-128">**Nombre de tabla**</span><span class="sxs-lookup"><span data-stu-id="3193f-128">**Table Name**</span></span>|\<friendly name>|<span data-ttu-id="3193f-129">Especifica el nombre descriptivo de la tabla.</span><span class="sxs-lookup"><span data-stu-id="3193f-129">Specifies the table's friendly name.</span></span> <span data-ttu-id="3193f-130">El nombre de tabla puede especificar cuándo se importa una tabla con el Asistente para la importación de tablas o en cualquier momento después de la importación.</span><span class="sxs-lookup"><span data-stu-id="3193f-130">The table name can be specified when a table is imported using the Table Import Wizard or at any time after import.</span></span> <span data-ttu-id="3193f-131">El nombre de tabla en el modelo puede ser diferente de la tabla asociada en el origen.</span><span class="sxs-lookup"><span data-stu-id="3193f-131">The table name in the model can be different from the associated table at the source.</span></span> <span data-ttu-id="3193f-132">El nombre descriptivo de la tabla aparece en la lista de campos de la aplicación cliente de informes como en la base de datos modelo en [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3193f-132">The table friendly name appears in the reporting client application field list as well as in the model database in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>|  
  
 <span data-ttu-id="3193f-133">**Propiedades de informes**</span><span class="sxs-lookup"><span data-stu-id="3193f-133">**Reporting Properties**</span></span>  
  
 <span data-ttu-id="3193f-134">Para obtener descripciones detalladas e información sobre la configuración de propiedades de informes, vea [Propiedades de informes de Vista avanzada &#40;SSAS tabular&#41;](properties-ssas-tabular.md).</span><span class="sxs-lookup"><span data-stu-id="3193f-134">For detailed descriptions and configuration information for reporting properties, see [Power View Reporting Properties &#40;SSAS Tabular&#41;](properties-ssas-tabular.md).</span></span>  
  
|<span data-ttu-id="3193f-135">Propiedad</span><span class="sxs-lookup"><span data-stu-id="3193f-135">Property</span></span>|<span data-ttu-id="3193f-136">Valor predeterminado</span><span class="sxs-lookup"><span data-stu-id="3193f-136">Default Setting</span></span>|<span data-ttu-id="3193f-137">Descripción</span><span class="sxs-lookup"><span data-stu-id="3193f-137">Description</span></span>|  
|--------------|---------------------|-----------------|  
|<span data-ttu-id="3193f-138">**Conjunto de campos predeterminado**</span><span class="sxs-lookup"><span data-stu-id="3193f-138">**Default Field Set**</span></span>|||  
|<span data-ttu-id="3193f-139">Comportamiento de tabla</span><span class="sxs-lookup"><span data-stu-id="3193f-139">Table Behavior</span></span>|||  
  
###  <a name="to-configure-table-property-settings"></a><a name="bkmk_config_prop"></a><span data-ttu-id="3193f-140">Para configurar los valores de las propiedades de tabla</span><span class="sxs-lookup"><span data-stu-id="3193f-140">To configure table property settings</span></span>  
  
1.  <span data-ttu-id="3193f-141">En el diseñador de modelos, en la vista de datos, haga clic en una tabla (pestaña), o bien, en la vista de diagramas, haga clic en un encabezado de tabla.</span><span class="sxs-lookup"><span data-stu-id="3193f-141">In the model designer, in Data View, click a table (tab), or, in Diagram View, click a table header.</span></span>  
  
2.  <span data-ttu-id="3193f-142">En la ventana **Propiedades** , haga clic en una propiedad y, a continuación, escriba un valor o haga clic en el botón de opciones de configuración adicionales.</span><span class="sxs-lookup"><span data-stu-id="3193f-142">In the **Properties** window, click on a property, and then type a value or click the button for additional configuration options.</span></span>  
  
  
