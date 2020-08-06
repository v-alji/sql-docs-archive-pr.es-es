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
# <a name="specifying-an-axis-sqlxml-40"></a>Especificar un eje (SQLXML 4.0)
    
-   El eje especifica la relación jerárquica entre los nodos seleccionados por el paso de ubicación y el nodo de contexto. Se admiten los ejes siguientes: `child`  
  
     Contiene el elemento secundario del nodo de contexto.  
  
     La expresión XPath siguiente (ruta de acceso de ubicación) selecciona del nodo de contexto actual todos los **\<Customer>** elementos secundarios:  
  
    ```  
    child::Customer  
    ```  
  
     En la consulta XPath siguiente, `child` es el eje. `Customer` es la prueba de nodo.  
  
-   `parent`  
  
     Contiene el elemento primario del nodo de contexto.  
  
     La expresión XPath siguiente selecciona todos los **\<Customer>** elementos primarios de los **\<Order>** elementos secundarios:  
  
    ```  
    child::Customer/child::Order[parent::Customer/@customerID="ALFKI"]  
    ```  
  
     Esto equivale a especificar `child::Customer`. En esta consulta XPath, `child` y `parent` son los ejes. `Customer` y `Order` son las pruebas de nodo.  
  
-   `attribute`  
  
     Contiene el atributo del nodo de contexto.  
  
     La expresión XPath siguiente selecciona el atributo **CustomerID** del nodo de contexto:  
  
    ```  
    attribute::CustomerID  
    ```  
  
-   `self`  
  
     Contiene el propio nodo de contexto.  
  
     La expresión XPath siguiente selecciona el nodo actual si es el **\<Order>** nodo:  
  
    ```  
    self::Order  
    ```  
  
     En esta consulta XPath, `self` es el eje y `Order` es la prueba de nodo.  
  
  
