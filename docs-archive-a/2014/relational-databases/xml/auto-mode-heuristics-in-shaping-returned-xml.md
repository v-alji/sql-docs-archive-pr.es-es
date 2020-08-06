---
title: Heurística del modo AUTO para dar forma al XML devuelto | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- AUTO FOR XML mode, heuristics in shaping returned XML
ms.assetid: 6c5cb6c1-2921-4ba1-8100-0bf8074f9103
author: rothja
ms.author: jroth
ms.openlocfilehash: 7a64cda8989e1e45d4ad869f8883e1c9d65f4b7e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87662714"
---
# <a name="auto-mode-heuristics-in-shaping-returned-xml"></a><span data-ttu-id="30559-102">Heurística del modo AUTO para dar forma al XML devuelto</span><span class="sxs-lookup"><span data-stu-id="30559-102">AUTO Mode Heuristics in Shaping Returned XML</span></span>
  <span data-ttu-id="30559-103">El modo AUTO determina la forma del XML devuelto en función de la consulta.</span><span class="sxs-lookup"><span data-stu-id="30559-103">AUTO mode determines the shape of returned XML based on the query.</span></span> <span data-ttu-id="30559-104">Al determinar cómo se anidan los elementos, la heurística del modo AUTO compara los valores de columna de filas adyacentes.</span><span class="sxs-lookup"><span data-stu-id="30559-104">In determining how elements are to be nested, AUTO mode heuristics compare column values in adjacent rows.</span></span> <span data-ttu-id="30559-105">Se comparan columnas de todos los tipos, excepto **ntext**, **text**, **image**y **xml**.</span><span class="sxs-lookup"><span data-stu-id="30559-105">Columns of all types, except **ntext**, **text**, **image**, and **xml**, are compared.</span></span> <span data-ttu-id="30559-106">Se comparan columnas de tipo **(n)varchar(max)** y **varbinary(max)** .</span><span class="sxs-lookup"><span data-stu-id="30559-106">Columns of type **(n)varchar(max)** and **varbinary(max)** are compared.</span></span>  
  
 <span data-ttu-id="30559-107">El siguiente ejemplo muestra la heurística del modo AUTO que determina la forma del XML resultante:</span><span class="sxs-lookup"><span data-stu-id="30559-107">The following example illustrates the AUTO mode heuristics that determine the shape of the resulting XML:</span></span>  
  
```  
SELECT T1.Id, T2.Id, T1.Name  
FROM   T1, T2  
WHERE ...  
FOR XML AUTO  
ORDER BY T1.Id  
```  
  
 <span data-ttu-id="30559-108">Para determinar dónde comienza un nuevo elemento <`T1`>, se comparan todos los valores de columna de T1, excepto **ntext**, **text**, **image** y **xml**, si no se especifica la clave en la tabla T1.</span><span class="sxs-lookup"><span data-stu-id="30559-108">To determine where a new <`T1`> element starts, all column values of T1, except **ntext**, **text**, **image** and **xml**, are compared if the key on the table T1 is not specified.</span></span> <span data-ttu-id="30559-109">Después imagine que la columna **Name** es de tipo **nvarchar(40)** y que la instrucción SELECT devuelve este conjunto de filas:</span><span class="sxs-lookup"><span data-stu-id="30559-109">Next, assume that the **Name** column is **nvarchar(40)** and the SELECT statement returns this rowset:</span></span>  
  
```  
T1.Id  T1.Name  T2.Id  
-----------------------  
1       Andrew    2  
1       Andrew    3  
1       Nancy     4  
```  
  
 <span data-ttu-id="30559-110">La heurística del modo AUTO compara todos los valores de la tabla T1, las columnas Id y Name.</span><span class="sxs-lookup"><span data-stu-id="30559-110">The AUTO mode heuristics compare all the values of table T1, the Id and Name columns.</span></span> <span data-ttu-id="30559-111">Puesto que las dos primeras filas tienen los mismos valores para las columnas Id y Name, se agrega al resultado un elemento \<T1> que tiene dos elementos \<T2> secundarios.</span><span class="sxs-lookup"><span data-stu-id="30559-111">Because the first two rows have the same values for the Id and Name columns, one \<T1> element having two \<T2> child elements is added in the result.</span></span>  
  
 <span data-ttu-id="30559-112">A continuación se muestra el XML devuelto:</span><span class="sxs-lookup"><span data-stu-id="30559-112">Following is the XML that is returned:</span></span>  
  
```  
<T1 Id="1" Name="Andrew">  
    <T2 Id="2" />  
    <T2 Id="3" />  
</T1>  
<T1 Id="1" Name="Nancy" >  
      <T2 Id="4" />  
</T>  
```  
  
 <span data-ttu-id="30559-113">Imagine ahora que la columna Name es de tipo **text** .</span><span class="sxs-lookup"><span data-stu-id="30559-113">Now assume that the Name column is of **text** type.</span></span> <span data-ttu-id="30559-114">La heurística del modo AUTO no compara los valores para este tipo.</span><span class="sxs-lookup"><span data-stu-id="30559-114">The AUTO mode heuristics do not compare the values for this type.</span></span> <span data-ttu-id="30559-115">En su lugar, asume que los valores no son los mismos.</span><span class="sxs-lookup"><span data-stu-id="30559-115">Instead, it assumes that the values are not the same.</span></span> <span data-ttu-id="30559-116">Esto genera el siguiente XML:</span><span class="sxs-lookup"><span data-stu-id="30559-116">This results in XML generation as shown in the following:</span></span>  
  
```  
<T1 Id="1" Name="Andrew" >  
  <T2 Id="2" />  
</T1>  
<T1 Id="1" Name="Andrew" >  
  <T2 Id="3" />  
</T1>  
<T1 Id="1" Name="Nancy" >  
  <T2 Id="4" />  
</T1>  
```  
  
## <a name="see-also"></a><span data-ttu-id="30559-117">Consulte también</span><span class="sxs-lookup"><span data-stu-id="30559-117">See Also</span></span>  
 [<span data-ttu-id="30559-118">Usar el modo AUTO con FOR XML</span><span class="sxs-lookup"><span data-stu-id="30559-118">Use AUTO Mode with FOR XML</span></span>](use-auto-mode-with-for-xml.md)  
  
  
