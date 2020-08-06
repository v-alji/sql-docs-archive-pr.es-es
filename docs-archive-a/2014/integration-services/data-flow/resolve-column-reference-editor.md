---
title: Resolver el editor de referencias de columna | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.resolvereferences.mapper.F1
- sql12.dts.designer.resolvereferences.preview.F1
ms.assetid: bb3ee33c-79c4-4c76-a82f-71581b4a60f1
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 600b6f4d5ec12290d654f0854cc548a5bbcf4335
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87673812"
---
# <a name="resolve-column-reference-editor"></a><span data-ttu-id="dd713-102">Resolver el editor de referencias de columna</span><span class="sxs-lookup"><span data-stu-id="dd713-102">Resolve Column Reference Editor</span></span>
  <span data-ttu-id="dd713-103">Cuando una ruta de acceso de entrada está desconectada o si hay columnas no asignadas en la ruta de acceso, se muestra un icono de error al lado de la ruta de acceso de datos correspondiente.</span><span class="sxs-lookup"><span data-stu-id="dd713-103">When an input path is disconnected or if there are any unmapped columns in the path, an error icon is displayed beside the corresponding data path.</span></span> <span data-ttu-id="dd713-104">Para simplificar la resolución de los errores de referencia de columna, el nuevo editor de resolución de referencias permite vincular las columnas de salida no asignadas con las columnas de entrada no asignadas para todas las rutas de acceso en el árbol de ejecución.</span><span class="sxs-lookup"><span data-stu-id="dd713-104">To simplify the resolution of column reference errors, the new Resolve References editor allows you to link unmapped output columns with unmapped input columns for all paths in the execution tree.</span></span> <span data-ttu-id="dd713-105">El editor de resolución de referencias también resaltará las rutas de acceso para indicar cuáles de ellas se están resolviendo.</span><span class="sxs-lookup"><span data-stu-id="dd713-105">The Resolve References editor will also highlight the paths to indicate which paths are being resolved.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="dd713-106">Ahora es posible editar un componente aunque su ruta de acceso de entrada esté desconectada.</span><span class="sxs-lookup"><span data-stu-id="dd713-106">It is now possible to edit a component even when its input path is disconnected</span></span>  
  
 <span data-ttu-id="dd713-107">Una vez resueltas todas las referencias de columna, si no hay otros errores de ruta de acceso de datos, no se mostrarán iconos de error al lado de las rutas de acceso de datos.</span><span class="sxs-lookup"><span data-stu-id="dd713-107">After all column references have been resolved, if there are no other data path errors, no error icons will be displayed beside the data paths.</span></span>  
  
## <a name="options"></a><span data-ttu-id="dd713-108">Opciones</span><span class="sxs-lookup"><span data-stu-id="dd713-108">Options</span></span>  
 <span data-ttu-id="dd713-109">Columnas de salida no asignadas (origen):</span><span class="sxs-lookup"><span data-stu-id="dd713-109">Unmapped Output Columns (Source):</span></span>  
 <span data-ttu-id="dd713-110">Columnas de la ruta de acceso de nivel superior que no están asignadas actualmente.</span><span class="sxs-lookup"><span data-stu-id="dd713-110">Columns from the upstream path that are not currently mapped</span></span>  
  
 <span data-ttu-id="dd713-111">Columnas asignadas (origen):</span><span class="sxs-lookup"><span data-stu-id="dd713-111">Mapped Columns (Source):</span></span>  
 <span data-ttu-id="dd713-112">Columnas de la ruta de acceso de nivel superior que están asignadas a columnas de la ruta de acceso de nivel inferior.</span><span class="sxs-lookup"><span data-stu-id="dd713-112">Columns from the upstream path that are mapped to columns from the downstream path</span></span>  
  
 <span data-ttu-id="dd713-113">Columnas asignadas (destino):</span><span class="sxs-lookup"><span data-stu-id="dd713-113">Mapped Columns (Destination):</span></span>  
 <span data-ttu-id="dd713-114">Columnas de la ruta de acceso de nivel superior que están asignadas a columnas de la ruta de acceso de nivel inferior.</span><span class="sxs-lookup"><span data-stu-id="dd713-114">Columns from the upstream path that are mapped to columns from the downstream path</span></span>  
  
 <span data-ttu-id="dd713-115">Columnas de entrada no asignadas (destino):</span><span class="sxs-lookup"><span data-stu-id="dd713-115">Unmapped Input Columns (Destination):</span></span>  
 <span data-ttu-id="dd713-116">Columnas de la ruta de acceso de nivel inferior que no están asignadas actualmente.</span><span class="sxs-lookup"><span data-stu-id="dd713-116">Columns from the downstream path that are not currently mapped</span></span>  
  
 <span data-ttu-id="dd713-117">Eliminar columnas de entrada no asignadas</span><span class="sxs-lookup"><span data-stu-id="dd713-117">Delete Unmapped Input Columns</span></span>  
 <span data-ttu-id="dd713-118">Active Eliminar columnas de entrada no asignadas para omitir las columnas no asignadas en el destino de la ruta de acceso de datos.</span><span class="sxs-lookup"><span data-stu-id="dd713-118">Check Delete Unmapped Input Columns to ignore unmapped columns at the destination of the data path.</span></span> <span data-ttu-id="dd713-119">El botón Vista previa de los cambios muestra una lista de los cambios que se producirán cuando presione el botón Aceptar.</span><span class="sxs-lookup"><span data-stu-id="dd713-119">The Preview Changes button displays a list of the changes that will occur when you press the OK button.</span></span>  
  
  
