---
title: Funcionalidad del servidor de ADOMD.NET | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: reference
helpviewer_keywords:
- functionality [ADOMD.NET]
- ADOMD.NET, functionality
ms.assetid: b74c6957-3f64-4e09-aa09-d06ee93f82fa
author: minewiskan
ms.author: owend
ms.openlocfilehash: f00215c6bcc0104c920be29e0837288a469b252e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87744417"
---
# <a name="adomdnet-server-functionality"></a><span data-ttu-id="b8d60-102">Funcionalidad del servidor de ADOMD.NET</span><span class="sxs-lookup"><span data-stu-id="b8d60-102">ADOMD.NET Server Functionality</span></span>
  <span data-ttu-id="b8d60-103">Todos los objetos de servidor de ADOMD.NET proporcionan acceso de solo lectura a los datos y metadatos del servidor.</span><span class="sxs-lookup"><span data-stu-id="b8d60-103">All ADOMD.NET server objects provide read-only access to the data and metadata on the server.</span></span> <span data-ttu-id="b8d60-104">Para recuperar datos y metadatos, utilice el modelo de objetos del servidor ADOMD.NET, ya que el modelo de objetos de servidor no admite conjuntos de filas de esquema.</span><span class="sxs-lookup"><span data-stu-id="b8d60-104">To retrieve data and metadata, you use the ADOMD.NET server object model as the server object model does not support schema rowsets.</span></span>  
  
 <span data-ttu-id="b8d60-105">Con los objetos de servidor ADOMD.NET, puede crear una función definida por el usuario (UDF) o un procedimiento almacenado para [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b8d60-105">With ADOMD.NET server objects, you can create a user defined function (UDF) or a stored procedure for [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span></span> <span data-ttu-id="b8d60-106">Para llamar a estos métodos incrustados se utilizan instrucciones de consulta creadas en lenguajes como MDX (Expresiones multidimensionales), DMX (Extensiones de minería de datos) o SQL.</span><span class="sxs-lookup"><span data-stu-id="b8d60-106">These in-process methods are called through query statements created in languages such as Multidimensional Expressions (MDX), Data Mining Extensions (DMX), or SQL.</span></span> <span data-ttu-id="b8d60-107">Estos métodos incrustados también proporcionan otras funciones sin las latencias asociadas a las comunicaciones de red.</span><span class="sxs-lookup"><span data-stu-id="b8d60-107">These in-process methods also provide added functionality without the latencies associated with network communications.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="b8d60-108">El objeto [Microsoft. AnalysisServices. AdomdServer. AdomdCommand](/previous-versions/sql/sql-server-2014/ms143286(v=sql.120)) solo admite DMX.</span><span class="sxs-lookup"><span data-stu-id="b8d60-108">The [Microsoft.AnalysisServices.AdomdServer.AdomdCommand](/previous-versions/sql/sql-server-2014/ms143286(v=sql.120)) object only supports DMX.</span></span>  
  
## <a name="what-is-a-udf"></a><span data-ttu-id="b8d60-109">¿Qué es una UDF?</span><span class="sxs-lookup"><span data-stu-id="b8d60-109">What is a UDF?</span></span>  
 <span data-ttu-id="b8d60-110">Una *UDF* es un método que tiene las siguientes características:</span><span class="sxs-lookup"><span data-stu-id="b8d60-110">A *UDF* is a method that has the following characteristics:</span></span>  
  
-   <span data-ttu-id="b8d60-111">Puede llamar a la UDF en el contexto de una consulta.</span><span class="sxs-lookup"><span data-stu-id="b8d60-111">You can call the UDF in the context of a query.</span></span>  
  
-   <span data-ttu-id="b8d60-112">La UDF puede aceptar un número cualquiera de parámetros.</span><span class="sxs-lookup"><span data-stu-id="b8d60-112">The UDF can take any number of parameters.</span></span>  
  
-   <span data-ttu-id="b8d60-113">La UDF puede devolver varios tipos de datos.</span><span class="sxs-lookup"><span data-stu-id="b8d60-113">The UDF can return various types of data.</span></span>  
  
 <span data-ttu-id="b8d60-114">En el ejemplo siguiente se utiliza una UDF ficticia, `FinalSalesNumber`:</span><span class="sxs-lookup"><span data-stu-id="b8d60-114">The following example uses the fictional UDF, `FinalSalesNumber`:</span></span>  
  
```  
SELECT SalesPerson.Name ON ROWS,  
       FinalSalesNumber() ON COLUMNS  
FROM SalesModel  
```  
  
## <a name="what-is-a-stored-procedure"></a><span data-ttu-id="b8d60-115">¿Qué es un procedimiento almacenado?</span><span class="sxs-lookup"><span data-stu-id="b8d60-115">What is a Stored Procedure?</span></span>  
 <span data-ttu-id="b8d60-116">Un *procedimiento almacenado* es un método que tiene las siguientes características:</span><span class="sxs-lookup"><span data-stu-id="b8d60-116">A *stored procedure* is a method that has the following characteristics:</span></span>  
  
-   <span data-ttu-id="b8d60-117">Se llama a un procedimiento almacenado por su cuenta con la instrucción de [llamada](/sql/mdx/mdx-data-manipulation-call) MDX.</span><span class="sxs-lookup"><span data-stu-id="b8d60-117">You call a stored procedure on its own with the MDX [CALL](/sql/mdx/mdx-data-manipulation-call) statement.</span></span>  
  
-   <span data-ttu-id="b8d60-118">Un procedimiento almacenado puede aceptar un número cualquiera de parámetros.</span><span class="sxs-lookup"><span data-stu-id="b8d60-118">A stored procedure can take any number of parameters.</span></span>  
  
-   <span data-ttu-id="b8d60-119">Un procedimiento almacenado puede devolver un conjunto de datos, un elemento `IDataReader` o un resultado vacío.</span><span class="sxs-lookup"><span data-stu-id="b8d60-119">A stored procedure can return a dataset, an `IDataReader`, or an empty result.</span></span>  
  
 <span data-ttu-id="b8d60-120">En el ejemplo siguiente se utiliza un procedimiento almacenado ficticio, `FinalSalesNumbers`:</span><span class="sxs-lookup"><span data-stu-id="b8d60-120">The following example uses the fictional stored procedure, `FinalSalesNumbers`:</span></span>  
  
```  
CALL FinalSalesNumbers()  
```  
  
## <a name="see-also"></a><span data-ttu-id="b8d60-121">Consulte también</span><span class="sxs-lookup"><span data-stu-id="b8d60-121">See Also</span></span>  
 [<span data-ttu-id="b8d60-122">Programación del servidor ADOMD.NET</span><span class="sxs-lookup"><span data-stu-id="b8d60-122">ADOMD.NET Server Programming</span></span>](https://docs.microsoft.com/bi-reference/adomd/multidimensional-models-adomd-net-server/adomd-net-server-programming)  
  
  
