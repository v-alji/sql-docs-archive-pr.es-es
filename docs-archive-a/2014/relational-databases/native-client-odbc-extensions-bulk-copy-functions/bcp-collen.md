---
title: bcp_collen | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
api_name:
- bcp_collen
api_location:
- sqlncli11.dll
topic_type:
- apiref
helpviewer_keywords:
- bcp_collen function
ms.assetid: faaf1f7a-81f2-4852-a178-56602c33673a
author: rothja
ms.author: jroth
ms.openlocfilehash: 3099e26b0c2cd0d1cfee7578f5b149b812f01765
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87750906"
---
# <a name="bcp_collen"></a><span data-ttu-id="c8dca-102">bcp_collen</span><span class="sxs-lookup"><span data-stu-id="c8dca-102">bcp_collen</span></span>
  <span data-ttu-id="c8dca-103">Establece la longitud de los datos de la variable del programa para la copia masiva actual en [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c8dca-103">Sets the data length in the program variable for the current bulk copy into [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c8dca-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c8dca-104">Syntax</span></span>  
  
```  
  
RETCODE bcp_collen (  
HDBC   
hdbc  
,  
DBINT   
cbData  
,  
INT   
idxServerCol  
);  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="c8dca-105">Argumentos</span><span class="sxs-lookup"><span data-stu-id="c8dca-105">Arguments</span></span>  
 <span data-ttu-id="c8dca-106">*hdbc*</span><span class="sxs-lookup"><span data-stu-id="c8dca-106">*hdbc*</span></span>  
 <span data-ttu-id="c8dca-107">Es el identificador de la conexión ODBC habilitada para la copia masiva.</span><span class="sxs-lookup"><span data-stu-id="c8dca-107">Is the bulk copy-enabled ODBC connection handle.</span></span>  
  
 <span data-ttu-id="c8dca-108">*cbData*</span><span class="sxs-lookup"><span data-stu-id="c8dca-108">*cbData*</span></span>  
 <span data-ttu-id="c8dca-109">Es la longitud de los datos de la variable del programa; no incluye la longitud del indicador ni del terminador de longitud.</span><span class="sxs-lookup"><span data-stu-id="c8dca-109">Is the length of the data in the program variable, not including the length of any length indicator or terminator.</span></span> <span data-ttu-id="c8dca-110">Si se establece *cbData* en SQL_NULL_DATA, se indica que todas las filas copiadas en el servidor contienen un valor NULL para la columna.</span><span class="sxs-lookup"><span data-stu-id="c8dca-110">Setting *cbData* to SQL_NULL_DATA indicates all rows copied to the server contain a NULL value for the column.</span></span> <span data-ttu-id="c8dca-111">Si se establece en SQL_VARLEN_DATA, se indica que se utiliza un terminador de cadena u otro método para determinar la longitud de los datos copiados.</span><span class="sxs-lookup"><span data-stu-id="c8dca-111">Setting it to SQL_VARLEN_DATA indicates that a string terminator or other method is used to determine the length of data copied.</span></span> <span data-ttu-id="c8dca-112">Si hay un indicador y un terminador de longitud, el sistema utiliza el que permita que se copien menos datos.</span><span class="sxs-lookup"><span data-stu-id="c8dca-112">If both a length indicator and a terminator exist, the system uses whichever one results in less data being copied.</span></span>  
  
 <span data-ttu-id="c8dca-113">*idxServerCol*</span><span class="sxs-lookup"><span data-stu-id="c8dca-113">*idxServerCol*</span></span>  
 <span data-ttu-id="c8dca-114">Es la posición ordinal de la columna en la tabla en la que se copian los datos.</span><span class="sxs-lookup"><span data-stu-id="c8dca-114">Is the ordinal position of the column in the table to which the data is copied.</span></span> <span data-ttu-id="c8dca-115">La primera columna es 1.</span><span class="sxs-lookup"><span data-stu-id="c8dca-115">The first column is 1.</span></span> <span data-ttu-id="c8dca-116">La posición ordinal de una columna se notifica mediante [SQLColumns](../native-client-odbc-api/sqlcolumns.md).</span><span class="sxs-lookup"><span data-stu-id="c8dca-116">The ordinal position of a column is reported by [SQLColumns](../native-client-odbc-api/sqlcolumns.md).</span></span>  
  
## <a name="returns"></a><span data-ttu-id="c8dca-117">Devoluciones</span><span class="sxs-lookup"><span data-stu-id="c8dca-117">Returns</span></span>  
 <span data-ttu-id="c8dca-118">SUCCEED o FAIL.</span><span class="sxs-lookup"><span data-stu-id="c8dca-118">SUCCEED or FAIL.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c8dca-119">Observaciones</span><span class="sxs-lookup"><span data-stu-id="c8dca-119">Remarks</span></span>  
 <span data-ttu-id="c8dca-120">La función **bcp_collen** permite cambiar la longitud de los datos en la variable del programa para una determinada columna al copiar los datos en [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] con [bcp_sendrow](bcp-sendrow.md).</span><span class="sxs-lookup"><span data-stu-id="c8dca-120">The **bcp_collen** function allows you to change the data length in the program variable for a particular column when copying data to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] with [bcp_sendrow](bcp-sendrow.md).</span></span>  
  
 <span data-ttu-id="c8dca-121">La longitud de los datos se determina inicialmente cuando se llama a [bcp_bind](bcp-bind.md) .</span><span class="sxs-lookup"><span data-stu-id="c8dca-121">Initially, the data length is determined when [bcp_bind](bcp-bind.md) is called.</span></span> <span data-ttu-id="c8dca-122">Si la longitud de los datos cambia entre las llamadas a **bcp_sendrow** y no se utiliza ningún prefijo o terminador de longitud, puede llamar a **bcp_collen** para restablecer la longitud.</span><span class="sxs-lookup"><span data-stu-id="c8dca-122">If the data length changes between calls to **bcp_sendrow** and no length prefix or terminator is being used, you can call **bcp_collen** to reset the length.</span></span> <span data-ttu-id="c8dca-123">La llamada siguiente a **bcp_sendrow** utiliza la longitud establecida por la llamada a **bcp_collen**.</span><span class="sxs-lookup"><span data-stu-id="c8dca-123">The next call to **bcp_sendrow** uses the length set by the call to **bcp_collen**.</span></span>  
  
 <span data-ttu-id="c8dca-124">Debe llamar una vez a **bcp_collen** para cada columna de la tabla cuya longitud de los datos desee modificar.</span><span class="sxs-lookup"><span data-stu-id="c8dca-124">You must call **bcp_collen** once for each column in the table whose data length you want to modify.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c8dca-125">Consulte también</span><span class="sxs-lookup"><span data-stu-id="c8dca-125">See Also</span></span>  
 [<span data-ttu-id="c8dca-126">Bulk Copy Functions</span><span class="sxs-lookup"><span data-stu-id="c8dca-126">Bulk Copy Functions</span></span>](sql-server-driver-extensions-bulk-copy-functions.md)  
  
  
