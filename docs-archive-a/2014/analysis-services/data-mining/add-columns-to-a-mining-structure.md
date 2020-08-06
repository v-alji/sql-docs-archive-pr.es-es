---
title: Agregar columnas a una estructura de minería de datos | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- mining structures [Analysis Services], columns
- columns [data mining], mining structure columns
- adding columns
ms.assetid: 3f879344-9f66-4178-851a-e8c5ccccf4cb
author: minewiskan
ms.author: owend
ms.openlocfilehash: 093d78b36ab3aae6600b890a8137025c9dc9134e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87675056"
---
# <a name="add-columns-to-a-mining-structure"></a><span data-ttu-id="ad152-102">Agregar columnas a una estructura de minería de datos</span><span class="sxs-lookup"><span data-stu-id="ad152-102">Add Columns to a Mining Structure</span></span>
  <span data-ttu-id="ad152-103">Utilice el Diseñador de minería de datos de [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] para agregar columnas a una estructura de minería de datos después de definirla en el Asistente para minería de datos.</span><span class="sxs-lookup"><span data-stu-id="ad152-103">Use Data Mining Designer in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] to add columns to a mining structure after you have defined it in the Data Mining Wizard.</span></span> <span data-ttu-id="ad152-104">Puede agregar cualquier columna existente en la vista de origen que se haya utilizado para definir la estructura de minería de datos.</span><span class="sxs-lookup"><span data-stu-id="ad152-104">You can add any column that exists in the data source view that was used to define the mining structure.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="ad152-105">Puede agregar varias copias de una columna a una estructura de minería de datos; sin embargo, no debería utilizar más de una copia de la columna dentro del mismo modelo para evitar las correlaciones falsas entre la columna de origen y la derivada.</span><span class="sxs-lookup"><span data-stu-id="ad152-105">You can add multiple copies of columns to a mining structure; however, you should avoid using more than one instance of the column within the same model, to avoid false correlations between the source and the derived column.</span></span>  
  
### <a name="to-add-a-column-to-a-mining-structure"></a><span data-ttu-id="ad152-106">Para agregar una columna a una estructura de minería de datos</span><span class="sxs-lookup"><span data-stu-id="ad152-106">To add a column to a mining structure</span></span>  
  
1.  <span data-ttu-id="ad152-107">Seleccione la pestaña **Estructura de minería de datos** en el Diseñador de minería de datos.</span><span class="sxs-lookup"><span data-stu-id="ad152-107">Select the **Mining Structure** tab in Data Mining Designer.</span></span>  
  
2.  <span data-ttu-id="ad152-108">Haga clic con el botón derecho en la estructura de minería de datos y seleccione **Agregar una columna**.</span><span class="sxs-lookup"><span data-stu-id="ad152-108">Right-click the mining structure and select **Add a Column**.</span></span>  
  
     <span data-ttu-id="ad152-109">Se abrirá el cuadro de diálogo **Seleccionar una columna** .</span><span class="sxs-lookup"><span data-stu-id="ad152-109">The **Select a Column** dialog box opens.</span></span>  
  
3.  <span data-ttu-id="ad152-110">En **Tabla de origen**, seleccione la tabla de la vista del origen de datos en la que reside la columna.</span><span class="sxs-lookup"><span data-stu-id="ad152-110">Under **Source table**, select the table in the data source view where the column resides.</span></span>  
  
4.  <span data-ttu-id="ad152-111">En **Columna de origen**, seleccione la columna que desee agregar a la estructura de minería de datos.</span><span class="sxs-lookup"><span data-stu-id="ad152-111">Under **Source column**, select the column that you want to add to the mining structure.</span></span>  
  
5.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
> [!NOTE]  
>  <span data-ttu-id="ad152-112">Si agrega una columna que ya existe, se incluirá una copia en la estructura con el número "1" adjuntado al nombre.</span><span class="sxs-lookup"><span data-stu-id="ad152-112">If you add a column that already exists, a copy will be included in the structure, and the name appended with a "1".</span></span> <span data-ttu-id="ad152-113">Para cambiar el nombre de la columna copiada a algo más descriptivo, escriba un nuevo nombre en la propiedad **Name** de la columna de la estructura de minería de datos.</span><span class="sxs-lookup"><span data-stu-id="ad152-113">You can change the name of the copied column to something more descriptive by typing a new name in the **Name** property of the mining structure column.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ad152-114">Consulte también</span><span class="sxs-lookup"><span data-stu-id="ad152-114">See Also</span></span>  
 [<span data-ttu-id="ad152-115">Tareas y procedimientos de las estructuras de minería de datos</span><span class="sxs-lookup"><span data-stu-id="ad152-115">Mining Structure Tasks and How-tos</span></span>](mining-structure-tasks-and-how-tos.md)  
  
  
