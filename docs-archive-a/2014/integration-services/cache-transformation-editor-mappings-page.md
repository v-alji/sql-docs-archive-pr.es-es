---
title: Editor de transformación caché (página asignaciones) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.cachetransmap.f1
ms.assetid: ffd53f18-9646-458a-a84a-f2467d601ea5
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 6bb31e479ea98133da34dcbf257d59e70f4ffe8f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87676146"
---
# <a name="cache-transformation-editor-mappings-page"></a><span data-ttu-id="5f19e-102">Editor de transformación de caché (página Asignaciones)</span><span class="sxs-lookup"><span data-stu-id="5f19e-102">Cache Transformation Editor (Mappings Page)</span></span>
  <span data-ttu-id="5f19e-103">Utilice la página **Asignaciones** del **Editor de transformación Caché** para asignar las columnas de entrada de la transformación de caché a las columnas de destino del administrador de conexiones de caché.</span><span class="sxs-lookup"><span data-stu-id="5f19e-103">Use the **Mappings** page of the **Cache Transformation Editor** to map the input columns in the Cache Transform transformation to destination columns in the Cache connection manager.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="5f19e-104">Cada columna de entrada debe estar asignada a una columna de destino y los tipos de datos de columna deben ser iguales.</span><span class="sxs-lookup"><span data-stu-id="5f19e-104">Each input column must be mapped to a destination column, and the column data types must match.</span></span> <span data-ttu-id="5f19e-105">De lo contrario, el Diseñador [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] muestra un mensaje de error.</span><span class="sxs-lookup"><span data-stu-id="5f19e-105">Otherwise, [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] Designer displays an error message.</span></span>  
  
 <span data-ttu-id="5f19e-106">Para obtener más información acerca de la transformación Caché, vea [Cache Transform](data-flow/transformations/cache-transform.md).</span><span class="sxs-lookup"><span data-stu-id="5f19e-106">To learn more about the Cache Transform, see [Cache Transform](data-flow/transformations/cache-transform.md).</span></span>  
  
 <span data-ttu-id="5f19e-107">Para obtener más información acerca del administrador de conexiones de caché, vea [Cache Connection Manager](connection-manager/cache-connection-manager.md).</span><span class="sxs-lookup"><span data-stu-id="5f19e-107">To learn more about the Cache connection manager, see [Cache Connection Manager](connection-manager/cache-connection-manager.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="5f19e-108">Opciones</span><span class="sxs-lookup"><span data-stu-id="5f19e-108">Options</span></span>  
 <span data-ttu-id="5f19e-109">**Columnas de entrada disponibles**</span><span class="sxs-lookup"><span data-stu-id="5f19e-109">**Available Input Columns**</span></span>  
 <span data-ttu-id="5f19e-110">Muestra la lista de columnas de entrada disponibles.</span><span class="sxs-lookup"><span data-stu-id="5f19e-110">View the list of available input columns.</span></span> <span data-ttu-id="5f19e-111">Utilice una operación de arrastrar y colocar para asignar columnas de entrada disponibles a columnas de destino.</span><span class="sxs-lookup"><span data-stu-id="5f19e-111">Use a drag-and-drop operation to map available input columns to destination columns.</span></span>  
  
 <span data-ttu-id="5f19e-112">También puede asignar columnas de entrada a columnas de destino utilizando el teclado, resaltando una columna en la tabla **Columnas de entrada disponibles** , presionando la tecla de menú y seleccionando a continuación **Asignar elementos por coincidencia de nombres**.</span><span class="sxs-lookup"><span data-stu-id="5f19e-112">You can also map input columns to destination columns using the keyboard, by highlighting a column in the **Available Input Columns** table, pressing the menu key, and then selecting **Map Items By Matching Names**.</span></span>  
  
 <span data-ttu-id="5f19e-113">**Columnas de destino disponibles**</span><span class="sxs-lookup"><span data-stu-id="5f19e-113">**Available Destination Columns**</span></span>  
 <span data-ttu-id="5f19e-114">Muestra la lista de columnas de destino disponibles.</span><span class="sxs-lookup"><span data-stu-id="5f19e-114">View the list of available destination columns.</span></span> <span data-ttu-id="5f19e-115">Utilice una operación de arrastrar y colocar para asignar columnas de destino disponibles a columnas de entrada.</span><span class="sxs-lookup"><span data-stu-id="5f19e-115">Use a drag-and-drop operation to map available destination columns to input columns.</span></span>  
  
 <span data-ttu-id="5f19e-116">También puede asignar columnas de entrada a columnas de destino utilizando el teclado, resaltando una columna en la tabla **Columnas de destino disponibles** , presionando la tecla de menú y seleccionando a continuación **Asignar elementos por coincidencia de nombres**.</span><span class="sxs-lookup"><span data-stu-id="5f19e-116">You can also map input columns to destination columns using the keyboard, by highlighting a column in the **Available Destination Columns** table, pressing the menu key, and then selecting **Map Items By Matching Names**.</span></span>  
  
 <span data-ttu-id="5f19e-117">**Columna de entrada**</span><span class="sxs-lookup"><span data-stu-id="5f19e-117">**Input Column**</span></span>  
 <span data-ttu-id="5f19e-118">Muestra las columnas de entrada seleccionadas anteriormente en este tema.</span><span class="sxs-lookup"><span data-stu-id="5f19e-118">View input columns selected earlier in this topic.</span></span> <span data-ttu-id="5f19e-119">Puede cambiar las asignaciones utilizando la lista de **Columnas de entrada disponibles**.</span><span class="sxs-lookup"><span data-stu-id="5f19e-119">You can change the mappings by using the list of **Available Input Columns**.</span></span>  
  
 <span data-ttu-id="5f19e-120">**Columna de destino**</span><span class="sxs-lookup"><span data-stu-id="5f19e-120">**Destination Column**</span></span>  
 <span data-ttu-id="5f19e-121">Muestra cada columna de destino disponible.</span><span class="sxs-lookup"><span data-stu-id="5f19e-121">View each available destination column.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5f19e-122">Consulte también</span><span class="sxs-lookup"><span data-stu-id="5f19e-122">See Also</span></span>  
 [<span data-ttu-id="5f19e-123">Editor de transformación Caché &#40;página Administrador de conexiones&#41;</span><span class="sxs-lookup"><span data-stu-id="5f19e-123">Cache Transformation Editor &#40;Connection Manager Page&#41;</span></span>](../../2014/integration-services/cache-transformation-editor-connection-manager-page.md)  
  
  
