---
title: bcp_colptr | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
api_name:
- bcp_colptr
api_location:
- sqlncli11.dll
topic_type:
- apiref
helpviewer_keywords:
- bcp_colptr function
ms.assetid: 02ece13e-1da3-4f9d-b860-3177e43d2471
author: rothja
ms.author: jroth
ms.openlocfilehash: 8b725ace58ee1768fbca1a433cdea27e3e0e546e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87750910"
---
# <a name="bcp_colptr"></a><span data-ttu-id="cbaa1-102">bcp_colptr</span><span class="sxs-lookup"><span data-stu-id="cbaa1-102">bcp_colptr</span></span>
  <span data-ttu-id="cbaa1-103">Establece la dirección de datos de la variable de programa para la copia actual en [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="cbaa1-103">Sets the program variable data address for the current copy into [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cbaa1-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="cbaa1-104">Syntax</span></span>  
  
```  
  
RETCODE bcp_colptr (  
HDBC   
hdbc  
,  
LPCBYTE   
pData  
,  
INT   
idxServerCol  
);  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="cbaa1-105">Argumentos</span><span class="sxs-lookup"><span data-stu-id="cbaa1-105">Arguments</span></span>  
 <span data-ttu-id="cbaa1-106">*hdbc*</span><span class="sxs-lookup"><span data-stu-id="cbaa1-106">*hdbc*</span></span>  
 <span data-ttu-id="cbaa1-107">Es el identificador de la conexión ODBC habilitada para la copia masiva.</span><span class="sxs-lookup"><span data-stu-id="cbaa1-107">Is the bulk copy-enabled ODBC connection handle.</span></span>  
  
 <span data-ttu-id="cbaa1-108">*pData*</span><span class="sxs-lookup"><span data-stu-id="cbaa1-108">*pData*</span></span>  
 <span data-ttu-id="cbaa1-109">Es un puntero a los datos que van a copiarse.</span><span class="sxs-lookup"><span data-stu-id="cbaa1-109">Is a pointer to the data to copy.</span></span> <span data-ttu-id="cbaa1-110">Si el tipo de datos enlazado es un tipo de valor grande (como SQLTEXT o SQLIMAGE), *pdata* puede ser null.</span><span class="sxs-lookup"><span data-stu-id="cbaa1-110">If the bound data type is large value type (such as SQLTEXT or SQLIMAGE), *pData* can be NULL.</span></span> <span data-ttu-id="cbaa1-111">Un *PDATA* null indica que los valores de datos largos se enviarán a SQL Server en fragmentos mediante [bcp_moretext](bcp-moretext.md).</span><span class="sxs-lookup"><span data-stu-id="cbaa1-111">A NULL *pData* indicates long data values will be sent to SQL Server in chunks using [bcp_moretext](bcp-moretext.md).</span></span>  
  
 <span data-ttu-id="cbaa1-112">Si *pdata* se establece en NULL y la columna correspondiente al campo enlazado no es un tipo de valor grande, **bcp_colptr** producirá un error.</span><span class="sxs-lookup"><span data-stu-id="cbaa1-112">If *pData* is set to NULL and the column corresponding to the bound field is not a large value type, **bcp_colptr** fails.</span></span>  
  
 <span data-ttu-id="cbaa1-113">Para obtener más información sobre los tipos de valor grande, vea [bcp_bind](bcp-bind.md)**.**</span><span class="sxs-lookup"><span data-stu-id="cbaa1-113">For more information on large value types, see [bcp_bind](bcp-bind.md)**.**</span></span>  
  
 <span data-ttu-id="cbaa1-114">*idxServerCol*</span><span class="sxs-lookup"><span data-stu-id="cbaa1-114">*idxServerCol*</span></span>  
 <span data-ttu-id="cbaa1-115">Es la posición ordinal de la columna en la tabla de base de datos en la que se copian los datos.</span><span class="sxs-lookup"><span data-stu-id="cbaa1-115">Is the ordinal position of the column in the database table to which the data is copied.</span></span> <span data-ttu-id="cbaa1-116">La primera columna de una tabla es la columna 1.</span><span class="sxs-lookup"><span data-stu-id="cbaa1-116">The first column in a table is column 1.</span></span> <span data-ttu-id="cbaa1-117">La posición ordinal de una columna se notifica mediante [SQLColumns](../native-client-odbc-api/sqlcolumns.md).</span><span class="sxs-lookup"><span data-stu-id="cbaa1-117">The ordinal position of a column is reported by [SQLColumns](../native-client-odbc-api/sqlcolumns.md).</span></span>  
  
## <a name="returns"></a><span data-ttu-id="cbaa1-118">Devoluciones</span><span class="sxs-lookup"><span data-stu-id="cbaa1-118">Returns</span></span>  
 <span data-ttu-id="cbaa1-119">SUCCEED o FAIL.</span><span class="sxs-lookup"><span data-stu-id="cbaa1-119">SUCCEED or FAIL.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="cbaa1-120">Observaciones</span><span class="sxs-lookup"><span data-stu-id="cbaa1-120">Remarks</span></span>  
 <span data-ttu-id="cbaa1-121">La función **bcp_colptr** permite cambiar la dirección de los datos de origen de una columna determinada al copiar los datos en SQL Server con [bcp_sendrow](bcp-sendrow.md).</span><span class="sxs-lookup"><span data-stu-id="cbaa1-121">The **bcp_colptr** function allows you to change the address of source data for a particular column when copying data to SQL Server with [bcp_sendrow](bcp-sendrow.md).</span></span>  
  
 <span data-ttu-id="cbaa1-122">Inicialmente, el puntero a los datos de usuario se establece mediante una llamada a **bcp_bind**.</span><span class="sxs-lookup"><span data-stu-id="cbaa1-122">Initially, the pointer to user data is set by a call to **bcp_bind**.</span></span> <span data-ttu-id="cbaa1-123">Si la dirección de datos de la variable de programa cambia entre las llamadas a **bcp_sendrow**, puede llamar a **bcp_colptr** para restablecer el puntero a los datos.</span><span class="sxs-lookup"><span data-stu-id="cbaa1-123">If the program variable data address changes between calls to **bcp_sendrow**, you can call **bcp_colptr** to reset the pointer to the data.</span></span> <span data-ttu-id="cbaa1-124">La siguiente llamada a **bcp_sendrow** envía los datos direccionados por la llamada a **bcp_colptr**.</span><span class="sxs-lookup"><span data-stu-id="cbaa1-124">The next call to **bcp_sendrow** sends the data addressed by the call to **bcp_colptr**.</span></span>  
  
 <span data-ttu-id="cbaa1-125">Debe haber una llamada de **bcp_colptr** independiente para cada columna de la tabla cuya dirección de datos desee modificar.</span><span class="sxs-lookup"><span data-stu-id="cbaa1-125">There must be a separate **bcp_colptr** call for every column in the table whose data address you want to modify.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cbaa1-126">Consulte también</span><span class="sxs-lookup"><span data-stu-id="cbaa1-126">See Also</span></span>  
 [<span data-ttu-id="cbaa1-127">Bulk Copy Functions</span><span class="sxs-lookup"><span data-stu-id="cbaa1-127">Bulk Copy Functions</span></span>](sql-server-driver-extensions-bulk-copy-functions.md)  
  
  
