---
title: Esquematización de código
ms.custom: seo-lt-2019
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- Query Editor [SQL Server Management Studio], outlining code
- Query Editor [SQL Server Management Studio], hiding code
ms.assetid: 556c7dfe-7bc8-4cab-a36f-2b753a05d3f1
author: rothja
ms.author: jroth
ms.openlocfilehash: 0a142ca8fbdcdfcfbfd1b71de06c0b0fd4c5339c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87671451"
---
# <a name="code-outlining"></a><span data-ttu-id="068d9-102">Esquematización de código</span><span class="sxs-lookup"><span data-stu-id="068d9-102">Code Outlining</span></span>
  <span data-ttu-id="068d9-103">Puede usar la característica de esquematización de los editores de consultas de [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] para ocultar selectivamente el código mientras modifica las consultas.</span><span class="sxs-lookup"><span data-stu-id="068d9-103">You can use the outlining feature in the [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] query editors to selectively hide code when you edit queries.</span></span> <span data-ttu-id="068d9-104">Esto permite ver más fácilmente el código en el que se está trabajando, sobre todo en archivos de consulta de gran tamaño.</span><span class="sxs-lookup"><span data-stu-id="068d9-104">This enables you to more easily view the code you are working on, especially in large query files.</span></span>

## <a name="outlining-overview"></a><span data-ttu-id="068d9-105">Información general sobre la esquematización</span><span class="sxs-lookup"><span data-stu-id="068d9-105">Outlining Overview</span></span>
 <span data-ttu-id="068d9-106">De forma predeterminada, todo el código está visible al abrir una ventana de un editor de consultas.</span><span class="sxs-lookup"><span data-stu-id="068d9-106">By default, all code is visible when you open a query editor window.</span></span> <span data-ttu-id="068d9-107">Las regiones de código se pueden contraer para ocultarlas.</span><span class="sxs-lookup"><span data-stu-id="068d9-107">Regions of the code can be collapsed to hide it from view.</span></span> <span data-ttu-id="068d9-108">En el borde izquierdo de la ventana del editor, se ve una línea vertical que muestra un cuadrado con un signo menos (-) para identificar el inicio de cada región de código contraíble.</span><span class="sxs-lookup"><span data-stu-id="068d9-108">A vertical line on the left edge of the editor window uses a square with a minus sign (-) to identify the start of each collapsible code region.</span></span> <span data-ttu-id="068d9-109">Al hacer clic en un signo menos, el texto de la región de código se reemplaza por un cuadro que contiene puntos suspensivos (...) y el signo menos cambia a un signo más (+).</span><span class="sxs-lookup"><span data-stu-id="068d9-109">When you click a minus sign, the text of the code region is replaced with a box that contains three periods (...), and the minus sign changes to a plus sign (+).</span></span> <span data-ttu-id="068d9-110">Al hacer clic en un signo más, aparece el código contraído y el signo más cambia a un signo menos.</span><span class="sxs-lookup"><span data-stu-id="068d9-110">When you click a plus sign, the collapsed code appears and the plus sign changes to a minus sign.</span></span> <span data-ttu-id="068d9-111">Al mover el puntero sobre un cuadro que tiene puntos suspensivos, aparece una información sobre herramientas que muestra el código de la sección contraída.</span><span class="sxs-lookup"><span data-stu-id="068d9-111">When you move the pointer over a box that has three periods, a tooltip appears that shows the code in the collapsed section.</span></span>

## <a name="system-outline-regions"></a><span data-ttu-id="068d9-112">Regiones de esquema del sistema</span><span class="sxs-lookup"><span data-stu-id="068d9-112">System Outline Regions</span></span>
 <span data-ttu-id="068d9-113">Cada editor de [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] genera un conjunto de regiones de esquema predeterminadas definidas por el sistema.</span><span class="sxs-lookup"><span data-stu-id="068d9-113">Each [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] editor generates a set of default, system-defined outline regions.</span></span>

 <span data-ttu-id="068d9-114">Los editores de código MDX y DMX crean regiones de esquema para cada instrucción de varias líneas.</span><span class="sxs-lookup"><span data-stu-id="068d9-114">The MDX and DMX code editors create outline regions for each multiline statement.</span></span> <span data-ttu-id="068d9-115">Este es el único nivel de esquematización que admiten estos editores.</span><span class="sxs-lookup"><span data-stu-id="068d9-115">This is the only level of outlining that these editors support.</span></span>

### <a name="analysis-services-xmla-query-editor-regions"></a><span data-ttu-id="068d9-116">Regiones del Editor de consultas XMLA de Analysis Services</span><span class="sxs-lookup"><span data-stu-id="068d9-116">Analysis Services XMLA Query Editor Regions</span></span>
 <span data-ttu-id="068d9-117">El Editor de consultas XMLA de [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] genera una región de esquema para cada atributo XML de varias líneas.</span><span class="sxs-lookup"><span data-stu-id="068d9-117">The [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] XMLA Query Editor generates an outline region for each multiline XML attribute.</span></span> <span data-ttu-id="068d9-118">El editor anida las regiones de esquema correspondientes a las etiquetas anidadas.</span><span class="sxs-lookup"><span data-stu-id="068d9-118">The editor nests the outline regions for nested tags.</span></span> <span data-ttu-id="068d9-119">Por ejemplo, el Editor de consultas XMLA crea tres regiones de esquema para el documento siguiente.</span><span class="sxs-lookup"><span data-stu-id="068d9-119">For example, the XMLA Editor creates three outline regions for the following document.</span></span>

 <span data-ttu-id="068d9-120">![Código XML que muestra la esquematización](../../database-engine/media/editoutlinexmlfull.gif "Código XML que muestra la esquematización")</span><span class="sxs-lookup"><span data-stu-id="068d9-120">![XML code showing outlining](../../database-engine/media/editoutlinexmlfull.gif "XML code showing outlining")</span></span>

 <span data-ttu-id="068d9-121">Al hacer clic en el signo menos de la \<InnerTag> línea, solo se contrae el InnerTag, tal y como se muestra en la siguiente ilustración.</span><span class="sxs-lookup"><span data-stu-id="068d9-121">When you click the minus sign on the \<InnerTag> line, just the InnerTag is collapsed, as shown in the following illustration.</span></span>

 <span data-ttu-id="068d9-122">![Código XML con el nodo interno oculto](../../database-engine/media/editoutlinexmlinnercol.gif "Código XML con el nodo interno oculto")</span><span class="sxs-lookup"><span data-stu-id="068d9-122">![XML code with inner node hidden](../../database-engine/media/editoutlinexmlinnercol.gif "XML code with inner node hidden")</span></span>

 <span data-ttu-id="068d9-123">Al mover el puntero sobre el cuadro que tiene los puntos suspensivos (...), el código de la región contraída aparece en una información sobre herramientas, como se muestra en la ilustración siguiente.</span><span class="sxs-lookup"><span data-stu-id="068d9-123">When you move the pointer over the box that has the three periods (...), the code in the collapsed region appears in a tooltip, as shown in the following illustration.</span></span>

 <span data-ttu-id="068d9-124">![Código XML con información sobre herramientas que muestra el código oculto](../../database-engine/media/editoutlinexmlmouse.gif "Código XML con información sobre herramientas que muestra el código oculto")</span><span class="sxs-lookup"><span data-stu-id="068d9-124">![XML code with tooltip showing hidden code](../../database-engine/media/editoutlinexmlmouse.gif "XML code with tooltip showing hidden code")</span></span>

 <span data-ttu-id="068d9-125">Al hacer clic en el signo menos de la \<MiddleTag> línea, MiddleTag y InnerTag están contraídos, tal como se muestra en la siguiente ilustración.</span><span class="sxs-lookup"><span data-stu-id="068d9-125">When you click the minus sign on the \<MiddleTag> line, both the MiddleTag and InnerTag are collapsed, as shown in the following illustration.</span></span>

 <span data-ttu-id="068d9-126">![Código XML con las etiquetas internas y centrales ocultas](../../database-engine/media/editoutlinexmlmiddlecol.gif "Código XML con las etiquetas internas y centrales ocultas")</span><span class="sxs-lookup"><span data-stu-id="068d9-126">![XML code with inner and middle tags hidden](../../database-engine/media/editoutlinexmlmiddlecol.gif "XML code with inner and middle tags hidden")</span></span>

 <span data-ttu-id="068d9-127">Al hacer clic en el signo menos de la \<OuterTag> línea, se contraen las tres líneas, como se muestra en la siguiente ilustración.</span><span class="sxs-lookup"><span data-stu-id="068d9-127">When you click the minus sign on the \<OuterTag> line, all three lines are collapsed, as shown in the following illustration.</span></span>

 <span data-ttu-id="068d9-128">![Código XML con todas las tres etiquetas ocultas](../../database-engine/media/editoutlinexmloutercol.gif "Código XML con todas las tres etiquetas ocultas")</span><span class="sxs-lookup"><span data-stu-id="068d9-128">![XML code showing all three tags hidden](../../database-engine/media/editoutlinexmloutercol.gif "XML code showing all three tags hidden")</span></span>

### <a name="database-engine-query-editor-regions"></a><span data-ttu-id="068d9-129">Regiones del Editor de consultas de Database Engine</span><span class="sxs-lookup"><span data-stu-id="068d9-129">Database Engine Query Editor Regions</span></span>
 <span data-ttu-id="068d9-130">El Editor de consultas de [!INCLUDE[ssDE](../../../includes/ssde-md.md)] genera regiones de esquema para cada elemento de la jerarquía siguiente:</span><span class="sxs-lookup"><span data-stu-id="068d9-130">The [!INCLUDE[ssDE](../../../includes/ssde-md.md)] Query Editor generates outline regions for each element in the following hierarchy:</span></span>

1.  <span data-ttu-id="068d9-131">Lotes.</span><span class="sxs-lookup"><span data-stu-id="068d9-131">Batches.</span></span> <span data-ttu-id="068d9-132">El primer lote es el código desde el principio del archivo hasta el primer comando GO o hasta el final del archivo si no hay ningún comando GO.</span><span class="sxs-lookup"><span data-stu-id="068d9-132">The first batch is the code from the start of the file to either the first GO command or the end of the file when there are no GO commands.</span></span> <span data-ttu-id="068d9-133">Después del primer comando GO, hay un lote desde cada comando GO hasta el comando GO siguiente o hasta el final del archivo.</span><span class="sxs-lookup"><span data-stu-id="068d9-133">After the first GO, there is one batch from each GO command to either the next GO command or the end of the file.</span></span>

2.  <span data-ttu-id="068d9-134">Bloques delimitados por las palabras clave siguientes:</span><span class="sxs-lookup"><span data-stu-id="068d9-134">Blocks delimited by the following keywords:</span></span>

    -   <span data-ttu-id="068d9-135">BEGIN - END</span><span class="sxs-lookup"><span data-stu-id="068d9-135">BEGIN - END</span></span>

    -   <span data-ttu-id="068d9-136">BEGIN TRY - END TRY</span><span class="sxs-lookup"><span data-stu-id="068d9-136">BEGIN TRY - END TRY</span></span>

    -   <span data-ttu-id="068d9-137">BEGIN CATCH - END CATCH</span><span class="sxs-lookup"><span data-stu-id="068d9-137">BEGIN CATCH - END CATCH</span></span>

3.  <span data-ttu-id="068d9-138">Instrucciones de varias líneas.</span><span class="sxs-lookup"><span data-stu-id="068d9-138">Multiline statements.</span></span>

 <span data-ttu-id="068d9-139">Por ejemplo, el Editor de consultas de [!INCLUDE[ssDE](../../../includes/ssde-md.md)] crea tres regiones de esquema para la consulta siguiente:</span><span class="sxs-lookup"><span data-stu-id="068d9-139">For example, the [!INCLUDE[ssDE](../../../includes/ssde-md.md)] Query Editor creates three outline regions for the following query:</span></span>

```
CREATE PROCEDURE Sales.SampleProc --Outline region 1
AS
BEGIN --Outline region 2 
  SELECT GETDATE() AS TimeOfQuery;
  SELECT * --Outline region 3
  FROM sys.transmission_queue;
  SELECT @@VERSION;
END;
GO
```

 <span data-ttu-id="068d9-140">Puede hacer clic en el signo menos de la línea `SELECT *` para contraer únicamente esa instrucción `SELECT` .</span><span class="sxs-lookup"><span data-stu-id="068d9-140">You can click the minus sign on the `SELECT *` line to collapse just that `SELECT` statement.</span></span> <span data-ttu-id="068d9-141">Para contraer el bloque `BEGIN - END` completo, haga clic en el signo menos de la línea `BEGIN` .</span><span class="sxs-lookup"><span data-stu-id="068d9-141">To collapse the whole `BEGIN - END` block, click the minus sign on the `BEGIN` line.</span></span> <span data-ttu-id="068d9-142">Para contraer el bloque completo hasta el comando `GO` , haga clic en el signo menos de la línea `CREATE PROCEDURE` .</span><span class="sxs-lookup"><span data-stu-id="068d9-142">To collapse the whole batch to the `GO` command, click the minus sign on the `CREATE PROCEDURE` line.</span></span> <span data-ttu-id="068d9-143">No se pueden contraer individualmente las líneas `SELECT GETDATE()` y `SELECT @@VERSION` porque son instrucciones de una sola línea y no se les asignan regiones de esquematización.</span><span class="sxs-lookup"><span data-stu-id="068d9-143">You cannot collapse the `SELECT GETDATE()` or `SELECT @@VERSION` lines individually because they are single line statements and do not get outlining regions.</span></span>


