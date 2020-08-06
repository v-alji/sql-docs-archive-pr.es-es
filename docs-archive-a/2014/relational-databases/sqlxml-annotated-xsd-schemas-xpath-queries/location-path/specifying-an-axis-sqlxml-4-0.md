---
title: Especificar un eje (SQLXML 4,0) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- XPath queries [SQLXML], axes
- XPath queries [SQLXML], location paths
- self axis
- attribute axis [SQLXML]
- axis [SQLXML]
- child axis
- parent axis
- location path for XPath query
- axes [SQLXML]
ms.assetid: 65631795-3389-40cf-90ea-85e9438956c5
author: rothja
ms.author: jroth
ms.openlocfilehash: 5e43281fe31d323a7eea19e749b80b59458752b7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87673579"
---
# <a name="specifying-an-axis-sqlxml-40"></a><span data-ttu-id="1368a-102">Especificar un eje (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="1368a-102">Specifying an Axis (SQLXML 4.0)</span></span>
    
-   <span data-ttu-id="1368a-103">El eje especifica la relación jerárquica entre los nodos seleccionados por el paso de ubicación y el nodo de contexto.</span><span class="sxs-lookup"><span data-stu-id="1368a-103">The axis specifies the tree relationship between the nodes selected by the location step and the context node.</span></span> <span data-ttu-id="1368a-104">Se admiten los ejes siguientes: `child`</span><span class="sxs-lookup"><span data-stu-id="1368a-104">The following axes are supported:  `child`</span></span>  
  
     <span data-ttu-id="1368a-105">Contiene el elemento secundario del nodo de contexto.</span><span class="sxs-lookup"><span data-stu-id="1368a-105">Contains the child of the context node.</span></span>  
  
     <span data-ttu-id="1368a-106">La expresión XPath siguiente (ruta de acceso de ubicación) selecciona del nodo de contexto actual todos los **\<Customer>** elementos secundarios:</span><span class="sxs-lookup"><span data-stu-id="1368a-106">The following XPath expression (location path) selects from the current context node all the **\<Customer>** children:</span></span>  
  
    ```  
    child::Customer  
    ```  
  
     <span data-ttu-id="1368a-107">En la consulta XPath siguiente, `child` es el eje.</span><span class="sxs-lookup"><span data-stu-id="1368a-107">In the following XPath query, `child` is the axis.</span></span> <span data-ttu-id="1368a-108">`Customer` es la prueba de nodo.</span><span class="sxs-lookup"><span data-stu-id="1368a-108">`Customer` is the node test.</span></span>  
  
-   `parent`  
  
     <span data-ttu-id="1368a-109">Contiene el elemento primario del nodo de contexto.</span><span class="sxs-lookup"><span data-stu-id="1368a-109">Contains the parent of the context node.</span></span>  
  
     <span data-ttu-id="1368a-110">La expresión XPath siguiente selecciona todos los **\<Customer>** elementos primarios de los **\<Order>** elementos secundarios:</span><span class="sxs-lookup"><span data-stu-id="1368a-110">The following XPath expression selects all the **\<Customer>** parents of the **\<Order>** children:</span></span>  
  
    ```  
    child::Customer/child::Order[parent::Customer/@customerID="ALFKI"]  
    ```  
  
     <span data-ttu-id="1368a-111">Esto equivale a especificar `child::Customer`.</span><span class="sxs-lookup"><span data-stu-id="1368a-111">This is the same as specifying `child::Customer`.</span></span> <span data-ttu-id="1368a-112">En esta consulta XPath, `child` y `parent` son los ejes.</span><span class="sxs-lookup"><span data-stu-id="1368a-112">In this XPath query, `child` and `parent` are the axes.</span></span> <span data-ttu-id="1368a-113">`Customer` y `Order` son las pruebas de nodo.</span><span class="sxs-lookup"><span data-stu-id="1368a-113">`Customer` and `Order` are the node tests.</span></span>  
  
-   `attribute`  
  
     <span data-ttu-id="1368a-114">Contiene el atributo del nodo de contexto.</span><span class="sxs-lookup"><span data-stu-id="1368a-114">Contains the attribute of the context node.</span></span>  
  
     <span data-ttu-id="1368a-115">La expresión XPath siguiente selecciona el atributo **CustomerID** del nodo de contexto:</span><span class="sxs-lookup"><span data-stu-id="1368a-115">The following XPath expression selects the **CustomerID** attribute of the context node:</span></span>  
  
    ```  
    attribute::CustomerID  
    ```  
  
-   `self`  
  
     <span data-ttu-id="1368a-116">Contiene el propio nodo de contexto.</span><span class="sxs-lookup"><span data-stu-id="1368a-116">Contains the context node itself.</span></span>  
  
     <span data-ttu-id="1368a-117">La expresión XPath siguiente selecciona el nodo actual si es el **\<Order>** nodo:</span><span class="sxs-lookup"><span data-stu-id="1368a-117">The following XPath expression selects the current node if it is the **\<Order>** node:</span></span>  
  
    ```  
    self::Order  
    ```  
  
     <span data-ttu-id="1368a-118">En esta consulta XPath, `self` es el eje y `Order` es la prueba de nodo.</span><span class="sxs-lookup"><span data-stu-id="1368a-118">In this XPath query, `self` is the axis and `Order` is the node test.</span></span>  
  
  
