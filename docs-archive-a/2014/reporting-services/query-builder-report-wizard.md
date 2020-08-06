---
title: Generador de consultas (Asistente para informes) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
f1_keywords:
- sql12.rtp.rptdesigner.dataview.vdtquerydesigner.f1
- sql12.rtp.rptwizard.querybuilder.f1
helpviewer_keywords:
- Query Builder [Reporting Services]
ms.assetid: 1b0904ea-28c1-448e-b56c-c0fdfbc8b222
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 34369bc72fadae75afbc93eb03c0e40509dd27a4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87662634"
---
# <a name="query-builder-report-wizard"></a><span data-ttu-id="6ecbc-102">Generador de consultas (Asistente para informes)</span><span class="sxs-lookup"><span data-stu-id="6ecbc-102">Query Builder (Report Wizard)</span></span>
  <span data-ttu-id="6ecbc-103">Utilice el Generador de consultas para especificar una consulta que recupera un conjunto de resultados para utilizarlo en un informe.</span><span class="sxs-lookup"><span data-stu-id="6ecbc-103">Use the Query Builder to specify a query that retrieves a result set to use in a report.</span></span> <span data-ttu-id="6ecbc-104">Puede elegir entre dos generadores de consultas:</span><span class="sxs-lookup"><span data-stu-id="6ecbc-104">You can choose between two query builders:</span></span>  
  
-   <span data-ttu-id="6ecbc-105">El generador de consultas basado en texto (predeterminado) proporciona un área de trabajo sencilla para especificar una consulta y ver los resultados.</span><span class="sxs-lookup"><span data-stu-id="6ecbc-105">The text-based query builder (default) provides a simple workspace for specifying a query and viewing the results.</span></span> <span data-ttu-id="6ecbc-106">Puede especificar varias sintaxis de consulta, comandos o instrucciones [!INCLUDE[tsql](../includes/tsql-md.md)] para extensiones de procesamiento de datos personalizadas, y consultas que se especifican como expresiones.</span><span class="sxs-lookup"><span data-stu-id="6ecbc-106">You can specify multiple [!INCLUDE[tsql](../includes/tsql-md.md)] statements, query or command syntax for custom data processing extensions, and queries that are specified as expressions.</span></span> <span data-ttu-id="6ecbc-107">Dado que el generador de consultas genérico no procesa previamente la consulta y puede dar cabida a todo tipo de sintaxis de consulta, es la herramienta de generación de consultas predeterminada para el Diseñador de informes.</span><span class="sxs-lookup"><span data-stu-id="6ecbc-107">Because the generic query builder does not preprocess the query and can accommodate any kind of query syntax, it is the default query builder tool for Report Designer.</span></span>  
  
-   <span data-ttu-id="6ecbc-108">El generador de consultas gráfico proporciona una experiencia visual más rica.</span><span class="sxs-lookup"><span data-stu-id="6ecbc-108">The graphical query builder provides a richer visual experience.</span></span> <span data-ttu-id="6ecbc-109">Se utiliza en [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] y en otras partes de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6ecbc-109">It is used in [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] and in other parts of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="6ecbc-110">Puede utilizar el generador de consultas gráfico si no está creando expresiones o instrucciones SQL formadas por varias partes.</span><span class="sxs-lookup"><span data-stu-id="6ecbc-110">You can use the graphical query builder if you are not creating expressions or multi-part SQL statements.</span></span>  
  
     <span data-ttu-id="6ecbc-111">Para cambiar al generador de consultas gráfico, alterne la activación del botón **Editar como texto** en la esquina superior izquierda de la ventana.</span><span class="sxs-lookup"><span data-stu-id="6ecbc-111">To switch to the graphical query builder, toggle the **Edit As Text** button in the top left corner of the window.</span></span>  
  
 <span data-ttu-id="6ecbc-112">También puede importar una consulta de otro informe.</span><span class="sxs-lookup"><span data-stu-id="6ecbc-112">You can also import a query from another report.</span></span>  
  
## <a name="query-builder-options"></a><span data-ttu-id="6ecbc-113">Opciones del generador de consultas</span><span class="sxs-lookup"><span data-stu-id="6ecbc-113">Query Builder Options</span></span>  
 <span data-ttu-id="6ecbc-114">**Editar como texto**</span><span class="sxs-lookup"><span data-stu-id="6ecbc-114">**Edit As Text**</span></span>  
 <span data-ttu-id="6ecbc-115">Alterna entre el diseñador de consultas basado en texto y el diseñador gráfico de consultas, si ambos van a funcionar para la consulta.</span><span class="sxs-lookup"><span data-stu-id="6ecbc-115">Toggles between the text-based and graphical query designers, if both will work for the query.</span></span>  
  
 <span data-ttu-id="6ecbc-116">**Importar**</span><span class="sxs-lookup"><span data-stu-id="6ecbc-116">**Import**</span></span>  
 <span data-ttu-id="6ecbc-117">Abre el cuadro de diálogo **Importar consulta** y muestra los archivos .rdl y .sql de cualquier informe disponible.</span><span class="sxs-lookup"><span data-stu-id="6ecbc-117">Opens the **Import Query** dialog box and displays .rdl and .sql files for any available report.</span></span> <span data-ttu-id="6ecbc-118">Puede utilizar la consulta importada tal cual o modificarla en el generador de consultas.</span><span class="sxs-lookup"><span data-stu-id="6ecbc-118">You can use the imported query as it is, or you can modify it in the query builder.</span></span>  
  
 <span data-ttu-id="6ecbc-119">**! (Ejecutar)**</span><span class="sxs-lookup"><span data-stu-id="6ecbc-119">**! (Run)**</span></span>  
 <span data-ttu-id="6ecbc-120">Ejecuta la consulta y devuelve un conjunto de resultados si la consulta es válida.</span><span class="sxs-lookup"><span data-stu-id="6ecbc-120">Runs the query and returns a result set if the query is valid.</span></span> <span data-ttu-id="6ecbc-121">Tenga en cuenta que no puede ejecutar la consulta si se trata de una expresión.</span><span class="sxs-lookup"><span data-stu-id="6ecbc-121">Note that you cannot execute the query if it is an expression.</span></span> <span data-ttu-id="6ecbc-122">Para comprobar una consulta basada en una expresión, debe generar una vista previa del informe.</span><span class="sxs-lookup"><span data-stu-id="6ecbc-122">To verify an expression-based query, you must preview the report.</span></span>  
  
 <span data-ttu-id="6ecbc-123">**Tipo de comando**</span><span class="sxs-lookup"><span data-stu-id="6ecbc-123">**Command type**</span></span>  
 <span data-ttu-id="6ecbc-124">Especifica texto, procedimiento almacenado o tabla directa.</span><span class="sxs-lookup"><span data-stu-id="6ecbc-124">Specifies text, stored procedure, or table direct.</span></span> <span data-ttu-id="6ecbc-125">La disponibilidad de un tipo de comando depende de la extensión de procesamiento de datos especificada.</span><span class="sxs-lookup"><span data-stu-id="6ecbc-125">Availability of a command type depends on the data processing extension you specified.</span></span>  
  
 <span data-ttu-id="6ecbc-126">**Panel consulta**</span><span class="sxs-lookup"><span data-stu-id="6ecbc-126">**Query pane**</span></span>  
 <span data-ttu-id="6ecbc-127">Escriba la consulta.</span><span class="sxs-lookup"><span data-stu-id="6ecbc-127">Type the query.</span></span>  
  
 <span data-ttu-id="6ecbc-128">**Panel de resultados**</span><span class="sxs-lookup"><span data-stu-id="6ecbc-128">**Result pane**</span></span>  
 <span data-ttu-id="6ecbc-129">Muestra el conjunto de resultados que devuelve la consulta.</span><span class="sxs-lookup"><span data-stu-id="6ecbc-129">Shows the result set returned from the query.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6ecbc-130">Consulte también</span><span class="sxs-lookup"><span data-stu-id="6ecbc-130">See Also</span></span>  
 <span data-ttu-id="6ecbc-131">[Conjuntos de valores integrados de informe y conjuntos de recursos compartidos &#40;Generador de informes y SSRS&#41;](report-data/report-embedded-datasets-and-shared-datasets-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="6ecbc-131">[Report Embedded Datasets and Shared Datasets &#40;Report Builder and SSRS&#41;](report-data/report-embedded-datasets-and-shared-datasets-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="6ecbc-132">Ayuda del Asistente para informes</span><span class="sxs-lookup"><span data-stu-id="6ecbc-132">Report Wizard Help</span></span>](../../2014/reporting-services/report-wizard-help.md)  
  
  
