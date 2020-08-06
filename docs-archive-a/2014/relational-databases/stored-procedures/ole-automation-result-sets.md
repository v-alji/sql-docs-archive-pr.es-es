---
title: Conjuntos de resultados de automatización OLE | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: stored-procedures
ms.topic: conceptual
helpviewer_keywords:
- data types [SQL Server], OLE Automation
- two-dimensional arrays
- one-dimensional arrays
- result sets [SQL Server], OLE Automation
- OLE Automation [SQL Server], result sets
- arrays [SQL Server]
ms.assetid: b2f99e33-2303-427c-94b9-9d55f8e2a6ab
author: stevestein
ms.author: sstein
ms.openlocfilehash: f7c9bdc4d51d989db2d4d676b29e0824c0e5b59a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87678159"
---
# <a name="ole-automation-result-sets"></a><span data-ttu-id="1b9e7-102">Conjuntos de resultados de automatización OLE</span><span class="sxs-lookup"><span data-stu-id="1b9e7-102">OLE Automation Result Sets</span></span>
  <span data-ttu-id="1b9e7-103">Si una propiedad o método de automatización OLE devuelve datos en una matriz de una o dos dimensiones, la matriz se devuelve al cliente como un conjunto de resultados:</span><span class="sxs-lookup"><span data-stu-id="1b9e7-103">If an OLE Automation property or method returns data in an array with one or two dimensions, the array is returned to the client as a result set:</span></span>  
  
-   <span data-ttu-id="1b9e7-104">Se devuelve al cliente una matriz unidimensional como conjunto de resultados de fila única con tantas columnas como elementos tenga la matriz.</span><span class="sxs-lookup"><span data-stu-id="1b9e7-104">A one-dimensional array is returned to the client as a single-row result set with as many columns as there are elements in the array.</span></span> <span data-ttu-id="1b9e7-105">Por ejemplo, array(10) se devuelve como una fila única de 10 columnas.</span><span class="sxs-lookup"><span data-stu-id="1b9e7-105">For example, an array(10) is returned as a single row of 10 columns.</span></span>  
  
-   <span data-ttu-id="1b9e7-106">Se devuelve al cliente una matriz bidimensional como conjunto de resultados con tantas columnas como elementos haya en la primera dimensión de la matriz y con tantas filas como elementos haya en la segunda dimensión de la matriz.</span><span class="sxs-lookup"><span data-stu-id="1b9e7-106">A two-dimensional array is returned to the client as a result set with as many columns as there are elements in the first dimension of the array and with as many rows as there are elements in the second dimension of the array.</span></span> <span data-ttu-id="1b9e7-107">Por ejemplo, array(2,3) se devuelve como 2 columnas en 3 filas.</span><span class="sxs-lookup"><span data-stu-id="1b9e7-107">For example, an array(2,3) is returned as 2 columns in 3 rows.</span></span>  
  
 <span data-ttu-id="1b9e7-108">Cuando un valor devuelto por una propiedad o por un método es una matriz, sp_OAGetProperty o sp_OAMethod devuelven un conjunto de resultados al cliente.</span><span class="sxs-lookup"><span data-stu-id="1b9e7-108">When a property return value or method return value is an array, sp_OAGetProperty or sp_OAMethod returns a result set to the client.</span></span> <span data-ttu-id="1b9e7-109">(Los parámetros de salida del método no pueden ser matrices.) Estos procedimientos recorren todos los valores de datos de la matriz para determinar los tipos de datos y las longitudes de datos de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] adecuados para cada columna del conjunto de resultados.</span><span class="sxs-lookup"><span data-stu-id="1b9e7-109">(Method output parameters cannot be arrays.) These procedures scan all the data values in the array to determine the appropriate [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] data types and data lengths to use for each column in the result set.</span></span> <span data-ttu-id="1b9e7-110">Para una columna determinada, estos procedimientos utilizan el tipo y la longitud de datos necesarios para representar todos los valores de los datos de la columna.</span><span class="sxs-lookup"><span data-stu-id="1b9e7-110">For a particular column, these procedures use the data type and length required to represent all data values in that column.</span></span>  
  
 <span data-ttu-id="1b9e7-111">Cuando todos los valores de datos de una columna comparten el mismo tipo de datos, se utiliza ese tipo para toda la columna.</span><span class="sxs-lookup"><span data-stu-id="1b9e7-111">When all data values in a column share the same data type, that data type is used for the whole column.</span></span> <span data-ttu-id="1b9e7-112">Cuando los valores de datos de una columna son tipos de datos diferentes, el tipo de datos de toda la columna se elige según la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="1b9e7-112">When data values in a column are different data types, the data type of the whole column is chosen based on the following table.</span></span> <span data-ttu-id="1b9e7-113">Para utilizar la tabla siguiente, busque un tipo de datos a lo largo del eje de la fila izquierdo y un segundo tipo de datos a lo largo del eje de la columna superior.</span><span class="sxs-lookup"><span data-stu-id="1b9e7-113">To use the following table, find one data type along the left row axis and a second data type along the top column axis.</span></span> <span data-ttu-id="1b9e7-114">La intersección de la fila y columna describe el tipo de datos de la columna del conjunto de resultados.</span><span class="sxs-lookup"><span data-stu-id="1b9e7-114">The intersection of the row and column describes the data type of the result set column.</span></span>  
  
||||||||  
|-|-|-|-|-|-|-|  
||`int`|`float`|`money`|`datetime`|`varchar`|`nvarchar`|  
|`int`|`int`|`float`|`money`|`varchar`|`varchar`|`nvarchar`|  
|`float`|`float`|`float`|`money`|`varchar`|`varchar`|`nvarchar`|  
|`money`|`money`|`money`|`money`|`varchar`|`varchar`|`nvarchar`|  
|`datetime`|`varchar`|`varchar`|`varchar`|`datetime`|`varchar`|`nvarchar`|  
|`varchar`|`varchar`|`varchar`|`varchar`|`varchar`|`varchar`|`nvarchar`|  
|`nvarchar`|`nvarchar`|`nvarchar`|`nvarchar`|`nvarchar`|`nvarchar`|`nvarchar`|  
  
## <a name="related-content"></a><span data-ttu-id="1b9e7-115">Contenido relacionado</span><span class="sxs-lookup"><span data-stu-id="1b9e7-115">Related Content</span></span>  
 [<span data-ttu-id="1b9e7-116">Procedimientos almacenados de automatización OLE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="1b9e7-116">OLE Automation Stored Procedures &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/ole-automation-stored-procedures-transact-sql)  
  
 [<span data-ttu-id="1b9e7-117">Ole Automation Procedures (opción de configuración del servidor)</span><span class="sxs-lookup"><span data-stu-id="1b9e7-117">Ole Automation Procedures Server Configuration Option</span></span>](../../database-engine/configure-windows/ole-automation-procedures-server-configuration-option.md)  
  
  
