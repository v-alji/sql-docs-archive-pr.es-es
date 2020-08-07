---
title: bcp_columns | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
api_name:
- bcp_columns
api_location:
- sqlncli11.dll
topic_type:
- apiref
helpviewer_keywords:
- bcp_columns function
ms.assetid: 5376f6fe-9508-439a-8c66-778d77f19ac3
author: rothja
ms.author: jroth
ms.openlocfilehash: 028bb80e88a29b366e3a489abae06c8b3b30cdf6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87745281"
---
# <a name="bcp_columns"></a><span data-ttu-id="b673e-102">bcp_columns</span><span class="sxs-lookup"><span data-stu-id="b673e-102">bcp_columns</span></span>
  <span data-ttu-id="b673e-103">Establece el número total de columnas del archivo de usuario para su uso con una copia masiva a o de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b673e-103">Sets the total number of columns found in the user file for use with a bulk copy into or out of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="b673e-104">[bcp_setbulkmode](bcp-setbulkmode.md) se puede utilizar en lugar de bcp_columns y [bcp_colfmt](bcp-colfmt.md).</span><span class="sxs-lookup"><span data-stu-id="b673e-104">[bcp_setbulkmode](bcp-setbulkmode.md) can be used instead of bcp_columns and [bcp_colfmt](bcp-colfmt.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b673e-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b673e-105">Syntax</span></span>  
  
```  
  
RETCODE bcp_columns (  
HDBC   
hdbc  
,  
INT   
nColumns  
);  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="b673e-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="b673e-106">Arguments</span></span>  
 <span data-ttu-id="b673e-107">*hdbc*</span><span class="sxs-lookup"><span data-stu-id="b673e-107">*hdbc*</span></span>  
 <span data-ttu-id="b673e-108">Es el identificador de la conexión ODBC habilitada para la copia masiva.</span><span class="sxs-lookup"><span data-stu-id="b673e-108">Is the bulk copy-enabled ODBC connection handle.</span></span>  
  
 <span data-ttu-id="b673e-109">*nColumns*</span><span class="sxs-lookup"><span data-stu-id="b673e-109">*nColumns*</span></span>  
 <span data-ttu-id="b673e-110">Es el número total de columnas en el archivo de usuario.</span><span class="sxs-lookup"><span data-stu-id="b673e-110">Is the total number of columns in the user file.</span></span> <span data-ttu-id="b673e-111">Incluso si está preparando la copia masiva de datos del archivo de usuario en una [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] tabla y no pretende copiar todas las columnas del archivo de usuario, debe establecer *nColumns* en el número total de columnas de archivo de usuario.</span><span class="sxs-lookup"><span data-stu-id="b673e-111">Even if you are preparing to bulk copy data from the user file to an [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] table and do not intend to copy all columns in the user file, you must still set *nColumns* to the total number of user-file columns.</span></span>  
  
## <a name="returns"></a><span data-ttu-id="b673e-112">Devoluciones</span><span class="sxs-lookup"><span data-stu-id="b673e-112">Returns</span></span>  
 <span data-ttu-id="b673e-113">SUCCEED o FAIL.</span><span class="sxs-lookup"><span data-stu-id="b673e-113">SUCCEED or FAIL.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b673e-114">Observaciones</span><span class="sxs-lookup"><span data-stu-id="b673e-114">Remarks</span></span>  
 <span data-ttu-id="b673e-115">Solo se puede llamar a esta función después de que se haya llamado a [bcp_init](bcp-init.md) con un nombre de archivo válido.</span><span class="sxs-lookup"><span data-stu-id="b673e-115">This function can be called only after [bcp_init](bcp-init.md) has been called with a valid file name.</span></span>  
  
 <span data-ttu-id="b673e-116">Solo debe llamar a esta función si piensa utilizar un formato de archivo de usuario que difiere del valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="b673e-116">You should call this function only if you intend to use a user-file format that differs from the default.</span></span> <span data-ttu-id="b673e-117">Para obtener más información sobre una descripción del formato de archivo de usuario predeterminado, vea **bcp_init**.</span><span class="sxs-lookup"><span data-stu-id="b673e-117">For more information about a description of the default user-file format, see **bcp_init**.</span></span>  
  
 <span data-ttu-id="b673e-118">Después de llamar a `bcp_columns` , debe llamar a [bcp_colfmt](bcp-colfmt.md)por cada columna del archivo de usuario para definir completamente un formato de archivo personalizado.</span><span class="sxs-lookup"><span data-stu-id="b673e-118">After calling `bcp_columns`, you must call [bcp_colfmt](bcp-colfmt.md)for each column in the user file to completely define a custom file format.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b673e-119">Consulte también</span><span class="sxs-lookup"><span data-stu-id="b673e-119">See Also</span></span>  
 [<span data-ttu-id="b673e-120">Bulk Copy Functions</span><span class="sxs-lookup"><span data-stu-id="b673e-120">Bulk Copy Functions</span></span>](sql-server-driver-extensions-bulk-copy-functions.md)  
  
  
