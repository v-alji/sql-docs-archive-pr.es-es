---
title: Editar manualmente una consulta de predicción | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- modifying prediction queries
- Mining Model Prediction [Analysis Services], modifying prediction queries
- manual prediction query modification [Analysis Services]
ms.assetid: 9f6a9298-49d5-4675-ad49-977a47dff5a6
author: minewiskan
ms.author: owend
ms.openlocfilehash: e887e935dafcd2428859fd959cb7bc64650c660d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87677948"
---
# <a name="manually-edit-a-prediction-query"></a><span data-ttu-id="98e29-102">Modificar manualmente una consulta de predicción</span><span class="sxs-lookup"><span data-stu-id="98e29-102">Manually Edit a Prediction Query</span></span>
  <span data-ttu-id="98e29-103">Después de diseñar una consulta mediante el Generador de consultas de predicción, puede modificarla cambiando a la vista Texto de consulta en la pestaña **Predicción de modelo de minería de datos** del Diseñador de minería de datos.</span><span class="sxs-lookup"><span data-stu-id="98e29-103">After you have designed a query by using the Prediction Query Builder, you can modify the query by switching to Query Text view on the **Mining Model Prediction** tab of Data Mining Designer.</span></span> <span data-ttu-id="98e29-104">Un editor de texto aparece en la parte inferior de la pantalla donde se muestra la consulta creada por el generador de consultas.</span><span class="sxs-lookup"><span data-stu-id="98e29-104">A text editor appears at the bottom of the screen to display the query that the query builder created.</span></span>  
  
 <span data-ttu-id="98e29-105">Cambiar a la la vista de texto de consulta es útil para realizar adiciones a la consulta.</span><span class="sxs-lookup"><span data-stu-id="98e29-105">Switching to Query Text view is useful for making additions to the query.</span></span> <span data-ttu-id="98e29-106">Por ejemplo, puede agregar una cláusula WHERE o cláusula ORDER BY.</span><span class="sxs-lookup"><span data-stu-id="98e29-106">For example, you can add a WHERE clause or ORDER BY clause.</span></span>  
  
 <span data-ttu-id="98e29-107">Use la cuadrícula del Generador de consultas de predicción para insertar los nombres de objetos y de columnas y configurar la sintaxis de las funciones de predicción y, a continuación cambie al modo manual para modificar los valores de parámetro.</span><span class="sxs-lookup"><span data-stu-id="98e29-107">Use the grid in the Prediction Query Builder to insert the names of objects and columns and set up the syntax for individual prediction functions, and then switch to manual editing mode to change parameter values.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="98e29-108">Si regresa a la vista **Diseño** desde la vista **Texto de consulta** , se perderán todos los cambios realizados en la vista **Texto de consulta** .</span><span class="sxs-lookup"><span data-stu-id="98e29-108">If you switch back to **Design** view from **Query Text** view, any changes that you made in **Query Text** view will be lost.</span></span>  
  
### <a name="modify-a-query"></a><span data-ttu-id="98e29-109">Modificar una consulta</span><span class="sxs-lookup"><span data-stu-id="98e29-109">Modify a query</span></span>  
  
1.  <span data-ttu-id="98e29-110">En la pestaña **Predicción de modelo de minería de datos** del Diseñador de minería de datos de [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], haga clic en **SQL**.</span><span class="sxs-lookup"><span data-stu-id="98e29-110">On the **Mining Model Prediction** tab in Data Mining Designer in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], click **SQL**.</span></span>  
  
     <span data-ttu-id="98e29-111">La cuadrícula de la parte inferior de la pantalla se sustituye por un editor de texto que contiene la consulta.</span><span class="sxs-lookup"><span data-stu-id="98e29-111">The grid at the bottom of the screen is replaced by a text editor that contains the query.</span></span> <span data-ttu-id="98e29-112">En este editor puede escribir los cambios que desea realizar en la consulta.</span><span class="sxs-lookup"><span data-stu-id="98e29-112">You can type changes to the query in this editor.</span></span>  
  
2.  <span data-ttu-id="98e29-113">Para ejecutar la consulta, en el menú **Modelo de minería de datos** , seleccione **Resultado**o haga clic en el botón para cambiar a los resultados de la consulta.</span><span class="sxs-lookup"><span data-stu-id="98e29-113">To run the query, on the **Mining Model** menu, select **Result**, or click the button to switch to query results.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="98e29-114">Si la consulta que ha creado no es válida, la ventana Resultados no muestra errores ni resultados.</span><span class="sxs-lookup"><span data-stu-id="98e29-114">If the query that you have created is invalid, the Results window does not display an error and does not display any results.</span></span> <span data-ttu-id="98e29-115">Haga clic en el botón **Diseño** , o seleccione **Diseño** o **Consulta** en el menú **Modelo de minería de datos** para corregir el problema y ejecutar de nuevo la consulta.</span><span class="sxs-lookup"><span data-stu-id="98e29-115">Click the **Design** button, or select **Design** or **Query** from the **Mining Model** menu to correct the problem and run the query again.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="98e29-116">Consulte también</span><span class="sxs-lookup"><span data-stu-id="98e29-116">See Also</span></span>  
 <span data-ttu-id="98e29-117">[Consultas de minería de datos](data-mining-queries.md) </span><span class="sxs-lookup"><span data-stu-id="98e29-117">[Data Mining Queries](data-mining-queries.md) </span></span>  
 <span data-ttu-id="98e29-118">[Predicción Generador de consultas &#40;de minería de datos&#41;](../prediction-query-builder-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="98e29-118">[Prediction Query Builder &#40;Data Mining&#41;](../prediction-query-builder-data-mining.md) </span></span>  
 [<span data-ttu-id="98e29-119">Lección 6: Crear y trabajar con predicciones &#40;Tutorial básico de minería de datos&#41;</span><span class="sxs-lookup"><span data-stu-id="98e29-119">Lesson 6: Creating and Working with Predictions &#40;Basic Data Mining Tutorial&#41;</span></span>](../../tutorials/lesson-6-creating-and-working-with-predictions-basic-data-mining-tutorial.md)  
  
  
