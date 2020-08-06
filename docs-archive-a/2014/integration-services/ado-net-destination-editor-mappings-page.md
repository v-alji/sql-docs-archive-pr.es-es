---
title: Editor de destinos de ADO NET (página asignaciones) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.adonetdest.mappings.f1
ms.assetid: 842d075f-8b7a-457c-a1a1-a7acbe10e9b7
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 7e7a2397e4e2d16e6eeca93d41f5127dfde4c35e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87662215"
---
# <a name="ado-net-destination-editor-mappings-page"></a><span data-ttu-id="6087f-102">Editor de destinos de ADO NET (página Asignaciones)</span><span class="sxs-lookup"><span data-stu-id="6087f-102">ADO NET Destination Editor (Mappings Page)</span></span>
  <span data-ttu-id="6087f-103">Use la página **Asignaciones** del cuadro de diálogo **Editor de destinos de ADO NET** para asignar columnas de entrada a columnas de destino.</span><span class="sxs-lookup"><span data-stu-id="6087f-103">Use the **Mappings** page of the **ADO NET Destination Editor** dialog box to map input columns to destination columns.</span></span>  
  
 <span data-ttu-id="6087f-104">Para obtener más información acerca del destino de ADO NET, vea [ADO NET Destination](data-flow/ado-net-destination.md).</span><span class="sxs-lookup"><span data-stu-id="6087f-104">To learn more about the ADO NET destination, see [ADO NET Destination](data-flow/ado-net-destination.md).</span></span>  
  
 <span data-ttu-id="6087f-105">**Para abrir la página Asignaciones**</span><span class="sxs-lookup"><span data-stu-id="6087f-105">**To open the Mappings page**</span></span>  
  
1.  <span data-ttu-id="6087f-106">En [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], abra el paquete [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] que tiene el destino de ADO NET.</span><span class="sxs-lookup"><span data-stu-id="6087f-106">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] package that has the ADO NET destination.</span></span>  
  
2.  <span data-ttu-id="6087f-107">En la pestaña **Flujo de datos** , haga doble clic en el destino de ADO NET.</span><span class="sxs-lookup"><span data-stu-id="6087f-107">On the **Data Flow** tab, double-click the ADO NET destination.</span></span>  
  
3.  <span data-ttu-id="6087f-108">En el **Editor de destinos de ADO NET**, haga clic en **Asignaciones**.</span><span class="sxs-lookup"><span data-stu-id="6087f-108">In the **ADO NET Destination Editor**, click **Mappings**.</span></span>  
  
## <a name="options"></a><span data-ttu-id="6087f-109">Opciones</span><span class="sxs-lookup"><span data-stu-id="6087f-109">Options</span></span>  
 <span data-ttu-id="6087f-110">**Columnas de entrada disponibles**</span><span class="sxs-lookup"><span data-stu-id="6087f-110">**Available Input Columns**</span></span>  
 <span data-ttu-id="6087f-111">Muestra la lista de columnas de entrada disponibles.</span><span class="sxs-lookup"><span data-stu-id="6087f-111">View the list of available input columns.</span></span> <span data-ttu-id="6087f-112">Utilice una operación de arrastrar y colocar para asignar columnas de entrada disponibles de la tabla a columnas de destino.</span><span class="sxs-lookup"><span data-stu-id="6087f-112">Use a drag-and-drop operation to map available input columns in the table to destination columns.</span></span>  
  
 <span data-ttu-id="6087f-113">**Columnas de destino disponibles**</span><span class="sxs-lookup"><span data-stu-id="6087f-113">**Available Destination Columns**</span></span>  
 <span data-ttu-id="6087f-114">Muestra la lista de columnas de destino disponibles.</span><span class="sxs-lookup"><span data-stu-id="6087f-114">View the list of available destination columns.</span></span> <span data-ttu-id="6087f-115">Utilice una operación de arrastrar y colocar para asignar columnas de destino disponibles de la tabla a columnas de entrada.</span><span class="sxs-lookup"><span data-stu-id="6087f-115">Use a drag-and-drop operation to map available destination columns in the table to input columns.</span></span>  
  
 <span data-ttu-id="6087f-116">**Columna de entrada**</span><span class="sxs-lookup"><span data-stu-id="6087f-116">**Input Column**</span></span>  
 <span data-ttu-id="6087f-117">Permite ver las columnas de entrada seleccionadas.</span><span class="sxs-lookup"><span data-stu-id="6087f-117">View the input columns that you selected.</span></span> <span data-ttu-id="6087f-118">Para quitar asignaciones, seleccione **\<ignore>** con el fin de excluir columnas de la salida.</span><span class="sxs-lookup"><span data-stu-id="6087f-118">You can remove mappings by selecting **\<ignore>** to exclude columns from the output.</span></span>  
  
 <span data-ttu-id="6087f-119">**Columna de destino**</span><span class="sxs-lookup"><span data-stu-id="6087f-119">**Destination Column**</span></span>  
 <span data-ttu-id="6087f-120">Muestra todas las columnas de destino disponibles, tanto si están asignadas como si no lo están.</span><span class="sxs-lookup"><span data-stu-id="6087f-120">View each available destination column, regardless of whether it is mapped or not.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6087f-121">Consulte también</span><span class="sxs-lookup"><span data-stu-id="6087f-121">See Also</span></span>  
 <span data-ttu-id="6087f-122">[Editor de destinos de ADO NET &#40;página Administrador de conexiones&#41;](../../2014/integration-services/ado-net-destination-editor-connection-manager-page.md) </span><span class="sxs-lookup"><span data-stu-id="6087f-122">[ADO NET Destination Editor &#40;Connection Manager Page&#41;](../../2014/integration-services/ado-net-destination-editor-connection-manager-page.md) </span></span>  
 [<span data-ttu-id="6087f-123">Editor de destinos de ADO NET &#40;página Salida de error&#41;</span><span class="sxs-lookup"><span data-stu-id="6087f-123">ADO NET Destination Editor &#40;Error Output Page&#41;</span></span>](../../2014/integration-services/ado-net-destination-editor-error-output-page.md)  
  
  
