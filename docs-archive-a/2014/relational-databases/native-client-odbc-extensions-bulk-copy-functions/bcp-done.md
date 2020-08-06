---
title: bcp_done | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
api_name:
- bcp_done
api_location:
- sqlncli11.dll
topic_type:
- apiref
helpviewer_keywords:
- bcp_done function
ms.assetid: e59b3f16-5b59-40da-880f-f3edf657d1ee
author: rothja
ms.author: jroth
ms.openlocfilehash: cb9b0cbcc927fcd10c2d81b3c5c3d39bb80a8e9b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87661998"
---
# <a name="bcp_done"></a><span data-ttu-id="f90ae-102">bcp_done</span><span class="sxs-lookup"><span data-stu-id="f90ae-102">bcp_done</span></span>
  <span data-ttu-id="f90ae-103">Finaliza una copia masiva de las variables de programa a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] realizada con [bcp_sendrow](bcp-sendrow.md).</span><span class="sxs-lookup"><span data-stu-id="f90ae-103">Ends a bulk copy from program variables to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] performed with [bcp_sendrow](bcp-sendrow.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f90ae-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f90ae-104">Syntax</span></span>  
  
```  
  
DBINT bcp_done (  
    HDBC   
hdbc  
);  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="f90ae-105">Argumentos</span><span class="sxs-lookup"><span data-stu-id="f90ae-105">Arguments</span></span>  
 <span data-ttu-id="f90ae-106">*hdbc*</span><span class="sxs-lookup"><span data-stu-id="f90ae-106">*hdbc*</span></span>  
 <span data-ttu-id="f90ae-107">Es el identificador de la conexión ODBC habilitada para la copia masiva.</span><span class="sxs-lookup"><span data-stu-id="f90ae-107">Is the bulk copy-enabled ODBC connection handle.</span></span>  
  
## <a name="returns"></a><span data-ttu-id="f90ae-108">Devoluciones</span><span class="sxs-lookup"><span data-stu-id="f90ae-108">Returns</span></span>  
 <span data-ttu-id="f90ae-109">El número de filas guardado permanentemente después de la última llamada a [bcp_batch](bcp-batch.md) , o-1 en caso de error.</span><span class="sxs-lookup"><span data-stu-id="f90ae-109">The number of rows permanently saved after the last call to [bcp_batch](bcp-batch.md) or -1 in case of error.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f90ae-110">Observaciones</span><span class="sxs-lookup"><span data-stu-id="f90ae-110">Remarks</span></span>  
 <span data-ttu-id="f90ae-111">Llame a **bcp_done** después de la última llamada a [bcp_sendrow](bcp-sendrow.md) o [bcp_moretext](bcp-moretext.md).</span><span class="sxs-lookup"><span data-stu-id="f90ae-111">Call **bcp_done** after the last call to [bcp_sendrow](bcp-sendrow.md) or [bcp_moretext](bcp-moretext.md).</span></span> <span data-ttu-id="f90ae-112">Si no se llama a **a bcp_done** después de copiar todos los datos se producen errores.</span><span class="sxs-lookup"><span data-stu-id="f90ae-112">Failure to call **bcp_done** after copying all data results in errors.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f90ae-113">Consulte también</span><span class="sxs-lookup"><span data-stu-id="f90ae-113">See Also</span></span>  
 [<span data-ttu-id="f90ae-114">Bulk Copy Functions</span><span class="sxs-lookup"><span data-stu-id="f90ae-114">Bulk Copy Functions</span></span>](sql-server-driver-extensions-bulk-copy-functions.md)  
  
  
