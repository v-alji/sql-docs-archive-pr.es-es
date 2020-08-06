---
title: Visor de datos | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.dataviewer.f1
helpviewer_keywords:
- Data Viewer dialog box
ms.assetid: 6351309a-688f-4e82-9697-1712130f10a1
author: chugugrace
ms.author: chugu
ms.openlocfilehash: dc576981e875eade84dd3576f4ed93b66784411f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87673816"
---
# <a name="data-viewer"></a><span data-ttu-id="f2b2b-102">Visor de datos</span><span class="sxs-lookup"><span data-stu-id="f2b2b-102">Data Viewer</span></span>
  <span data-ttu-id="f2b2b-103">Si una ruta de acceso se configura para utilizar un visor de datos, el Visor de datos muestra los datos por búfer a medida que éstos se mueven entre dos componentes de flujo de datos.</span><span class="sxs-lookup"><span data-stu-id="f2b2b-103">If a path is configured to use a data viewer, the Data Viewer displays the data buffer by buffer as data moves between two data flow components.</span></span>  
  
## <a name="options"></a><span data-ttu-id="f2b2b-104">Opciones</span><span class="sxs-lookup"><span data-stu-id="f2b2b-104">Options</span></span>  
 <span data-ttu-id="f2b2b-105">**Flecha de color verde**</span><span class="sxs-lookup"><span data-stu-id="f2b2b-105">**Green arrow**</span></span>  
 <span data-ttu-id="f2b2b-106">Haga clic en esta opción para mostrar los datos del siguiente búfer.</span><span class="sxs-lookup"><span data-stu-id="f2b2b-106">Click to display the data in the next buffer.</span></span> <span data-ttu-id="f2b2b-107">Si los datos pueden moverse en un único búfer, esta opción no está disponible.</span><span class="sxs-lookup"><span data-stu-id="f2b2b-107">If the data can be moved in a single buffer, this option is not available.</span></span>  
  
 <span data-ttu-id="f2b2b-108">**Separar**</span><span class="sxs-lookup"><span data-stu-id="f2b2b-108">**Detach**</span></span>  
 <span data-ttu-id="f2b2b-109">Separe el visor de datos.</span><span class="sxs-lookup"><span data-stu-id="f2b2b-109">Detach the data viewer.</span></span>  
  
 <span data-ttu-id="f2b2b-110">**Nota** La separación de un visor de datos no elimina el visor de datos.</span><span class="sxs-lookup"><span data-stu-id="f2b2b-110">**Note** Detaching a data viewer does not delete the data viewer.</span></span> <span data-ttu-id="f2b2b-111">Si el visor de datos se ha separado, los datos continúan circulando por la ruta de acceso, pero los datos del visor no se actualizan para coincidir con los datos de cada búfer.</span><span class="sxs-lookup"><span data-stu-id="f2b2b-111">If the data viewer has been detached, data continues to flow through the path, but the data in the viewer is not updated to match the data in each buffer.</span></span>  
  
 <span data-ttu-id="f2b2b-112">**Adjuntar**</span><span class="sxs-lookup"><span data-stu-id="f2b2b-112">**Attach**</span></span>  
 <span data-ttu-id="f2b2b-113">Adjunte un visor de datos.</span><span class="sxs-lookup"><span data-stu-id="f2b2b-113">Attach a data viewer.</span></span>  
  
 <span data-ttu-id="f2b2b-114">**Nota** Cuando el visor de datos se adjunta, muestra información de cada búfer en el flujo de datos y, a continuación, realiza una pausa.</span><span class="sxs-lookup"><span data-stu-id="f2b2b-114">**Note** When the data viewer is attached, it displays information from each buffer in the data flow and then pauses.</span></span> <span data-ttu-id="f2b2b-115">Puede utilizar la flecha de color verde para avanzar por los búferes.</span><span class="sxs-lookup"><span data-stu-id="f2b2b-115">You can advance through the buffers by using the green arrow.</span></span>  
  
 <span data-ttu-id="f2b2b-116">**Copiar datos**</span><span class="sxs-lookup"><span data-stu-id="f2b2b-116">**Copy Data**</span></span>  
 <span data-ttu-id="f2b2b-117">Copie datos del búfer actual al Portapapeles.</span><span class="sxs-lookup"><span data-stu-id="f2b2b-117">Copy data in the current buffer to the Clipboard.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f2b2b-118">Consulte también</span><span class="sxs-lookup"><span data-stu-id="f2b2b-118">See Also</span></span>  
 [<span data-ttu-id="f2b2b-119">Depurar el flujo de datos</span><span class="sxs-lookup"><span data-stu-id="f2b2b-119">Debugging Data Flow</span></span>](../troubleshooting/debugging-data-flow.md)  
  
  
