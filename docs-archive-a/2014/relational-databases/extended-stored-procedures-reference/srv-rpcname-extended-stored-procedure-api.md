---
title: srv_rpcname (API de procedimiento almacenado extendido) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: stored-procedures
ms.topic: reference
api_name:
- srv_rpcname
api_location:
- opends60.dll
topic_type:
- apiref
dev_langs:
- C++
helpviewer_keywords:
- srv_rpcname
ms.assetid: 0a1424e4-3319-4836-b8d8-5e0344cc683f
author: rothja
ms.author: jroth
ms.openlocfilehash: 21530b3e7b8aaa8c5a3f8770762cde7e258e3a43
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87751014"
---
# <a name="srv_rpcname-extended-stored-procedure-api"></a><span data-ttu-id="5002d-102">srv_rpcname (API de procedimiento almacenado extendido)</span><span class="sxs-lookup"><span data-stu-id="5002d-102">srv_rpcname (Extended Stored Procedure API)</span></span>
    
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureDontUse](../../includes/ssnotedepfuturedontuse-md.md)] <span data-ttu-id="5002d-103">Use la integración con CLR en su lugar.</span><span class="sxs-lookup"><span data-stu-id="5002d-103">Use CLR integration instead.</span></span>  
  
 <span data-ttu-id="5002d-104">Devuelve el componente nombre de procedimiento del procedimiento almacenado remoto actual.</span><span class="sxs-lookup"><span data-stu-id="5002d-104">Returns the procedure name component for the current remote stored procedure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5002d-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5002d-105">Syntax</span></span>  
  
```  
  
DBCHAR * srv_rpcname (  
SRV_PROC *  
srvproc  
,  
int *  
len   
);  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="5002d-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="5002d-106">Arguments</span></span>  
 <span data-ttu-id="5002d-107">*srvproc*</span><span class="sxs-lookup"><span data-stu-id="5002d-107">*srvproc*</span></span>  
 <span data-ttu-id="5002d-108">Es un puntero a la estructura SRV_PROC, que es el identificador de una conexión de cliente determinada (en este caso, el identificador que recibió el procedimiento almacenado remoto).</span><span class="sxs-lookup"><span data-stu-id="5002d-108">Is a pointer to the SRV_PROC structure that is the handle for a particular client connection (in this case, the handle that received the remote stored procedure).</span></span> <span data-ttu-id="5002d-109">La estructura contiene información que la biblioteca de API Procedimiento almacenado extendido utiliza para administrar la comunicación y los datos entre la aplicación y el cliente.</span><span class="sxs-lookup"><span data-stu-id="5002d-109">The structure contains information that the Extended Stored Procedure API library uses to manage communication and data between the application and the client.</span></span>  
  
 <span data-ttu-id="5002d-110">*terminado*</span><span class="sxs-lookup"><span data-stu-id="5002d-110">*len*</span></span>  
 <span data-ttu-id="5002d-111">Es un puntero a una variable entera que recibe la longitud del nombre de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="5002d-111">Is a pointer to an integer variable that receives the length of the database name.</span></span> <span data-ttu-id="5002d-112">Si *len* es NULL, no se devuelve la longitud del nombre del procedimiento almacenado remoto.</span><span class="sxs-lookup"><span data-stu-id="5002d-112">If *len* is NULL, the length of the remote stored procedure name is not returned.</span></span>  
  
## <a name="returns"></a><span data-ttu-id="5002d-113">Devoluciones</span><span class="sxs-lookup"><span data-stu-id="5002d-113">Returns</span></span>  
 <span data-ttu-id="5002d-114">Un puntero DBCHAR a la cadena terminada en NULL para el componente nombre de procedimiento almacenado remoto del procedimiento almacenado remoto actual.</span><span class="sxs-lookup"><span data-stu-id="5002d-114">A DBCHAR pointer to the null-terminated string for the remote stored procedure name component of the current remote stored procedure.</span></span> <span data-ttu-id="5002d-115">Si no hay ningún procedimiento almacenado remoto actual, se devuelve NULL y *len* se establece en -1.</span><span class="sxs-lookup"><span data-stu-id="5002d-115">If there is not a current remote stored procedure, NULL is returned and *len* is set to -1.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5002d-116">Observaciones</span><span class="sxs-lookup"><span data-stu-id="5002d-116">Remarks</span></span>  
 <span data-ttu-id="5002d-117">Esta función solo devuelve el nombre del procedimiento almacenado remoto.</span><span class="sxs-lookup"><span data-stu-id="5002d-117">This function returns only the name of the remote stored procedure.</span></span> <span data-ttu-id="5002d-118">No incluye los especificadores opcionales propietario, nombre de la base de datos y número de procedimiento almacenado remoto.</span><span class="sxs-lookup"><span data-stu-id="5002d-118">It does not include the optional specifiers for owner, database name, and remote stored procedure number.</span></span>  
  
 <span data-ttu-id="5002d-119">Puesto que es válido llamar a **srv_rpcname** cuando no es un procedimiento almacenado remoto (no se produce ningún error informativo), esta función proporciona un método para determinar si existe un procedimiento almacenado remoto.</span><span class="sxs-lookup"><span data-stu-id="5002d-119">Because it is valid to call **srv_rpcname** when there is not a remote stored procedure (no informational error occurs), this function provides a method for determining whether a remote stored procedure exists.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="5002d-120">Debe revisar minuciosamente el código fuente de los procedimientos almacenados extendidos y debe probar las DLL compiladas antes de instalarlas en el servidor de producción.</span><span class="sxs-lookup"><span data-stu-id="5002d-120">You should thoroughly review the source code of extended stored procedures, and you should test the compiled DLLs before you install them on a production server.</span></span> <span data-ttu-id="5002d-121">Para obtener información acerca de la revisión y pruebas de seguridad, vea este [sitio web de Microsoft](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span><span class="sxs-lookup"><span data-stu-id="5002d-121">For information about security review and testing, see this [Microsoft Web site](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span></span>  
  
  
