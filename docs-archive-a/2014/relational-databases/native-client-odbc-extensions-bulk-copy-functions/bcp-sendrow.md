---
title: bcp_sendrow | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
api_name:
- bcp_sendrow
api_location:
- sqlncli11.dll
topic_type:
- apiref
helpviewer_keywords:
- bcp_sendrow function
ms.assetid: ddbdb4bd-ad4e-4bf1-9a75-656aa26ce10a
author: rothja
ms.author: jroth
ms.openlocfilehash: 3d2f55486ba57101ffc7b1903de5d19ac8eaaca2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87671041"
---
# <a name="bcp_sendrow"></a><span data-ttu-id="783bb-102">bcp_sendrow</span><span class="sxs-lookup"><span data-stu-id="783bb-102">bcp_sendrow</span></span>
  <span data-ttu-id="783bb-103">Envía una fila de datos de las variables de programa a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="783bb-103">Sends a row of data from program variables to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="783bb-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="783bb-104">Syntax</span></span>  
  
```  
  
RETCODE bcp_sendrow (  
    HDBC   
hdbc  
);  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="783bb-105">Argumentos</span><span class="sxs-lookup"><span data-stu-id="783bb-105">Arguments</span></span>  
 <span data-ttu-id="783bb-106">*hdbc*</span><span class="sxs-lookup"><span data-stu-id="783bb-106">*hdbc*</span></span>  
 <span data-ttu-id="783bb-107">Es el identificador de la conexión ODBC habilitada para la copia masiva.</span><span class="sxs-lookup"><span data-stu-id="783bb-107">Is the bulk copy-enabled ODBC connection handle.</span></span>  
  
## <a name="returns"></a><span data-ttu-id="783bb-108">Devoluciones</span><span class="sxs-lookup"><span data-stu-id="783bb-108">Returns</span></span>  
 <span data-ttu-id="783bb-109">SUCCEED o FAIL.</span><span class="sxs-lookup"><span data-stu-id="783bb-109">SUCCEED or FAIL.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="783bb-110">Observaciones</span><span class="sxs-lookup"><span data-stu-id="783bb-110">Remarks</span></span>  
 <span data-ttu-id="783bb-111">La función **bcp_sendrow** genera una fila a partir de las variables de programa y la envía a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="783bb-111">The **bcp_sendrow** function builds a row from program variables and sends it to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="783bb-112">Antes de llamar a **a bcp_sendrow**, debe hacer llamadas a [bcp_bind](bcp-bind.md) para especificar las variables de programa que contienen los datos de la fila.</span><span class="sxs-lookup"><span data-stu-id="783bb-112">Before calling **bcp_sendrow**, you must make calls to [bcp_bind](bcp-bind.md) to specify the program variables containing row data.</span></span>  
  
 <span data-ttu-id="783bb-113">Si se llama a **bcp_bind** especificando un tipo de datos largo, de longitud variable, por ejemplo un parámetro *eDataType* de SQLTEXT y un parámetro *pData* no NULL, **bcp_sendrow** envía el valor entiredata, igual que para cualquier otro tipo de datos.</span><span class="sxs-lookup"><span data-stu-id="783bb-113">If **bcp_bind** is called specifying a long, variable-length data type, for example, an *eDataType* parameter of SQLTEXT and a nonNULL *pData* parameter, **bcp_sendrow** sends the entiredata value, just as it does for any other data type.</span></span> <span data-ttu-id="783bb-114">Si, no obstante, **bcp_bind** tiene un parámetro *pData* NULL, **bcp_sendrow** devuelve inmediatamente el control a la aplicación inmediatamente después de enviar todas las columnas con datos especificados a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="783bb-114">If, however, **bcp_bind** has a NULL *pData* parameter, **bcp_sendrow** returns control to the application immediately after all columns with data specified are sent to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="783bb-115">A continuación, la aplicación puede llamar repetidamente a [bcp_moretext](bcp-moretext.md) para enviar los datos largos, de longitud variable a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], un fragmento a la vez.</span><span class="sxs-lookup"><span data-stu-id="783bb-115">The application can then call [bcp_moretext](bcp-moretext.md) repeatedly to send the long, variable-length data to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], a chunk at a time.</span></span> <span data-ttu-id="783bb-116">Para obtener más información, vea [bcp_moretext](bcp-moretext.md).</span><span class="sxs-lookup"><span data-stu-id="783bb-116">For more information, see [bcp_moretext](bcp-moretext.md).</span></span>  
  
 <span data-ttu-id="783bb-117">Cuando se utiliza **bcp_sendrow** para la copia masiva de filas de variables de programa en tablas [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , las filas solamente se confirman cuando el usuario llama a [a bcp_batch](bcp-batch.md) o a [bcp_done](bcp-done.md).</span><span class="sxs-lookup"><span data-stu-id="783bb-117">When **bcp_sendrow** is used to bulk copy rows from program variables into [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] tables, rows are committed only when the user calls [bcp_batch](bcp-batch.md) or [bcp_done](bcp-done.md).</span></span> <span data-ttu-id="783bb-118">El usuario puede elegir llamar a **bcp_batch** una vez cada *n* filas o cuando haya un periodo de inactividad entre períodos de entrada de datos.</span><span class="sxs-lookup"><span data-stu-id="783bb-118">The user can choose to call **bcp_batch** once every *n* rows or when there is a lull between periods of incoming data.</span></span> <span data-ttu-id="783bb-119">Si nunca se llama a **bcp_batch** , las filas se confirman cuando se llama a **bcp_done** .</span><span class="sxs-lookup"><span data-stu-id="783bb-119">If **bcp_batch** is never called, the rows are committed when **bcp_done** is called.</span></span>  
  
 <span data-ttu-id="783bb-120">Para obtener información sobre un cambio importante en la copia masiva a partir de [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] , vea [realizar operaciones de copia masiva &#40;ODBC&#41;](../native-client-odbc-bulk-copy-operations/performing-bulk-copy-operations-odbc.md).</span><span class="sxs-lookup"><span data-stu-id="783bb-120">For information about a breaking change in bulk-copying beginning in [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)], see [Performing Bulk Copy Operations &#40;ODBC&#41;](../native-client-odbc-bulk-copy-operations/performing-bulk-copy-operations-odbc.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="783bb-121">Consulte también</span><span class="sxs-lookup"><span data-stu-id="783bb-121">See Also</span></span>  
 [<span data-ttu-id="783bb-122">Bulk Copy Functions</span><span class="sxs-lookup"><span data-stu-id="783bb-122">Bulk Copy Functions</span></span>](sql-server-driver-extensions-bulk-copy-functions.md)  
  
  
