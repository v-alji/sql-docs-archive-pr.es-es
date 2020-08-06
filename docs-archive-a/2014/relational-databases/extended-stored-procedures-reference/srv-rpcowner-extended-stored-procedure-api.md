---
title: srv_rpcowner (API de procedimiento almacenado extendido) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: stored-procedures
ms.topic: reference
api_name:
- srv_rpcowner
api_location:
- opends60.dll
topic_type:
- apiref
dev_langs:
- C++
helpviewer_keywords:
- srv_rpcowner
ms.assetid: e81a60e6-14ea-47bc-a11c-3d7635344447
author: rothja
ms.author: jroth
ms.openlocfilehash: f903870d0ee01256addb1557eb7e9123853b39e6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87752145"
---
# <a name="srv_rpcowner-extended-stored-procedure-api"></a><span data-ttu-id="cf19a-102">srv_rpcowner (API de procedimiento almacenado extendido)</span><span class="sxs-lookup"><span data-stu-id="cf19a-102">srv_rpcowner (Extended Stored Procedure API)</span></span>
    
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureDontUse](../../includes/ssnotedepfuturedontuse-md.md)] <span data-ttu-id="cf19a-103">Use la integración con CLR en su lugar.</span><span class="sxs-lookup"><span data-stu-id="cf19a-103">Use CLR integration instead.</span></span>  
  
 <span data-ttu-id="cf19a-104">Devuelve el componente de propietario del procedimiento almacenado remoto actual.</span><span class="sxs-lookup"><span data-stu-id="cf19a-104">Returns the owner component for the current remote stored procedure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cf19a-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="cf19a-105">Syntax</span></span>  
  
```  
  
DBCHAR * srv_rpcowner (  
SRV_PROC *  
srvproc  
,  
int *  
len   
);  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="cf19a-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="cf19a-106">Arguments</span></span>  
 <span data-ttu-id="cf19a-107">*srvproc*</span><span class="sxs-lookup"><span data-stu-id="cf19a-107">*srvproc*</span></span>  
 <span data-ttu-id="cf19a-108">Es un puntero a la estructura SRV_PROC, que es el identificador de una conexión de cliente determinada (en este caso, el identificador que recibió el procedimiento almacenado remoto).</span><span class="sxs-lookup"><span data-stu-id="cf19a-108">Is a pointer to the SRV_PROC structure that is the handle for a particular client connection (in this case, the handle that received the remote stored procedure).</span></span> <span data-ttu-id="cf19a-109">La estructura contiene información que la biblioteca de API Procedimiento almacenado extendido utiliza para administrar la comunicación y los datos entre la aplicación y el cliente.</span><span class="sxs-lookup"><span data-stu-id="cf19a-109">The structure contains information that the Extended Stored Procedure API library uses to manage communication and data between the application and the client.</span></span>  
  
 <span data-ttu-id="cf19a-110">*terminado*</span><span class="sxs-lookup"><span data-stu-id="cf19a-110">*len*</span></span>  
 <span data-ttu-id="cf19a-111">Es un puntero a una variable entera que recibe la longitud del nombre del propietario.</span><span class="sxs-lookup"><span data-stu-id="cf19a-111">Is a pointer to an integer variable that receives the length of the owner name.</span></span> <span data-ttu-id="cf19a-112">El parámetro *len* puede ser NULL, en cuyo caso no se devuelve la longitud del componente de propietario.</span><span class="sxs-lookup"><span data-stu-id="cf19a-112">The parameter *len* can be NULL, in which case the length of the owner component is not returned.</span></span>  
  
## <a name="returns"></a><span data-ttu-id="cf19a-113">Devoluciones</span><span class="sxs-lookup"><span data-stu-id="cf19a-113">Returns</span></span>  
 <span data-ttu-id="cf19a-114">Un puntero DBCHAR al componente de propietario terminado en NULL para el procedimiento almacenado remoto actual.</span><span class="sxs-lookup"><span data-stu-id="cf19a-114">A DBCHAR pointer to the null-terminated owner component for the current remote stored procedure.</span></span> <span data-ttu-id="cf19a-115">Si no hay ningún procedimiento almacenado remoto actual, se devuelve NULL y *len* se establece en -1.</span><span class="sxs-lookup"><span data-stu-id="cf19a-115">If there is no current remote stored procedure, NULL is returned and *len* is set to - 1.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="cf19a-116">Observaciones</span><span class="sxs-lookup"><span data-stu-id="cf19a-116">Remarks</span></span>  
 <span data-ttu-id="cf19a-117">Esta función únicamente devuelve el componente de propietario del procedimiento almacenado remoto.</span><span class="sxs-lookup"><span data-stu-id="cf19a-117">This function returns only the owner component of the remote stored procedure.</span></span> <span data-ttu-id="cf19a-118">No incluye los especificadores opcionales para el nombre, nombre de procedimiento almacenado remoto, y número de procedimiento almacenado remoto.</span><span class="sxs-lookup"><span data-stu-id="cf19a-118">It does not include the optional specifiers for name, remote stored procedure name, and remote stored procedure number.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="cf19a-119">Debe revisar minuciosamente el código fuente de los procedimientos almacenados extendidos y debe probar las DLL compiladas antes de instalarlas en el servidor de producción.</span><span class="sxs-lookup"><span data-stu-id="cf19a-119">You should thoroughly review the source code of extended stored procedures, and you should test the compiled DLLs before you install them on a production server.</span></span> <span data-ttu-id="cf19a-120">Para obtener información acerca de la revisión y pruebas de seguridad, vea este [sitio web de Microsoft](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span><span class="sxs-lookup"><span data-stu-id="cf19a-120">For information about security review and testing, see this [Microsoft Web site](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span></span>  
  
  
