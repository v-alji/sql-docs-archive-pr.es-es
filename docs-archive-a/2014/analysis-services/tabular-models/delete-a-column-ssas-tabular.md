---
title: Eliminar una columna (SSAS tabular) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 703db83b-e554-450e-813e-23ad08c1cdad
author: minewiskan
ms.author: owend
ms.openlocfilehash: 06af0b7fd9879661db95bb2073cced545bb4eef5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87673915"
---
# <a name="delete-a-column-ssas-tabular"></a><span data-ttu-id="d25b1-102">Eliminar una columna (SSAS tabular)</span><span class="sxs-lookup"><span data-stu-id="d25b1-102">Delete a Column (SSAS Tabular)</span></span>
  <span data-ttu-id="d25b1-103">En este tema se describe cómo eliminar una columna de una tabla de modelo tabular.</span><span class="sxs-lookup"><span data-stu-id="d25b1-103">This topic describes how to delete a column from a tabular model table.</span></span>  
  
## <a name="delete-a-model-table-column"></a><span data-ttu-id="d25b1-104">Eliminar una columna de tabla modelo</span><span class="sxs-lookup"><span data-stu-id="d25b1-104">Delete a Model Table Column</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="d25b1-105">Al eliminar una columna de una tabla de modelo no se elimina la columna de una definición de consulta de partición.</span><span class="sxs-lookup"><span data-stu-id="d25b1-105">Deleting a column from a model table does not delete the column from a partition query definition.</span></span> <span data-ttu-id="d25b1-106">Si la columna que va a eliminar forma parte de una partición, debe eliminar manualmente la columna de la definición de consulta de partición.</span><span class="sxs-lookup"><span data-stu-id="d25b1-106">If the column you are deleting is part of a partition, you must manually delete the column from the partition query definition.</span></span> <span data-ttu-id="d25b1-107">Si no se elimina la columna de la definición de consulta de partición, se consultará la columna y se devolverán datos, pero no se rellenan en la tabla de modelo, durante las operaciones de procesamiento.</span><span class="sxs-lookup"><span data-stu-id="d25b1-107">Failure to delete the column from the partition query definition will cause the column to be queried and data returned, but not populated to the model table, during processing operations.</span></span> <span data-ttu-id="d25b1-108">Para obtener más información, vea [Particiones &#40;SSAS tabular&#41;](partitions-ssas-tabular.md).</span><span class="sxs-lookup"><span data-stu-id="d25b1-108">For more information, see [Partitions &#40;SSAS Tabular&#41;](partitions-ssas-tabular.md).</span></span>  
  
#### <a name="to-delete-a-model-table-column"></a><span data-ttu-id="d25b1-109">Para eliminar una columna de tabla de modelo</span><span class="sxs-lookup"><span data-stu-id="d25b1-109">To delete a model table column</span></span>  
  
-   <span data-ttu-id="d25b1-110">En el diseñador de modelos, en la tabla que contiene la columna que quiere eliminar, haga clic con el botón derecho en la columna y, después, haga clic en **Eliminar**.</span><span class="sxs-lookup"><span data-stu-id="d25b1-110">In the model designer, in the table that contains the column you want to delete, right-click on the column, and then click **Delete**.</span></span>  
  
#### <a name="to-delete-a-model-table-column-by-using-the-table-properties-dialog-box"></a><span data-ttu-id="d25b1-111">Para eliminar una columna de tabla de modelo mediante el cuadro de diálogo Propiedades de tabla</span><span class="sxs-lookup"><span data-stu-id="d25b1-111">To delete a model table column by using the Table Properties dialog box</span></span>  
  
1.  <span data-ttu-id="d25b1-112">En el diseñador de modelos, haga clic en la tabla que contiene la columna que desea eliminar, y, a continuación, haga clic en el menú **Tabla** y, a continuación, en  **Propiedades de tabla**.</span><span class="sxs-lookup"><span data-stu-id="d25b1-112">In the model designer, click on the table which contains the column you want to delete, then click the **Table** menu, and then click  **Table Properties**.</span></span>  
  
2.  <span data-ttu-id="d25b1-113">En **Nombres de columna de**, seleccione **Modelo** (*para usar los nombres de columna de tabla de modelo, si son distintos del origen*).</span><span class="sxs-lookup"><span data-stu-id="d25b1-113">In **Column names from**, select **Model** (*to use model table column names, if different from source*).</span></span>  
  
3.  <span data-ttu-id="d25b1-114">En el cuadro de diálogo **Editar propiedades de tabla** , en la ventana de vista previa de la tabla, desactive la columna de origen que desee eliminar y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="d25b1-114">In the **Edit Table Properties** dialog box, in the table preview window, uncheck the column you want to delete, and then click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d25b1-115">Consulte también</span><span class="sxs-lookup"><span data-stu-id="d25b1-115">See Also</span></span>  
 <span data-ttu-id="d25b1-116">[Agregar columnas a una tabla &#40;&#41;tabular de SSAS](add-columns-to-a-table-ssas-tabular.md) </span><span class="sxs-lookup"><span data-stu-id="d25b1-116">[Add Columns to a Table &#40;SSAS Tabular&#41;](add-columns-to-a-table-ssas-tabular.md) </span></span>  
 [<span data-ttu-id="d25b1-117">Particiones &#40;SSAS tabular&#41;</span><span class="sxs-lookup"><span data-stu-id="d25b1-117">Partitions &#40;SSAS Tabular&#41;</span></span>](partitions-ssas-tabular.md)  
  
  
