---
title: Funciones definidas por el usuario y procedimientos almacenados | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: reference
helpviewer_keywords:
- stored procedures [ADOMD.NET]
- ADOMD.NET, user defined functions
- user defined functions [ADOMD.NET]
- ADOMD.NET, UDFs
- ADOMD.NET, stored procedures
ms.assetid: 07e8aa47-37d4-4bbc-8bff-49e422d12897
author: minewiskan
ms.author: owend
ms.openlocfilehash: a49aa41d158bf2c9fd1ebb1a711d6ff35c0df98b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87743679"
---
# <a name="user-defined-functions-and-stored-procedures"></a><span data-ttu-id="22402-102">Funciones definidas por el usuario y procedimientos almacenados</span><span class="sxs-lookup"><span data-stu-id="22402-102">User Defined Functions and Stored Procedures</span></span>
  <span data-ttu-id="22402-103">Con los objetos de servidor ADOMD.net, puede crear funciones definidas por el usuario (UDF) o procedimientos almacenados para [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] que interactúen con metadatos y datos del servidor.</span><span class="sxs-lookup"><span data-stu-id="22402-103">With ADOMD.NET server objects, you can create user defined function (UDF) or stored procedures for [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] that interact with metadata and data from the server.</span></span> <span data-ttu-id="22402-104">Se llama a estos métodos incrustados a través de instrucciones de expresiones multidimensionales (MDX) o extensiones de minería de datos (DMX) para proporcionar una funcionalidad adicional sin las latencias asoció a las comunicaciones de red.</span><span class="sxs-lookup"><span data-stu-id="22402-104">These in-process methods are called through Multidimensional Expressions (MDX) or Data Mining Extensions (DMX) statements to provide added functionality without the latencies associated with network communications.</span></span>  
  
## <a name="udf-examples"></a><span data-ttu-id="22402-105">Ejemplos de UDF</span><span class="sxs-lookup"><span data-stu-id="22402-105">UDF Examples</span></span>  
 <span data-ttu-id="22402-106">UDF es un método al que se puede llamar en el contexto de una instrucción MDX o DMX, admite cualquier número de parámetros y devuelve cualquier tipo de datos.</span><span class="sxs-lookup"><span data-stu-id="22402-106">A UDF is a method that can be called in the context of an MDX or DMX statement, can take any number of parameters, and can return any type of data.</span></span>  
  
 <span data-ttu-id="22402-107">Un UDF que se crea mediante MDX es similar al que se crea para DMX.</span><span class="sxs-lookup"><span data-stu-id="22402-107">A UDF created using MDX is similar to one created for DMX.</span></span> <span data-ttu-id="22402-108">La principal diferencia es que determinadas propiedades del objeto [Microsoft. AnalysisServices. AdomdServer. Context](/previous-versions/sql/sql-server-2014/ms143353(v=sql.120)) , como las propiedades [Microsoft. AnalysisServices. AdomdServer. Context. CurrentCube \*](/previous-versions/sql/sql-server-2014/ms137081(v=sql.120)) y [Microsoft. AnalysisServices. AdomdServer. Context. CurrentMiningModel \*](/previous-versions/sql/sql-server-2014/ms137178(v=sql.120)) , solo están disponibles para un lenguaje de scripting o para el otro.</span><span class="sxs-lookup"><span data-stu-id="22402-108">The main difference is that certain properties of the [Microsoft.AnalysisServices.AdomdServer.Context](/previous-versions/sql/sql-server-2014/ms143353(v=sql.120)) object, such as the [Microsoft.AnalysisServices.AdomdServer.Context.CurrentCube\*](/previous-versions/sql/sql-server-2014/ms137081(v=sql.120)) and [Microsoft.AnalysisServices.AdomdServer.Context.CurrentMiningModel\*](/previous-versions/sql/sql-server-2014/ms137178(v=sql.120)) properties, are available only for one scripting language or the other.</span></span>  
  
 <span data-ttu-id="22402-109">En los ejemplos siguientes se muestra cómo usar un método UDF para devolver una descripción del nodo, filtrar tuplas y aplican un filtro a una tupla.</span><span class="sxs-lookup"><span data-stu-id="22402-109">The following examples show how to use a UDF to return a node description, filter tuples, and apply a filter to a tuple.</span></span>  
  
### <a name="returning-a-node-description"></a><span data-ttu-id="22402-110">Devolver una descripción del nodo.</span><span class="sxs-lookup"><span data-stu-id="22402-110">Returning a Node Description</span></span>  
 <span data-ttu-id="22402-111">En el ejemplo siguiente se crea un UDF que devuelve la descripción del nodo para un nodo especificado.</span><span class="sxs-lookup"><span data-stu-id="22402-111">The following example creates a UDF that returns the node description for a specified node.</span></span> <span data-ttu-id="22402-112">UDF usa el contexto actual en el que se ejecuta y utiliza una cláusula DMX FROM para recuperar el nodo del modelo de minería actual.</span><span class="sxs-lookup"><span data-stu-id="22402-112">The UDF uses the current context in which it is being run, and uses a DMX FROM clause to retrieve the node from the current mining model.</span></span>  
  
```  
public string GetNodeDescription(string nodeUniqueName)  
{  
   return Context.CurrentMiningModel.GetNodeFromUniqueName(nodeUniqueName).Description;  
}  
```  
  
 <span data-ttu-id="22402-113">Una vez implementado, la expresión DMX siguiente puede llamar al ejemplo UDF anterior, que recupera el nodo de predicción más probable.</span><span class="sxs-lookup"><span data-stu-id="22402-113">Once deployed, the previous UDF example can be called by the following DMX expression, which retrieves the most-likely prediction node.</span></span> <span data-ttu-id="22402-114">La descripción contiene información que describe las condiciones que constituyen el nodo de predicción.</span><span class="sxs-lookup"><span data-stu-id="22402-114">The description contains information that describes the conditions that make up the prediction node.</span></span>  
  
```  
select Cluster(), SampleAssembly.GetNodeDescription( PredictNodeId(Cluster()) ) FROM [Customer Clusters]  
```  
  
### <a name="returning-tuples"></a><span data-ttu-id="22402-115">Devolver tuplas</span><span class="sxs-lookup"><span data-stu-id="22402-115">Returning Tuples</span></span>  
 <span data-ttu-id="22402-116">En el ejemplo siguiente se establece un conjunto y un recuento del retorno, y se recuperan de forma aleatoria las tuplas del conjunto, devolviendo un subconjunto final:</span><span class="sxs-lookup"><span data-stu-id="22402-116">The following example takes a set and a return count, and randomly retrieves tuples from the set, returning a final subset:</span></span>  
  
```  
public Set RandomSample(Set set, int returnCount)  
{  
   //Return the original set if there are fewer tuples  
   //in the set than the number requested.  
   if (set.Tuples.Count <= returnCount)  
      return set;  
  
   System.Random r = new System.Random();  
   SetBuilder returnSet = new SetBuilder();  
  
   //Retrieve random tuples until the return set is filled.  
   int i = set.Tuples.Count;  
   foreach (Tuple t in set.Tuples)  
   {  
      if (r.Next(i) < returnCount)  
      {  
         returnCount--;  
         returnSet.Add(t);  
      }  
      i--;  
      //Stop the loop if we have enough tuples.  
      if (returnCount == 0)  
         break;  
   }  
   return returnSet.ToSet();  
}  
```  
  
 <span data-ttu-id="22402-117">Se llama al ejemplo anterior en el ejemplo MDX siguiente.</span><span class="sxs-lookup"><span data-stu-id="22402-117">The previous example is called in the following MDX example.</span></span> <span data-ttu-id="22402-118">En este ejemplo de MDX, se recuperan cinco Estados o provincias aleatorios de la base de datos de **Adventure Works** .</span><span class="sxs-lookup"><span data-stu-id="22402-118">In this MDX example, five random states or provinces are retrieved from the **Adventure Works** database.</span></span>  
  
```  
SELECT SampleAssembly.RandomSample([Geography].[State-Province].Members, 5) on ROWS,   
[Date].[Calendar].[Calendar Year] on COLUMNS  
FROM [Adventure Works]  
WHERE [Measures].[Reseller Freight Cost]  
```  
  
### <a name="applying-a-filter-to-a-tuple"></a><span data-ttu-id="22402-119">Aplicar un filtro a una tupla</span><span class="sxs-lookup"><span data-stu-id="22402-119">Applying a Filter to a Tuple</span></span>  
 <span data-ttu-id="22402-120">En el ejemplo siguiente, se define un UDF para que establezca un conjunto y aplique un filtro a cada tupla en el conjunto mediante el objeto Expression.</span><span class="sxs-lookup"><span data-stu-id="22402-120">In the following example, a UDF is defined that takes a set, and applies a filter to each tuple in the set, using the Expression object.</span></span> <span data-ttu-id="22402-121">Cualquier tupla que cumpla el filtro se agregará a un conjunto que se devuelve.</span><span class="sxs-lookup"><span data-stu-id="22402-121">Any tuples that conform to the filter will be added to a set that is returned.</span></span>  
  
 [!code-csharp[Adomd.NetServer#FilterSet](../../snippets/csharp/SQL14/adomd.net/adomd.netserver/cs/class1.cs#filterset)]  
  
 <span data-ttu-id="22402-122">En el siguiente ejemplo MDX se llama al ejemplo anterior, que filtra el conjunto por ciudades con nombres que empiezan por 'A.'</span><span class="sxs-lookup"><span data-stu-id="22402-122">The previous example is called in the following MDX example, which filters the set to cities with names beginning with 'A'.</span></span>  
  
```  
Select Measures.Members on Rows,  
SampleAssembly.FilterSet([Customer].[Customer Geography].[City], "[Customer].[Customer Geography].[City].CurrentMember.Name < 'B'") on Columns  
From [Adventure Works]  
```  
  
## <a name="stored-procedure-example"></a><span data-ttu-id="22402-123">Ejemplo de procedimiento almacenado</span><span class="sxs-lookup"><span data-stu-id="22402-123">Stored Procedure Example</span></span>  
 <span data-ttu-id="22402-124">En el ejemplo siguiente, un procedimiento almacenado basado en MDX utiliza AMO para crear particiones para Internet Sales si es necesario.</span><span class="sxs-lookup"><span data-stu-id="22402-124">In the following example, an MDX-based stored procedure uses AMO to create partitions, if needed, for Internet Sales.</span></span>  
  
 [!code-csharp[Adomd.NetServer#CreateInternetSalesMeasureGroupPartitions](../../snippets/csharp/SQL14/adomd.net/adomd.netserver/cs/class1.cs#createinternetsalesmeasuregrouppartitions)]  
  
  
