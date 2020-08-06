---
title: MSSQLSERVER_33081 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 33081 (Database Engine error)
ms.assetid: 839705e7-fa37-4c0d-9f3f-95a9eab98bcf
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 0752220cc20641d9b51a3a66fecc86f9efd63433
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87672054"
---
# <a name="mssqlserver_33081"></a><span data-ttu-id="5d934-102">MSSQLSERVER_33081</span><span class="sxs-lookup"><span data-stu-id="5d934-102">MSSQLSERVER_33081</span></span>
    
## <a name="details"></a><span data-ttu-id="5d934-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="5d934-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="5d934-104">Nombre de producto</span><span class="sxs-lookup"><span data-stu-id="5d934-104">Product Name</span></span>|<span data-ttu-id="5d934-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="5d934-105">SQL Server</span></span>|  
|<span data-ttu-id="5d934-106">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="5d934-106">Event ID</span></span>|<span data-ttu-id="5d934-107">33081</span><span class="sxs-lookup"><span data-stu-id="5d934-107">33081</span></span>|  
|<span data-ttu-id="5d934-108">Origen de eventos</span><span class="sxs-lookup"><span data-stu-id="5d934-108">Event Source</span></span>|<span data-ttu-id="5d934-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="5d934-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="5d934-110">Componente</span><span class="sxs-lookup"><span data-stu-id="5d934-110">Component</span></span>|<span data-ttu-id="5d934-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="5d934-111">SQLEngine</span></span>|  
|<span data-ttu-id="5d934-112">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="5d934-112">Symbolic Name</span></span>|<span data-ttu-id="5d934-113">SEC_DLL_TRUST_VERIFICATION_FAILED</span><span class="sxs-lookup"><span data-stu-id="5d934-113">SEC_DLL_TRUST_VERIFICATION_FAILED</span></span>|  
|<span data-ttu-id="5d934-114">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="5d934-114">Message Text</span></span>|<span data-ttu-id="5d934-115">No se pudo cargar el proveedor de servicios criptográficos '%.\*ls' debido a una firma Authenticode o una ruta de archivo no válida.</span><span class="sxs-lookup"><span data-stu-id="5d934-115">Failed to load cryptographic provider '%.\*ls' due to an invalid Authenticode signature or invalid file path.</span></span>  <span data-ttu-id="5d934-116">Revise los mensajes de otros errores anteriores.</span><span class="sxs-lookup"><span data-stu-id="5d934-116">Check previous messages for other failures.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="5d934-117">Explicación</span><span class="sxs-lookup"><span data-stu-id="5d934-117">Explanation</span></span>  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="5d934-118">no pudo cargar el proveedor de servicios criptográficos enumerado en el mensaje de error.</span><span class="sxs-lookup"><span data-stu-id="5d934-118">was unable to load the cryptographic provider listed in the error message.</span></span> <span data-ttu-id="5d934-119">Hay varios errores de la API de Windows que podrían producir este error.</span><span class="sxs-lookup"><span data-stu-id="5d934-119">There are several Win API failures which might cause this error.</span></span> <span data-ttu-id="5d934-120">El búfer en anillo contiene el nombre de la API con errores y el código de error de Windows devueltos por la API.</span><span class="sxs-lookup"><span data-stu-id="5d934-120">The ring buffer contains the name of the failed API and the Windows error code returned by the API.</span></span> <span data-ttu-id="5d934-121">Para obtener más información, consulte la vista de sys.dm_os_ring_buffers mediante lo siguiente.</span><span class="sxs-lookup"><span data-stu-id="5d934-121">To get more information, query the sys.dm_os_ring_buffers view using the following query.</span></span>  
  
```  
SELECT * FROM sys.dm_os_ring_buffers   
WHERE ring_buffer_type = 'RING_BUFFER_SECURITY_ERROR';  
```  
  
## <a name="user-action"></a><span data-ttu-id="5d934-122">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="5d934-122">User Action</span></span>  
 <span data-ttu-id="5d934-123">Para estudiar el problema, busque el código de error de Windows en MSDN (https://msdn.microsoft.com/).</span><span class="sxs-lookup"><span data-stu-id="5d934-123">To investigate the problem, search for the Windows error code in MSDN (https://msdn.microsoft.com/).</span></span> <span data-ttu-id="5d934-124">Resuelva el error o póngase en contacto con [!INCLUDE[msCoName](../../includes/msconame-md.md)] CSS para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="5d934-124">Resolve the error, or contact [!INCLUDE[msCoName](../../includes/msconame-md.md)] CSS for more information.</span></span> <span data-ttu-id="5d934-125">Si necesita ponerse en contacto con CSS, recopile la información siguiente para nuestro personal de soporte técnico.</span><span class="sxs-lookup"><span data-stu-id="5d934-125">If you need to contact CSS, collect the following information for our support staff.</span></span>  
  
-   <span data-ttu-id="5d934-126">El registro de errores que muestra el error de carga del proveedor de servicios criptográficos.</span><span class="sxs-lookup"><span data-stu-id="5d934-126">The error log showing the failed to load cryptographic provider error.</span></span>  
  
-   <span data-ttu-id="5d934-127">La salida de la instrucción siguiente:</span><span class="sxs-lookup"><span data-stu-id="5d934-127">The output from the following statement:</span></span>  
  
    ```  
    SELECT * FROM sys.dm_os_ring_buffers   
    WHERE ring_buffer_type = 'RING_BUFFER_SECURITY_ERROR';  
    ```  
  
> [!NOTE]  
>  <span data-ttu-id="5d934-128">Intente recopilar la información de búfer en anillo enseguida, ya que se puede perder durante un reinicio.</span><span class="sxs-lookup"><span data-stu-id="5d934-128">Try to collect the ring buffer information promptly as ring buffer information can be lost during a restart.</span></span>  
  
  
