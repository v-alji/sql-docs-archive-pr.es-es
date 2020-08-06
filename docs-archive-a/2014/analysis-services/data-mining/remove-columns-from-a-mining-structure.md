---
title: Quitar columnas de una estructura de minería de datos | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- mining structures [Analysis Services], columns
- removing columns
- deleting columns
- columns [data mining], mining structure columns
ms.assetid: 41073ffe-9351-416b-9f0c-62634bc213f9
author: minewiskan
ms.author: owend
ms.openlocfilehash: 44ad1de08d57d00fd9798e1ceeddb85d146d7111
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87662358"
---
# <a name="remove-columns-from-a-mining-structure"></a><span data-ttu-id="66ac7-102">Quitar columnas de una estructura de minería de datos</span><span class="sxs-lookup"><span data-stu-id="66ac7-102">Remove Columns from a Mining Structure</span></span>
  <span data-ttu-id="66ac7-103">Puede usar el Diseñador de minería de datos para quitar columnas de la estructura de minería de datos después de que haya sido creada.</span><span class="sxs-lookup"><span data-stu-id="66ac7-103">You can use Data Mining Designer to remove columns from a mining structure after the structure has already been created.</span></span> <span data-ttu-id="66ac7-104">Algunos ejemplos de razones para quitar una columna de la estructura de minería de datos son:</span><span class="sxs-lookup"><span data-stu-id="66ac7-104">Reasons to remove a mining structure column might include the following:</span></span>  
  
-   <span data-ttu-id="66ac7-105">La estructura de minería de datos contiene varias copias de una columna y quiere evitar el uso de datos duplicados en un modelo.</span><span class="sxs-lookup"><span data-stu-id="66ac7-105">The mining structure contains multiple copies of a column and you want to avoid the use of duplicate data in a model.</span></span>  
  
-   <span data-ttu-id="66ac7-106">Los datos deberían estar protegidos, pero se ha habilitado la obtención de detalles.</span><span class="sxs-lookup"><span data-stu-id="66ac7-106">The data should be protected, but drillthrough has been enabled.</span></span>  
  
-   <span data-ttu-id="66ac7-107">Los datos no se usan en el modelado y no deben procesarse.</span><span class="sxs-lookup"><span data-stu-id="66ac7-107">The data is unused in modeling and should not be processed.</span></span>  
  
 <span data-ttu-id="66ac7-108">Eliminar una columna de la estructura de minería de datos no cambia la columna en la vista del origen de datos o en los datos externos; solamente se suprimen los metadatos.</span><span class="sxs-lookup"><span data-stu-id="66ac7-108">Deleting a column from the mining structure does not change the column in the data source view or in the external data; only metadata is deleted.</span></span> <span data-ttu-id="66ac7-109">Sin embargo, cuando cambia las columnas usadas en la estructura de minería de datos, debe volver a procesar la estructura y cualquier modelo basado en ella.</span><span class="sxs-lookup"><span data-stu-id="66ac7-109">However, when you change the columns used in a mining structure, you must reprocess the structure and any models based on it.</span></span>  
  
### <a name="to-remove-a-column-from-the-mining-structure"></a><span data-ttu-id="66ac7-110">Para quitar una columna de la estructura de minería de datos</span><span class="sxs-lookup"><span data-stu-id="66ac7-110">To remove a column from the mining structure</span></span>  
  
1.  <span data-ttu-id="66ac7-111">Seleccione la pestaña **Estructura de minería de datos** en el Diseñador de minería de datos.</span><span class="sxs-lookup"><span data-stu-id="66ac7-111">Select the **Mining Structure** tab in Data Mining Designer.</span></span>  
  
2.  <span data-ttu-id="66ac7-112">Expanda el árbol de la estructura de minería de datos para mostrar todas las columnas.</span><span class="sxs-lookup"><span data-stu-id="66ac7-112">Expand the tree for the mining structure, to show all the columns.</span></span>  
  
3.  <span data-ttu-id="66ac7-113">Haga clic con el botón derecho en la columna que quiera eliminar y, después, seleccione **Eliminar**.</span><span class="sxs-lookup"><span data-stu-id="66ac7-113">Right-click the column that you want to delete, and then select **Delete**.</span></span>  
  
4.  <span data-ttu-id="66ac7-114">En el cuadro de diálogo **Eliminar objetos** , haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="66ac7-114">In the **Delete Objects** dialog box, click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="66ac7-115">Consulte también</span><span class="sxs-lookup"><span data-stu-id="66ac7-115">See Also</span></span>  
 [<span data-ttu-id="66ac7-116">Tareas y procedimientos de las estructuras de minería de datos</span><span class="sxs-lookup"><span data-stu-id="66ac7-116">Mining Structure Tasks and How-tos</span></span>](mining-structure-tasks-and-how-tos.md)  
  
  
