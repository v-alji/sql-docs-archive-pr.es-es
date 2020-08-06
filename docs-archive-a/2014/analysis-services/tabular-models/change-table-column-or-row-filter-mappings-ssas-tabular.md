---
title: Cambiar las asignaciones de filtro de tabla, columna o fila (SSAS tabular) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 2124c526-5772-4f84-a019-9dd3e906e8dd
author: minewiskan
ms.author: owend
ms.openlocfilehash: d8a597fb51804ea12caace63f3308b07bffc5899
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87671700"
---
# <a name="change-table-column-or-row-filter-mappings-ssas-tabular"></a><span data-ttu-id="6914e-102">Cambiar las asignaciones de filtros de tabla, columna o fila (SSAS tabular)</span><span class="sxs-lookup"><span data-stu-id="6914e-102">Change table, column, or row filter mappings (SSAS Tabular)</span></span>
  <span data-ttu-id="6914e-103">Este tema describe cómo cambiar las asignaciones de filtros de tabla, columna o fila mediante el cuadro de diálogo **Editar propiedades de tabla** de [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6914e-103">This topic describes how to change table, column, or row filter mappings by using the **Edit Table Properties** dialog box in [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)].</span></span>  
  
 <span data-ttu-id="6914e-104">Las opciones del cuadro de diálogo **Editar propiedades de tabla** serán diferentes dependiendo de si importó los datos originalmente seleccionando las tablas en una lista o usando una consulta SQL.</span><span class="sxs-lookup"><span data-stu-id="6914e-104">Options in the **Edit Table Properties** dialog box are different depending on whether you originally imported data by selecting tables from a list or by using a SQL query.</span></span> <span data-ttu-id="6914e-105">Si importó originalmente los datos seleccionándolos en una lista, el cuadro de diálogo **Editar propiedades de tabla** mostrará el modo de vista previa de tabla.</span><span class="sxs-lookup"><span data-stu-id="6914e-105">If you originally imported the data by selecting from a list, the **Edit Table Properties** dialog box displays the Table Preview mode.</span></span> <span data-ttu-id="6914e-106">Este modo mostrará únicamente un subconjunto limitado a las primeras cincuenta filas de la tabla de origen.</span><span class="sxs-lookup"><span data-stu-id="6914e-106">This mode displays only a subset limited to the first fifty rows of the source table.</span></span> <span data-ttu-id="6914e-107">Si importó originalmente los datos mediante una instrucción SQL, el cuadro de diálogo **Editar propiedades de tabla** solo mostrará una instrucción SQL.</span><span class="sxs-lookup"><span data-stu-id="6914e-107">If you originally imported the data by using a SQL statement, the **Edit Table Properties** dialog box only displays a SQL statement.</span></span> <span data-ttu-id="6914e-108">Mediante una instrucción de consulta SQL, se puede recuperar un subconjunto de filas diseñando un filtro o editando la instrucción SQL manualmente.</span><span class="sxs-lookup"><span data-stu-id="6914e-108">Using a SQL query statement, you can retrieve a subset of rows, either by designing a filter, or by manually editing the SQL statement.</span></span>  
  
 <span data-ttu-id="6914e-109">Si se cambia el origen a una tabla que tiene columnas distintas que la tabla actual, aparece un mensaje que advierte que las columnas son distintas.</span><span class="sxs-lookup"><span data-stu-id="6914e-109">If you change the source to a table that has different columns than the current table, a message is displayed warning that the columns are different.</span></span> <span data-ttu-id="6914e-110">En ese caso, debe seleccionar las columnas que desea poner en la tabla actual y hacer clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="6914e-110">You must then select the columns that you want to put in the current table and click **Save**.</span></span> <span data-ttu-id="6914e-111">Puede reemplazar toda la tabla activando la casilla de la izquierda de la tabla.</span><span class="sxs-lookup"><span data-stu-id="6914e-111">You can replace the entire table by selecting the check box at the left of the table.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="6914e-112">Si la tabla tiene más de una partición, no puede utilizar el cuadro de diálogo Editar propiedades de tabla para cambiar las asignaciones de filtro de fila.</span><span class="sxs-lookup"><span data-stu-id="6914e-112">If your table has more than one partition, you cannot use the Edit Table Properties dialog box to change row filter mappings.</span></span> <span data-ttu-id="6914e-113">Para cambiar las asignaciones de filtro de fila para las tablas con varias particiones, utilice el Administrador de particiones.</span><span class="sxs-lookup"><span data-stu-id="6914e-113">To change row filter mappings for tables with multiple partitions, use Partition Manager.</span></span> <span data-ttu-id="6914e-114">Para obtener más información, vea [Particiones &#40;SSAS tabular&#41;](partitions-ssas-tabular.md).</span><span class="sxs-lookup"><span data-stu-id="6914e-114">For more information, see [Partitions &#40;SSAS Tabular&#41;](partitions-ssas-tabular.md).</span></span>  
  
#### <a name="to-change-table-column-or-row-filter-mappings"></a><span data-ttu-id="6914e-115">Para cambiar las asignaciones de filtros de tabla, columna o fila</span><span class="sxs-lookup"><span data-stu-id="6914e-115">To change table, column, or row filter mappings</span></span>  
  
1.  <span data-ttu-id="6914e-116">En el diseñador de modelos, haga clic en la tabla, haga clic en el menú **Tabla** y, a continuación, en **Propiedades de tabla**.</span><span class="sxs-lookup"><span data-stu-id="6914e-116">In the model designer, click the table, then click on the **Table** menu, and then click **Table Properties**.</span></span>  
  
2.  <span data-ttu-id="6914e-117">En el cuadro de diálogo **Editar propiedades de tabla** , busque la columna que contiene los criterios por los que desea filtrar y, a continuación, haga clic en la flecha hacia abajo que hay a la derecha del encabezado de columna.</span><span class="sxs-lookup"><span data-stu-id="6914e-117">In the **Edit Table Properties** dialog box, locate the column that contains the criteria you want to filter on, and then click the down arrow at the right of the column heading.</span></span>  
  
3.  <span data-ttu-id="6914e-118">En el menú **Autofiltro** , realice una de las acciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="6914e-118">In the **AutoFilter** menu, do one of the following:</span></span>  
  
    -   <span data-ttu-id="6914e-119">En la lista de valores de columna, active o desactive uno o varios valores para filtrar y haga clic en Aceptar.</span><span class="sxs-lookup"><span data-stu-id="6914e-119">In the list of column values, select or clear one or more values to filter by, and then click OK.</span></span>  
  
         <span data-ttu-id="6914e-120">Si el número de valores es sumamente grande, algunos elementos individuales podrían no mostrarse en la lista.</span><span class="sxs-lookup"><span data-stu-id="6914e-120">If the number of values is extremely large, individual items might not be shown in the list.</span></span> <span data-ttu-id="6914e-121">En su lugar, verá un mensaje similar a "Demasiados elementos para mostrar".</span><span class="sxs-lookup"><span data-stu-id="6914e-121">Instead, you will see the message, "Too many items to show."</span></span>  
  
    -   <span data-ttu-id="6914e-122">Haga clic en **Numerar filtros** o **Filtros de texto** (según el tipo de columna) y, después, haga clic en uno de los comandos de operador de comparación (como Es igual a) o haga clic en Filtro personalizado.</span><span class="sxs-lookup"><span data-stu-id="6914e-122">Click **Number Filters** or **Text Filters** (depending on the type of column), and then clicke of the comparison operator commands (such as Equals), or click Custom Filter.</span></span> <span data-ttu-id="6914e-123">En el cuadro de diálogo **Filtro personalizado** , cree el filtro y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="6914e-123">In the **Custom Filter** dialog box, create the filter, and then click **OK**.</span></span>  
  
         <span data-ttu-id="6914e-124">Si comete un error y necesita volver a empezar, haga clic en **Borrar filtros de fila**.</span><span class="sxs-lookup"><span data-stu-id="6914e-124">If you make a mistake and need to start over, click **Clear Row Filters**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6914e-125">Consulte también</span><span class="sxs-lookup"><span data-stu-id="6914e-125">See Also</span></span>  
 [<span data-ttu-id="6914e-126">Cuadro de diálogo Editar propiedades de tabla &#40;SSAS&#41;</span><span class="sxs-lookup"><span data-stu-id="6914e-126">Edit Table Properties Dialog Box &#40;SSAS&#41;</span></span>](../edit-table-properties-dialog-box-ssas.md)  
  
  
