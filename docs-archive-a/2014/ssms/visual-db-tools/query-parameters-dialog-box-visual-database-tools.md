---
title: Cuadro de diálogo Parámetros de la consulta (Visual Database Tools) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- vdtsql.chm:69645
- vdt.dlgbox.definequeryparameters
ms.assetid: 31cdaee2-d7cd-4d64-a45f-924b27e8b1f0
author: stevestein
ms.author: sstein
ms.openlocfilehash: 76052876ad2899fc959aa7fc49f4299e08bac713
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87744959"
---
# <a name="query-parameters-dialog-box-visual-database-tools"></a><span data-ttu-id="42513-102">Parámetros de la consulta (cuadro de diálogo, Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="42513-102">Query Parameters Dialog Box (Visual Database Tools)</span></span>
  <span data-ttu-id="42513-103">Este cuadro de diálogo permite escribir los valores de los parámetros definidos en la consulta.</span><span class="sxs-lookup"><span data-stu-id="42513-103">This dialog allows you to enter values for the parameters defined in the query.</span></span> <span data-ttu-id="42513-104">Este cuadro de diálogo aparece cuando se ejecuta una consulta con parámetros que requieren la entrada de datos por parte del usuario en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="42513-104">This dialog box appears when you execute a query that contains parameters that require end-user input at run time.</span></span>  
  
## <a name="options"></a><span data-ttu-id="42513-105">Opciones</span><span class="sxs-lookup"><span data-stu-id="42513-105">Options</span></span>  
 <span data-ttu-id="42513-106">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="42513-106">**Name**</span></span>  
 <span data-ttu-id="42513-107">Muestra los parámetros definidos para la consulta que se va a ejecutar.</span><span class="sxs-lookup"><span data-stu-id="42513-107">Lists the parameters defined for the query being executed.</span></span> <span data-ttu-id="42513-108">Si la consulta contiene parámetros con nombre, estos nombres aparecerán en la lista.</span><span class="sxs-lookup"><span data-stu-id="42513-108">If the query contains named parameters, the names appear in the list.</span></span> <span data-ttu-id="42513-109">Si la consulta contiene parámetros sin nombre, los nombres de parámetro definidos por el sistema se enumerarán para cada parámetro de la consulta.</span><span class="sxs-lookup"><span data-stu-id="42513-109">If the query contains unnamed parameters, system-defined parameter names are listed for each parameter in the query.</span></span>  
  
 <span data-ttu-id="42513-110">**Valor**</span><span class="sxs-lookup"><span data-stu-id="42513-110">**Value**</span></span>  
 <span data-ttu-id="42513-111">Escriba el valor de cada uno de los parámetros mostrados en **Nombre**.</span><span class="sxs-lookup"><span data-stu-id="42513-111">Enter the value for each parameter listed under **Name**.</span></span> <span data-ttu-id="42513-112">El último valor utilizado aparece como valor predeterminado del parámetro.</span><span class="sxs-lookup"><span data-stu-id="42513-112">The value used most recently appears as the default parameter value.</span></span>  
  
## <a name="example"></a><span data-ttu-id="42513-113">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="42513-113">Example</span></span>  
 <span data-ttu-id="42513-114">La consulta siguiente en el panel de SQL abre el cuadro de diálogo Parámetros de la consulta cuando se ejecuta en la base de datos [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="42513-114">The following query in the SQL Pane, opens the Query Parameters dialog box when executed in the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] database.</span></span>  
  
```  
SELECT   FirstName, LastName  
FROM    Person.Person AS Lastname  
WHERE   (LastName = @Param1);  
```  
  
## <a name="see-also"></a><span data-ttu-id="42513-115">Consulte también</span><span class="sxs-lookup"><span data-stu-id="42513-115">See Also</span></span>  
 [<span data-ttu-id="42513-116">Realizar consultas con parámetros &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="42513-116">Query with Parameters &#40;Visual Database Tools&#41;</span></span>](visual-database-tools.md)  
  
  
