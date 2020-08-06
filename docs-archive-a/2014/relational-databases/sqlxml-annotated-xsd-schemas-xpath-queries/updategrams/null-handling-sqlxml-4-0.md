---
title: Control de valores NULL (SQLXML 4,0) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- updg:nullvalue attribute
- updategrams [SQLXML], null values
- nullvalue attribute
- null values [SQLXML]
ms.assetid: 5e11eebb-d94e-4ce6-a6d0-870225706bc1
author: rothja
ms.author: jroth
ms.openlocfilehash: 430643e8a6c9bd3dd00b2763990645c6a162ee40
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87674740"
---
# <a name="null-handling-sqlxml-40"></a><span data-ttu-id="6e1af-102">Controlar valores NULL (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="6e1af-102">NULL Handling (SQLXML 4.0)</span></span>
  <span data-ttu-id="6e1af-103">La sintaxis XML indica NULL como una ausencia.</span><span class="sxs-lookup"><span data-stu-id="6e1af-103">XML syntax denotes NULL as an absence.</span></span> <span data-ttu-id="6e1af-104">(Por ejemplo, si un valor de atributo o elemento es NULL, ese atributo o elemento está ausente del documento XML). En [!INCLUDE[msCoName](../../../includes/msconame-md.md)] SQLXML, el `updg:nullvalue` atributo permite especificar null para un valor de elemento o atributo.</span><span class="sxs-lookup"><span data-stu-id="6e1af-104">(For example, if an attribute or element value is NULL, that attribute or element is absent from the XML document.) In [!INCLUDE[msCoName](../../../includes/msconame-md.md)] SQLXML, the `updg:nullvalue` attribute enables specifying NULL for an element or attribute value.</span></span>  
  
 <span data-ttu-id="6e1af-105">Por ejemplo, el siguiente diagrama garantiza que el valor de **título** de un contacto con **ContactID** de 64 es NULL y, a continuación, actualiza el valor del **título** a "Mr".</span><span class="sxs-lookup"><span data-stu-id="6e1af-105">For example, the following updategram ensures that the **Title** value for a contact with **ContactID** of 64 is NULL, and then updates the **Title** value to "Mr."</span></span> <span data-ttu-id="6e1af-106">para este contacto.</span><span class="sxs-lookup"><span data-stu-id="6e1af-106">for this contact.</span></span>  
  
```  
<ROOT xmlns:updg="urn:schemas-microsoft-com:xml-updategram">  
  <updg:sync updg:nullvalue="IsNULL"  >  
    <updg:before>  
       <Person.Contact ContactID="64" Title="IsNULL" />  
    </updg:before>  
    <updg:after>  
       <Person.Contact ContactID="64" Title="Mr." />  
    </updg:after>  
  </updg:sync>  
</ROOT>  
```  
  
 <span data-ttu-id="6e1af-107">Cuando se pasan parámetros a un diagrama de actualización, se puede pasar NULL como valor de parámetro.</span><span class="sxs-lookup"><span data-stu-id="6e1af-107">When parameters are passed to an updategram, NULL can be passed as the parameter value.</span></span> <span data-ttu-id="6e1af-108">Esto se hace especificando el atributo `nullvalue` en el bloque `<updg:header>`.</span><span class="sxs-lookup"><span data-stu-id="6e1af-108">This is done by specifying the `nullvalue` attribute in the `<updg:header>` block.</span></span> <span data-ttu-id="6e1af-109">Para obtener un ejemplo, vea [pasar parámetros a diagramas &#40;SQLXML 4,0&#41;](passing-parameters-to-updategrams-sqlxml-4-0.md).</span><span class="sxs-lookup"><span data-stu-id="6e1af-109">For an example, see [Passing Parameters to Updategrams &#40;SQLXML 4.0&#41;](passing-parameters-to-updategrams-sqlxml-4-0.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6e1af-110">Consulte también</span><span class="sxs-lookup"><span data-stu-id="6e1af-110">See Also</span></span>  
 [<span data-ttu-id="6e1af-111">Consideraciones de seguridad de diagrama &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="6e1af-111">Updategram Security Considerations &#40;SQLXML 4.0&#41;</span></span>](../security/updategram-security-considerations-sqlxml-4-0.md)  
  
  
