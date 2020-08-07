---
title: REPLACENULL (expresión de SSIS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 70db7832-b5a0-4db5-a8ad-42ad8630d8e8
author: chugugrace
ms.author: chugu
ms.openlocfilehash: f10bb6ef6102076fe7b1cc236461e2358ad96372
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87746368"
---
# <a name="replacenull-ssis-expression"></a><span data-ttu-id="59258-102">REPLACENULL (expresión SSIS)</span><span class="sxs-lookup"><span data-stu-id="59258-102">REPLACENULL (SSIS Expression)</span></span>
  <span data-ttu-id="59258-103">Devuelve el valor del parámetro de la segunda expresión si el parámetro de la primera expresión es NULL; en caso contrario, devuelve el valor de la primera expresión.</span><span class="sxs-lookup"><span data-stu-id="59258-103">Returns the value of second expression parameter if the value of first expression parameter is NULL; otherwise, returns the value of first expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="59258-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="59258-104">Syntax</span></span>  
  
```vb  
REPLACENULL(expression 1,expression 2)  
```  
  
## <a name="arguments"></a><span data-ttu-id="59258-105">Argumentos</span><span class="sxs-lookup"><span data-stu-id="59258-105">Arguments</span></span>  
 <span data-ttu-id="59258-106">*expression 1*</span><span class="sxs-lookup"><span data-stu-id="59258-106">*expression 1*</span></span>  
 <span data-ttu-id="59258-107">El resultado de esta expresión se comprueba con NULL.</span><span class="sxs-lookup"><span data-stu-id="59258-107">The result of this expression is checked against NULL.</span></span>  
  
 <span data-ttu-id="59258-108">*expression 2*</span><span class="sxs-lookup"><span data-stu-id="59258-108">*expression 2*</span></span>  
 <span data-ttu-id="59258-109">El resultado de esta expresión se devuelve si la primera expresión se evalúa como NULL.</span><span class="sxs-lookup"><span data-stu-id="59258-109">The result of this expression is returned if the first expression evaluates to NULL.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="59258-110">Tipos de resultado</span><span class="sxs-lookup"><span data-stu-id="59258-110">Result Types</span></span>  
 <span data-ttu-id="59258-111">DT_WSTR</span><span class="sxs-lookup"><span data-stu-id="59258-111">DT_WSTR</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="59258-112">Observaciones</span><span class="sxs-lookup"><span data-stu-id="59258-112">Remarks</span></span>  
  
-   <span data-ttu-id="59258-113">La longitud de *expression 2* puede ser cero.</span><span class="sxs-lookup"><span data-stu-id="59258-113">The length of *expression 2* may be zero.</span></span>  
  
-   <span data-ttu-id="59258-114">REPLACENULL devuelve un resultado NULL si alguno de los argumentos es NULL.</span><span class="sxs-lookup"><span data-stu-id="59258-114">REPLACENULL returns a null result if any argument is null.</span></span>  
  
-   <span data-ttu-id="59258-115">Las columnas de objetos binarios (DT_TEXT, DT_NTEXT, DT_IMAGE) no se admiten en ninguno de los dos parámetros.</span><span class="sxs-lookup"><span data-stu-id="59258-115">BLOB columns (DT_TEXT, DT_NTEXT, DT_IMAGE) are not supported for either parameter.</span></span>  
  
-   <span data-ttu-id="59258-116">Se espera que las dos expresiones devuelvan el mismo tipo de valor devuelto.</span><span class="sxs-lookup"><span data-stu-id="59258-116">The two expressions are expected to have the same return type.</span></span> <span data-ttu-id="59258-117">Si no es así, la función intenta convertir la segunda expresión al tipo de valor devuelto de la primera expresión, lo que puede producir un error si los tipos de datos son incompatibles.</span><span class="sxs-lookup"><span data-stu-id="59258-117">If they do not, the function attempts to cast the 2nd expression to the return type of the 1st expression, which may result in an error if the data types are incompatible.</span></span>  
  
## <a name="expression-examples"></a><span data-ttu-id="59258-118">Ejemplos de expresiones</span><span class="sxs-lookup"><span data-stu-id="59258-118">Expression Examples</span></span>  
 <span data-ttu-id="59258-119">En el siguiente ejemplo se reemplaza cualquier valor NULL de una columna de base de datos con una cadena (1900-01-01).</span><span class="sxs-lookup"><span data-stu-id="59258-119">The following example replaces any NULL value in a database column with a string (1900-01-01).</span></span> <span data-ttu-id="59258-120">Esta función se utiliza especialmente en los patrones de columnas derivadas comunes en los casos en los que se desee reemplazar los valores NULL por algo más.</span><span class="sxs-lookup"><span data-stu-id="59258-120">This function is especially used in common Derived Column patterns where you want to replace NULL values with something else.</span></span>  
  
```  
REPLACENULL(MyColumn, "1900-01-01")  
```  
  
> [!NOTE]  
>  <span data-ttu-id="59258-121">En el ejemplo siguiente se muestra cómo se realizó en [!INCLUDE[ssISversion2005](../../includes/ssisversion2005-md.md)]/[!INCLUDE[ssISversion10](../../includes/ssisversion10-md.md)].</span><span class="sxs-lookup"><span data-stu-id="59258-121">The following example shows how it was done in [!INCLUDE[ssISversion2005](../../includes/ssisversion2005-md.md)]/[!INCLUDE[ssISversion10](../../includes/ssisversion10-md.md)].</span></span>  
  
```  
(DT_DBTIMESTAMP) (ISNULL(MyColumn) ? "1900-01-01" : MyColumn)   
```  
  
  
