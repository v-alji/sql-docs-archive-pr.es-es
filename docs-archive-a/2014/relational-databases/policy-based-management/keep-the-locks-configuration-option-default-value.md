---
title: Mantenimiento del valor predeterminado de la opción de configuración Bloqueos | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- Best Practices [Database Engine]
ms.assetid: f214f05b-5f0b-4786-b2ad-b8b4b6e58d72
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: a1d1dcf82d9cd0ef8ef2c15cb68ef78b53a8a54a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87663435"
---
# <a name="keep-the-locks-configuration-option-default-value"></a><span data-ttu-id="53076-102">Mantener el valor predeterminado de la opción de configuración Bloqueos</span><span class="sxs-lookup"><span data-stu-id="53076-102">Keep the Locks Configuration Option Default Value</span></span>
  <span data-ttu-id="53076-103">Esta regla comprueba el valor de la opción de configuración locks.</span><span class="sxs-lookup"><span data-stu-id="53076-103">This rule checks the value of the locks configuration option.</span></span> <span data-ttu-id="53076-104">Esta opción determina el número máximo de bloqueos disponibles.</span><span class="sxs-lookup"><span data-stu-id="53076-104">This option determines the maximum number of available locks.</span></span> <span data-ttu-id="53076-105">Limita cuánta memoria usa [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] para los bloqueos.</span><span class="sxs-lookup"><span data-stu-id="53076-105">This limits how much memory the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] uses for locks.</span></span> <span data-ttu-id="53076-106">El valor predeterminado es 0, lo que habilita al [!INCLUDE[ssDE](../../includes/ssde-md.md)] para asignar y cancelar la asignación de estructuras de bloqueos de manera dinámica a partir de requisitos variables del sistema.</span><span class="sxs-lookup"><span data-stu-id="53076-106">The default setting of 0 enables the [!INCLUDE[ssDE](../../includes/ssde-md.md)] to allocate and deallocate lock structures dynamically based on changing system requirements.</span></span>  
  
 <span data-ttu-id="53076-107">Si locks es distinto de cero, los trabajos por lotes se detendrán y se generará un mensaje de error "sin bloqueos", si se supera el valor especificado.</span><span class="sxs-lookup"><span data-stu-id="53076-107">If locks is nonzero, batch jobs will stop, and an "out of locks" error message will be generated, if the value specified is exceeded.</span></span>  
  
## <a name="best-practices-recommendations"></a><span data-ttu-id="53076-108">Prácticas recomendadas</span><span class="sxs-lookup"><span data-stu-id="53076-108">Best Practices Recommendations</span></span>  
 <span data-ttu-id="53076-109">Utilice el procedimiento almacenado de sistema sp_configure para cambiar el valor de locks a su configuración predeterminada utilizando la instrucción siguiente:</span><span class="sxs-lookup"><span data-stu-id="53076-109">Use the sp_configure system stored procedure to change the value of locks to its default setting by using the following statement:</span></span>  
  
```  
EXEC sp_configure 'locks', 0;  
```  
  
## <a name="for-more-information"></a><span data-ttu-id="53076-110">Para obtener más información</span><span class="sxs-lookup"><span data-stu-id="53076-110">For More Information</span></span>  
 [<span data-ttu-id="53076-111">Establecer la opción de configuración del servidor Bloqueos</span><span class="sxs-lookup"><span data-stu-id="53076-111">Configure the locks Server Configuration Option</span></span>](../../database-engine/configure-windows/configure-the-locks-server-configuration-option.md)  
  
 [<span data-ttu-id="53076-112">sys.dm_tran_locks &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="53076-112">sys.dm_tran_locks &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-dynamic-management-views/sys-dm-tran-locks-transact-sql)  
  
 [<span data-ttu-id="53076-113">sys.dm_os_wait_stats &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="53076-113">sys.dm_os_wait_stats &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-dynamic-management-views/sys-dm-os-wait-stats-transact-sql)  
  
 [<span data-ttu-id="53076-114">Artículo 271509 de Microsoft Knowledge Base</span><span class="sxs-lookup"><span data-stu-id="53076-114">Microsoft Knowledge Base article 271509</span></span>](https://go.microsoft.com/fwlink/?linkid=117788)  
  
## <a name="see-also"></a><span data-ttu-id="53076-115">Consulte también</span><span class="sxs-lookup"><span data-stu-id="53076-115">See Also</span></span>  
 [<span data-ttu-id="53076-116">Supervisar y aplicar las prácticas recomendadas usando la administración basada en directivas</span><span class="sxs-lookup"><span data-stu-id="53076-116">Monitor and Enforce Best Practices by Using Policy-Based Management</span></span>](monitor-and-enforce-best-practices-by-using-policy-based-management.md)  
  
  
