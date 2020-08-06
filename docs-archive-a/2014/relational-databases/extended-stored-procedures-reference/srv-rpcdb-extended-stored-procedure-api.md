---
title: srv_rpcdb (API de procedimiento almacenado extendido) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: stored-procedures
ms.topic: reference
api_name:
- srv_rpcdb
api_location:
- opends60.dll
topic_type:
- apiref
dev_langs:
- C++
helpviewer_keywords:
- srv_rpcdb
ms.assetid: d52bfd22-7a7c-4ab0-af65-df96ff359e6f
author: rothja
ms.author: jroth
ms.openlocfilehash: c951a4a821bbd49748182d9ddf5df017344a174d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87749326"
---
# <a name="srv_rpcdb-extended-stored-procedure-api"></a><span data-ttu-id="dc707-102">srv_rpcdb (API de procedimiento almacenado extendido)</span><span class="sxs-lookup"><span data-stu-id="dc707-102">srv_rpcdb (Extended Stored Procedure API)</span></span>
    
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureDontUse](../../includes/ssnotedepfuturedontuse-md.md)] <span data-ttu-id="dc707-103">Use la integración con CLR en su lugar.</span><span class="sxs-lookup"><span data-stu-id="dc707-103">Use CLR integration instead.</span></span>  
  
 <span data-ttu-id="dc707-104">Devuelve el componente nombre de base de datos del procedimiento almacenado remoto actual.</span><span class="sxs-lookup"><span data-stu-id="dc707-104">Returns the database name component for the current remote stored procedure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dc707-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="dc707-105">Syntax</span></span>  
  
```  
  
DBCHAR * srv_rpcdb (  
SRV_PROC * srvproc,int *len );  
```  
  
## <a name="arguments"></a><span data-ttu-id="dc707-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="dc707-106">Arguments</span></span>  
 <span data-ttu-id="dc707-107">*srvproc*</span><span class="sxs-lookup"><span data-stu-id="dc707-107">*srvproc*</span></span>  
 <span data-ttu-id="dc707-108">Es un puntero a la estructura SRV_PROC que es el identificador de una conexión cliente determinada.</span><span class="sxs-lookup"><span data-stu-id="dc707-108">Is a pointer to the SRV_PROC structure that is the handle for a particular client connection.</span></span> <span data-ttu-id="dc707-109">La estructura contiene información que la biblioteca de API de procedimiento almacenado extendido usa para administrar la comunicación y los datos entre la aplicación y el cliente.</span><span class="sxs-lookup"><span data-stu-id="dc707-109">The structure contains information the Extended Stored Procedure API library uses to manage communication and data between the application and the client.</span></span>  
  
 <span data-ttu-id="dc707-110">*terminado*</span><span class="sxs-lookup"><span data-stu-id="dc707-110">*len*</span></span>  
 <span data-ttu-id="dc707-111">Es un puntero a una variable `int` que recibe la longitud del nombre de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="dc707-111">Is a pointer to an `int` variable that receives the length of the database name.</span></span> <span data-ttu-id="dc707-112">Si *len* es NULL, no se devuelve la longitud del nombre de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="dc707-112">If *len* is NULL, the length of the database name is not returned.</span></span>  
  
## <a name="returns"></a><span data-ttu-id="dc707-113">Devoluciones</span><span class="sxs-lookup"><span data-stu-id="dc707-113">Returns</span></span>  
 <span data-ttu-id="dc707-114">Un puntero DBCHAR a la cadena terminada en NULL para la parte de nombre de base de datos del procedimiento almacenado remoto actual.</span><span class="sxs-lookup"><span data-stu-id="dc707-114">A DBCHAR pointer to the null-terminated string for the database name part of the current remote stored procedure.</span></span> <span data-ttu-id="dc707-115">Si no hay ningún procedimiento almacenado remoto actual, se devuelve NULL y el parámetro *len* se establece en -1.</span><span class="sxs-lookup"><span data-stu-id="dc707-115">If there is no current remote stored procedure, NULL is returned and the *len* parameter is set to - 1.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="dc707-116">Observaciones</span><span class="sxs-lookup"><span data-stu-id="dc707-116">Remarks</span></span>  
 <span data-ttu-id="dc707-117">Esta función devuelve solamente el componente de base de datos del nombre de objeto del procedimiento almacenado remoto.</span><span class="sxs-lookup"><span data-stu-id="dc707-117">This function returns only the database component of the remote stored procedure object name.</span></span> <span data-ttu-id="dc707-118">No incluye los especificadores opcionales para propietario, nombre de procedimiento almacenado remoto y número de procedimiento almacenado remoto.</span><span class="sxs-lookup"><span data-stu-id="dc707-118">It does not include the optional specifiers for owner, remote stored procedure name, and remote stored procedure number.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="dc707-119">Debe revisar minuciosamente el código fuente de los procedimientos almacenados extendidos y debe probar las DLL compiladas antes de instalarlas en el servidor de producción.</span><span class="sxs-lookup"><span data-stu-id="dc707-119">You should thoroughly review the source code of extended stored procedures, and you should test the compiled DLLs before you install them on a production server.</span></span> <span data-ttu-id="dc707-120">Para obtener información acerca de la revisión y pruebas de seguridad, vea este [sitio web de Microsoft](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span><span class="sxs-lookup"><span data-stu-id="dc707-120">For information about security review and testing, see this [Microsoft Web site](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span></span>  
  
  
