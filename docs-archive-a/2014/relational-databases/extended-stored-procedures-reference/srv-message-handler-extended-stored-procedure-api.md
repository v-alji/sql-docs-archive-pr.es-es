---
title: srv_message_handler (API de procedimiento almacenado extendido) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: stored-procedures
ms.topic: reference
api_name:
- srv_message_handler
api_location:
- opends60.dll
topic_type:
- apiref
dev_langs:
- C++
helpviewer_keywords:
- srv_message_handler
ms.assetid: 41bcd057-436f-4fa8-8293-fc8057a30877
author: rothja
ms.author: jroth
ms.openlocfilehash: 7e7b6472ed4fabb6dc2d545eb51a1e026635ce19
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87670390"
---
# <a name="srv_message_handler-extended-stored-procedure-api"></a><span data-ttu-id="1a5e1-102">srv_message_handler (API de procedimiento almacenado extendido)</span><span class="sxs-lookup"><span data-stu-id="1a5e1-102">srv_message_handler (Extended Stored Procedure API)</span></span>
    
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureDontUse](../../includes/ssnotedepfuturedontuse-md.md)] <span data-ttu-id="1a5e1-103">Use la integración con CLR en su lugar.</span><span class="sxs-lookup"><span data-stu-id="1a5e1-103">Use CLR integration instead.</span></span>  
  
 <span data-ttu-id="1a5e1-104">Llama al controlador de mensajes de la API Procedimiento almacenado extendido instalado.</span><span class="sxs-lookup"><span data-stu-id="1a5e1-104">Calls the installed Extended Stored Procedure API message handler.</span></span> <span data-ttu-id="1a5e1-105">Esta función se utiliza normalmente para llamar a [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] desde un procedimiento almacenado extendido para registrar un error (definido por el procedimiento almacenado extendido) en el [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] archivo de registro de errores o en el [!INCLUDE[msCoName](../../includes/msconame-md.md)] registro de aplicación de Windows.</span><span class="sxs-lookup"><span data-stu-id="1a5e1-105">This function is usually used to call [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] from an extended stored procedure to log an error (defined by the extended stored procedure) in the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log file or the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows application log.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1a5e1-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="1a5e1-106">Syntax</span></span>  
  
```  
  
int srv_message_handler (  
SRV_PROC *  
srvproc  
,  
int  
errornum  
,  
BYTE   
severity  
,  
BYTE  
state  
,  
int  
oserrnum  
,  
char *  
errtext  
,  
int  
errtextlen  
,  
char *  
oserrtext  
,  
int  
oserrtextlen  
);  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="1a5e1-107">Argumentos</span><span class="sxs-lookup"><span data-stu-id="1a5e1-107">Arguments</span></span>  
 <span data-ttu-id="1a5e1-108">*srvproc*</span><span class="sxs-lookup"><span data-stu-id="1a5e1-108">*srvproc*</span></span>  
 <span data-ttu-id="1a5e1-109">Es un puntero a la estructura SRV_PROC que es el identificador de una conexión cliente determinada.</span><span class="sxs-lookup"><span data-stu-id="1a5e1-109">Is a pointer to the SRV_PROC structure that is the handle for a particular client connection.</span></span> <span data-ttu-id="1a5e1-110">El parámetro *srvproc* contiene información que se usa para administrar la comunicación y los datos entre la aplicación y el cliente.</span><span class="sxs-lookup"><span data-stu-id="1a5e1-110">The *srvproc* parameter contains information that is used to manage communication and data between the application and the client.</span></span>  
  
 <span data-ttu-id="1a5e1-111">*errornum*</span><span class="sxs-lookup"><span data-stu-id="1a5e1-111">*errornum*</span></span>  
 <span data-ttu-id="1a5e1-112">Es un número de error definido por el procedimiento almacenado extendido.</span><span class="sxs-lookup"><span data-stu-id="1a5e1-112">Is an error number defined by the extended stored procedure.</span></span> <span data-ttu-id="1a5e1-113">Este número debe estar comprendido entre 50.001 y 2.147.483.647.</span><span class="sxs-lookup"><span data-stu-id="1a5e1-113">This number must be from 50,001 through 2,147,483,647.</span></span>  
  
 <span data-ttu-id="1a5e1-114">*severity*</span><span class="sxs-lookup"><span data-stu-id="1a5e1-114">*severity*</span></span>  
 <span data-ttu-id="1a5e1-115">Es un valor de gravedad de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] estándar para el error.</span><span class="sxs-lookup"><span data-stu-id="1a5e1-115">Is a standard [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] severity value for the error.</span></span> <span data-ttu-id="1a5e1-116">Este número debe estar comprendido entre 0 y 24.</span><span class="sxs-lookup"><span data-stu-id="1a5e1-116">This number must be from 0 through 24.</span></span>  
  
 <span data-ttu-id="1a5e1-117">*state*</span><span class="sxs-lookup"><span data-stu-id="1a5e1-117">*state*</span></span>  
 <span data-ttu-id="1a5e1-118">Es un valor de estado de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para el error.</span><span class="sxs-lookup"><span data-stu-id="1a5e1-118">Is a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] state value for the error.</span></span>  
  
 <span data-ttu-id="1a5e1-119">*oserrnum*</span><span class="sxs-lookup"><span data-stu-id="1a5e1-119">*oserrnum*</span></span>  
 <span data-ttu-id="1a5e1-120">Es el número de error del sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="1a5e1-120">Is the operating-system error number.</span></span> <span data-ttu-id="1a5e1-121">Este argumento se pasa por alto.</span><span class="sxs-lookup"><span data-stu-id="1a5e1-121">This argument is ignored.</span></span>  
  
 <span data-ttu-id="1a5e1-122">*errtext*</span><span class="sxs-lookup"><span data-stu-id="1a5e1-122">*errtext*</span></span>  
 <span data-ttu-id="1a5e1-123">Es la descripción del error del procedimiento almacenado extendido *errornum*.</span><span class="sxs-lookup"><span data-stu-id="1a5e1-123">Is the description of the extended stored procedure error *errornum*.</span></span>  
  
 <span data-ttu-id="1a5e1-124">*errtextlen*</span><span class="sxs-lookup"><span data-stu-id="1a5e1-124">*errtextlen*</span></span>  
 <span data-ttu-id="1a5e1-125">Es la longitud de la cadena del error del procedimiento almacenado extendido *errtext*.</span><span class="sxs-lookup"><span data-stu-id="1a5e1-125">Is the length of the extended stored procedure error string *errtext*.</span></span>  
  
 <span data-ttu-id="1a5e1-126">*oserrtext*</span><span class="sxs-lookup"><span data-stu-id="1a5e1-126">*oserrtext*</span></span>  
 <span data-ttu-id="1a5e1-127">Es la descripción del error del sistema operativo *oserrnum*.</span><span class="sxs-lookup"><span data-stu-id="1a5e1-127">Is the description of the operating-system error *oserrnum*.</span></span> <span data-ttu-id="1a5e1-128">Este argumento se pasa por alto.</span><span class="sxs-lookup"><span data-stu-id="1a5e1-128">This argument is ignored.</span></span>  
  
 <span data-ttu-id="1a5e1-129">*oserrtextlen*</span><span class="sxs-lookup"><span data-stu-id="1a5e1-129">*oserrtextlen*</span></span>  
 <span data-ttu-id="1a5e1-130">Es la longitud de la cadena de error del sistema operativo *oserrtext*.</span><span class="sxs-lookup"><span data-stu-id="1a5e1-130">Is the length of the operating-system error string *oserrtext*.</span></span>  
  
## <a name="returns"></a><span data-ttu-id="1a5e1-131">Devoluciones</span><span class="sxs-lookup"><span data-stu-id="1a5e1-131">Returns</span></span>  
 <span data-ttu-id="1a5e1-132">SUCCEED o FAIL.</span><span class="sxs-lookup"><span data-stu-id="1a5e1-132">SUCCEED or FAIL.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1a5e1-133">Observaciones</span><span class="sxs-lookup"><span data-stu-id="1a5e1-133">Remarks</span></span>  
 <span data-ttu-id="1a5e1-134">La función **srv_message_handler** permite que un procedimiento almacenado extendido se integre con las características centralizadas de registro e informe de errores de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1a5e1-134">The **srv_message_handler** function enables an extended stored procedure to integrate with the centralized error logging and reporting features of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="1a5e1-135">Se pueden establecer alertas de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para eventos a partir de los procedimientos almacenados extendidos; el Agente SQL Server supervisa estas condiciones de alerta.</span><span class="sxs-lookup"><span data-stu-id="1a5e1-135">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] alerts can be established for events from extended stored procedures, and SQL Server Agent will monitor for these alert conditions.</span></span>  
  
 <span data-ttu-id="1a5e1-136">Si el mensaje de error es más largo, se trunca a 412 bytes.</span><span class="sxs-lookup"><span data-stu-id="1a5e1-136">If the error message is longer, it is truncated to 412 bytes.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="1a5e1-137">Debe revisar minuciosamente el código fuente de los procedimientos almacenados extendidos y debe probar las DLL compiladas antes de instalarlas en el servidor de producción.</span><span class="sxs-lookup"><span data-stu-id="1a5e1-137">You should thoroughly review the source code of extended stored procedures, and you should test the compiled DLLs before you install them on a production server.</span></span> <span data-ttu-id="1a5e1-138">Para obtener información acerca de la revisión y pruebas de seguridad, vea este [sitio web de Microsoft](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span><span class="sxs-lookup"><span data-stu-id="1a5e1-138">For information about security review and testing, see this [Microsoft Web site](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span></span>  
  
  
