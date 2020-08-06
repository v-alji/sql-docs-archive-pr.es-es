---
title: Agregar un parámetro de varios valores a un informe | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 12ad0e77-4c28-4bbb-ab11-473ae89ec9f1
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 5269293b6a21f3b1d82eb6835efbd275e3be9620
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87744497"
---
# <a name="add-a-multi-value-parameter-to-a-report"></a><span data-ttu-id="e2122-102">Agregar un parámetro de varios valores a un informe</span><span class="sxs-lookup"><span data-stu-id="e2122-102">Add a multi-value parameter to a Report</span></span>
  <span data-ttu-id="e2122-103">Puede agregar un parámetro a un informe que permita al usuario seleccionar más de un valor para el parámetro.</span><span class="sxs-lookup"><span data-stu-id="e2122-103">You can add a parameter to a report that allows the user to select more than one value for the parameter.</span></span>  
  
 <span data-ttu-id="e2122-104">Puede pasar varios valores de parámetro al informe dentro de la dirección URL del informe.</span><span class="sxs-lookup"><span data-stu-id="e2122-104">You can pass multiple parameter values to the report within the report URL.</span></span> <span data-ttu-id="e2122-105">Para ver un ejemplo de dirección URL que incluye un parámetro de varios valores, vea [Pasar un parámetro de informe en una dirección URL](../pass-a-report-parameter-within-a-url.md).</span><span class="sxs-lookup"><span data-stu-id="e2122-105">For a URL example includes a multi-value parameter, see [Pass a Report Parameter Within a URL](../pass-a-report-parameter-within-a-url.md).</span></span>  
  
 <span data-ttu-id="e2122-106">Para obtener información sobre cómo pasar varios valores de parámetro a un procedimiento almacenado, vea [Working With Multi-Select Parameters for SSRS Reports](https://go.microsoft.com/fwlink/?LinkId=321529) (Trabajar con parámetros de selección múltiple en informes de SSRS) en mssqltips.com.</span><span class="sxs-lookup"><span data-stu-id="e2122-106">For information on how to pass multiple parameter values to a stored procedure, see [Working With Multi-Select Parameters for SSRS Reports](https://go.microsoft.com/fwlink/?LinkId=321529) on mssqltips.com.</span></span>  
  
### <a name="to-add-a-multi-value-parameter"></a><span data-ttu-id="e2122-107">Para agregar un parámetro de varios valores</span><span class="sxs-lookup"><span data-stu-id="e2122-107">To add a multi-value parameter</span></span>  
  
1.  <span data-ttu-id="e2122-108">En el Generador de informes, abra el informe al que desea agregar el parámetro de varios valores.</span><span class="sxs-lookup"><span data-stu-id="e2122-108">In Report Builder, open the report that you want to add the multi-value parameter to.</span></span>  
  
2.  <span data-ttu-id="e2122-109">Haga clic con el botón derecho en el conjunto de datos del informe y, después, haga clic en **Propiedades del conjunto de datos**.</span><span class="sxs-lookup"><span data-stu-id="e2122-109">Right-click the report dataset, and then click **Dataset Properties**</span></span>  
  
3.  <span data-ttu-id="e2122-110">Agregue una variable a la consulta del conjunto de datos; para ello, edite el texto de la consulta en el cuadro **Consulta** o agregue un filtro mediante el diseñador de consultas.</span><span class="sxs-lookup"><span data-stu-id="e2122-110">Add a variable to the dataset query by either editing the query text in the **Query** box, or by adding a filter by using the query designer.</span></span> <span data-ttu-id="e2122-111">Para más información, vea [Crear una consulta en el Diseñador de consultas relacionales &#40;Generador de informes y SSRS&#41;](../report-data/build-a-query-in-the-relational-query-designer-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="e2122-111">For more information, see [Build a Query in the Relational Query Designer &#40;Report Builder and SSRS&#41;](../report-data/build-a-query-in-the-relational-query-designer-report-builder-and-ssrs.md).</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="e2122-112">El texto de consulta no debe incluir la instrucción DECLARE para la variable de consulta.</span><span class="sxs-lookup"><span data-stu-id="e2122-112">The query text must not include the DECLARE statement for the query variable.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="e2122-113">El texto de la variable de consulta debe incluir el operador `IN`, como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="e2122-113">The text for the query variable must include the `IN` operator, as shown in the following example.</span></span>  
  
    ```  
    WHERE  
      Production.ProductInventory.ProductID IN (@ProductID)  
    ```  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="e2122-114">Si no incluye los paréntesis alrededor de la variable como se muestra arriba, el informe no se representa y se muestra el error "debe declarar la variable escalar".</span><span class="sxs-lookup"><span data-stu-id="e2122-114">If you don't include the parentheses around the variable as shown above, the report fails to render and the "must declare the scalar variable" error is displayed.</span></span>  
  
     <span data-ttu-id="e2122-115">Se crea automáticamente un parámetro de conjunto de datos para un conjunto de datos incrustado o compartido para la variable de consulta.</span><span class="sxs-lookup"><span data-stu-id="e2122-115">A dataset parameter for an embedded dataset or a shared dataset is created automatically for the query variable.</span></span> <span data-ttu-id="e2122-116">Se crea automáticamente un parámetro de informe para el parámetro de conjunto de datos.</span><span class="sxs-lookup"><span data-stu-id="e2122-116">A report parameter is created automatically for the dataset parameter.</span></span>  
  
4.  <span data-ttu-id="e2122-117">En el panel **Datos de informe** , expanda el nodo **Parámetros** , haga clic con el botón derecho en el parámetro de informe que se creó automáticamente para el parámetro de conjunto de datos y, después, haga clic en **Propiedades del parámetro**.</span><span class="sxs-lookup"><span data-stu-id="e2122-117">In the **Report Data** pane, expand the **Parameters** node, right-click the report parameter that was automatically created for the dataset parameter, and then click **Parameter Properties**.</span></span>  
  
5.  <span data-ttu-id="e2122-118">En la pestaña **General** , seleccione **Permitir varios valores** para permitir a los usuarios seleccionar más de un valor para el parámetro.</span><span class="sxs-lookup"><span data-stu-id="e2122-118">In the **General** tab, select **Allow multiple values** to allow a user to select more than one value for the parameter.</span></span>  
  
6.  <span data-ttu-id="e2122-119">(Opcionalmente) En la pestaña **Valores disponibles** , especifique una lista de valores disponibles que se mostrarán al usuario.</span><span class="sxs-lookup"><span data-stu-id="e2122-119">(Optionally) In the **Available** values tab, specify a list of available values to display to the user.</span></span>  
  
     <span data-ttu-id="e2122-120">La existencia de una lista de valores disponibles limita las opciones del usuario a únicamente los valores válidos para el parámetro.</span><span class="sxs-lookup"><span data-stu-id="e2122-120">An available values list limits the choices a user can make to only valid values for the parameter.</span></span> <span data-ttu-id="e2122-121">Cuando hay varios valores, en la parte superior de la lista aparece la característica **Seleccionar todo** , que permite al usuario seleccionar o desactivar todos los valores con un solo clic.</span><span class="sxs-lookup"><span data-stu-id="e2122-121">For multiple values, the top of list begins with a **Select All** feature so the user can select or clear all values with a single click.</span></span> <span data-ttu-id="e2122-122">Si opta por obtener los valores disponibles para el parámetro de informe a partir de una consulta del conjunto de datos, asegúrese de seleccionar un conjunto de datos que no contenga la variable de consulta que se asoció al mismo parámetro de informe.</span><span class="sxs-lookup"><span data-stu-id="e2122-122">If you choose to get the available values for the report parameter from a dataset query, be sure to select a dataset that does not contain the query variable that is associated with the same report parameter.</span></span>  
  
     <span data-ttu-id="e2122-123">Para más información, vea [Agregar, cambiar o eliminar los valores disponibles para un parámetro de informe &#40;Generador de informes y SSRS&#41;](add-change-or-delete-available-values-for-a-report-parameter.md).</span><span class="sxs-lookup"><span data-stu-id="e2122-123">For more information, see [Add, Change, or Delete Available Values for a Report Parameter &#40;Report Builder and SSRS&#41;](add-change-or-delete-available-values-for-a-report-parameter.md).</span></span>  
  
### <a name="to-add-a-multi-value-parameter"></a><span data-ttu-id="e2122-124">Para agregar un parámetro de varios valores</span><span class="sxs-lookup"><span data-stu-id="e2122-124">To add a multi-value parameter</span></span>  
  
1.  <span data-ttu-id="e2122-125">En el Generador de informes, abra el informe al que desea agregar el parámetro de varios valores.</span><span class="sxs-lookup"><span data-stu-id="e2122-125">In Report Builder, open the report that you want to add the multi-value parameter to.</span></span>  
  
2.  <span data-ttu-id="e2122-126">Haga clic con el botón derecho en el conjunto de datos del informe y, después, haga clic en **Propiedades del conjunto de datos**.</span><span class="sxs-lookup"><span data-stu-id="e2122-126">Right-click the report dataset, and then click **Dataset Properties**</span></span>  
  
3.  <span data-ttu-id="e2122-127">Agregue una variable a la consulta del conjunto de datos; para ello, edite el texto de la consulta en el cuadro **Consulta** o agregue un filtro mediante el diseñador de consultas.</span><span class="sxs-lookup"><span data-stu-id="e2122-127">Add a variable to the dataset query by either editing the query text in the **Query** box, or by adding a filter by using the query designer.</span></span> <span data-ttu-id="e2122-128">Para más información, vea [Crear una consulta en el Diseñador de consultas relacionales &#40;Generador de informes y SSRS&#41;](../report-data/build-a-query-in-the-relational-query-designer-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="e2122-128">For more information, see [Build a Query in the Relational Query Designer &#40;Report Builder and SSRS&#41;](../report-data/build-a-query-in-the-relational-query-designer-report-builder-and-ssrs.md).</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="e2122-129">El texto de consulta no debe incluir la instrucción DECLARE para la variable de consulta.</span><span class="sxs-lookup"><span data-stu-id="e2122-129">The query text must not include the DECLARE statement for the query variable.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="e2122-130">El texto de la variable de consulta debe incluir el operador `IN`, como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="e2122-130">The text for the query variable must include the `IN` operator, as shown in the following example.</span></span>  
  
    ```  
    WHERE  
      Production.ProductInventory.ProductID IN (@ProductID)  
    ```  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="e2122-131">Si no incluye los paréntesis alrededor de la variable como se muestra arriba, el informe no se representa y se muestra el error "debe declarar la variable escalar".</span><span class="sxs-lookup"><span data-stu-id="e2122-131">If you don't include the parentheses around the variable as shown above, the report fails to render and the "must declare the scalar variable" error is displayed.</span></span>  
  
     <span data-ttu-id="e2122-132">Se crea automáticamente un parámetro de conjunto de datos para un conjunto de datos incrustado o compartido para la variable de consulta.</span><span class="sxs-lookup"><span data-stu-id="e2122-132">A dataset parameter for an embedded dataset or a shared dataset is created automatically for the query variable.</span></span> <span data-ttu-id="e2122-133">Se crea automáticamente un parámetro de informe para el parámetro de conjunto de datos.</span><span class="sxs-lookup"><span data-stu-id="e2122-133">A report parameter is created automatically for the dataset parameter.</span></span>  
  
4.  <span data-ttu-id="e2122-134">En el panel **Datos de informe** , expanda el nodo **Parámetros** , haga clic con el botón derecho en el parámetro de informe que se creó automáticamente para el parámetro de conjunto de datos y, después, haga clic en **Propiedades del parámetro**.</span><span class="sxs-lookup"><span data-stu-id="e2122-134">In the **Report Data** pane, expand the **Parameters** node, right-click the report parameter that was automatically created for the dataset parameter, and then click **Parameter Properties**.</span></span>  
  
5.  <span data-ttu-id="e2122-135">En la pestaña **General** , seleccione **Permitir varios valores** para permitir a los usuarios seleccionar más de un valor para el parámetro.</span><span class="sxs-lookup"><span data-stu-id="e2122-135">In the **General** tab, select **Allow multiple values** to allow a user to select more than one value for the parameter.</span></span>  
  
6.  <span data-ttu-id="e2122-136">(Opcionalmente) En la pestaña **Valores disponibles** , especifique una lista de valores disponibles que se mostrarán al usuario.</span><span class="sxs-lookup"><span data-stu-id="e2122-136">(Optionally) In the **Available** values tab, specify a list of available values to display to the user.</span></span>  
  
     <span data-ttu-id="e2122-137">La existencia de una lista de valores disponibles limita las opciones del usuario a únicamente los valores válidos para el parámetro.</span><span class="sxs-lookup"><span data-stu-id="e2122-137">An available values list limits the choices a user can make to only valid values for the parameter.</span></span> <span data-ttu-id="e2122-138">Cuando hay varios valores, en la parte superior de la lista aparece la característica **Seleccionar todo** , que permite al usuario seleccionar o desactivar todos los valores con un solo clic.</span><span class="sxs-lookup"><span data-stu-id="e2122-138">For multiple values, the top of list begins with a **Select All** feature so the user can select or clear all values with a single click.</span></span> <span data-ttu-id="e2122-139">Si opta por obtener los valores disponibles para el parámetro de informe a partir de una consulta del conjunto de datos, asegúrese de seleccionar un conjunto de datos que no contenga la variable de consulta que se asoció al mismo parámetro de informe.</span><span class="sxs-lookup"><span data-stu-id="e2122-139">If you choose to get the available values for the report parameter from a dataset query, be sure to select a dataset that does not contain the query variable that is associated with the same report parameter.</span></span>  
  
     <span data-ttu-id="e2122-140">Para más información, vea [Agregar, cambiar o eliminar los valores disponibles para un parámetro de informe &#40;Generador de informes y SSRS&#41;](add-change-or-delete-available-values-for-a-report-parameter.md).</span><span class="sxs-lookup"><span data-stu-id="e2122-140">For more information, see [Add, Change, or Delete Available Values for a Report Parameter &#40;Report Builder and SSRS&#41;](add-change-or-delete-available-values-for-a-report-parameter.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e2122-141">Consulte también</span><span class="sxs-lookup"><span data-stu-id="e2122-141">See Also</span></span>  
 <span data-ttu-id="e2122-142">[Agregar parámetros en cascada a un informe &#40;Generador de informes y SSRS&#41;](add-cascading-parameters-to-a-report-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="e2122-142">[Add Cascading Parameters to a Report &#40;Report Builder and SSRS&#41;](add-cascading-parameters-to-a-report-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="e2122-143">Agregar, cambiar o eliminar parámetros de informe &#40;Generador de informes y SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="e2122-143">Add, Change, or Delete a Report Parameter &#40;Report Builder and SSRS&#41;</span></span>](add-change-or-delete-a-report-parameter-report-builder-and-ssrs.md)  
  
  
