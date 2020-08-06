---
title: Usar datos de tabla anidada como entrada para un gráfico de precisión | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- Mining Accuracy Chart [Analysis Services], nested tables
- Mining Accuracy Chart [Analysis Services], input tables
- nested tables
- adding nested tables
ms.assetid: 162e0686-ada3-4dd3-9151-9589926e6613
author: minewiskan
ms.author: owend
ms.openlocfilehash: 97d5bbd75d09b1a9e4276c4723ad6986dbabf9e4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87662342"
---
# <a name="using-nested-table-data-as-an-input-for-an-accuracy-chart"></a><span data-ttu-id="bd979-102">Usar datos de tabla anidada como entrada para un gráfico de precisión</span><span class="sxs-lookup"><span data-stu-id="bd979-102">Using Nested Table Data as an Input for an Accuracy Chart</span></span>
  <span data-ttu-id="bd979-103">Al probar la precisión de un modelo de minería de datos usando datos externos, si el modelo de minería de datos contiene tablas anidadas, los datos externos también deben contener una tabla de casos y una tabla anidada asociada.</span><span class="sxs-lookup"><span data-stu-id="bd979-103">When you test the accuracy of a mining model by using external data, if the mining model contains nested tables, the external data must also contain a case table and an associated nested table.</span></span>  
  
 <span data-ttu-id="bd979-104">En este tema se describe cómo trabajar con las tablas anidadas que se usan para probar los modelos, cómo asignar tablas de casos y anidadas en el modo y en los datos externos, y cómo aplicar un filtro a una tabla anidada.</span><span class="sxs-lookup"><span data-stu-id="bd979-104">This topic describes how to work with nested tables used for model testing, how to map nested and case tables in the mode and in the external data, and how to apply a filter to a nested table.</span></span>  
  
 <span data-ttu-id="bd979-105">Al trabajar con tablas anidadas, tenga en cuenta estas sugerencias:</span><span class="sxs-lookup"><span data-stu-id="bd979-105">When working with nested tables, keep in mind these tips:</span></span>  
  
-   <span data-ttu-id="bd979-106">Si selecciona la opción **Usar casos de prueba de modelo de minería de datos** o **Usar casos de prueba de estructura de minería de datos**, no es necesario que especifique una tabla de casos o una tabla anidada.</span><span class="sxs-lookup"><span data-stu-id="bd979-106">If you select the option **Use mining model test cases** or **Use mining structure test cases**, you do not need to specify a case table or nested table.</span></span> <span data-ttu-id="bd979-107">Con estas opciones, la definición de los datos de prueba se almacena en la estructura de minería de datos y dichos datos se seleccionan automáticamente al crear el gráfico de precisión.</span><span class="sxs-lookup"><span data-stu-id="bd979-107">With those options, the definition of the test data is stored in the mining structure and the test data is automatically selected when you create the accuracy chart.</span></span>  
  
-   <span data-ttu-id="bd979-108">Si ya existe una relación entre el caso y la tabla anidada en el origen de datos, las columnas de la estructura de minería de datos se asignan automáticamente a las columnas que tienen el mismo nombre en la tabla de entrada.</span><span class="sxs-lookup"><span data-stu-id="bd979-108">If a relationship already exists between the case and nested table in the data source, the columns in the mining structure are automatically mapped to the columns that have the same name in the input table.</span></span>  
  
-   <span data-ttu-id="bd979-109">No podrá seleccionar una tabla anidada hasta que haya especificado la tabla de casos.</span><span class="sxs-lookup"><span data-stu-id="bd979-109">You cannot select a nested table until you have specified the case table.</span></span> <span data-ttu-id="bd979-110">Tampoco podrá especificar una tabla anidada como entrada a menos que el modelo de minería de datos use también una estructura de tabla de casos y tabla anidada.</span><span class="sxs-lookup"><span data-stu-id="bd979-110">Also, you cannot specify a nested table as an input unless the mining model also uses a case table and nested table structure.</span></span>  
  
### <a name="use-a-nested-table-as-input-to-an-accuracy-chart"></a><span data-ttu-id="bd979-111">Utilice una tabla anidada como entrada para un gráfico de precisión</span><span class="sxs-lookup"><span data-stu-id="bd979-111">Use a nested table as input to an accuracy chart</span></span>  
  
1.  <span data-ttu-id="bd979-112">Haga doble clic en la estructura de minería de datos para abrirla en el Diseñador de minería de datos.</span><span class="sxs-lookup"><span data-stu-id="bd979-112">Double-click the mining structure to open it in Data Mining Designer.</span></span>  
  
2.  <span data-ttu-id="bd979-113">Seleccione la pestaña **Gráfico de precisión de minería de datos** y luego seleccione la pestaña **Selección de entrada** .</span><span class="sxs-lookup"><span data-stu-id="bd979-113">Select the **Mining Accuracy Chart** tab, and then select the **Input Selection** tab.</span></span>  
  
3.  <span data-ttu-id="bd979-114">En **Seleccionar un conjunto de datos para usarlo en un gráfico de precisión**, seleccione la opción **Especificar otro conjunto de datos**.</span><span class="sxs-lookup"><span data-stu-id="bd979-114">In **Select data set to be used for accuracy chart**, select the option **Specify a different data set**.</span></span>  
  
4.  <span data-ttu-id="bd979-115">Haga clic en el botón examinar **(...)** para elegir el conjunto de datos externos en una lista de vistas del origen de datos en el servidor actual.</span><span class="sxs-lookup"><span data-stu-id="bd979-115">Click the browse button **(...)** to choose the external data set from a list of data source views on the current server.</span></span>  
  
5.  <span data-ttu-id="bd979-116">Haga clic en **Seleccionar tabla de casos**.</span><span class="sxs-lookup"><span data-stu-id="bd979-116">Click **Select Case Table**.</span></span> <span data-ttu-id="bd979-117">En el cuadro de diálogo **Seleccionar tabla** , elija la tabla en la vista del origen de datos que contiene los datos de los casos y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="bd979-117">In the **Select Table** dialog box, choose the table from the data source view that contains the case data, and then click **OK**.</span></span>  
  
6.  <span data-ttu-id="bd979-118">Haga clic en **Seleccionar tabla anidada**.</span><span class="sxs-lookup"><span data-stu-id="bd979-118">Click **Select Nested Table**.</span></span> <span data-ttu-id="bd979-119">En el cuadro de diálogo **Seleccionar tabla** , seleccione la tabla que contiene los datos anidados y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="bd979-119">In the **Select Table** dialog box, select the table that contains the nested data, and then click **OK**.</span></span>  
  
7.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
     <span data-ttu-id="bd979-120">Si tiene que modificar la relación entre la tabla anidada y la tabla de casos, haga clic en **Modificar combinación** para abrir el cuadro de diálogo **Crear relación** .</span><span class="sxs-lookup"><span data-stu-id="bd979-120">If you need to modify the relationship between the nested table and the case table, click **Modify Join** to open the **Create Relationship** dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bd979-121">Consulte también</span><span class="sxs-lookup"><span data-stu-id="bd979-121">See Also</span></span>  
 <span data-ttu-id="bd979-122">[Elegir y asignar los datos de prueba del modelo](choose-and-map-model-testing-data.md) </span><span class="sxs-lookup"><span data-stu-id="bd979-122">[Choose and Map Model Testing Data](choose-and-map-model-testing-data.md) </span></span>  
 [<span data-ttu-id="bd979-123">Aplicar filtros a los datos de prueba del modelo</span><span class="sxs-lookup"><span data-stu-id="bd979-123">Apply Filters to Model Testing Data</span></span>](apply-filters-to-model-testing-data.md)  
  
  
